---
# required metadata

title: Proceso del programa Beneficio de incorporación y migración a Microsoft FastTrack para Enterprise Mobility Suite (responsabilidades de Microsoft)
description:
keywords:
author: staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: c8fd871e-f1bc-43ec-a5f3-ad025df9b026

# optional metadata

ROBOTS: noindex
#audience:
#ms.devlang:
ms.reviewer: 
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Proceso del programa Beneficio de incorporación y migración a Microsoft FastTrack para Enterprise Mobility Suite (responsabilidades de Microsoft)
En las siguientes secciones se describen lo que puede esperarse de Microsoft cuando se usa [Beneficio de incorporación y migración a Microsoft FastTrack para Enterprise Mobility Suite (EMS)](fasttrack-center-benefit-for-enterprise-mobility-suite-ems.md) con el fin de preparar Azure Active Directory Premium, Microsoft Intune o Azure Rights Management para su uso.

Para obtener información sobre las otras partes del proceso de incorporación de FastTrack, consulte [Beneficio de incorporación y migración a Microsoft FastTrack para Enterprise Mobility Suite (EMS)](fasttrack-center-benefit-process-for-enterprise-mobility-suite-ems.md).


## General

-   Proporcionar asistencia remota para las actividades de configuración necesarias, como se explica en las descripciones detalladas de cada fase.

-   Proporcionar la documentación y las herramientas de software, las consolas de administración y los scripts necesarios para ayudarle a reducir o eliminar las tareas de configuración.

## Fase de inicio

-   Ponerse en contacto con usted en un plazo de 30 días a partir de la compra de licencias aptas para un nuevo inquilino.

-   Trabajar con el usuario para comenzar con la incorporación.

-   Definir los servicios elegibles que desea incorporar.

## Fase de evaluación

-   Proporcionar una introducción administrativa.

-   Proporcionar instrucciones sobre:

    -   Necesidades de infraestructura, red y DNS.

    -   Necesidades del cliente (explorador de Internet, sistema operativo cliente y servicios).

    -   Identidad de usuario y aprovisionamiento.

    -   Habilitar los servicios elegibles que se han comprado y definido como parte de la incorporación.

-   Establecer la escala de tiempo para las actividades de corrección.

-   Proporcionar una lista de comprobación de correcciones.

## Fase de corrección

-   Celebrar teleconferencias con usted según la programación acordada para revisar el progreso de las actividades de corrección.

-   Ayudar por medio de las herramientas en ejecución a identificar y corregir problemas, así como a interpretar los resultados.

## Fase de habilitación
Proporcionar instrucciones sobre:

-   Activar el inquilino de Microsoft Online Services.

-   Configurar protocolos TCP/IP y puertos de firewall.

-   Configurar DNS para los servicios elegibles.

-   Validar la conectividad a Microsoft Online Services.

-   Para un entorno de un bosque único:

    -   Instalación de un servidor de sincronización de directorios entre los Servicios de dominio de Active Directory (AD DS) y los servicios de Microsoft Online Services elegibles, si es necesario.

    -   Configurar la sincronización de contraseña (hash de contraseña) para Microsoft Intune (Azure Active Directory) con la herramienta Azure Active Directory Connect.

        > [!NOTE] El desarrollo y la implementación de extensiones de reglas personalizadas están fuera del ámbito.

-   Para un bosque único cuando el destino son identidades federadas: Instalar y configurar los Servicios de federación de Active Directory (AD FS) para la autenticación de dominio local con Microsoft Intune en una configuración de sitio único con tolerancia a errores, si es necesario.

    > [!NOTE] Para todas las configuraciones de bosques múltiples, las implementaciones de AD FS están fuera del ámbito.

-   Probar la función de inicio de sesión único (SSO) si está implementada.

### Fase de habilitación: Azure Active Directory Premium

Proporcionar instrucciones sobre las acciones siguientes:

-   Activar el inquilino de Microsoft Azure Active Directory Premium.

-   Configurar puertos de firewall.

-   Configurar DNS para los servicios elegibles.

-   Validar la conectividad a servicios de Microsoft Azure Active Directory Premium.

-   Para un entorno de un bosque único:

    -   Instalar una sincronización de directorios entre los Servicios de dominio de Active Directory (AD DS) y Azure Active Directory Connect, si es necesario.

    -   Configuración de la sincronización de contraseñas con la herramienta Azure Active Directory Connect.

-   Para entornos de varios bosques:

    -   Instale la sincronización de Azure Active Directory Connect y configúrela para escenarios de bosques múltiples. Tenga en cuenta que la sincronización de hash de contraseña y la escritura diferida de contraseñas admiten varios bosques.  Sin embargo, no se admiten otros escenarios de escritura diferida.

    -   Configure la sincronización entre bosques de Active Directory local y el directorio de Microsoft Azure Active Directory Premium (Azure Active Directory).

        > [!NOTE] El desarrollo y la implementación de extensiones de reglas personalizadas están fuera del ámbito.

-   Para un bosque único cuando el destino son identidades federadas: instalar y configurar los Servicios de federación de Active Directory (AD FS) para realizar la autenticación del dominio local con Microsoft Azure AD Premium en una configuración de sitio único con tolerancia a errores, si es necesario.

    > [!NOTE] Para todas las configuraciones de bosques múltiples, las implementaciones de AD FS están fuera del ámbito.

-   Probar la función de inicio de sesión único (SSO) si está implementada.

### Fase de habilitación: Azure Active Directory Premium con Azure Active Directory Connect y los Servicios de federación de Active Directory (AD FS)

