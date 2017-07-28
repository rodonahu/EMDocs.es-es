---
title: Proteger los datos empresariales sin necesidad de administrar dispositivos | Microsoft Docs
description: "EMS ofrece funcionalidades innovadoras de protección contra la pérdida de datos con Microsoft Intune. Con ella, puede proteger los datos de la empresa y conservar la experiencia de usuario excelente con aplicaciones de Office 365 a las que están acostumbrados los empleados sin tener que administrar sus dispositivos."
keywords: 
author: jeffgilb
manager: swadhwa
ms.date: 6/7/2017
ms.topic: solution
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b46877f3-cf32-4919-ba63-4df55cd2af32
ms.reviewer: vlpetros
ms.suite: ems
ms.openlocfilehash: b17952c8b7b5e0ab6d02d647740c33a5a54484ea
ms.sourcegitcommit: 0541e4aa400a818551469fe9df8929c25c2dd918
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/25/2017
---
# <a name="protect-company-data-without-managing-devices-with-intune"></a>Proteger los datos empresariales sin necesidad de administrar dispositivos con Intune
Vivimos en un mundo móvil donde los empleados necesitan en el acceso a datos corporativos y herramientas de productividad en sus propios dispositivos móviles allá donde vayan. Debido a su popularidad e importancia, muchas organizaciones buscan una mayor protección de los datos de Office 365 para evitar la pérdida de datos de aplicaciones móviles de Office, a la vez que conservan una experiencia de usuario final excepcional. El departamento de TI necesita proteger el acceso a Office 365 y evitar la pérdida de datos empresariales por parte de los dispositivos y aplicaciones móviles que no pertenecen a la empresa o que esta no administra. El problema es que, mientras que el departamento de TI necesita mantener los datos empresariales, a muchos empleados les preocupa su privacidad cuando el departamento de TI toma control sobre sus dispositivos personales.

## <a name="how-can-enterprise-mobility--security-ems-help-you"></a>¿Cómo puede ayudarle Enterprise Mobility + Security (EMS)?

EMS ofrece funcionalidades innovadoras de protección contra la pérdida de datos con Microsoft Intune. Con ella, puede proteger los datos de la empresa y conservar la experiencia de usuario excelente con aplicaciones de Office 365 a las que están acostumbrados los empleados. Y puede hacerlo sin que los usuarios tengan que inscribir sus dispositivos para la administración, lo que puede aumentar considerablemente las posibilidades de éxito de su programa de BYOD y de cumplimiento de las políticas de TI por parte del usuario final. Obtiene el control que necesita y los usuarios disfrutan de la experiencia moderna que esperan.  Debido a que Microsoft Intune funciona directamente con Azure Active Directory y Office 365 para administrar el acceso y proteger los datos empresariales, no es necesario instalar y mantener una infraestructura local o enrutar todo el tráfico a través de él.

### <a name="recommended-solution"></a>Solución recomendada

Microsoft Intune permite a las organizaciones proporcionar acceso a las aplicaciones móviles y proteger contra pérdidas de datos de Office 365 sin necesidad de que los empleados se inscriban en la administración de dispositivos. La administración de dispositivos (MDM) todavía se puede realizar si es necesario, pero ahora es opcional. Las poderosas funcionalidades de protección de aplicaciones de Intune ayudan al departamento de TI a proteger los datos empresariales en el nivel de la aplicación sin tener que administrar los dispositivos reales. Para datos muy confidenciales, la protección puede ampliarse más allá del nivel de archivo con Azure Information Protection. Empleados, proveedores y socios pueden usar sus dispositivos móviles favoritos para tener acceso a herramientas de productividad conocidas y datos corporativos sin riesgo de intrusión en su privacidad. Y si el departamento de TI ya tiene una solución MDM instalada, Intune puede agregar una protección avanzada contra la pérdida de datos de control de acceso a Office 365 sin necesidad de anular la inscripción de la solución actual de MDM de los dispositivos y volver a inscribirlos en MDM de Intune.

Vea esta demostración para ver cómo puede evitar la pérdida de datos de aplicaciones móviles (incluidos Office 365 y las aplicaciones internas de línea de negocio o LOB) con las innovadoras funcionalidades de protección de aplicaciones de Intune que no requieren la inscripción de los dispositivos del usuario en Intune MDM:

<iframe width="675" height="480"  src="https://www.youtube.com/embed/BcwgKmsAy18?list=TLGGQ9qBhVYxOZIxMzEyMjAxNg" frameborder="0" allowfullscreen></iframe>

### <a name="how-to-implement-this-solution"></a>Cómo implementar esta solución

