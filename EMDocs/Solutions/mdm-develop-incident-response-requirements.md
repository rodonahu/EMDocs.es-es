---
title: Desarrollo de los requisitos de respuesta a incidentes
description: 
keywords: 
author: YuriDio
manager: swadhwa
ms.date: 8/1/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6f9fd9b3-492b-48e1-871c-e5abefe1293a
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e51462f1b238f7e3b518a7a9c8042ff3ad78a5a5
ms.openlocfilehash: 5013c939b6060d8098e5015834682e60fe9be2b3


---

# Desarrollo de los requisitos de respuesta a incidentes

>[!NOTE]
>Este tema forma parte de una guía de consideraciones de diseño más extensa. Si desea comenzar por el principio de la guía, consulte el [tema principal](mdm-design-considerations-guide.md). Para obtener una copia descargable de toda esta guía, visite la [Galería de TechNet](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582).

Aunque muchas organizaciones ya han implantado un plan de respuesta a incidentes (IR), debe asegurarse de que el plan incluya dispositivos móviles y comprobar los pasos que hay que realizar en caso de que se notifique un incidente en esos dispositivos. Si su compañía está adoptando justo ahora una solución de movilidad, es probable que el plan de IR actual no abarque os dispositivos móviles. Si su organización no tiene un plan de IR, es importante trabajar muy de cerca con su equipo de seguridad para conocer los requisitos a medida que se desarrollan; de este modo, sabrá cuáles son las preguntas adecuadas que plantear y elegir la mejor solución MDM en función de sus necesidades. 
 
>[!TIP] 
> Consulte [Respuesta a incidentes de seguridad de TI](https://technet.microsoft.com/library/cc700825.aspx) para comprender mejor los requisitos mínimos de un plan de IR.

Cuando diseñe la solución MDM, asegúrese de que formula las preguntas siguientes para asegurarse de que se pueden administrar dispositivos móviles si se produce un incidente.

- ¿Su organización tiene un plan de respuesta a incidentes existente?
    - Si es así, ¿incluye los procesos y los procedimientos para controlar los dispositivos móviles que se han puesto en peligro?
- ¿La directiva de respuesta a incidentes cubre los escenarios en los que un usuario final informa de que ha perdido su dispositivo móvil?
    - ¿Está permitido borrar todo el dispositivo para evitar la pérdida de datos? 
        - Si es así, ¿su compañía tiene la directiva de copia de seguridad en su lugar para los datos que residen en dispositivos móviles?
- ¿Su organización tiene diferentes procedimientos para dispositivos propiedad de la compañía y personales en caso de que se pierdan?
    - Si es así, ¿cuáles son los procedimientos?
    - ¿Esos procedimientos afectarán a la selección de la solución MDM?
- Si un usuario pierde su dispositivo móvil personal, pero no autoriza a su compañía a borrar todo el dispositivo, ¿la solución MDM permite el borrado selectivo del dispositivo?
- Cuando un dispositivo móvil está en peligro y necesita impedir que ese dispositivo distribuya aplicaciones malintencionadas en la red corporativa, ¿la solución MDM le permite aplicar directivas que puedan contener rápidamente al dispositivo en peligro?
- ¿La solución MDM le permite planificar ataques potenciales para emprender acciones proactivas para solucionar los problemas?
- ¿La solución MDM le permite identificar cuándo un archivo está infectado con malware mediante una consola de administración?




<!--HONumber=Aug16_HO1-->


