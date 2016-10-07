---
title: "Especificación de los requisitos de ubicación de la administración de dispositivos móviles"
description: 
keywords: 
author: YuriDio
manager: swadhwa
ms.date: 10/3/2016
ms.topic: solution
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: c8824726-082e-417a-8522-183a69328ae4
ms.reviewer: 
ms.suite: ems
ms.custom: microsoft-intune
translationtype: Human Translation
ms.sourcegitcommit: 0808c833aa2b6f36baa8d8f48ce797cc9f18aafa
ms.openlocfilehash: ab4178172344c25dba2db28a2fd8f3c8b4ad0ef5


---

# Especificación de los requisitos de ubicación de la administración de dispositivos móviles

>[!NOTE]
>Este tema forma parte de una guía de consideraciones de diseño más extensa. Si desea comenzar por el principio de la guía, consulte el [tema principal](mdm-design-considerations-guide.md). Para obtener una copia descargable de toda esta guía, visite la [Galería de TechNet](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582).

Los requisitos de ubicación son uno de los numerosos factores que debe tener en cuenta al diseñar la estrategia de administración de dispositivos móviles. La ubicación es importante desde la perspectiva de la solución de administración de dispositivos móviles, así como desde el propio dispositivo. Responda a las siguientes preguntas:

- Seguimiento de usuarios: para algunos tipos de control de dispositivos móviles, puede que tenga que implementar directivas que pueden restringir el acceso a los recursos de la compañía en función de la ubicación de un usuario.
    - ¿La empresa necesita implementar mecanismos para cubrir la barrera geográfica o la capacidad de aplicar directivas basadas en la ubicación geográfica del dispositivo? 
    - ¿La empresa necesita realizar un seguimiento de dónde se encontraba ubicado geográficamente el usuario cuando obtuvo acceso a un recurso de la compañía?
- Modelo de administración: dependiendo de la solución de administración de dispositivos móviles que implemente, la administración puede distribuirse en distintos sitios (ubicaciones) o centralizarse en una única ubicación. Un sitio de administración central es adecuado para implementaciones a gran escala y proporciona un punto central de administración y la flexibilidad necesaria para admitir dispositivos distribuidos por la infraestructura de red global. Un sitio primario es adecuado para implementaciones de tamaño más reducido, aunque tiene menos opciones para adecuarse al crecimiento futuro. Determine si el control de MDM debe ser centralizado o distribuido.
    - ¿Su compañía necesita un modelo de administración centralizado?
    - ¿La solución de administración de dispositivos necesita ubicarse en local?
        - Si no es así, ¿puede ubicarse en la nube?
        - Si no es así, ¿puede ser híbrida?
    - ¿Su compañía necesita un modelo descentralizado en el que diferentes ubicaciones deben tener autonomía sobre la administración de dispositivos?

>[!TIP] 
> Asegúrese de que toma las notas de cada respuesta y de que comprende la lógica subyacente en la respuesta. La siguiente sección tratará las opciones disponibles, así como las ventajas y desventajas de cada opción.  Con las respuestas a estas preguntas, podrá seleccionar qué solución se adapta mejor a sus necesidades empresariales.




<!--HONumber=Oct16_HO1-->


