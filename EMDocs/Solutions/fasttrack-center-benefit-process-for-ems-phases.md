---
# required metadata

title: Proceso del programa Beneficio de incorporación y migración a Microsoft FastTrack para Enterprise Mobility Suite (fases)
description:
keywords:
author: 
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: e51f030b-8b08-4fea-96c9-d4ded435a264

# optional metadata

ROBOTS: noindex
#audience:
#ms.devlang:
ms.reviewer: 
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Proceso del programa Beneficio de incorporación y migración a Microsoft FastTrack para Enterprise Mobility Suite (fases)
Cuando se usa [Beneficio de incorporación y migración a Microsoft FastTrack para Enterprise Mobility Suite (EMS)](fasttrack-center-benefit-for-enterprise-mobility-suite-ems.md) con el fin de preparar Azure Active Directory Premium, Microsoft Intune o Azure Rights Management para su uso, el proceso constará de varias fases. En las secciones siguientes se describe cada fase del proceso de incorporación.

Para obtener información sobre las otras partes del proceso de incorporación de FastTrack, consulte [Beneficio de incorporación y migración a Microsoft FastTrack para Enterprise Mobility Suite (EMS)](fasttrack-center-benefit-process-for-enterprise-mobility-suite-ems.md).


La incorporación tiene cuatro fases principales, tal y como se muestra en la ilustración siguiente:


![](./media/Intune-onboarding-phases-9-15-15.png)


## Fase de inicio