El resto de esta solución se divide en las secciones siguientes que muestran cómo proteger los datos de la empresa de Office 365 con Intune:

- **Proteger los datos de aplicaciones con las directivas de protección de aplicaciones móviles de Intune** En esta sección se describe cómo crear e implementar directivas de protección de aplicaciones de Microsoft Intune para proporcionar funcionalidades de prevención contra la pérdida de datos (como copiar, pegar, guardar como, PIN, cifrado, borrado selectivo, etc.) a los usuarios de dispositivos móviles no administrados.

- **Permitir solo aplicaciones móviles que admitan directivas de protección de aplicaciones para acceder a servicios de Office 365** En esta sección aprenderá a crear una directiva que permita que solo las aplicaciones móviles que admiten directivas MAM de Intune tengan acceso a servicios de Office 365 como Exchange Online.

## <a name="protect-app-data-with-intune-mobile-app-protection-policies"></a>Proteger los datos de aplicaciones con las directivas de protección de aplicaciones móviles de Intune

Al proteger los datos de aplicaciones en dispositivos no administrados, no implementará las aplicaciones como haría con los dispositivos administrados. En su lugar, los usuarios descargan las aplicaciones de Office 365 desde el almacén de aplicaciones público en sus dispositivos iOS o Android personales y, después, inician sesión con sus cuentas de trabajo como habitualmente.

Las directivas de protección de aplicaciones para dichas aplicaciones son sencillas de crear para dispositivos iOS y Android en Azure Portal. Estos tipos de directivas permiten restringir las acciones del usuario como cortar, copiar, pegar y guardar como o exigir un PIN, requerir el cifrado y borrar de forma selectiva los datos empresariales de aplicaciones móviles. Cuando se asignan a los usuarios, las directivas de protección de aplicaciones se aplican automáticamente mediante Intune y de forma obligatoria entre aplicaciones y cuentas personales y de trabajo. Dado que Intune se integra perfectamente con Azure AD y Office 365, los datos de trabajo estarán protegidos mientras que los datos personales en las mismas aplicaciones de Office permanecen inalterados.

