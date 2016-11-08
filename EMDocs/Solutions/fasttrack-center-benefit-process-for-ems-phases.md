---
title: "Fases de migración e incorporación"
description: Fases del beneficio del centro de FastTrack
keywords: 
author: staciebarker
manager: angrobe
ms.date: 10/02/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: e51f030b-8b08-4fea-96c9-d4ded435a264
ROBOTS: noindex
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b8c690844c5bae7898bfe908d4ce923a0edf41dd
ms.openlocfilehash: d760cc15bca135889b198636290765a109932b51


---

# Fases de migración e incorporación
Cuando usa los [Planes y servicios aptos del beneficio del centro de FastTrack](fasttrack-center-benefit-for-enterprise-mobility-suite-ems.md) para obtener Azure Active Directory Premium o Microsoft Intune para su uso, existen varias fases implicadas en el proceso. En las secciones siguientes se describe cada fase del proceso de incorporación.

La incorporación tiene las siguientes fases principales:

![Las cuatro fases del proceso de incorporación de FastTrack](./media/ft-onboarding-benefit.png)


## Fase de inicio

Una vez haya adquirido el número adecuado de licencias, siga las instrucciones que encontrará en el correo electrónico de confirmación de compra para asociar las licencias a un inquilino existente o a un nuevo inquilino. Microsoft comprobará si cumple los requisitos para disfrutar del programa de beneficio de incorporación y migración a Microsoft FastTrack y tratará de ponerse en contacto con usted para ofrecerle asistencia de incorporación. También puede solicitar asistencia desde el [Centro de FastTrack](http://fasttrack.microsoft.com/) si está listo para implementar estos servicios para su organización.

Para solicitar asistencia, inicie sesión en el [Centro de FastTrack](http://fasttrack.microsoft.com/) (http://fasttrack.microsoft.com) con su cuenta profesional o educativa, haga clic en su empresa (o agréguela si es necesario), haga clic en la pestaña Servicios y en "Request Assistance for Microsoft Intune or Azure Active Directory Premium" (Solicitar asistencia para Microsoft Intune o Azure Active Directory Premium). Cuando empiece el soporte técnico de incorporación, configuraremos una programación de reuniones en línea.

Durante esta fase, explicaremos el proceso de incorporación, comprobaremos los datos y convocaremos una reunión de puesta en marcha.

![Fase de inicio de la incorporación](./media/ft-initiate-phase.png)

## Fase de evaluación

Una vez iniciado el proceso de incorporación, Microsoft trabajará con usted para evaluar su entorno de origen y los requisitos. Se ejecutarán herramientas para evaluar su entorno y Microsoft le ayudará a evaluar su Active Directory local, exploradores de Internet, sistemas operativos de dispositivos cliente, DNS, red, infraestructura y sistema de identidad para determinar si se requieren cambios para la incorporación.

Microsoft también se pondrá en contacto con usted para ofrecerle instrucciones sobre cómo impulsar la adopción correcta de los servicios aptos.

Según la configuración actual, le presentaremos un plan de corrección para que su entorno de origen reúna los requisitos mínimos para incorporar correctamente EMS o sus servicios en la nube individuales. También programaremos llamadas de control pertinentes durante la fase de corrección.

![Fase de evaluación de la incorporación](./media/ft-assess-phase.png)

## Fase de corrección
Si es necesario, realizará las tareas del plan de corrección en su entorno de origen para cumplir los requisitos de incorporación y adopción de cada servicio.

![Fase de corrección de la incorporación](./media/ft-remediate-phase.png)

Antes de comenzar la fase de habilitación, comprobaremos juntos los resultados de las actividades de corrección para asegurarnos de que está listo para continuar.

## Fase de habilitación
Cuando complete todas las actividades de corrección, el proyecto pasará a la configuración de la infraestructura básica de consumo del servicio y al aprovisionamiento de cada servicio en la nube de EMS apto.

**Habilitar la fase: capacidades principales**

La incorporación principal implica el aprovisionamiento del servicio y la integración de inquilinos e identidades. También incluye los pasos para proporcionar una base con el objetivo de incorporar servicios en línea como Azure Active Directory Premium y Microsoft Intune.

![Fase de habilitación de la incorporación: capacidades principales](./media/ft-enable-phase-core-01.png)

![Fase de habilitación de la incorporación: capacidades principales](./media/ft-enable-phase-core-02.png)

### Fase de habilitación: Azure Active Directory Premium

Según sea necesario, el entorno de Azure Active Directory Premium puede configurarse con la sincronización de directorios de la herramienta Azure Active Directory Connect y los Servicios de federación de Active Directory (AD FS).

Para los escenarios de Azure Active Directory Premium que incluyen la sincronización de identidades locales en la nube, le ayudaremos mediante la adición de usuarios y administradores de TI a su suscripción, la configuración de los requisitos previos de administración, la configuración de Azure Active Directory Premium, la configuración de la sincronización de directorios y los Servicios de federación de Active Directory (AD FS) mediante la herramienta Azure Active Directory Connect, la configuración de usuarios de prueba y la validación de sus principales casos de uso para el servicio.

El programa de instalación de Azure Active Directory Premium incluye las siguientes características:

-   Restablecimiento de la contraseña de autoservicio (SSPR).

-   Azure Multi-Factor Authentication (Azure MFA).

-   Integración de aplicaciones de software como servicio (SaaS) con el inicio de sesión único (SSO) desde [Azure Active Directory Marketplace](https://azure.microsoft.com/marketplace/active-directory/).

-   Pantalla de inicio de sesión personalizada, que incluye un logotipo, texto e imágenes.

-   Grupo dinámico y de autoservicio (Grupos).

-   Proxy de aplicación de Azure Active Directory.

-   Azure Active Directory Connect Health.

-   Identity Protection.

-   Privileged Identity Management.

-   Informes de uso y seguridad para administradores.

-   Alertas y notificaciones administrativas.

![Fase de habilitación de la incorporación: AADP](./media/ft-enable-phase_aad-premium_adconnect_adfed.png)

### Fase de habilitación: Microsoft Intune

En el caso de Microsoft Intune, y según el dispositivo móvil y las necesidades de administración de aplicaciones móviles, le guiaremos durante la preparación para usar Microsoft Intune para administrar dispositivos. Los pasos exactos dependerán del entorno de origen y pueden incluir:

-   Concesión de licencias a los usuarios finales. Cuando sea necesario, también proporcionaremos asistencia sobre cómo activar las licencias por volumen para su inquilino de servicio en la nube de Microsoft.

-   Configurar identidades para su uso con Microsoft Intune mediante el aprovechamiento de las identidades de Active Directory local o en la nube.

-   Agregar usuarios a su suscripción de Microsoft Intune, definir roles de administrador de TI y crear grupos de usuarios y dispositivos.

-   Configuración de la entidad de administración de dispositivos móviles, según sus necesidades de administración:

    -   Establecer Microsoft Intune como entidad de MDM en los casos en que Microsoft Intune es la única solución de MDM o cuando se usa con la administración de dispositivos móviles para Office 365.

    -   Si tiene una implementación existente de System Center Configuration Manager y quiere ampliar sus funcionalidades de administración con Microsoft Intune, establezca Configuration Manager como entidad de MDM.

        > [!NOTE]
        > Si solo quiere sacar partido de la administración de aplicaciones móviles en dispositivos de propiedad, en dispositivos compartidos o en dispositivos de tipo quiosco de sus usuarios finales, no es necesario configurar ninguna entidad de MDM.

-   Si la administración de dispositivos móviles está incluida, le ofreceremos instrucciones para lo siguiente:

    -   Configurar grupos de prueba que se usarán para validar las directivas de administración de MDM.

    -   Configurar directivas de administración de MDM y servicios como los siguientes:

        -   Implementación de aplicaciones para cada plataforma compatible mediante vínculos web o vínculos profundos.

        -   Directivas de acceso condicional.

        -   Implementación de correo electrónico, Wi-Fi y perfiles de VPN.

        -   Configurar Microsoft Intune Exchange Connector, si corresponde.

    -   Inscribir dispositivos de prueba de [cada plataforma compatible](https://technet.microsoft.com/library/dn600287.aspx) en Microsoft Intune o Configuration Manager con el servicio de Microsoft Intune.

-   Si la administración de aplicaciones móviles (MAM) está incluida, o bien si lo que quiere es complementar su solución existente de MDM de Microsoft o de terceros con directivas de MAM, le proporcionamos orientación con lo siguiente:

    -   Configurar directivas de MAM para cada plataforma compatible.

    -   Configurar directivas de acceso condicional para aplicaciones administradas.

    -   Establecer como destino los grupos de usuarios adecuados con las directivas de MAM anteriores.

    -   Usar los informes de uso de las aplicaciones administradas.

-   Si la administración de equipos está incluida, le ofreceremos instrucciones para lo siguiente:

    -   Instalar el software de cliente de Intune, cuando sea necesario.

    -   Usar los informes de hardware y software disponibles en Intune.

Microsoft también se pondrá en contacto con usted para ofrecerle instrucciones sobre cómo impulsar la adopción correcta de los servicios aptos.

![Fase de habilitación de la incorporación: Intune](./media/ft-enable-phase_intune_mam.png)

![Fase de habilitación de la incorporación: Intune](./media/ft-enable-phase_intune_mdm-mam_cloudonly.png)

![Fase de habilitación de la incorporación: Intune](./media/ft-enable-phase-intune-mdm-mam-sccm.png)

**¿Desea obtener más información?**

[Enterprise Mobility + Security](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility)


<!--HONumber=Oct16_HO3-->


