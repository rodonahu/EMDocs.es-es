---
title: Acceso condicional en Exchange con Intune y Configuration Manager
description: "Use una coexistencia de Exchange local y Exchange Online junto con Configuration Manager e Intune para administrar el acceso al correo electrónico y proteger los datos de correo electrónico en dispositivos móviles."
keywords: 
author: craigcaseyMSFT
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 5ccd033f-bc31-4fae-b6bf-9e1c2722627f
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 026e6701b635a3b05753404fd064fee5bf10147e
ms.openlocfilehash: 8d1e7f6bf8d798dee570d970c30e98974f9bd5be


---

# Implementación de Exchange Online y Exchange Server local con Microsoft Intune y Configuration Manager
Ahora que ha leído la [Guía de arquitectura para proteger los documentos y correos electrónicos de la empresa](architecture-guidance-for-protecting-company-email-and-documents.md), ya puede continuar con la implementación de una solución.

Un entorno en el que tanto Exchange local como Exchange Online se usen para administrar los perfiles de correo electrónico ofrece a las empresas la capacidad de ampliar la experiencia con múltiples características y el control administrativo de los que ya disponen con la organización local existente de Microsoft Exchange en la nube. Este tipo "híbrido" de implementación ofrece la apariencia y el funcionamiento sin problemas de una sola organización de Exchange entre una organización de Exchange Server 2013 local y Exchange Online en Microsoft Office 365. Además, este tipo de implementación puede servir como un paso intermedio para pasar completamente a una organización de Exchange Online.

Si ya usa Configuration Manager junto con una coexistencia de Exchange local y Exchange Online, puede incorporar Intune para administrar el acceso al correo electrónico y proteger los datos de correo electrónico en dispositivos móviles. Para implementar esta solución, siga las instrucciones de arriba para implementar cada solución por separado.

## Requisitos previos
Para configurar un tipo de coexistencia del entorno que implemente Exchange local y Exchange Online, la organización de Exchange existente debe cumplir determinados requisitos. Si no se cumplen estos requisitos, no se podrán completar los pasos necesarios para configurar una implementación híbrida entre la organización de Exchange local y la organización de Exchange Online de Microsoft Office 365.

Vea [Requisitos previos de implementación híbrida](https://technet.microsoft.com/en-us/library/hh534377.aspx) para revisar los requisitos para crear y configurar este tipo de entorno.

## Pasos de implementación
Para implementar una solución de coexistencia, siga los pasos anteriores con el fin de implementar las soluciones de [Exchange Server local](conditional-access-intune-configmgr-exchange.md) y [Exchange Online](conditional-access-intune-configmgr-exchange-online.md).

## Próximos pasos
Cuando haya implementado una solución para proteger el correo electrónico corporativo y los datos de correo electrónico de los dispositivos móviles, puede obtener más información sobre la [experiencia de acceso condicional del usuario final](end-user-experience-conditional-access.md). Esto le ayudará a prepararse para problemas que podrían surgir al inscribir sus dispositivos específicos.



<!--HONumber=Jul16_HO4-->


