---
title: Expectativas del entorno de origen
description: Requisitos del entorno de origen para el uso del beneficio del centro de FastTrack
keywords: 
author: NathBarn
ms.author: NathBarn
manager: angrobe
ms.date: 02/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9048f3e5-cc28-4744-bb5e-36f974abb261
ms.reviewer: 
ms.suite: ems
ms.translationtype: Human Translation
ms.sourcegitcommit: 07aeaee067dbd6c827992b9d613d7716b5d57954
ms.openlocfilehash: 6c871d792424f5066328d26892c27c3883605a06
ms.contentlocale: es-es
ms.lasthandoff: 07/07/2017


---


# <a name="source-environment-expectations"></a>Expectativas del entorno de origen
Cuando se usa el [Programa FastTrack para Enterprise Mobility Suite](fasttrack-center-benefit-for-enterprise-mobility-suite-ems.md) con el fin de preparar Microsoft Azure Active Directory Premium y Microsoft Intune para su uso, su entorno tendrá que cumplir los requisitos que se describen en las secciones siguientes.

Es posible que ya disponga de Microsoft Active Directory de forma local en su entorno de origen y que quiera integrarlo con EMS para aprovechar la administración de identidades enriquecida desde una sola consola. El Beneficio del Centro de FastTrack le ayuda a integrar Azure AD con su implementación local existente. Si se requiere la integración, el entorno de origen debe cumplir el nivel mínimo de la aplicación.

En la tabla siguiente se muestran las expectativas del entorno de origen existente para la incorporación.

|Actividad|Expectativa del entorno de origen|
|------------|----------------------------------|
|Incorporación principal|Bosques de Active Directory con el nivel funcional del bosque establecido en Windows Server 2008 o posterior, con la siguiente configuración de bosque:<br /><br />Un único bosque de Active Directory<br />Bosques múltiples de Active Directory </br></br>**Nota**: Para todas las configuraciones de bosques múltiples, la implementación de Servicios de federación de Active Directory (AD FS) está fuera del ámbito del Beneficio del centro de FastTrack.|
|Incorporación de Azure AD Premium|Active Directory local y el entorno se han preparado para Azure AD Premium, que incluye la corrección de los problemas identificados que podrían impedir la integración con funcionalidades de Azure AD y Azure AD Premium.|
|Incorporación de Intune, solo en la nube o integrado con System Center Configuration Manager|Para la administración de dispositivos con Configuration Manager 2012 R2 o una versión posterior en conexión con Intune, los administradores de TI deberán seguir la [Lista de comprobación de administrador: Configuración de Configuration Manager para administrar dispositivos móviles con Microsoft Intune](https://technet.microsoft.com/library/jj943763.aspx).</br></br> **Nota**: El beneficio de servicio no incluye asistencia para configurar ni actualizar Configuration Manager con los requisitos mínimos necesarios para la integración de Microsoft Intune con Configuration Manager.</br></br>Para la implementación de perfiles de VPN y Wi-Fi, los administradores de TI necesitan tener infraestructuras existentes de VPN, Wi-Fi o entidades de certificación que ya estén funcionando en sus entornos de producción.</br></br> **Nota**: El servicio no incluye la asistencia para instalar o configurar infraestructuras de VPN, Wi-Fi o entidades de certificación. |
|Intune en la experiencia de administración de Azure | En diciembre de 2016, Microsoft Intune [anunció](https://blogs.technet.microsoft.com/enterprisemobility/2016/12/07/public-preview-of-intune-on-azure/) la versión preliminar pública de su nueva experiencia de administración de Intune en Azure Portal (portal.azure.com), que se conoce comúnmente como Intune en Azure.<br><br>Durante el período de versión preliminar pública, el soporte técnico de incorporación para Intune en Azure se proporcionará solo como un mejor esfuerzo. El soporte técnico de incorporación completo continuará para la consola administrativa existente (manage.microsoft.com).<br><br>FastTrack será totalmente compatible con la experiencia de Intune en Azure una vez que esté disponible de forma general en los próximos meses.


**¿Quiere obtener más información?**

[Enterprise Mobility + Security](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility)