>[!NOTE]
>Las directivas de protección de aplicaciones como estas están disponibles para los equipos de Windows 10 administrados por Intune como dispositivos móviles mediante las [directivas de Windows Information Protection (WIP)](https://technet.microsoft.com/itpro/windows/keep-secure/create-wip-policy-using-intune).

Vea lo fácil que es seleccionar aplicaciones para proteger, configurar la directiva de protección de aplicaciones e implementar la directiva en grupos de usuarios finales después de iniciar sesión en Azure Portal:

>[!TIP]
>Para ver la configuración de la directiva de protección de aplicaciones de Intune, inicie sesión en [Azure Portal](https://portal.azure.com) con sus credenciales de administrador de Intune y busque **Protección de aplicaciones de Intune** en el cuadro *Buscar recursos* de la parte superior del portal. Todos los pasos siguientes se completan desde allí.

-   **Crear una directiva de protección de aplicaciones móviles** Además de proporcionar un nombre (y una descripción opcional) para la directiva, todo lo que necesita hacer para [crear una directiva de protección de aplicaciones](https://docs.microsoft.com/intune-azure/manage-apps/app-protection-policies#create-an-app-protection-policy) consiste en definir la plataforma, seleccionar las aplicaciones que quiere proteger y establecer la configuración de directiva que quiere aplicar:

> **Definir la plataforma**: podrá seleccionar la plataforma iOS o Android al crear una nueva directiva, pero no podrá crear directivas de protección de aplicaciones para dispositivos Windows. En su lugar, puede [usar directivas de Windows Information Protection (WIP)](https://technet.microsoft.com/itpro/windows/keep-secure/create-wip-policy-using-intune).

> **Seleccione una o más aplicaciones** de destino de la lista de aplicaciones disponibles capaces de estar protegidas en dispositivos no administrados. A medida que se admitan más, se agregarán automáticamente a la lista de aplicaciones disponibles. De forma predeterminada, no se selecciona ninguna, pero puede seleccionar con CTRL + clic tantas aplicaciones como quiera proteger con la directiva. Como alternativa, puede [agregar nuestra propia aplicación de línea de negocio (LOB)](https://docs.microsoft.com/intune/deploy-use/protect-line-of-business-apps-and-data-on-devices-not-enrolled-in-microsoft-intune) para iOS y Android.

> **Establezca la configuración de directiva necesaria** [para iOS y Android](https://docs.microsoft.com/en-us/intune-azure/manage-apps/app-protection-policies#policy-settings) de Reubicación de datos (cortar, copiar, pegar, guardar como, cifrado, etc.) y acceso (requerir PIN, intervalo sin conexión, etc.).

- **Implemente la directiva de protección de aplicaciones a grupos de usuarios** mediante [la selección de los grupos de usuarios](https://docs.microsoft.com/intune-azure/manage-apps/app-protection-policies#deploy-a-policy-to-users) a los que se aplicarán las directivas. Estos pueden ser los mismos grupos que ya administra en Office 365 o cualquier grupo disponible en Azure Active Directory.

La primera vez que un usuario final abre una aplicación protegida por una directiva de protección de aplicaciones, recibirá un mensaje que le indica que su departamento de TI ahora protege los datos empresariales en la aplicación. Si la configuración de acceso de la directiva se ha configurado para requerir un PIN o una contraseña, también se solicitará al usuario que cree uno antes de tener acceso a la aplicación protegida, tal como se muestra a continuación desde un dispositivo Android:

![Requisito de PIN de directiva de protección de aplicaciones](..\Solutions\media\protect-company-data-without-managing-devices\protect-company-data-without-managing-devices-fig1.png)

Dado que las directivas de protección de aplicaciones funcionan en las aplicaciones y no en los dispositivos, Intune facilita al departamento de TI la protección de los datos empresariales al restringir el uso compartido de datos entre aplicaciones personales y administradas, entre las cuentas personales y corporativas dentro de la misma aplicación, y solo permite que los datos corporativos se guarden en ubicaciones aprobadas. Los empleados móviles no volverán a ceder el control de sus dispositivos para obtener acceso a herramientas y datos corporativos esenciales sobre la marcha.

>[!TIP]
>Para datos muy confidenciales, la protección puede ampliarse más allá del nivel de archivo con la tecnología de protección empleada por Azure Information Protection: [Azure Rights Management (Azure RMS).](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)

## <a name="allow-only-mobile-apps-that-support-app-protection-policies-to-access-office-365-services"></a>Permitir solo aplicaciones móviles que admitan directivas de protección de aplicaciones para acceder a servicios de Office 365
De forma predeterminada, todos los usuarios y todas las aplicaciones tienen acceso a la información empresarial alojada en Exchange Online. Con Intune puede controlar de forma sencilla a quién y a qué aplicaciones se les concede acceso configurando directivas de acceso condicional. Estas permiten el acceso a servicios de Office 365 solo a las aplicaciones que admiten directivas de protección de aplicaciones de Intune. Por ejemplo, desde [Azure Portal](https://portal.azure.com) puede crear una directiva que permita el acceso a Exchange Online solo a algunos grupos y aplicaciones en iOS y Android, tanto si el dispositivo se administra como si no.

- **Crear una directiva de acceso condicional de protección de aplicaciones en Exchange Online** [Estas directivas se crean](https://docs.microsoft.com/intune/deploy-use/mam-ca-for-exchange-online) en el mismo lugar que las directivas de protección de aplicaciones comentadas anteriormente. Además de definir qué aplicaciones pueden tener acceso a Exchange Online, también tendrá que definir grupos de acceso de usuario para administrar las conexiones con Exchange Online.

- Los usuarios deberán **configurar una aplicación de agente** la primera vez que intenten usar una aplicación de directiva compatible para tener acceso a Exchange Online. Para dispositivos iOS, la aplicación de agente es Microsoft Authenticator, y los dispositivos Android tendrán que instalar la aplicación Portal de empresa de Intune. Aunque [estas aplicaciones de agente](https://docs.microsoft.com/intune/deploy-use/use-apps-with-mam-ca) registrarán el dispositivo con Azure AD para proporcionar la comprobación de identidad de dispositivo, no inscribirán el dispositivo para su administración.

Con la directiva de acceso condicional para Exchange Online lista, los usuarios recibirán un mensaje similar al siguiente cuando intenten tener acceso a su correo electrónico corporativo mediante el cliente de correo electrónico nativo, tal como se muestra en un dispositivo Android:

![Requisito de la aplicación Outlook de directiva de protección de aplicaciones](..\Solutions\media\protect-company-data-without-managing-devices\protect-company-data-without-managing-devices-fig2.png)

Cuando el usuario final seleccione el vínculo *Empezar ahora* del correo electrónico, el explorador web predeterminado para el dispositivo se abre y muestra https://portal.manage.microsoft.com/OutlookRedirect.aspx. Desde allí, se solicita al usuario que instale la aplicación gratuita de Microsoft Outlook desde la tienda de aplicaciones usada por el dispositivo.

### <a name="learn-more"></a>Obtener más información

[Introducción al uso de Enterprise Mobility + Security](https://docs.microsoft.com/enterprise-mobility/solutions/ems-get-started)

[Microsoft Enterprise Mobility](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility)
