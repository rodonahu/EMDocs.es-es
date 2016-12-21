---
title: Proteger los datos de empresa mediante MAM con MDM
description: "Cree e implemente aplicaciones con directivas de administración de aplicaciones móviles (MAM) para proteger mejor los datos de la empresa."
keywords: 
author: craigcaseyMSFT
ms.author: v-craic
manager: swadhwa
ms.date: 05/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6c7088a9-ca88-4ff2-97a6-f842691fd3c7
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: fd6318efea58b5b6b72de306339629b568bc902d
ms.openlocfilehash: dcf178146e9145f7526368763a8c1452327d939a


---

# Proteger los datos de la empresa en dispositivos móviles mediante directivas de administración de aplicaciones
Proteger los datos de su empresa es de vital importancia y supone un desafío que no deja de aumentar en complejidad, ya que cada vez más empleados usan sus dispositivos móviles para obtener acceso a recursos de la empresa como el correo electrónico y sus datos adjuntos. Como administrador de TI, debe asegurarse de que los datos de la empresa están protegidos incluso cuando los dispositivos móviles no están dentro de la ubicación física de la empresa.

Esta guía se centrará en la habilitación de aplicaciones administradas tal como se aplica a dos implementaciones de MDM de Intune:

- Como una solución de administración de la nube mediante Intune
- Como un servicio integrado con Configuration Manager

Esto le permite crear e implementar aplicaciones con directivas de administración de aplicaciones móviles (MAM) para proteger mejor los datos de la empresa.

Este documento se centra en la creación de estas directivas basadas en MAM cuando el dispositivo del usuario final se inscribe en Intune para MDM. Consulte [Proteger aplicaciones y datos de línea de negocio en dispositivos no inscritos en Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/protect-line-of-business-apps-and-data-on-devices-not-enrolled-in-microsoft-intune) para obtener información sobre la configuración de estas directivas MAM cuando el propio dispositivo no está inscrito en Intune para MDM.

> [!TIP]
> Obtenga una copia descargable de este tema completo de la [Galería de TechNet](https://gallery.technet.microsoft.com/Protect-Company-Data-on-d972f4f4/file/154240/1/Protect%20Company%20Data%20on%20Mobile%20Devices%20through%20Application%20Management%20Policies.pdf).

## Introducción
Las aplicaciones administradas son aplicaciones que tienen directivas de MAM que las hacen compatibles con los requisitos de seguridad de su empresa. Tiene dos opciones para administrar aplicaciones móviles:
- **La funcionalidad predeterminada**, como Apple Managed Open In, que protege los datos corporativos mediante el control de las aplicaciones que pueden abrir determinados documentos y datos adjuntos de correo electrónico
- **El SDK para aplicaciones de Intune**, que permite limitar la funcionalidad y restringir el uso compartido de datos en las aplicaciones que tienen habilitado el SDK para aplicaciones de Intune. Algunas de las principales características del SDK para aplicaciones de Intune es que permite:
  - Administrar la función guardar como
  - Evitar operaciones de cortar, copiar y pegar
  - Exigir autenticación cuando se accede a una aplicación
  - Borrar datos corporativos desde una aplicación administrada por Intune

  Consulte [Información general del SDK para aplicaciones de Intune](https://docs.microsoft.com/intune/develop/intune-app-sdk) para obtener una descripción de todas las características del SDK.

## Antes de comenzar
- **Más información sobre la implementación de aplicaciones con Microsoft Intune:** [conozca los aspectos básicos](https://docs.microsoft.com/intune/understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune) sobre la implementación de aplicaciones de Intune.

- **Evalúe la implementación deseada:** con todas las distintas opciones de diseño y configuración que existen para administrar dispositivos móviles, es difícil determinar cuál es la combinación que mejor se adapta a las necesidades de la empresa. La [Guía de consideraciones de diseño de administración de dispositivos móviles](https://docs.microsoft.com/enterprise-mobility/Solutions/mdm-design-considerations-guide) le ayudará a comprender los requisitos de diseño de la administración de dispositivos móviles y le proporcionará detalles para seguir una serie de pasos y tareas que le ayudarán a diseñar la solución que mejor se adapte a las necesidades tecnológicas y de negocio de su empresa.
- **Comprenda la experiencia del usuario final de alto nivel:** después de implementar la solución, podrá proteger los datos en dispositivos administrados por la empresa o no. Con solo implementar directivas de nivel de aplicación, puede restringir el acceso a los recursos de la empresa y mantener los datos dentro del ámbito del departamento de TI.

   > [!NOTE]
   > La experiencia del usuario final de esta solución se describe con más detalle en el artículo [Experiencia del usuario final](end-user-experience-mam.md).

- **Comprenda el ciclo de vida de la aplicación:** al igual que ocurre con la administración de los dispositivos, las aplicaciones tienen un ciclo de vida que comienza con la preparación y continúa con la implementación, la supervisión, la actualización y la retirada. Intune puede ayudarle en todas las fases de este ciclo de vida. Para obtener información detallada sobre el ciclo de vida de la aplicación, consulte la [Información general sobre el ciclo de vida de la aplicación](https://docs.microsoft.com/intune/deploy-use/overview-of-app-lifecycle-in-microsoft-intune).
- **Obtenga más información sobre las aplicaciones de Microsoft que se pueden usar con directivas de MAM:** la página de [socios de aplicaciones de Microsoft Intune](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners) contiene la información más reciente sobre aplicaciones de Microsoft y otras empresas que puede usar con directivas de administración de aplicaciones móviles.

  Puede usar la herramienta de ajuste de aplicaciones de Microsoft Intune para modificar el comportamiento de las aplicaciones internas a fin de configurar características de la aplicación sin modificar el código de la propia aplicación. Para obtener información más concreta, consulte los siguientes temas:
 - [Preparar aplicaciones iOS para la administración de aplicaciones móviles con la herramienta de ajuste de aplicaciones de Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool)
 - [Preparar aplicaciones Android para la administración de aplicaciones móviles con la Herramienta de ajuste de aplicaciones de Intune](https://docs.microsoft.com/intune/deploy-use/prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool)

- **Comprenda cómo se resuelven los conflictos entre directivas:** cuando hay un conflicto entre directivas de administración de aplicaciones móviles en la primera implementación para el usuario o el dispositivo, el valor específico de configuración en conflicto se quitará de la directiva implementada en la aplicación y esta usará un valor de conflicto integrado (el valor predeterminado es el **más restrictivo**).

  Cuando hay un conflicto de directivas de administración de aplicaciones móviles en implementaciones posteriores para la aplicación o el usuario, el valor específico de la configuración en conflicto no se actualizará en la directiva de administración de aplicaciones móviles implementada para la aplicación y la aplicación usará el valor existente para dicha configuración.

  En casos en los que el dispositivo o el usuario recibe dos directivas en conflicto, se aplica el comportamiento siguiente:
  - Si ya se implementó una directiva para el dispositivo, la configuración de directiva existente no se sobrescribe.
  - Si todavía no se implementó ninguna directiva para el dispositivo y se implementan dos configuraciones en conflicto, se usa la configuración predeterminada integrada en el dispositivo.

## Próximos pasos
Ahora que está familiarizado con el proceso general de MAM, está listo para [usar directivas de administración de aplicaciones móviles en Intune](mam-intune.md) o [usar directivas de administración de aplicaciones móviles en Configuration Manager](mam-configmgr.md). También puede leer sobre la [experiencia del usuario final de directivas MAM](end-user-experience-mam.md).



<!--HONumber=Nov16_HO2-->


