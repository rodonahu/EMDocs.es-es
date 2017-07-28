---
title: Responsabilidades de Microsoft
description: Responsabilidades de Microsoft cuando los clientes usan el beneficio del centro de FastTrack
keywords: 
author: NathBarn
ms.author: NathBarn
manager: angrobe
ms.date: 02/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c8fd871e-f1bc-43ec-a5f3-ad025df9b026
ms.reviewer: 
ms.suite: ems
ms.openlocfilehash: 77e668d5f638ee2e4b9a9e81a1f9181252fde8b9
ms.sourcegitcommit: 0541e4aa400a818551469fe9df8929c25c2dd918
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/25/2017
---
# <a name="microsoft-responsibilities"></a>Responsabilidades de Microsoft

Microsoft tiene las siguientes responsabilidades durante la incorporación.

## <a name="general"></a>General

-   Proporcionar asistencia remota para las actividades de configuración necesarias, como se explica en las descripciones detalladas de cada fase.

-   Proporcionar la documentación y las herramientas de software, las consolas de administración y los scripts necesarios para ayudarle a reducir o eliminar las tareas de configuración.

## <a name="initiate-phase"></a>Fase de inicio

-   Ponerse en contacto con usted en un plazo de 30 días a partir de la compra de licencias aptas para un nuevo inquilino.

-   Trabajar con el usuario para comenzar con la incorporación.

-   Definir los servicios elegibles que desea incorporar.

## <a name="assess-phase"></a>Fase de evaluación

-   Proporcionar una introducción administrativa.

-   Proporcionar instrucciones sobre:

    -   Necesidades de infraestructura, red y DNS.

    -   Necesidades del cliente (explorador de Internet, sistema operativo cliente y servicios).

    -   Identidad de usuario y aprovisionamiento.

    -   Habilitar los servicios elegibles que se han comprado y definido como parte de la incorporación.

-   Establecer la escala de tiempo para las actividades de corrección.

-   Proporcionar una lista de comprobación de correcciones.

## <a name="remediate-phase"></a>Fase de corrección

-   Celebrar teleconferencias con usted según la programación acordada para revisar el progreso de las actividades de corrección.

-   Ayudar por medio de las herramientas en ejecución a identificar y corregir problemas, así como a interpretar los resultados.

## <a name="enable-phase"></a>Fase de habilitación
Proporcionar instrucciones sobre:

-   Activar el inquilino de Microsoft Online Services.

-   Configurar protocolos TCP/IP y puertos de firewall.

-   Configurar DNS para los servicios elegibles.

-   Validar la conectividad a Microsoft Online Services.

-   Para un entorno de un bosque único:

    -   Instalación de un servidor de sincronización de directorios entre Active Directory Domain Services (AD DS) y los servicios de Microsoft Online Services pertinentes, si es necesario.

    -   Configurar la sincronización de contraseña (hash de contraseña) para Microsoft Intune (Azure Active Directory) con la herramienta Azure Active Directory Connect.

        > [!NOTE]
        > El desarrollo y la implementación de extensiones de reglas personalizadas están fuera del ámbito.

-   Para un bosque único cuando el destino son identidades federadas: Instalar y configurar los Servicios de federación de Active Directory (AD FS) para la autenticación de dominio local con Intune en una configuración de sitio único con tolerancia a errores, si es necesario.

    > [!NOTE]
    > Para todas las configuraciones de bosques múltiples, las implementaciones de AD FS están fuera del ámbito.

-   Probar la función de inicio de sesión único (SSO) si está implementada.

### <a name="enable-phase---microsoft-azure-active-directory-premium"></a>Fase de habilitación: Microsoft Azure Active Directory Premium

Proporcionar instrucciones sobre las acciones siguientes:

-   Activar el inquilino de Azure AD Premium.

-   Configurar puertos de firewall.

-   Configurar DNS para los servicios elegibles.

-   Validar la conectividad a servicios Azure AD Premium.

-   Para un entorno de un bosque único:

    -   Instalación de una sincronización de directorios entre los Servicios de dominio de Active Directory (AD DS) y Azure AD Connect, si es necesario.

    -   Configuración de la sincronización de contraseñas con la herramienta Azure AD Connect.