Una vez haya adquirido el número adecuado de licencias, siga las instrucciones que encontrará en el correo electrónico de confirmación de compra para asociar las licencias a un inquilino existente o a un nuevo inquilino. Microsoft comprobará si cumple los requisitos para disfrutar del programa de beneficio de incorporación y migración a Microsoft FastTrack y tratará de ponerse en contacto con usted para ofrecerle asistencia de incorporación. También puede solicitar asistencia desde el [Centro de FastTrack](http://fasttrack.microsoft.com/) si está listo para implementar estos servicios para su organización. Para solicitar asistencia, inicie sesión en el [Centro de FastTrack](http://fasttrack.microsoft.com/) (http://fasttrack.microsoft.com), vaya al panel, seleccione el nombre de su empresa, haga clic en la pestaña Offers (Ofertas) y, luego, en "Request Assistance for Microsoft Intune, Azure Active Directory Premium or Azure Rights Management Premium" (Solicitar asistencia para Microsoft Intune, Azure Active Directory Premium o Azure Rights Management Premium). Cuando empiece el soporte técnico de incorporación, configuraremos una programación de reuniones en línea.

Durante esta fase, explicaremos el proceso de incorporación, comprobaremos los datos y convocaremos una reunión de puesta en marcha.

![](./media/Intune-initiate-phase-9-15-15-v2.png)

## Fase de evaluación

Una vez iniciado el proceso de incorporación, Microsoft trabajará con usted para evaluar su entorno de origen y los requisitos. Se ejecutarán herramientas para evaluar su entorno y Microsoft le ayudará a evaluar su Active Directory local, exploradores de Internet, sistemas operativos de dispositivos cliente, DNS, red, infraestructura y sistema de identidad para determinar si se requieren cambios para la incorporación.

Microsoft también se pondrá en contacto con usted para ofrecerle instrucciones sobre cómo impulsar la adopción correcta de los servicios aptos.

Según la configuración actual, le presentaremos un plan de corrección para que su entorno de origen reúna los requisitos mínimos para incorporar correctamente EMS o sus servicios en la nube individuales. También programaremos llamadas de control pertinentes durante la fase de corrección.

![](./media/Intune-assess-phase-9-15-15.png)

## Fase de corrección
Si es necesario, realizará las tareas del plan de corrección en su entorno de origen para cumplir los requisitos de incorporación y adopción de cada servicio.

![](./media/Microsoft-Intune-onboarding-remediate-phase-1.png)

Antes de comenzar la fase de habilitación, comprobaremos juntos los resultados de las actividades de corrección para asegurarnos de que está listo para continuar.

## Fase de habilitación
Cuando complete todas las actividades de corrección, el proyecto pasará a la configuración de la infraestructura básica de consumo del servicio y al aprovisionamiento de cada servicio en la nube de EMS apto.

**Habilitar la fase: capacidades principales**

La incorporación principal implica el aprovisionamiento del servicio y la integración de inquilinos e identidades. También incluye los pasos para proporcionar una base con el objetivo de incorporar servicios en línea como Azure Active Directory Premium, Microsoft Intune y Azure Rights Management Premium.

![](./media/Intune-enable-phase-core-9-15-15.png)

###Fase de habilitación: Azure Active Directory Premium

Según sea necesario, el entorno de Azure Active Directory Premium puede configurarse con la sincronización de directorios de la herramienta Azure Active Directory Connect y los Servicios de federación de Active Directory (AD FS).

Para los escenarios de Azure Active Directory Premium que incluyen la sincronización de identidades locales en la nube, le ayudaremos mediante la adición de usuarios y administradores de TI a su suscripción, la configuración de los requisitos previos de administración, la configuración de Azure Active Directory Premium, la configuración de la sincronización de directorios con la herramienta Azure Active Directory Connect, los Servicios de federación de Active Directory (AD FS) mediante la herramienta Azure Active Directory Connect, la configuración de usuarios de prueba y la validación de sus principales casos de uso para el servicio.

El programa de instalación de Azure Active Directory Premium incluye las siguientes características:

-   Restablecimiento de la contraseña de autoservicio (SSPR)

-   Azure Multi-Factor Authentication (MFA).

-   Aplicación de software como servicio (SaaS): configurar una aplicación de SaaS desde [Azure Active Directory Marketplace](https://azure.microsoft.com/marketplace/active-directory/).

-   Administración de grupos de autoservicio (SSGM)

-   Informes administrativos

![](./media/Microsoft-Azure-AD-Premium-enable-phase-2.png)

###Fase de habilitación: Microsoft Intune

En el caso de Microsoft Intune, y según el dispositivo móvil y las necesidades de administración de aplicaciones móviles, le guiaremos durante la preparación para usar Microsoft Intune para administrar dispositivos. Los pasos exactos dependerán del entorno de origen y pueden incluir:

-   Concesión de licencias a los usuarios finales. Cuando sea necesario, también proporcionaremos asistencia sobre cómo activar las licencias por volumen para su inquilino de servicio en la nube de Microsoft.

-   Configurar identidades para su uso con Microsoft Intune mediante el aprovechamiento de las identidades de Active Directory local o en la nube.

-   Agregar usuarios a su suscripción de Microsoft Intune, definir roles de administrador de TI y crear grupos de usuarios y dispositivos.

-   Configuración de la entidad de administración de dispositivos móviles, según sus necesidades de administración:

    -   Establecer Microsoft Intune como entidad de MDM en los casos en que Microsoft Intune es la única solución de MDM o cuando se usa con la administración de dispositivos móviles para Office 365.

    -   Si tiene una implementación existente de System Center Configuration Manager y desea para ampliar sus capacidades de administración con Microsoft Intune, establezca Configuration Manager como entidad de MDM.

        > [!NOTE]
        > Si solo desea sacar partido de la administración de aplicaciones móviles en dispositivos de propiedad, en dispositivos compartidos o en dispositivos de tipo quiosco de sus usuarios finales, no es necesario configurar ninguna entidad de MDM.

-   Si la administración de dispositivos móviles está incluida, le ofreceremos instrucciones para lo siguiente:

    -   Configurar grupos de prueba que se usarán para validar las directivas de administración de MDM.

    -   Configurar directivas de administración de MDM y servicios como los siguientes:

        -   Implementación de aplicaciones para cada plataforma compatible mediante vínculos web o vínculos profundos.

        -   Directivas de acceso condicional.

        -   Implementación de perfiles de correo electrónico.

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

![](./media/Enable-phase-Intune-11-20-15.png)

###Fase de habilitación: Azure Rights Management Premium

Según sea necesario, el entorno de Azure Rights Management Premium puede configurarse con la sincronización de directorios de Azure Active Directory Connect y los Servicios de federación de Active Directory (AD FS).

En el caso de los escenarios de Azure RMS que incluyan la sincronización de identidades locales en la nube, para ayudarlo, agregaremos usuarios y administradores de TI a su suscripción; configuraremos los requisitos previos de administración, Azure Rights Management Premium, la sincronización de directorios con la herramienta Azure Active Directory Connect, los Servicios de federación de Active Directory mediante Azure Active Directory Connect, y los usuarios de prueba; luego, validaremos sus principales casos de uso para el servicio.

El programa de instalación de Azure RMS incluye la habilitación de las siguientes características:

-   Habilitación del servicio de RMS

-   Configuración de IRM para Exchange Online y Sharepoint Online

-   Conector Rights Management con Exchange y Sharepoint locales

-   Aplicación de uso compartido de RMS para dispositivos Windows y dispositivos que no son Windows

![](./media/Microsoft-Azure-AD-Premium-enable-phase-2.png)


>[!div class="step-by-step"]
[Entorno de origen de FastTrack](fasttrack-center-benefit-process-for-ems-environment-expectations.md)
[Responsabilidades del cliente en FastTrack](fasttrack-center-benefit-process-for-ems-your-responsibilities.md)

### ¿Desea obtener más información?
Consulte [Enterprise Mobility Suite](https://www.microsoft.com/en-us/server-cloud/enterprise-mobility/overview.aspx).



<!--HONumber=Apr16_HO2-->


