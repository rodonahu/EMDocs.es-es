---
title: "Usar directivas de administración de aplicaciones móviles en Intune"
description: "Cree e implemente una aplicación en Intune con una directiva de administración de aplicaciones móviles."
keywords: 
author: craigcaseyMSFT
ms.author: v-craic
manager: swadhwa
ms.date: 01/10/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6d7c4104-b85f-407e-8832-0e6bbac934f5
ms.reviewer: 
ms.suite: ems
ms.openlocfilehash: 418aa02b98040a8a74313513f05b231a20ea472a
ms.sourcegitcommit: 0541e4aa400a818551469fe9df8929c25c2dd918
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/25/2017
---
# <a name="use-mobile-app-management-policies-in-intune"></a>Usar directivas de administración de aplicaciones móviles en Intune
Uno de los principales motivos de que muchas empresas usen Microsoft Intune es para implementar las aplicaciones que los usuarios necesitan para realizar su trabajo. Antes de implementar las aplicaciones, tendrá que [administrar los dispositivos](https://docs.microsoft.com/intune/deploy-use/enroll-devices-in-microsoft-intune).

Por ejemplo, si la empresa usa Microsoft Word, hay versiones disponibles para Windows, iOS, Android y otros. El desafío al que se enfrenta como administrador de TI consiste en administrar la gran cantidad de aplicaciones disponibles en muchos dispositivos diferentes y plataformas informáticas, de forma que los usuarios puedan hacer su trabajo y a la vez se garantice la seguridad de los datos de la empresa.

Si usa Intune con Configuration Manager, vea [Cómo controlar aplicaciones mediante directivas de administración de aplicaciones móviles en Configuration Manager](https://technet.microsoft.com/library/mt131414.aspx?f=255&MSPPError=-2147217396).

Compatibilidad de las directivas de administración de aplicaciones móviles (MAM):
- Dispositivos que ejecutan Android 4 y versiones posteriores.
- Dispositivos que ejecutan iOS 7 y versiones posteriores.

> [!NOTE]
> Las directivas de MAM son compatibles con los dispositivos que están inscritos en Intune. Para más información sobre cómo crear directivas de administración de aplicaciones para dispositivos no administrados por Intune, consulte [Proteger datos de aplicación mediante directivas de administración de aplicaciones móviles con Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune).

A diferencia de otras directivas de Intune, no se implementa una directiva de MAM directamente. En su lugar, se asocia la directiva con la aplicación que desea restringir. Cuando la aplicación se implementa e instala en dispositivos, se aplicará la configuración especificada.

Para aplicar restricciones a una aplicación, esta debe incorporar el Kit de desarrollo de software (SDK) para aplicaciones de Microsoft Intune. Existen dos métodos de obtención de este tipo de aplicación:

- **Usar una aplicación administrada por directiva**: tiene integrado el SDK de la aplicación. Para agregar este tipo de aplicación, especifique un vínculo a la aplicación desde una tienda de aplicaciones como, por ejemplo, iTunes Store o Google Play. No es necesario ningún procesamiento adicional para este tipo de aplicación. Para ver la lista completa de las aplicaciones de Microsoft compatibles, vaya a Microsoft Intune mobile application gallery (Galería de aplicaciones móviles de Microsoft Intune) en la página [Microsoft Intune application partners](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners) (Socios de aplicaciones de Microsoft Intune). Haga clic en la aplicación para ver los escenarios y las plataformas admitidos y si la aplicación admite o no varias identidades.
- **Usar una aplicación "ajustada"**: las aplicaciones se vuelven a empaquetar a fin de incluir el SDK para aplicaciones con la herramienta de ajuste de aplicaciones de Microsoft Intune. Esta herramienta se usa normalmente para procesar aplicaciones de empresa que se hayan creado internamente. No se puede usar para procesar aplicaciones que se hayan descargado desde la tienda de aplicaciones. Vea:
  - [Preparar aplicaciones iOS para la administración de aplicaciones móviles con la herramienta de ajuste de aplicaciones de Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool)
  - [Preparar aplicaciones Android para la administración de aplicaciones móviles con la Herramienta de ajuste de aplicaciones de Intune](https://docs.microsoft.com/intune/deploy-use/prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool)

Algunas aplicaciones administradas, como la aplicación Outlook para iOS y Android admiten **identidades múltiples**. Esto significa que Intune solo aplica la configuración de administración a las cuentas corporativas o los datos de la aplicación.

Por ejemplo, mediante la aplicación de Outlook:
- Si el usuario configura una cuenta de correo electrónico de trabajo y otra personal, Intune solo aplica la configuración de administración a la cuenta de trabajo y no administra la cuenta personal.
- Si el dispositivo se retira o se cancela la inscripción, solo los datos corporativos de Outlook se quitan del dispositivo.
- La cuenta de trabajo empleada debe ser la misma cuenta que se usó para inscribir el dispositivo con Intune.

Word, Excel y PowerPoint también admiten varias identidades, aunque las restricciones de directivas solo se aplican al administrar y editar datos de identificación de empresa desde un servicio como OneDrive o SharePoint.

## <a name="create-and-deploy-an-app-in-intune-with-a-mobile-app-management-policy"></a>Crear e implementar una aplicación en Intune con una directiva de administración de aplicaciones móviles

- Paso 1: obtenga el vínculo a una aplicación administrada por directivas o cree una aplicación ajustada.
- Paso 2: publique la aplicación en el espacio de almacenamiento en la nube.
- Paso 3: cree una directiva de administración de aplicaciones móviles.
- Paso 4: implemente la aplicación (seleccione la opción para asociar la aplicación a una directiva de administración de aplicaciones móviles).
- Paso 5: supervise la implementación de la aplicación.

### <a name="step-1-obtain-the-link-to-a-policy-managed-app-or-create-a-wrapped-app"></a>Paso 1: obtenga el vínculo a una aplicación administrada por directivas o cree una aplicación ajustada
- **Para obtener un vínculo a una aplicación administrada por directiva**: desde la tienda de aplicaciones, busque y anote la dirección URL de la aplicación administrada por directiva que quiere implementar.
Por ejemplo, la dirección URL de la aplicación Microsoft Word para iPad es [https://itunes.apple.com/es/app/microsoft-word-for-ipad/id586447913?mt=8](https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8)
- **Para crear una aplicación ajustada:** use la información de los temas [Preparar aplicaciones iOS para la administración de aplicaciones móviles con la Herramienta de ajuste de aplicaciones de Intune](https://docs.microsoft.com/intune/deploy-use/prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool) y [Preparar aplicaciones Android para la administración de aplicaciones móviles con la Herramienta de ajuste de aplicaciones de Intune](https://docs.microsoft.com/intune/deploy-use/prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool) para crear una aplicación ajustada. La herramienta crea una aplicación procesada que se usará al publicar la aplicación en su espacio de almacenamiento en nube.

### <a name="step-2-upload-the-app-to-your-cloud-storage-space"></a>Paso 2: publique la aplicación en el espacio de almacenamiento en la nube.
Cuando se publica una aplicación administrada, los procedimientos difieren en función de si se publica una aplicación administrada por directiva o una aplicación que se procesó mediante la Microsoft Intune App Wrapping Tool para iOS.

Consulte [Agregar aplicaciones para dispositivos móviles en Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune#add-the-app) para ver todos los pasos necesarios para cargar una aplicación en el espacio de almacenamiento en la nube.

### <a name="step-3-create-a-mobile-app-management-policy"></a>Paso 3: cree una directiva de administración de aplicaciones móviles.
El portal de Azure es la consola de administración recomendada para crear directivas MAM. El portal de Azure admite los siguientes escenarios de MAM:
- Dispositivos inscritos en Intune
- Dispositivos administrados por una solución de MDM de terceros
- Dispositivos que no están administrados por ninguna solución de MDM (BYOD).

Consulte [Crear e implementar directivas de administración de aplicaciones móviles con Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune) para obtener más información sobre el uso del portal de Azure para crear una directiva MAM.

Si actualmente usa la consola de administración de Intune para administrar los dispositivos, puede crear una directiva MAM que admita aplicaciones para los dispositivos inscritos en Intune mediante la [consola de administración de Intune](https://docs.microsoft.com/intune/deploy-use/configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console#-step-3-create-a-mobile-application-management-policy).


### <a name="step-4-deploy-the-app-selecting-the-option-to-associate-the-app-with-a-mobile-application-management-policy"></a>Paso 4: implemente la aplicación seleccionando la opción para asociar la aplicación a una directiva de administración de aplicaciones móviles
Si usa el portal de Azure, [implemente la directiva MAM para los usuarios](https://docs.microsoft.com/intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune#deploy-a-policy-to-users).

Si usa el portal de Intune, [implemente la aplicación](https://docs.microsoft.com/intune/deploy-use/deploy-apps-in-microsoft-intune#deploy-an-app), asegurándose de seleccionar la directiva de administración de aplicaciones móviles en la página Administración de aplicaciones móviles para asociar la directiva a la aplicación.

Si se anula la inscripción del dispositivo en Intune, no se eliminan las directivas de las aplicaciones; las aplicaciones que tenían directivas aplicadas conservarán la configuración de las directivas, aunque la aplicación se desinstale y reinstale.

#### <a name="what-to-do-when-an-app-is-already-deployed-on-devices"></a>Qué hacer cuando ya se ha implementado una aplicación en dispositivos

Puede haber situaciones en que implemente una aplicación y uno de los usuarios o dispositivos de destino ya tenga una versión no administrada de la aplicación instalada, por ejemplo, si el usuario ha instalado Microsoft Word desde la tienda de aplicaciones.

En este caso, debe pedir al usuario que desinstale manualmente la versión no administrada para que se pueda instalar la versión administrada que se ha configurado.

En cambio, en el caso de los dispositivos que ejecutan iOS 9 y versiones posteriores, Intune pedirá automáticamente al usuario permiso para ocuparse de la administración de la aplicación existente. Si acepta, Intune administrará la aplicación y también se aplicarán las directivas de MAM que ha asociado a la aplicación.


### <a name="step-5-monitor-the-app-deployment-with-mam-policy"></a>Paso 5: supervise la implementación de la aplicación con la directiva MAM
Use los procedimientos siguientes para supervisar la implementación de la aplicación a través de la consola de Intune y para resolver cualquier conflicto entre directivas.

1. En la [consola de administración de Microsoft Intune](https://manage.microsoft.com/), haga clic en **Grupos**.
2. Realice uno de los siguientes pasos:
  -  Haga clic en **Todos los usuarios** y luego haga doble clic en el usuario cuyos dispositivos desea examinar. En la página Propiedades del usuario, haga clic en **Dispositivos** y luego haga doble clic en el dispositivo que quiere examinar.
  -  Haga clic en **Todos los dispositivos > Todos los dispositivos móviles**. En la página Propiedades de grupo de dispositivos, haga clic en **Dispositivos** y luego haga doble clic en el dispositivo que quiere examinar.
3. En la página Propiedades del dispositivo móvil, haga clic en **Directiva** para ver una lista de las directivas de MAM que se hayan implementado en el dispositivo.
4. Seleccione la directiva de MAM cuyo estado quiere ver. Puede ver los detalles de la directiva en el panel inferior y expandir el nodo para mostrar su configuración.
5.  En la columna Estado de cada una de las directivas de MAM, se mostrará Cumplimiento, Cumplimiento (pendiente) o Error. Si la directiva seleccionada tiene uno o más valores en conflicto, se mostrará Error en este campo.
6.  Cuando haya identificado un conflicto, puede modificar las configuraciones de directivas en conflicto para que usen la misma configuración o implementar una sola directiva para la aplicación y el usuario.

> [!NOTE]
> Puede obtener más información general sobre la supervisión de aplicaciones a través del [portal de Azure](https://docs.microsoft.com/intune/deploy-use/monitor-mobile-app-management-policies-with-microsoft-intune) o mediante la [consola de Intune](https://docs.microsoft.com/intune/deploy-use/monitor-apps-in-microsoft-intune).

## <a name="where-to-go-from-here"></a>Próximos pasos

Después de haber creado e implementado una aplicación asociada a una directiva MAM, puede obtener más información sobre la [experiencia del usuario final de MAM](end-user-experience-mam.md). Esto le ayudará a prepararse para los problemas que pudieran surgir.