Proporcionar instrucciones sobre la configuración:

-   Aprovisionamiento de usuarios, incluidas las licencias.

-   Sincronización de directorios de Azure Active Directory Connect (con escritura diferida de contraseñas y sincronización de hash de contraseña).

-   Servicios de federación de Active Directory (AD FS)

- Restablecimiento de la contraseña de autoservicio (SSPR).

- Azure Multi-Factor Authentication (MFA).

- Una sola aplicación integrada que puede incluir el inicio de sesión único para las aplicaciones de SaaS.

- Informes de uso y seguridad para administradores.

- Administración de grupos de autoservicio (SSGM).

- Proxy de aplicación.

- Notificaciones del administrador.

- Pantalla de inicio de sesión personalizada, que incluye un logotipo, texto e imágenes.
 
### Fase de habilitación: Microsoft Intune
Proporcionar instrucciones sobre:

-   Concesión de licencias a los usuarios finales. Cuando sea necesario, también proporcionaremos asistencia sobre cómo activar las licencias por volumen para su inquilino de servicio en la nube de Microsoft.

-   Configurar identidades para su uso con Microsoft Intune mediante el aprovechamiento de las identidades de Active Directory local o en la nube.

-   Agregar usuarios a su suscripción de Microsoft Intune, definir roles de administrador de TI y crear grupos de usuarios y dispositivos.

-   Configuración de la entidad de administración de dispositivos móviles, según sus necesidades de administración:

    -   Establecer Microsoft Intune como entidad de MDM en los casos en que Microsoft Intune es la única solución de MDM o cuando se usa con la administración de dispositivos móviles para Office 365.

    -   Si tiene una implementación existente de System Center Configuration Manager y desea para ampliar sus capacidades de administración con Microsoft Intune, establezca Configuration Manager como entidad de MDM.

        > [!NOTE] Si solo desea sacar partido de la administración de aplicaciones móviles en dispositivos de propiedad, en dispositivos compartidos o en dispositivos de tipo quiosco de sus usuarios finales, no es necesario configurar ninguna entidad de MDM.

-   Si la administración de dispositivos móviles está incluida, le ofreceremos instrucciones para lo siguiente:

    -   Configurar grupos de prueba que se usarán para validar las directivas de administración de MDM.

    -   Configurar directivas de administración de MDM y servicios como los siguientes:

        -   Implementación de aplicaciones para cada plataforma compatible mediante vínculos web o vínculos profundos.

        -   Directivas de acceso condicional.

        -   Implementación de perfiles de correo electrónico.

        -   Configurar Microsoft Intune Exchange Connector, si corresponde.

    -   Inscribir hasta dos dispositivos de prueba de cada plataforma compatible en Microsoft Intune o Configuration Manager con el servicio de Microsoft Intune.

    -   Usar informes de inventario de software y hardware.

-   Si la administración de aplicaciones móviles (MAM) está incluida, o bien si lo que quiere es complementar su solución existente de MDM de terceros con directivas de MAM, le proporcionamos orientación con lo siguiente:

    -   Configurar directivas de MAM para cada plataforma compatible.

    -   Configurar directivas de acceso condicional para aplicaciones administradas.

    -   Establecer como destino los grupos de usuarios adecuados con las directivas de MAM anteriores.

    -   Usar los informes de uso de las aplicaciones administradas.

-   Si la administración de equipos está incluida, le ofreceremos instrucciones para lo siguiente:

    -   Instalar el software de cliente de Intune, cuando sea necesario.

    -   Usar los informes de hardware y software disponibles en Intune.

### Fase de habilitación: Azure Rights Management Premium

Proporcionar instrucciones sobre las acciones siguientes:

-   Activar el inquilino de Azure RMS.

-   Adición de administradores de seguridad de información adicionales para administrar plantillas.

-   Asignación de una cuenta de superusuario para Azure RMS.

-   Licencias para dos usuarios pilotos de Azure RMS.

-   Configuración de dos grupos de distribución de prueba para validar directivas.

-   Configuración de una plantilla personalizada de Azure RMS para su directorio.

-   Instrucciones para la configuración de la integración de SharePoint Online y Exchange Online con Azure RMS, que incluyen:

    -   Configuración y validación de la integración de Exchange Online con Azure RMS.

    -   Configuración de una regla de flujo de correo de prueba para cifrar mensajes confidenciales enviados a destinatarios ajenos a la organización.

    -   Configuración y validación de la protección de SharePoint Online de una biblioteca de prueba que se protegerá con Azure RMS.

-   Configuración de un servidor local con el conector RMS, cuando sea aplicable:

    -   La configuración y validación de la integración de Exchange 2013/2010 local con Azure RMS.

    -   La configuración de una regla de flujo de correo de prueba para cifrar mensajes confidenciales enviados a destinatarios ajenos a la organización mediante el conector.

    -   La configuración y validación de la protección de SharePoint 2013/2010 local de una biblioteca de prueba que se protegerá con Azure RMS.

-   La configuración de la aplicación de uso compartido de RMS para dispositivos Windows y dispositivos que no son Windows.

Lea sobre la siguiente parte del proceso de incorporación de FastTrack: [Responsabilidades del cliente](fasttrack-center-benefit-process-for-ems-your-responsibilities.md).

### ¿Desea obtener más información?
Consulte [Enterprise Mobility Suite](https://www.microsoft.com/en-us/server-cloud/enterprise-mobility/overview.aspx).



<!--HONumber=Jun16_HO1-->


