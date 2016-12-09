---
title: "Recopilación de requisitos de supervisión"
description: "En este artículo se proporciona información sobre la identificación de las opciones de supervisión de la administración de dispositivos móviles a la hora de planear y diseñar una solución de administración de dispositivos móviles de Microsoft con Enterprise Mobility + Security."
keywords: 
author: andredm7
ms.author: andredm
manager: swadhwa
ms.date: 10/3/2016
ms.topic: solution
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: ac136523-8089-409b-b74d-2d4c0ce399d4
ms.reviewer: 
ms.suite: ems
ms.custom: microsoft-intune
translationtype: Human Translation
ms.sourcegitcommit: 7d9c38008b5b47ea41ff331f1de763de5c119c5e
ms.openlocfilehash: 2a03416cf8255a29c0394746b3d5285057163d15


---

# <a name="gather-monitoring-requirements"></a>Recopilación de requisitos de supervisión

>[!NOTE]
>Este tema forma parte de una guía de consideraciones de diseño más extensa. Si desea comenzar por el principio de la guía, consulte el [tema principal](mdm-design-considerations-guide.md). Para obtener una copia descargable de toda esta guía, visite la [Galería de TechNet](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582).

Supervisar y capturar la información de estado y eventos para dispositivos móviles es fundamental para garantizar que los usuarios y dispositivos cumplen su estrategia de seguridad y directivas corporativas. Esto es especialmente importante para las organizaciones que deben cumplir con los requisitos de las disposiciones legales gubernamentales y directrices de cumplimiento del sector.

Los informes también pueden proporcionar información valiosa acerca de las licencias de software, hardware y software en su organización para ayudar en la administración de inventario. 

Tenga en cuenta la importancia de la privacidad de los usuarios cuando se están definiendo las directrices de informes y supervisión, especialmente cuando los usuarios pueden inscribir dispositivos personales en la solución de administración de dispositivos móviles de la organización. Su organización no debe ser capaz de capturar, supervisar, informar o compartir cualquier actividad personal o información.

En general, las soluciones de administración de dispositivos móviles dividen la supervisión en dos áreas generales:

- **Registro:** captura y almacenamiento de dispositivos móviles y de la información y del estado de la aplicación de dispositivos móviles.
- **Informes:** visualización de informes o notificaciones, incluidos los informes estándar y personalizables que pueden crearse a petición, y resumen automático e informes de estado del panel.

## <a name="monitoring-planning-questions"></a>Preguntas de planeación de supervisión

Responda a las siguientes preguntas de planificación sobre la supervisión de dispositivos:

- ¿Qué tipos de informes periódicos para dispositivos móviles necesitará?
 - ¿Inventario de dispositivos?
 - ¿Uso de dispositivos?
 - ¿Acceso de dispositivos?
 - ¿Aplicaciones de dispositivos?
- ¿Será necesario compartir informes?
 - ¿Entre los roles de TI?
 - ¿Fuera de la organización de TI?
 - ¿Acceso de forma remota (fuera de la red corporativa)?
- ¿Qué tipos de problemas con dispositivos necesitará identificar?
- ¿Sobre qué tipos de eventos capturados en la supervisión se tendrá que actuar? ¿En qué período de tiempo?
- ¿Se necesitarán informes personalizados y a petición?
- ¿Cuando se cancela la inscripción de un dispositivo, deben capturarse los eventos de informes e inventario específicos?
- Una vez cancelada la inscripción de un dispositivo, ¿los eventos de informes e inventario heredados deben archivarse/mantenerse?
 
>[!TIP]
>Asegúrese de que toma las notas de cada respuesta y de que comprende la lógica subyacente en la respuesta. Más adelante, las tareas tratarán las opciones disponibles, y las ventajas y desventajas de cada opción.  Responder a estas preguntas le ayudará a seleccionar la opción que mejor se adapte a sus necesidades empresariales.



<!--HONumber=Nov16_HO4-->