-   Para entornos de varios bosques:

    -   Instalación de la sincronización de Azure AD Connect y configuración de escenarios con varios bosques.

        > [!NOTE]
        > La sincronización de hash de contraseña y la escritura diferida de contraseñas admiten varios bosques, pero no se admiten otros escenarios de escritura diferida.

    -   Configuración de la sincronización entre bosques de Active Directory local y el directorio de Microsoft Azure Active Directory Premium (Azure Active Directory).

        > [!NOTE]
        > El desarrollo y la implementación de extensiones de reglas personalizadas están fuera del ámbito.

-   Para un bosque único cuando el destino son identidades federadas:

    -   Instalación y configuración de AD FS para la autenticación de dominio local con Azure AD Premium en una configuración de sitio único con tolerancia a errores, si es necesario.

    > [!NOTE]
    > Para todas las configuraciones de bosques múltiples, las implementaciones de AD FS están fuera del ámbito.

-   Probar la función de inicio de sesión único (SSO), si está implementada.

### <a name="enable-phase---azure-ad-premium--with-azure-ad-connect-and-ad-fs"></a>Fase de activación: Azure AD Premium con Azure AD Connect y AD FS

Proporcionar instrucciones sobre la configuración:

-   Aprovisionamiento de usuarios, incluidas las licencias.

-   Sincronización de directorios de Azure AD Connect (con escritura diferida de contraseñas y sincronización de hash de contraseña).

  - Restablecimiento de la contraseña de autoservicio (SSPR).

  - Azure Multi-Factor Authentication.

  - Integración de aplicaciones de software como servicio (SaaS) con el inicio de sesión único desde [Azure Active Directory Marketplace](https://azure.microsoft.com/marketplace/active-directory/).

  - Pantalla de inicio de sesión personalizada, que incluye un logotipo, texto e imágenes.

  - Grupos dinámicos y de autoservicio (Grupos).

  - Proxy de aplicación de Azure Active Directory.

  - Azure AD Connect Health.

  - Identity Protection.

  - Privileged Identity Management.

  - Informes de uso y seguridad para administradores.

  - Alertas y notificaciones administrativas.

### <a name="enable-phase---intune"></a>Fase de habilitación: Intune
Proporcionar instrucciones sobre las acciones siguientes:

-   Concesión de licencias a los usuarios finales.

-   Configurar identidades para su uso con Intune mediante el aprovechamiento de las identidades de Active Directory local o en la nube.

-   Agregar usuarios a su suscripción de Intune, definir roles de administrador de TI y crear grupos de usuarios y dispositivos.

-   Configurar la entidad de administración de dispositivos móviles (MDM), según sus necesidades de administración, lo que incluye lo siguiente:

    -   Establecer Intune como entidad de MDM en los casos en que Intune es la única solución de MDM o cuando se usa con la administración de dispositivos móviles para Office 365.

    -   Establecer System Center Configuration Manager como entidad de MDM si tiene una implementación existente de Configuration Manager y quiere ampliar sus funcionalidades de administración con Intune.

        > [!NOTE]
        > Si solo quiere sacar partido de MDM en dispositivos de propiedad, en dispositivos compartidos o en dispositivos de tipo quiosco de sus usuarios finales, no es necesario configurar ninguna entidad de MDM.

    -   Configurar grupos de prueba que se usarán para validar las directivas de administración de MDM.

    -   Configurar directivas de administración de MDM y servicios como los siguientes:

        -   Implementación de aplicaciones para cada plataforma compatible mediante vínculos web o vínculos profundos.

        -   Directivas de acceso condicional.

        -   Implementación de correo electrónico, redes inalámbricas y perfiles de VPN si tiene una infraestructura existente de VPN, Wi-Fi o entidad de certificación en su organización.

        -   Configuración de Microsoft Intune Exchange Connector, si corresponde.

    -   Inscribir dispositivos de cada plataforma compatible en Intune o Configuration Manager con el servicio de Microsoft Intune.

    -   Usar informes de inventario de software y hardware.

    -   Configurar directivas de MAM para cada plataforma compatible.

    -   Configurar directivas de acceso condicional para aplicaciones administradas.

    -   Establecer como destino los grupos de usuarios adecuados con las directivas de MAM anteriores.

    -   Usar los informes de uso de las aplicaciones administradas.

    -   Instalar el software de cliente de Intune, cuando sea necesario.

    -   Usar los informes de hardware y software disponibles en Intune.

**¿Quiere obtener más información?**

[Enterprise Mobility + Security](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility)
