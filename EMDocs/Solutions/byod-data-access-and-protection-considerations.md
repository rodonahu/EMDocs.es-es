---
title: "Consideraciones sobre la protección de datos y el acceso a estos"
description: "En este artículo se proporciona un conjunto de consideraciones de diseño para el acceso a datos y la protección de estos en un escenario de Bring Your Own Device."
keywords: 
author: YuriDio
ms.author: yurid
manager: mbaldwin
ms.date: 05/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 181eb917-119d-4e56-8ead-1182b1dc5cab
ms.reviewer: 
ms.suite: ems
ms.translationtype: Human Translation
ms.sourcegitcommit: 5adb7f68efacdfa20d78c3cf5853fa374793140a
ms.openlocfilehash: cbf0f54d2d288baf66f914ef8366a70448218607
ms.contentlocale: es-es
ms.lasthandoff: 11/28/2016


---

# <a name="data-access-and-protection-considerations"></a>Consideraciones sobre la protección de datos y el acceso a estos

La pérdida de datos confidenciales es un riesgo operativo para cualquier empresa, y con la llegada de BYOD, la información se almacena en más lugares que nunca. Esto se traduce en un panorama más amplio de amenazas y riesgos mayores que se deben mitigar correctamente. Dada la variedad de regulaciones legislativas, corporativas y sectoriales que rigen la protección de datos confidenciales, este proceso puede resultar complejo. Es importante tener en cuenta estos requisitos legales, las directivas corporativas internas y la normativa del sector.
Como parte de la estrategia de la infraestructura de BYOD es fundamental que una vez que se hayan definido las directivas y las clasificaciones de datos, los datos se ubiquen físicamente, se archiven en los niveles adecuados de clasificación y se les aplique la configuración de seguridad apropiada. Los departamentos de TI necesitan una forma de validar las identidades de los usuarios y puede que quieran aplicar otras condiciones a los tipos de dispositivos que pueden tener acceso a la información y las aplicaciones de la empresa.

## <a name="storage"></a>Almacenamiento

La forma en que se almacenarán los datos en los dispositivos de los usuarios puede repercutir directamente en el método de gestión que haya elegido para el acceso y la protección de los datos para BYOD. Se debe tener en cuenta el cifrado de datos y es preciso que los dispositivos permitan a los departamentos de TI controlar cuándo se habilita el cifrado de datos y para qué tipos de datos. Las empresas deben revisar sus directivas y reglamentos para entender qué tipos de datos pueden abandonar el centro de datos y guardarse en el almacenamiento de los dispositivos remotos. Es crucial el cifrado de datos almacenados en el centro de datos. Si su empresa no lo hace aún, debe considerarse una parte integrante de la estrategia para una infraestructura de BYOD. Lo idóneo es que se cifren los datos en todo el proceso.

