---
title: "Proceso del programa Beneficio de incorporación y migración a Microsoft FastTrack para Enterprise Mobility Suite (requisitos del entorno de origen)"
description: 
keywords: 
author: staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 9048f3e5-cc28-4744-bb5e-36f974abb261
ROBOTS: noindex
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a92fcc56cea75adb6c3db4eeb197dba77d2b63b7
ms.openlocfilehash: 5f1ab589594ccd846686e51612fe54f4ffd226b6


---


# Proceso del programa Beneficio de incorporación y migración a Microsoft FastTrack para Enterprise Mobility Suite (requisitos del entorno de origen)
Cuando se usa [Beneficio de incorporación y migración a Microsoft FastTrack para Enterprise Mobility Suite (EMS)](fasttrack-center-benefit-for-enterprise-mobility-suite-ems.md) con el fin de preparar Azure Active Directory Premium, Microsoft Intune y Azure Rights Management para su uso, su entorno tendrá que cumplir los requisitos que se describen en las secciones siguientes.

Para obtener información sobre las otras partes del proceso de incorporación de FastTrack, consulte [Beneficio de incorporación y migración a Microsoft FastTrack para Enterprise Mobility Suite (EMS)](fasttrack-center-benefit-process-for-enterprise-mobility-suite-ems.md).

Es posible que ya disponga de Microsoft Active Directory de forma local en su entorno de origen y que desee integrarlo con EMS para aprovechar la administración de identidades enriquecida desde una sola consola. El programa de beneficio de incorporación y migración a FastTrack incluye ayuda para integrar Microsoft Azure Active Directory Premium con su implementación local actual. Si se requiere la integración, el entorno de origen debe estar en un nivel mínimo de la aplicación.

En la tabla siguiente se muestran las expectativas del entorno de origen existente para la incorporación.

|Actividad|Expectativa del entorno de origen|
|------------|----------------------------------|
|Incorporación principal|Bosques de Active Directory con el nivel funcional del bosque establecido en Windows Server 2008 o posterior, con la siguiente configuración de bosque:<br /><br />Un único bosque de Active Directory<br />Bosques múltiples de Active Directory </br></br>**Nota**: Para todas las configuraciones de bosques múltiples, la implementación de AD FS está fuera del ámbito del Beneficio del centro de FastTrack.|
|Incorporación de Microsoft Azure Active Directory Premium|Active Directory local y el entorno se han preparado para Azure Active Directory Premium, que incluye la corrección de los problemas identificados que podrían impedir la integración con características de Azure Active Directory y Azure Active Directory Premium.|
|Microsoft Intune, solo nube o integrado con System Center Configuration Manager, incorporación|Para la administración de dispositivos con System Center Configuration Manager 2012 R2 o una versión posterior en conexión con Microsoft Intune, los administradores de TI deberán seguir la [Lista de comprobación de administrador: Configuración de Configuration Manager para administrar dispositivos móviles con Microsoft Intune](https://technet.microsoft.com/library/jj943763.aspx).</br></br> **Nota**: El beneficio de servicio no incluye asistencia para configurar ni actualizar System Center Configuration Manager con los requisitos mínimos necesarios para Microsoft Intune integrado con System Center Configuration Manager.|

Lea sobre la siguiente parte del proceso de incorporación de FastTrack: [Fases del proceso de incorporación](fasttrack-center-benefit-process-for-ems-phases.md).

### ¿Desea obtener más información?
Consulte [Enterprise Mobility Suite](https://www.microsoft.com/en-us/server-cloud/enterprise-mobility/overview.aspx).




<!--HONumber=Jun16_HO4-->


