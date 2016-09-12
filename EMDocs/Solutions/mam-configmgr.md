---
title: "Usar directivas de administración de aplicaciones móviles en Configuration Manager"
description: "Cree e implemente una aplicación en Configuration Manager con una directiva de administración de aplicaciones móviles (MAM)."
keywords: 
author: craigcaseyMSFT
manager: swadhwa
ms.date: 05/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 74288276-84d3-4d24-8307-7875491be9c9
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: faa30f461ff9a1a14d150bd85d86d37cd298570c
ms.openlocfilehash: 68598a547304ca4bc0884156334b02914e517814


---

# Usar directivas de administración de aplicaciones móviles en Configuration Manager
A partir de System Center 2012 Configuration Manager SP2, las directivas de administración de aplicaciones permiten modificar la funcionalidad de las aplicaciones que implementa para ayudar a armonizarlas con las directivas de cumplimiento y seguridad de la empresa. Por ejemplo, puede limitar las operaciones de cortar, copiar y pegar dentro de una aplicación restringida, o configurar una aplicación para abrir todos los vínculos web dentro de un explorador administrado. Las directivas de administración de aplicaciones son compatibles con:

- Dispositivos que ejecutan Android 4 y versiones posteriores.
- Dispositivos que ejecutan iOS 7 y versiones posteriores.

