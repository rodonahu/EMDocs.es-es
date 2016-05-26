---
# required metadata

title: Consideraciones sobre usuarios y dispositivos
description:
keywords:
author: YuriDio
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: d1653116-3922-40d3-bc4f-3d845b6aaecb

# optional metadataco

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: 
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Consideraciones sobre usuarios y dispositivos

El primer problema relacionado con usuarios y dispositivos al que se enfrentará es cómo afectarán las tecnologías implantadas a la experiencia del usuario cuando este acceda de forma segura a recursos de la compañía. Encargarse de la experiencia del usuario en diferentes dispositivos puede ser un reto, no solo desde el punto de vista de la seguridad, sino también desde la perspectiva del desarrollo de aplicaciones. Deberá tener en cuenta el canal de comunicación entre los recursos de la compañía y el dispositivo, para aplicar el nivel adecuado de seguridad de red necesario y evitar así la pérdida de datos mientras están en tránsito.

Las secciones siguientes se basan en los componentes del subdominio de usuarios y dispositivos que se muestran en la sección [Definición de los problemas de BYOD](byod-design-considerations-guide.md#problem-definition) de esta guía, que es el diagrama conceptual del dominio del problema de BYOD.

## Profiles

La comprensión de las necesidades y los requisitos de los usuarios para realizar sus tareas desde los dispositivos de su elección es fundamental para diseñar una solución de infraestructura BYOD. No todos los usuarios tendrán los mismos requisitos. Algunos usuarios siempre accederán a los datos desde la oficina, por lo que para ellos el cumplimiento de directivas puede ser diferente. Los trabajadores remotos accederán a datos de la compañía desde una variedad de ubicaciones y circunstancias. Debe tener en cuenta las opciones disponibles para satisfacer sus necesidades. Determine el perfil de cada usuario según sus necesidades:

- ¿Necesitan acceder solo a aplicaciones?
- ¿Necesitan acceder a carpetas ubicadas en un servidor de archivos?

Aunque en la siguiente tabla se sugiere un conjunto de requisitos para el perfil de cada usuario, puede personalizar esta tabla agregando o quitando requisitos en función de las necesidades de su compañía. La lógica de cada categoría de perfil en comparación con lo que debe contener se basa en los recursos que consume. Por ejemplo, un perfil ligero significa que se hace un uso escaso de los recursos del dispositivo y hay pocos requisitos de red. Asegúrese de que comprende el perfil de cada usuario. Esto le permitirá elegir las opciones más adecuadas en el resto del proceso de diseño.

Los perfiles de usuario propuestos en esta guía son:

- **Ligero**
    - Acceso a aplicaciones basadas en web local o en la nube
    - Acceso a aplicaciones móviles corporativas
- **Moderado**
    - Acceso a aplicaciones basadas en web local o en la nube
    - Acceso a aplicaciones móviles corporativas
    - Acceso a aplicaciones empresariales virtualizadas
    - Acceso a archivos ubicados en servidores de archivos locales
    - Acceso a archivos ubicados en la nube
- **Pesado**
    - Acceso a aplicaciones basadas en web local o en la nube
    - Acceso a aplicaciones móviles corporativas
    - Acceso a archivos ubicados en servidores de archivos locales
    - Acceso a archivos ubicados en la nube
    - Acceso a equipos con el Escritorio remoto
    - Acceso a otros equipos locales

Necesitará determinar qué perfil de usuario es más adecuado para su solución de infraestructura BYOD. Considere la posibilidad de establecer los perfiles de varios usuarios según sus requisitos de trabajo. Lo ideal es que la tecnología que se utiliza para implementar la solución de infraestructura BYOD deba poder dar cabida a todos los perfiles de usuario, ya que los requisitos pueden variar según cada usuario. 

## Dispositivos

El departamento de TI debe determinar si es necesario conocer los dispositivos. Por ejemplo, un escenario de BYOD es el de los empleados por horas que comprueban su ficha de horas o echan un vistazo a los avisos de la empresa o las redes sociales cuando están fuera de la oficina. En muchas organizaciones, estos requisitos eran tradicionalmente servicios solo de LAN, pero ahora puede abrirse a dispositivos personales. ¿Es necesaria la administración de dispositivos para alguien que comprueba su programación del día? Conocer la huella de los dispositivos ayudará al departamento de TI a:

- Saber qué usuario está registrando dispositivos. El hecho de que un usuario registre varios dispositivos a la semana puede ser indicativo de una actividad sospechosa.
- Comprender las huellas de los dispositivos. Saber qué tipos de dispositivos están en uso en la red puede ayudar al departamento de TI a dar servicio técnico a dichos dispositivos.

Considere la opción de almacenar en una ubicación central el vínculo entre el dispositivo y el usuario para que el departamento de TI lo use más adelante al realizar auditorías o informes. Para poder habilitar BYOD, el departamento de TI necesita pasar de un estado de dispositivo desconocido a un estado de dispositivo conocido. Esto le permitirá tener más control de los dispositivos que son activos corporativos. Normalmente, las compañías enfocan este requisito de tres maneras diferentes:

- Enfoque 1: instalación de un agente de administración en el dispositivo de cada usuario
- Enfoque 2: registro de todos los dispositivos en un repositorio central sin necesidad de instalar un agente de administración
- Enfoque 3 (1 y 2): registro e instalación de un agente de administración en el dispositivo de cada usuario


### Opciones de dispositivos conocidos y desconocidos: ventajas y desventajas

Utilice la siguiente lista para entender las ventajas y desventajas de las opciones de dispositivos conocidos y desconocidos:

- Instalación de un agente de administración en el dispositivo de cada usuario
    - Ventajas
        - Más control de los dispositivos de los usuarios.
        - Funcionalidad de borrado remoto
        - Funcionalidad de implementación de aplicaciones.
        - Más controles de seguridad disponibles para que el departamento de TI controle el dispositivo.
    - Desventajas
        - Se requiere que los usuarios instalen un agente de administración.
        - El agente de administración debe poder instalarse en diversas plataformas de dispositivos.
        - Más sobrecarga administrativa.
- Registro de todos los dispositivos en un repositorio central sin necesidad de instalar un agente de administración.
    - Ventajas
        - No se requiere un agente de administración.
        - Menos sobrecarga administrativa.
        - Autenticación de segundo factor de dispositivos.
        - Validación del vínculo entre los usuarios y los dispositivos.
    - Desventajas
        - Menos control de los dispositivos de los usuarios.
        - Menos controles de seguridad disponibles.
        - Falta de funcionalidad para realizar implementaciones de aplicaciones y borrados remotos.
- Registro e instalación de un agente de administración en el dispositivo de cada usuario.
    - Ventajas
        - Más control de los dispositivos de los usuarios.
        - Funcionalidad de borrado remoto
        - Funcionalidad de implementación de aplicaciones.
        - Más controles de seguridad.
        - Autenticación de segundo factor de dispositivos.
        - Validación del vínculo entre los usuarios y los dispositivos.
    - Desventajas
        - Se requiere que los usuarios instalen un agente de administración.
        - El agente de administración debe poder instalarse en diversas plataformas de dispositivos.
        - Más sobrecarga administrativa.

En Windows Server 2012 R2, el nuevo concepto de [Unión al lugar de trabajo](https://technet.microsoft.com/library/dn280945.aspx) permite al departamento de TI pasar el dispositivo de un estado desconocido a un estado conocido. El dispositivo también puede usarse como autenticación de segundo factor y un inicio de sesión único a las aplicaciones y los recursos de un área de trabajo. La herramienta Unión al lugar de trabajo está disponible de forma nativa en Windows 10, pero también es compatible con otras plataformas como iOS y Android. El área de trabajo aprovecha el servicio de registro de dispositivos (DRS). Para obtener más información sobre el servicio DRS, consulte [Configurar un servidor de federación con el Servicio de registro de dispositivos](https://technet.microsoft.com/library/dn486831.aspx). El área de trabajo es una nueva tecnología y funciona con casos de uso específicos. Consulte [Acceso seguro a recursos de la empresa desde cualquier ubicación y dispositivo](https://technet.microsoft.com/library/dn550982.aspx) para obtener más información sobre una solución que aprovecha Unión al lugar de trabajo con el inicio de sesión único.

Si quiere utilizar DRS, es preciso entender que esta característica no proporciona capacidades de administración. Si la compañía necesita más controles de seguridad para tener disponibles más opciones de control de los dispositivos de usuario, considere la opción de usar el DRS junto con una [inscripción de dispositivo móvil](https://technet.microsoft.com/library/jj733620.aspx) como solución de agente de administración. Sin embargo, si elige esta opción, debe tener una suscripción de Microsoft Intune. Para obtener más información sobre Microsoft Intune, consulte la [página de Microsoft Intune](/intune/understand-explore/introduction-to-microsoft-intune)..

## Red

Debe abordarse el acceso a la red corporativa desde la perspectiva del usuario y del dispositivo. ¿Cómo accederán los usuarios a los datos de la compañía al utilizar sus propios dispositivos? La mayoría de soluciones de infraestructura BYOD solo se centran mínimamente en el acceso remoto desde dispositivos de usuarios. Sin embargo, si se adopta un enfoque centrado en las personas, debe tener en cuenta dónde se encuentran los usuarios. Debe centrarse no solo en el acceso remoto, sino también en cómo accederán los usuarios a los datos mientras se encuentran en las oficinas. Además, deberá tener en cuenta los problemas normativos específicos de la alineación geopolítica de su organización. Por ejemplo, ¿cómo pueden los usuarios que están ubicados físicamente en otro país o región tener un acceso personalizado a la red?

Si su compañía tiene recursos en la nube pública que estarán disponibles mediante Internet desde dispositivos de los usuarios, debe tener en cuenta cómo se controlará el tráfico. Considere el uso de cifrado mientras los datos están en tránsito desde dispositivos de los usuarios al proveedor de nube. Cuando los usuarios accedan a los recursos internos, también debe utilizar el cifrado de datos.

### Opciones de conectividad de red: ventajas y desventajas

Utilice la siguiente lista para entender las ventajas y desventajas de las opciones de conectividad:

- VPN tradicional
    - Ventajas
        - Tecnología consolidada.
        - Fácil de configurar.
        - Ampliamente disponible en varias plataformas.
    - Desventajas
        - Sobrecarga de protocolos de los protocolos de cifrado y VPN.
        - Se debe iniciar antes de ejecutar las aplicaciones.
        - Se requiere la interacción del usuario para establecer la conexión.
- Microsoft Direct Access
    - Ventajas
        - Experiencia sin problemas para los usuarios (siempre activo).
        - Compatible con la autenticación de IPsec y el acceso al servidor seleccionado con un servidor de red de Internet.
        - Compatible con el cifrado y la autenticación descentralizada.
    - Desventajas
        - Se requiere una infraestructura local para admitir esta funcionalidad.
        - La solución de problemas puede ser difícil.
        - Mayor sobrecarga administrativa.
        - No disponible en todas las plataformas.
- Desencadenador automático VPN
    - Ventajas
        - Fácil de configurar.
        - La conexión al servidor local se inicia cuando una aplicación necesita acceder a los recursos corporativos.
    - Desventajas
        - Sobrecarga de protocolos de los protocolos de cifrado y VPN.
        - No disponible en todas las plataformas.
- Escritorio remoto con VDI
    - Ventajas
        - Experiencia de usuario sin problemas
        - Más control sobre el escritorio (consolidación).
        - Ampliamente disponible en varias plataformas.
    - Desventajas
        - Se requiere una infraestructura local para admitir esta funcionalidad.
        - La planeación de la capacidad de red, el almacenamiento y el cálculo deben realizarse cuidadosamente para evitar cuellos de botella en el rendimiento.
        - Cada dispositivo requiere una aplicación de cliente de acceso remoto.
- Acceso web
    - Ventajas
        - Ampliamente disponible en varias plataformas.
        - Cifrado disponible con HTTPS.
        - Tecnología consolidada.
        - Fácil de configurar.
    - Desventaja
        - Requiere certificados.
        - Si la infraestructura de certificados es interna, requiere una infraestructura de PKI.
        - Requiere una infraestructura perimetral para publicar aplicaciones de forma segura.

Después de definir el diseño de acceso a redes remotas, considere cómo se conectarán a la red los dispositivos propiedad del usuario mientras están físicamente conectados a ella. Los usuarios que lleven sus dispositivos al trabajo probablemente usarán funciones Wi-Fi para conectarse a los recursos corporativos. Considere usar la segmentación de red (física o lógica) para aislar los dispositivos de los usuarios.

También puede segmentar los dispositivos que se conectarán a la red Wi-Fi según la plataforma donde se ejecuten. Considere también cómo proteger su comunicación y autorización mientras están en las instalaciones accediendo a recursos corporativos.

Puede elegir una segmentación física en el punto de acceso inalámbrico y los componentes de red (conmutadores y enrutadores) para aislar a los usuarios que se conectan mediante el uso de sus propios dispositivos. También puede implementar este tipo de red con [perfiles Wi-Fi en Configuration Manager](https://technet.microsoft.com/library/dn261221.aspx). Puede elegir entre una amplia gama de opciones de seguridad, como certificados para la autenticación de clientes y la validación del servidor que se hayan aprovisionado con [perfiles de certificados de Configuration Manager](https://technet.microsoft.com/library/dn270540.aspx)..


### Opciones de segmentación de la red Wi-Fi: ventajas y desventajas

Utilice la siguiente lista para entender las ventajas y desventajas de las opciones de segmentación de la red Wi-Fi:

- Segmentación física
    - Ventajas
        - Segmentación de seguridad de nivel inferior.
        - Es relativamente fácil de configurar.
        - Se abstrae de la plataforma (sistema operativo).
    - Desventajas
        - La capacidad de administración puede variar según el proveedor.
        - La integración entre diferentes proveedores de hardware puede ser difícil.
        - Mayor costo de implementación y mantenimiento.
- Segmentación lógica (perfiles Wi-Fi)
    - Ventajas
        - Experiencia sin problemas para los usuarios.
        - Más fácil de administrar (en comparación con la segmentación física).
        - Menor costo de implementación (en comparación con la segmentación física).
        - Se abstrae del hardware que se utiliza para conectar dispositivos.
        - Admite varias plataformas (sistemas operativos).
    - Desventajas
        - No proporciona la misma segmentación de seguridad de nivel inferior que la solución de hardware.
- Segmentación dinámica
    - Ventajas
        - Los puntos de acceso inalámbrico usan una infraestructura y SSID comunes.
        - Los atributos de usuario final y de dispositivo aprovisionan dinámicamente el acceso a la red.
    - Desventajas
        - Requiere IPsec para la implementación con [Protección de acceso a redes (NAP)](https://technet.microsoft.com/library/cc731276(v=ws.10).aspx) de Microsoft, lo que puede ser un problema en un escenario de BYOD en el que se necesite compatibilidad para "todos los dispositivos".

> [!NOTE] Para obtener más información sobre los perfiles de Wi-Fi en Configuration Manager, consulte [Introducción a perfiles de Wi-Fi en Configuration Manager](https://technet.microsoft.com/library/dn261224.aspx)..

La ubicación de la red tiene un rol importante en las consideraciones sobre los usuarios y los dispositivos. Puede aprovechar el control de acceso multifactor en AD FS para habilitar las directivas de autorización por aplicación, con las que puede permitir o denegar el acceso en función del usuario, el dispositivo y la ubicación de red. Consulte [Guía de tutorial: Administración de riesgos con control de acceso condicional](https://technet.microsoft.com/library/dn280936.aspx) para obtener más información sobre cómo configurar un entorno para validar esta funcionalidad.



<!--HONumber=Apr16_HO4-->


