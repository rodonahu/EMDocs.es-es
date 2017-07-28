---
title: "Fases de migración e incorporación"
description: Fases del beneficio del centro de FastTrack
keywords: 
author: NathBarn
ms.author: NathBarn
manager: angrobe
ms.date: 02/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e51f030b-8b08-4fea-96c9-d4ded435a264
ms.reviewer: 
ms.suite: ems
ms.openlocfilehash: 0c404c758f66fba9ded4672fad904ba3987958b5
ms.sourcegitcommit: 0541e4aa400a818551469fe9df8929c25c2dd918
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/25/2017
---
# <a name="onboarding-and-migration-phases"></a>Fases de migración e incorporación
Cuando usa los [Planes y servicios aptos del beneficio del centro de FastTrack](fasttrack-center-benefit-for-enterprise-mobility-suite-ems.md) para obtener Microsoft Azure Active Directory Premium y Microsoft Intune para su uso, existen varias fases implicadas en el proceso. En las secciones siguientes se describe cada fase del proceso de incorporación.

La incorporación consta de cuatro fases principales:

![Las cuatro fases del proceso de incorporación de FastTrack](./media/ft-onboarding-benefit.png)


## <a name="initiate-phase"></a>Fase de inicio

Una vez haya adquirido el número adecuado de licencias, siga las instrucciones que encontrará en el correo electrónico de confirmación de compra para asociar las licencias a un inquilino existente o a un nuevo inquilino. Después, Microsoft comprueba si cumple los requisitos para disfrutar del beneficio del centro de FastTrack e intenta ponerse en contacto con usted para ofrecerle asistencia de incorporación. También puede solicitar asistencia desde el [Centro de FastTrack](http://fasttrack.microsoft.com/) si está listo para implementar estos servicios para su organización.

Para solicitar asistencia, inicie sesión en el [Centro de FastTrack](http://fasttrack.microsoft.com/) con su cuenta profesional o educativa, vaya al panel, expanda **¿Necesita ayuda?** a la izquierda de la pantalla y, después, siga las indicaciones para completar la solicitud. Cuando empiece el soporte técnico de incorporación, configuraremos una programación de reuniones en línea.

Durante esta fase, explicaremos el proceso de incorporación, comprobaremos los datos y convocaremos una reunión de puesta en marcha.

![Fase de inicio de la incorporación](./media/ft-initiate-phase.png)

## <a name="assess-phase"></a>Fase de evaluación

Una vez iniciado el proceso de incorporación, Microsoft trabajará con usted para evaluar su entorno de origen y los requisitos. Se ejecutarán herramientas para evaluar su entorno y Microsoft le ayudará a evaluar la instalación local de Active Directory, los exploradores de Internet, los sistemas operativos de dispositivos cliente, el Sistema de nombres de dominio (DNS), la red, la infraestructura y el sistema de identidades para determinar si se requieren cambios para la incorporación.

Microsoft también se pondrá en contacto con usted para ofrecerle instrucciones sobre cómo impulsar la adopción correcta de los servicios aptos.

Según la configuración actual, le presentaremos un plan de corrección para que su entorno de origen reúna los requisitos mínimos para incorporar correctamente EMS o sus servicios en la nube individuales. También programaremos llamadas de control pertinentes durante la fase de corrección.

![Fase de evaluación de la incorporación](./media/ft-assess-phase.png)

## <a name="remediate-phase"></a>Fase de corrección
Usted realizará las tareas del plan de corrección en su entorno de origen para cumplir los requisitos de incorporación y adopción de cada servicio, si es necesario.

![Fase de corrección de la incorporación](./media/ft-remediate-phase.png)

Antes de comenzar la fase de habilitación, comprobaremos juntos los resultados de las actividades de corrección para asegurarnos de que está listo para continuar.

## <a name="enable-phase"></a>Fase de habilitación
Cuando complete todas las actividades de corrección, el proyecto pasará a la configuración de la infraestructura básica de consumo del servicio y al aprovisionamiento de cada servicio en la nube de EMS apto.

**Fase de habilitación: capacidades principales**

La incorporación principal implica el aprovisionamiento del servicio y la integración de inquilinos e identidades. También incluye los pasos necesarios para proporcionar una base con el objetivo de incorporar servicios en línea, como Azure AD Premium e Intune.

![Fase de habilitación de la incorporación: capacidades principales](./media/ft-enable-phase-core-01.png)

![Fase de habilitación de la incorporación: capacidades principales](./media/ft-enable-phase-core-02.png)

### <a name="enable-phase---azure-ad-premium"></a>Fase de habilitación: Azure AD Premium

Según sea necesario, el entorno de Azure AD Premium puede configurarse con la sincronización de directorios de la herramienta Azure Active Directory Connect y los Servicios de federación de Active Directory (AD FS).

Para los escenarios de Azure AD Premium que incluyen la sincronización de identidades locales en la nube, le ayudaremos mediante la adición de usuarios y administradores de TI a su suscripción, la configuración de los requisitos previos de administración, la configuración de Azure AD Premium, la configuración de la sincronización de directorios y AD FS con la herramienta Azure AD Connect, la configuración de usuarios de prueba y la validación de los principales casos de uso que realiza del servicio.

El programa de instalación de Azure AD Premium incluye las siguientes funciones:

-   Restablecimiento de la contraseña de autoservicio (SSPR).

-   Azure Multi-Factor Authentication (Azure MFA).

-   Integración de aplicaciones de software como servicio (SaaS) con el inicio de sesión único (SSO) desde [Azure Active Directory Marketplace](https://azure.microsoft.com/marketplace/active-directory/).

-   Pantalla de inicio de sesión personalizada, que incluye un logotipo, texto e imágenes.

-   Grupos dinámicos y de autoservicio (Grupos).

-   Proxy de aplicación de Azure Active Directory.

-   Azure Active Directory Connect Health.

-   Identity Protection.

-   Privileged Identity Management.

-   Informes de uso y seguridad para administradores.

-   Alertas y notificaciones administrativas.

![Fase de habilitación de la incorporación: Azure AD Premium](./media/ft-enable-phase_aad-premium_adconnect_adfed.png)

### <a name="enable-phase---intune"></a>Fase de habilitación: Intune

En el caso de Intune, le guiaremos hasta que esté preparado para usar Microsoft Intune para administrar dispositivos. Los pasos específicos dependen del entorno de origen y se basan en el dispositivo móvil y en las necesidades de administración de aplicaciones móviles. Entre estos pasos, se pueden incluir los siguientes:

-   Concesión de licencias a los usuarios finales. También proporcionaremos asistencia sobre cómo activar las licencias por volumen para su inquilino de servicio en la nube de Microsoft, en caso de que sea necesario.

-   Configurar identidades para su uso con Intune mediante el aprovechamiento de las identidades de Active Directory local o en la nube.

-   Agregar usuarios a su suscripción de Intune, definir roles de administrador de TI y crear grupos de usuarios y dispositivos.

-   Configurar la entidad de administración de dispositivos móviles (MDM), según sus necesidades de administración, lo que incluye lo siguiente:

    -   Establecer Intune como entidad de MDM en los casos en que Intune es la única solución de MDM o cuando se usa con la administración de dispositivos móviles para Office 365.

    -   Establecer System Center Configuration Manager como entidad de MDM si tiene una implementación existente de Configuration Manager y quiere ampliar sus funcionalidades de administración con Intune.

        > [!NOTE]
        > Si solo quiere sacar partido de MDM en dispositivos de propiedad, en dispositivos compartidos o en dispositivos de tipo quiosco de sus usuarios finales, no es necesario configurar ninguna entidad de MDM.

-   Proporcionar instrucciones de MDM para:

    -   Configurar grupos de prueba que se usarán para validar las directivas de administración de MDM.

    -   Configurar directivas de administración de MDM y servicios como los siguientes:

        -   Implementación de aplicaciones para cada plataforma compatible mediante vínculos web o vínculos profundos.

        -   Directivas de acceso condicional.

        -   Implementación de correo electrónico, redes inalámbricas y perfiles de red privada virtual (VPN) si el usuario dispone de una infraestructura existente de VPN, Wi-Fi o entidades de certificación en su organización.

        -   Configuración de Microsoft Intune Exchange Connector, si corresponde.

    -   Inscribir dispositivos de cada [plataforma compatible](https://technet.microsoft.com/library/dn600287.aspx) en Intune o Configuration Manager con el servicio de Intune.

-   Proporcionar instrucciones de administración de aplicaciones móviles (MAM) para:

    -   Configurar directivas de MAM para cada plataforma compatible.

    -   Configurar directivas de acceso condicional para aplicaciones administradas.

    -   Establecer como destino los grupos de usuarios adecuados con las directivas de MAM anteriores.

    -   Usar los informes de uso de las aplicaciones administradas.

-   Proporcionar instrucciones de administración de equipos para:

    -   Instalar el software cliente de Intune, cuando sea necesario.

    -   Usar los informes de hardware y software disponibles en Intune.

Microsoft también se pondrá en contacto con usted para ofrecerle instrucciones sobre cómo impulsar la adopción correcta de los servicios aptos.

![Fase de habilitación de la incorporación: Intune](./media/ft-enable-phase_intune_mam.png)

![Fase de habilitación de la incorporación: Intune](./media/ft-enable-phase_intune_mdm-mam_cloudonly.png)

![Fase de habilitación de la incorporación: Intune](./media/ft-enable-phase-intune-mdm-mam-sccm.png)

**¿Quiere obtener más información?**

[Enterprise Mobility + Security](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility)