> [!TIP]
> Además de los dispositivos administrados, las directivas de administración de aplicaciones móviles (MAM) pueden usarse para proteger las aplicaciones de dispositivos que no están administrados por Intune. Con esta nueva capacidad, puede aplicar directivas de administración de aplicaciones móviles en aplicaciones que se conecten a los servicios de Office 365. Esto no se admite en aplicaciones que se conecten a Exchange o SharePoint local.
Para usar esta nueva funcionalidad, debe emplear el portal de Azure. Los siguientes temas le ayudarán a empezar a trabajar:
- [Get ready to configure mobile app management policies with Microsoft Intune (Preparación para configurar directivas de administración de aplicaciones móviles con Microsoft Intune)](https://docs.microsoft.com/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune)
- [Crear e implementar directivas de administración de aplicaciones móviles con Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune)

A diferencia de los elementos de configuración y las líneas de base de Configuration Manager, las directivas de administración de aplicaciones no se implementan directamente. En su lugar, debe asociar la directiva con el tipo de implementación (DT) de la aplicación que desea restringir. Cuando el DT de la aplicación se implementa e instala en dispositivos, se aplicará la configuración especificada.

Para aplicar restricciones a una aplicación, esta debe incorporar el Kit de desarrollo de software (SDK) para aplicaciones de Microsoft Intune. Existen dos métodos de obtención de este tipo de aplicación:

- **Usar una aplicación administrada por directivas** (Android e iOS): tiene integrado el SDK para aplicaciones. Para agregar este tipo de aplicación, especifique un vínculo a la aplicación desde una tienda de aplicaciones como, por ejemplo, iTunes Store o Google Play. No es necesario ningún procesamiento adicional para este tipo de aplicación. Para obtener una lista de aplicaciones administradas por directivas disponibles para dispositivos iOS y Android, consulte [Microsoft Intune mobile application gallery (Galería de aplicaciones móviles de Microsoft Intune)](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners).
- **Usar una aplicación "ajustada"** (Android e iOS): aplicaciones que se vuelven a empaquetar para incluir el SDK para aplicaciones mediante la herramienta de ajuste de aplicaciones de Microsoft Intune. Esta herramienta se usa normalmente para procesar aplicaciones de empresa que se hayan creado internamente. No se puede usar para procesar aplicaciones que se hayan descargado desde la tienda de aplicaciones. Vea [Preparar aplicaciones iOS para la administración de aplicaciones móviles con la herramienta de ajuste de aplicaciones de Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool) y [Preparar aplicaciones de Android para la administración de aplicaciones móviles con la herramienta de ajuste de aplicaciones de Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool).

## Crear e implementar una aplicación en Configuration Manager con una directiva de administración de aplicaciones móviles

- Paso 1: obtenga el vínculo a una aplicación administrada por directivas o cree una aplicación ajustada.
- Paso 2: cree una aplicación de Configuration Manager que contenga una aplicación.
- Paso 3: cree una directiva de administración de aplicaciones móviles.
- Paso 4: asocie la directiva de administración de aplicaciones a un tipo de implementación.
- Paso 5: supervise la implementación de la aplicación.

### Paso 1: obtenga el vínculo a una aplicación administrada por directivas o cree una aplicación ajustada.
- **Para obtener un vínculo a una aplicación administrada por directiva**: desde la tienda de aplicaciones, busque y anote la dirección URL de la aplicación administrada por directiva que quiere implementar.
Por ejemplo, la dirección URL de la aplicación Microsoft Word para iPad es [https://itunes.apple.com/es/app/microsoft-word-for-ipad/id586447913?mt=8](https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8)
- **Para crear una aplicación ajustada:** use la información de los temas [Preparar aplicaciones iOS para la administración de aplicaciones móviles con la Herramienta de ajuste de aplicaciones de Intune](https://docs.microsoft.com/intune/deploy-use/prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool) y [Preparar aplicaciones Android para la administración de aplicaciones móviles con la Herramienta de ajuste de aplicaciones de Intune](https://docs.microsoft.com/intune/deploy-use/prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool) para crear una aplicación ajustada. La herramienta crea una aplicación procesada y un archivo de manifiesto asociado. Usará estos archivos al crear una aplicación de Configuration Manager que contenga la aplicación.

### Paso 2: cree una aplicación de Configuration Manager que contenga una aplicación.
El procedimiento para crear la aplicación de Configuration Manager difiere en función de si usa una aplicación administrada por directivas (vínculo externo) o una creada con la herramienta de ajuste de aplicaciones de Microsoft Intune para iOS (paquete de aplicación de iOS).

Consulte [Cómo controlar aplicaciones mediante directivas de administración de aplicaciones móviles en Configuration Manager](https://technet.microsoft.com/library/mt131414.aspx?f=255&MSPPError=-2147217396#BKMK_Step2) para ver todos los pasos necesarios para crear una aplicación de Configuration Manager que contenga una aplicación.

Una vez creada, la aplicación se muestra en el nodo **Aplicaciones** del área de trabajo **Biblioteca de software**.

### Paso 3: cree una directiva de administración de aplicaciones móviles.
A continuación, [creará una directiva de administración de aplicaciones](https://technet.microsoft.com/library/mt131414.aspx?f=255&MSPPError=-2147217396#bkmk_step3) que asociará a la aplicación. Puede crear una directiva de explorador general o administrado.

Una vez creada, la directiva nueva se muestra en el nodo **Directivas de administración de aplicaciones** del área de trabajo **Biblioteca de software**.

### Paso 4: asocie la directiva de administración de aplicaciones a un tipo de implementación.
Cuando se crea un tipo de implementación para una aplicación que requiere una directiva de administración de aplicaciones, Configuration Manager reconoce que una directiva de administración de aplicaciones debe vincularse a este tipo de implementación cuando se implemente la aplicación asociada y le solicitará que asocie una directiva de administración de aplicaciones. Se le solicitará que asocie una directiva general y una directiva de explorador administrado para el explorador administrado. Para obtener más información, consulte [Crear e implementar aplicaciones para dispositivos móviles en Configuration Manager](https://technet.microsoft.com/library/dn469410.aspx).

> [!TIP]
> En el caso de dispositivos que ejecutan sistemas operativos anteriores a iOS 7.1, las directivas asociadas no se quitarán al desinstalar la aplicación.

> Si se anula la inscripción del dispositivo en Configuration Manager, las directivas no se quitan de las aplicaciones. Las aplicaciones que tenían directivas aplicadas conservarán la configuración de las directivas, incluso si la aplicación se desinstala y se vuelve a instalar.


### Paso 5: supervise la implementación de la aplicación.
Una vez haya creado e implementado una aplicación asociada a una directiva de MAM, puede [supervisar la aplicación y resolver cualquier conflicto entre directivas](https://technet.microsoft.com/library/mt131414.aspx?f=255&MSPPError=-2147217396#BKMK_Step5).

Para obtener información general sobre la supervisión de aplicaciones, consulte [Cómo supervisar aplicaciones en Configuration Manager](https://technet.microsoft.com/library/gg682201.aspx).

## Próximos pasos

Después de haber creado e implementado una aplicación asociada a una directiva MAM, puede obtener más información sobre la [experiencia del usuario final de MAM](end-user-experience-mam.md). Esto le ayudará a prepararse para los problemas que pudieran surgir.



<!--HONumber=Sep16_HO1-->