Con Windows Server 2012 R2, puede cifrar los datos en reposo en los dispositivos de los usuarios mediante Carpetas de trabajo. Los administradores de TI pueden usar las carpetas de trabajo para tener un mayor control sobre los datos corporativos y los dispositivos de los usuarios, además de poder centralizar los datos de trabajo para que puedan aplicar los procesos y las herramientas apropiados con el fin de que la empresa cumpla la normativa en todo momento. Esto puede variar desde simplemente tener una copia de los datos si el usuario deja la empresa, hasta una amplia gama de posibilidades, como copias de seguridad, retención, clasificación y cifrado automatizado. Si decide usar [Carpetas de trabajo](https://technet.microsoft.com/library/dn265974.aspx), asegúrese de que los servidores que hospedarán los recursos compartidos de sincronización también se organicen desde la perspectiva del rendimiento. Para obtener más información, lea [Performance Considerations for Work Folders Deployments](http://blogs.technet.com/b/filecab/archive/2013/11/01/performance-considerations-for-large-scale-work-folders-deployments.aspx) (Consideraciones de rendimiento relativas a implementaciones de Carpetas de trabajo).

Si su concepto de almacenamiento es un contenedor de contenidos, la protección del consumo de ese contenido aportará gran valor. Se puede evitar la fuga de datos si se aplican directivas para regular la forma en que el usuario final va a usar el contenido almacenado. Se puede usar [Active Directory Rights Management Services (AD RMS)](https://technet.microsoft.com/library/hh831554.aspx) para intensificar la estrategia de seguridad de la empresa mediante la protección de los documentos que utilicen Information Rights Management (IRM). AD RMS permite a usuarios y administradores establecer permisos de acceso a documentos, libros y presentaciones a través de las directivas de IRM. Esto ayuda a impedir que personas no autorizadas impriman, reenvíen o copien la información confidencial. Una vez que se haya restringido el permiso para un archivo mediante IRM, se aplican las restricciones de acceso y uso independientemente de dónde se encuentre la información, ya que el permiso para un archivo se almacena en el propio archivo.

Si quiere usar una solución basada en la nube en su empresa para proteger los archivos, también puede recurrir a [Azure Information Protection](/information-protection/understand-explore/what-is-information-protection). Azure Information Protection puede proteger la información confidencial de la empresa mediante directivas de cifrado, identidad y autorización para ayudar a garantizar la seguridad de los archivos y el correo electrónico. Además, funciona en varios dispositivos: teléfonos, tabletas y equipos PC. La información se mantendrá segura tanto dentro como fuera de la organización, ya que se conserva la protección de los datos, incluso cuando el usuario se sale de los límites de la empresa.

También se pueden usar otras tecnologías de almacenamiento que se incluyen en el sistema operativo Windows para mejorar la protección general de los datos, como BitLocker para el cifrado de unidades y el [Sistema de cifrado de archivos (EFS)](https://technet.microsoft.com/library/cc700811.aspx) para el cifrado de estos. Use la siguiente tabla para ver las ventajas y los inconvenientes de la protección del almacenamiento. Tenga en cuenta que estas opciones no son mutuamente excluyentes. En otras palabras, la decisión que tome sobre el diseño podría conllevar la necesidad de usar todas estas opciones en la solución de infraestructura BYOD para la protección del almacenamiento.

### <a name="storage-protection-options--advantages-and-disadvantages"></a>Opciones de protección del almacenamiento: ventajas y desventajas

Mediante la siguiente lista, podrá conocer las ventajas y desventajas de las opciones de protección del almacenamiento:

- Sistema de archivos cifrados (EFS)
    - Ventajas
        - Proporciona cifrado de archivos.
        - El proceso de cifrado es invisible para los usuarios, puesto que no se realiza en el nivel de las aplicaciones, sino en el sistema de archivos.
        - Brinda la posibilidad de realizar copias de seguridad con un Key Recovery Agent.
        - Se encuentra disponible en todas las versiones compatibles del sistema operativo Windows.
        - Se puede habilitar mediante directivas de grupo.
        - Cumple los requisitos de criptografía de Suite B establecidos por la Agencia nacional de protección (National Security Agency) para satisfacer las necesidades de protección de la información confidencial de los organismos gubernamentales de Estados Unidos.
    - Desventajas
        - Si el propietario de los datos no se encuentra disponible y no dispone del Key Recovery Agent, no podrá descifrar un archivo EFS.
        - Se debe haber implantado la administración de certificados para gestionar las claves privadas asociadas a los certificados de recuperación.
        - No está disponible en otras plataformas que no sean Windows.
- BitLocker
    - Ventajas
        - Brinda la posibilidad de cifrar unidades.
        - Favorece la integridad y comprobación del sistema; para ello, se sirve del Módulo de plataforma segura (TPM).
        - Mejora la protección para mitigar los ataques sin conexión basados en software.
        - Ofrece un método para comprobar que la integridad del archivo de arranque inicial no se haya visto afectada.
    - Desventajas
        - No se encuentra disponible en todas las versiones de Windows.
        - Requiere la versión 1.2 de TPM.
        - Requiere que el BIOS del sistema (para equipos con TPM y sin él) sea compatible con la clase de dispositivos de almacenamiento masivo USB.
        - No está disponible para clústeres anteriores a Windows Server 2012.
- Carpetas de trabajo
    - Ventajas
        - Usa EFS para cifrar archivos.
        - Permite que el departamento de TI cifre los datos en reposo en los dispositivos de los usuarios.
        - Se puede habilitar mediante directivas de grupo por usuario o por dispositivo.
        - Se integra con Microsoft Intune, que permite borrar de forma selectiva los datos ubicados en Carpetas de trabajo de los dispositivos de los usuarios.
        - Puede forzar a los usuarios a volver a realizar el proceso de autenticación para acceder a datos ubicados en Carpetas de trabajo.
        - Permite la integración con los servicios de Microsoft Information Protection para la clasificación de datos.
    - Desventajas
        - Solo se encuentra disponible para Windows 8.1, Windows RT 8.1 y Windows 10.
        - Requiere Windows Server 2012 R2 para hospedar los recursos compartidos de sincronización.
- Active Directory Rights Management Services (AD RMS)
    - Ventajas
        - Impedir que un destinatario no autorizado de contenido restringido reenvíe, copie, modifique, imprima, envíe por fax o pegue contenido de uso no autorizado.
        - Admitir la expiración de archivos para que los documentos ya no se puedan ver tras un período de tiempo especificado.
        - Impedir que se copie contenido restringido mediante el uso de la función Imprimir pantalla en Microsoft Windows.
    - Desventaja
        - Requiere la implementación de un nuevo rol de servidor (AD RMS).
        - No restringe la copia de contenido mediante programas de captura de pantalla de terceros.
        - No impide la pérdida o daño de contenido a causa de virus informáticos.

## <a name="network"></a>Red

Es esencial tener en cuenta los factores implicados en la habilitación de usuarios para utilizar sus dispositivos y para que los datos estén protegidos en la totalidad de la ruta de acceso entre centros de datos (local) o la nube y los dispositivos de los usuarios. Estos factores se ponen de relieve en la ilustración siguiente:

![Diagrama de red](./media/BYOD_Figure6.png)

Este diagrama resalta las áreas cruciales donde la protección de datos debe tenerse en cuenta para las infraestructuras de BYOD. Estas áreas se describen de forma más detallada en la sección siguiente.

### <a name="data-protection--locations-and-considerations"></a>Protección de datos: ubicaciones y consideraciones

Mediante la siguiente lista, podrá conocer las consideraciones relacionadas con la protección de datos según la ubicación de estos. Los números de la lista se corresponden con el diagrama anterior:

- (1) Datos en reposo en el centro de datos
    - Cifrado de almacenamiento: plantéese usar una solución de almacenamiento que admita el cifrado.
    - Administración de claves: se debe realizar una copia de seguridad de la clave que se usa para cifrar el almacenamiento y debe disponer de un Key Recovery Agent, en caso de que se necesite.
- (2) Datos en tránsito desde el centro de datos hasta el perímetro de la red corporativa
    - Cifrado de red: plantéese usar un protocolo web estándar de cifrado, como SSL.
    - Infraestructura de clave pública (PKI): si su empresa tiene una PKI, la puede usar para cifrar este canal de comunicación.
- (3) Datos en tránsito desde el perímetro de la red corporativa hasta los dispositivos de los usuarios
    - Cifrado de red: plantéese usar un protocolo web estándar de cifrado, como SSL.
    - PKI: dado que los usuarios tendrán acceso a este canal a través de sus dispositivos personales, considere la opción de usar un certificado público en el que probablemente ya confíen los dispositivos de los usuarios.
- (3.1) Datos en tránsito desde el perímetro de la red corporativa hasta el proveedor de servicios en la nube (opcional: solo se aplica si su empresa usa servicios en la nube para BYOD)
    - Cifrado de red: plantéese usar un protocolo web estándar de cifrado, como SSL.
    - PKI: dado que los usuarios tendrán acceso a este canal a través de sus dispositivos personales, considere la opción de usar un certificado público en el que probablemente ya confíen los dispositivos de los usuarios.
    - VPN de sitio a sitio: si tiene una [infraestructura de nube híbrida](http://blogs.technet.com/b/cloudsolutions/archive/2013/08/22/hybrid-it-infrastructure-solution-for-enterprise-it-overview.aspx) que esté conectada a Servicios en la nube, plantéese usar una VPN de sitio a sitio para que las aplicaciones de los dispositivos de los usuarios puedan mantener la disponibilidad del canal seguro.
- (3.2) Datos en reposo en el centro de datos del proveedor de servicios en la nube (opcional: solo se aplica si su empresa usa servicios en la nube para BYOD)
    - Proveedor de servicios en la nube: tenga en cuenta las opciones que puede ofrecer el proveedor de servicios en la nube para cifrar los datos en reposo.
    - Administración de claves: compruebe con el proveedor de servicios de nube cómo se realiza la administración de claves y el proceso de copia de seguridad. Tenga en cuenta también la integración entre los servicios en la nube y un sistema de administración de claves local (4) Datos inactivos en los dispositivos de los usuarios.
    - Cifrado de almacenamiento: plantéese usar una solución de almacenamiento que admita el cifrado.
    - Administración de claves: se debe realizar una copia de seguridad de la clave que se usa para cifrar el almacenamiento y debe disponer de un Key Recovery Agent, en caso de que se necesite.
    - Borrado remoto: se pueden eliminar de forma remota los datos ubicados en los dispositivos de los usuarios, en caso de que sea necesario.

Windows Server 2012 R2 permite el uso de [HTTPS](https://msdn.microsoft.com/library/aa767735.aspx) para publicar recursos con el [Proxy de aplicación web](https://technet.microsoft.com/library/dn280944.aspx) para proteger los datos mientras se transmiten por la red. También se puede cifrar la comunicación entre los servidores back-end con [IPsec](https://technet.microsoft.com/library/cc757613.aspx) o el [cifrado SMB](http://support.microsoft.com/kb/2709568) si el tráfico de red se basa exclusivamente en el [protocolo SMB](https://technet.microsoft.com/library/hh831795.aspx). Use la siguiente tabla para evaluar qué opción de protección de red se adapta mejor a los requisitos de diseño para la comunicación del servidor back-end.

Recurra a la siguiente sección para valorar qué opción de protección de red se adapta mejor a los requisitos de diseño relativos a la comunicación del servidor back-end.

### <a name="network-protection-options--advantages-and-disadvantages"></a>Opciones de protección de red: ventajas y desventajas

Mediante la siguiente lista, podrá conocer las ventajas y desventajas de las opciones de protección de red:

- SSL
    - Ventaja
        - Ofrece una amplia compatibilidad con numerosos dispositivos.
        - Autenticación sólida, privacidad de mensajes e integridad.
        - Interoperabilidad
    - Desventaja
        - Requiere una infraestructura de certificados, salvo que use certificados SSL públicos.
- IPSec
    - Ventajas
        - Ofrece el cifrado del datagrama de IP completo.
        - Permite la autenticación en equipos.
        - Ofrece una amplia compatibilidad con numerosas plataformas y se encuentra disponible en todas las versiones que admite Windows.
        - Incluye autenticación de Intercambio de claves por red (IKE) para limitar el acceso por red a los equipos de confianza.
    - Desventajas
        - Requiere una infraestructura de certificados, salvo que utilice una clave compartida previamente.
        - IPsec trabaja en el host, por lo que no se puede controlar en la aplicación.
        - Resulta difícil solucionar problemas.
- Cifrado SMB
    - Ventajas
        - Cifra los datos en tránsito mediante el protocolo SMB.
        - Resulta sencillo de implementar en la interfaz de usuario y a través de Windows PowerShell.
        - Es flexible, puesto que se puede implementar por servidor o por recurso compartido.
    - Desventaja
        - Solo funciona con Windows 8 y versiones posteriores de equipos cliente, así como con Windows Server 2012 y versiones posteriores de equipos de servidor.

## <a name="directory"></a>Directorio

Los atributos de usuario se deben almacenar en el directorio, de forma que el departamento de TI podrá consultar fácilmente información de usuario como los roles y los grupos. También debe tener en cuenta cómo llevará el seguimiento de la relación entre usuarios y dispositivos. Todos los dispositivos desconocidos que lleguen al conocimiento del departamento de TI o que este administre también deben tener un registro en la base de datos de administración o en el directorio que permita a TI auditar el dispositivo.

En entornos híbridos donde vaya a haber repositorios de autenticación diferentes, las empresas deben tener en cuenta cómo habilitar a los usuarios para que se autentiquen con las mismas credenciales independientemente de dónde se encuentren ellos y las aplicaciones. Plantéese usar los Servicios de federación de Active Directory (AD FS) si desea centralizar la autenticación en un entorno local en lugar de replicar el directorio con el proveedor de servicios en la nube. Recurra a la siguiente sección para evaluar las opciones de directorio para una infraestructura de BYOD.

### <a name="directory-options--advantages-and-disadvantages"></a>Opciones de directorio: ventajas y desventajas

Mediante la siguiente lista, podrá conocer las ventajas y desventajas de las opciones de protección de directorios:

- Centralizado en un entorno local
    - Ventaja
        - Todos los controles de seguridad se encuentran físicamente en el entorno local, de modo que el departamento de TI dispone de un control total.
        - El equipo de TI puede llevar a cabo la protección del servidor que contiene el rol de directorio.
        - Ofrece unas funciones más completas de auditoría y de registro.
    - Desventaja
        - El coste de mantenimiento es superior al de los servicios en la nube.
        - Carece de la integración con los servicios en la nube.
- Centralizado en la nube
    - Ventajas
        - El coste de mantenimiento es inferior al de una solución local.
        - Resulta más fácil de administrar en comparación con una solución local.
    - Desventajas
        - Carece de la opción de personalización.
        - Depende del proveedor de servicios en la nube para la obtención de datos de auditoría y registro.
- Sincronización de directorios entre el entorno local y la nube
    - Ventajas
        - Se integra en el entorno local y en el directorio en la nube.
        - Permite a los usuarios el inicio de sesión único.
        - El equipo de TI puede seguir protegiendo el servidor que contiene el rol de directorio en el entorno local.
        - Inicio de sesión sin problemas para los usuarios.
    - Desventajas
        - Requiere la sincronización de hash de contraseñas.
        - Requiere un servicio de firma.
- Federado entre el entorno local y la nube
    - Ventajas
        - Integrado en el entorno local y en el directorio de la nube.
        - Permite a los usuarios el inicio de sesión único.
        - El departamento de TI puede seguir protegiendo el servidor que contiene el rol de directorio en el entorno local.
        - Inicio de sesión sin problemas para usuarios.
        - Más sólido para las soluciones que requieren la integración con otros servicios de directorio.
        -Requiere sincronización, pero no sincroniza contraseñas.
    - Desventajas
        - Requiere un servicio de firma.
        - Requiere una infraestructura de servidor para federación.
        - Requiere certificados para proteger la comunicación entre el servidor de federación y el servicio de nube.

Los entornos híbridos en los que los usuarios necesiten disponer de conectividad con los servicios en la nube desde sus propios dispositivos pueden beneficiarse de la integración entre [Microsoft Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-whatis/) y los Servicios de dominio de Active Directory (AD DS). En un [escenario de identidad híbrida](https://technet.microsoft.com/library/dn550987.aspx), las empresas que quieran mantener una autenticación de usuario sin conflictos pueden elegir entre las siguientes opciones:

- Sincronización de directorios con sincronización de contraseñas: mediante DirSync con [sincronización de hash de contraseñas](https://technet.microsoft.com/library/dn246918.aspx) entre AD DS y Azure AD.
- Autenticación federada con inicio de sesión único: los atributos de usuario se sincronizan mediante DirSync. La autenticación se devuelve mediante federación (AD FS) y se completa según AD DS.

Cuando se usa el servicio de registro de dispositivos en Windows 8.1, se instala un certificado en el dispositivo del usuario y se crea un registro de este en AD DS con el número de huella digital del certificado. Este vínculo entre el dispositivo y el usuario permite al departamento de TI realizar un seguimiento de los dispositivos que registra cada usuario. Esta funcionalidad no requiere una PKI de empresa. El registro de dispositivos también está disponible en Azure AD para Windows 10. Lea [Introducción al Registro de dispositivos de Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-conditional-access-device-registration-overview/) para obtener más información sobre el registro de dispositivos con Azure AD y Windows 10.

## <a name="authentication-and-authorization"></a>Autenticación y autorización

La decisión de permitir a los usuarios tener acceso a aplicaciones y datos desde sus dispositivos debe garantizar que los usuarios se identifiquen mediante un proceso de autenticación de confianza y que los usuarios obtengan autorización para usar los recursos que se soliciten. Las empresas deben revisar las directivas vigentes de autenticación y autorización y tener en cuenta las siguientes preguntas:

- ¿Cuáles son los requisitos de autenticación para que los usuarios puedan tener acceso remoto a aplicaciones de la empresa desde sus dispositivos?
- ¿Es capaz la plataforma actual de exigir una autorización por usuario y por aplicación sin tener que volver a escribir las aplicaciones?
- ¿Es posible aplicar la autenticación multifactor según la ubicación de un usuario?

La autenticación y la autorización se controlan mediante AD FS en conexión con AD DS. Los datos en tránsito del centro de datos también usarán el protocolo HTTPS cuando se establezca la conexión con el rol de servidor de archivos y servicios de autenticación.

Para aplicar Multi-Factor Authentication, las empresas pueden usar las capacidades integradas en AD FS o usar [Azure Multi-Factor Authentication (MFA)](https://azure.microsoft.com/documentation/articles/multi-factor-authentication/). Si se usa esta capacidad en Azure, el departamento de TI podrá aplicar la autenticación multifactor a los usuarios que tengan acceso a recursos de la empresa desde Internet. Para obtener más información sobre la autenticación multifactor, consulte [Administración de riesgos con la autenticación multifactor adicional para aplicaciones confidenciales](https://technet.microsoft.com/library/dn280949.aspx).

Para aplicar la autorización por aplicación a los usuarios que tengan acceso a las aplicaciones desde una red interna o externa, el departamento de TI puede usar el Proxy de aplicación web. Con el Proxy de aplicación web, el departamento de TI puede crear reglas específicas para aplicar la autenticación y autorización junto con AD FS. La publicación del Proxy de aplicación web funciona en cualquier dispositivo de usuario; los usuarios pueden usar sus equipos portátiles, tabletas o smartphones personales. Además, no será necesario que los usuarios instalen ningún software adicional en sus dispositivos para tener acceso a las aplicaciones publicadas. El Proxy de aplicación web se usa como un proxy inverso para las aplicaciones publicadas a través de él y, como tal, la experiencia del usuario es la misma que si los dispositivos de los usuarios estuvieran directamente conectados a las aplicaciones. Para obtener más información sobre el Proxy de aplicación web, consulte la [Guía de tutorial de proxy de aplicación web](https://technet.microsoft.com/library/dn280944.aspx).

>[!NOTE]
> Si se encuentra en un escenario híbrido y necesita tener una experiencia perfecta de autenticación y autorización de usuarios, lea la guía [Consideraciones de diseño de identidad híbrida de Azure Active Directory](http://aka.ms/azhidcg).

## <a name="policy-and-compliance"></a>Directiva y cumplimiento

Las directivas y el cumplimiento de la normativa deberían ser una prioridad en cualquier estrategia donde se contemple BYOD. Es posible que algunas organizaciones tengan requisitos exigentes que no se pueden integrar en este modelo debido a la normativa empresarial. Las empresas que vayan a migrar a una estrategia centrada en las personas deben saber cómo son las directivas actuales y cómo se verán afectadas por la adopción de BYOD. Considere los requisitos relativos a la clasificación de datos y cómo el departamento de TI puede controlar esta clasificación de datos, incluso cuando estos se encuentren en el almacenamiento del dispositivo. En la clasificación de datos, es importante poder clasificar los datos mientras se están ejecutando ciertas operaciones (como la modificación de un archivo).

Las directivas se deben aplicar desde una ubicación centralizada para que el departamento de TI pueda dar una respuesta rápida en caso de cambios ad hoc que afecten a todos los usuarios. Tenga también en cuenta las eficaces capacidades de auditoría para dispositivos móviles. Si se produce un incumplimiento, es fundamental que el departamento de TI pueda identificar la directiva que se ha infringido, quién lo hizo y cuándo.

### <a name="policy-and-compliancecapabilities-and-considerations"></a>Directiva y cumplimiento: funciones y consideraciones

Mediante la siguiente lista, podrá conocer las consideraciones acerca de funciones relativas al cumplimiento y a la observación de directivas:

- Clasificación de datos
    - Aplique la clasificación de datos cuando se guarde contenido y cuando se produzcan cambios en él.
    - El departamento de TI debe poder clasificar los datos en reposo en el centro de datos y en los dispositivos de los usuarios.
- Administración centralizada
    - El departamento de TI debe tener la posibilidad de administrar la clasificación de datos desde una única ubicación, incluso si los datos se encuentran en varios dispositivos.
    - Los entornos de TI híbridos deben ser capaces de administrar recursos locales y que se ubiquen en la nube.
- Integración con servicios de directorio
    - El departamento de TI tiene que poder usar su servicio de directorio activo como el repositorio de identidades.
- Auditoría y registro
    - El departamento de TI tiene que poder auditar el acceso a los recursos y aumentar la capacidad de registro, cuando sea necesario.


La aplicación de la gobernanza de datos en todos los servidores de archivos para controlar quién puede tener acceso a la información y auditar quién lo ha hecho es un aspecto fundamental en BYOD. En Windows Server 2012 R2, esto se puede realizar mediante el [Control de acceso dinámico](https://technet.microsoft.com/library/dn408191.aspx), que se basa en inversiones en infraestructuras de las que pueden servirse las aplicaciones de líneas de negocios y partners. Las características de control de acceso dinámico pueden proporcionar un gran valor a las organizaciones que usan los servicios de dominio de Active Directory.

Con las capacidades del control de acceso dinámico, puede identificar datos mediante la clasificación automática y manual de los archivos de datos. Por ejemplo, puede etiquetar datos en servidores de archivos en toda la organización. También es posible controlar el acceso a archivos mediante la aplicación de directivas de red segura que usen directivas de acceso central. El control de acceso dinámico también usa la protección de Rights Management Services (RMS) mediante cifrado RMS automático para documentos confidenciales. Por ejemplo, puede configurar RMS para cifrar todos los documentos que contengan información sobre la Ley de transferencia y responsabilidad de seguros de salud (HIPAA). En lo relativo a la investigación forense y la auditoría, puede aprovechar las directivas de auditoría central para realizar informes sobre el cumplimiento de la normativa y para análisis forense. Puede identificar quién tuvo acceso a información muy confidencial.

El control de acceso dinámico, una función del rol de servidor de archivos, confiere al departamento de TI las funcionalidades que se describen en la tabla anterior. Para obtener más información acerca del Control de acceso dinámico, consulte [Control de acceso dinámico: Información general sobre el escenario](https://technet.microsoft.com/library/hh831717.aspx).

