---
title: "Especificación de los requisitos de privacidad"
description: 
keywords: 
author: YuriDio
manager: swadhwa
ms.date: 8/1/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d02d3ec2-706a-4e03-977c-b7c06cbd4ebd
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e51462f1b238f7e3b518a7a9c8042ff3ad78a5a5
ms.openlocfilehash: b5961c63ed885f762efe63998dfce663e60442b4


---

# Especificación de los requisitos de privacidad

>[!NOTE]
>Este tema forma parte de una guía de consideraciones de diseño más extensa. Si desea comenzar por el principio de la guía, consulte el [tema principal](mdm-design-considerations-guide.md). Para obtener una copia descargable de toda esta guía, visite la [Galería de TechNet](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582).


En el paso anterior, definió las tareas de administración de dispositivos, incluidas la administración de la distribución de contenido y la administración de dispositivos. En esta tarea, el objetivo es definir los requisitos de privacidad para el contenido de la compañía que residirá en el dispositivo móvil. 

>[!TIP] 
> Lea la solución Administración optimizada para dispositivos móviles y equipos en un entorno híbrido para obtener más información sobre la distribución de contenido para dispositivos móviles.

Los requisitos de privacidad y cumplimiento de la organización variarán según el sector, las normas aplicables y el tipo de negocio. Por ejemplo, puede que desee que la solución MDM le permita realizar inventarios de hardware básicos, inventarios de software, recopilaciones de archivos y la distribución de software en dispositivos móviles. La distribución de software y el inventario de hardware se admiten normalmente de forma predeterminada. 

Tenga en cuenta que las preocupaciones sobre privacidad que se aplican a los equipos cliente para la distribución de software e inventario también se aplican a los dispositivos móviles. 

Antes de elegir una solución de administración de dispositivos móviles, tenga en cuenta los requisitos de privacidad únicos. Por ejemplo, considere lo siguiente:

- Privacidad de cliente: permitir a los usuarios usar sus dispositivos móviles para conectarse y utilizar recursos de la compañía también implica que deben comprender la directiva de privacidad de la organización y cómo todo esto afectará a su privacidad.
    - ¿Tiene que proporcionar a los usuarios con la directiva de privacidad de su compañía y lo que debe incluir?
        - En caso afirmativo, ¿la solución MDM incluye la funcionalidad de proporcionar fácilmente una directiva de privacidad a los usuarios?
    - ¿La solución MDM almacena información del dispositivo móvil o los datos de los usuarios en la nube?
        - En caso afirmativo, ¿cómo se mantiene privacidad del usuario en la nube? 
- ¿Quién tiene acceso a los datos?
- ¿Cómo sus datos siguen siendo privados?
- Clasificación de datos y cumplimiento: es importante definir qué constituye los datos de la compañía y cómo se protegerá. Disponer de directivas y mecanismos en el lugar para clasificar datos debe formar parte del plan de garantía de la privacidad cuando se administran dispositivos móviles.
    - ¿Puede identificar o clasificar datos o documentos de la compañía que van a estar en el dispositivo móvil?
        - Si es así, ¿qué permisos o derechos de documentos o datos son compatibles?
    - ¿La clasificación viajará con los datos o los documentos, independientemente del dispositivo móvil que el usuario esté utilizando?
    - ¿Qué tipos de datos o de documentos se pueden clasificar y cuáles no?
    - ¿Los requisitos de cumplimiento afectarán a cómo elegir la plataforma de administración de dispositivos móviles?
        - En caso afirmativo, asegúrese de que enumere estos requisitos antes de seleccionar la plataforma de administración de dispositivos móviles.

Lea la [Declaración de privacidad de Microsoft Online Services](http://www.microsoft.com/server-cloud/products/intune-trust-center/privacy.aspx) para entender mejor cómo los servicios en la nube de Microsoft, incluido Intune, mantendrán la privacidad del usuario.



<!--HONumber=Aug16_HO1-->


