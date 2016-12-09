---
title: "Opciones de supervisión de dispositivos"
description: "En este artículo se proporcionan instrucciones sobre las opciones existentes de supervisión de dispositivos a la hora de planear y diseñar una solución de administración de dispositivos móviles de Microsoft con Enterprise Mobility + Security."
keywords: 
author: andredm7
ms.author: andredm
manager: swadhwa
ms.date: 10/3/2016
ms.topic: solution
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 23cfc12a-fa96-4fb3-8de1-af4569e8cb71
ms.reviewer: 
ms.suite: ems
ms.custom: microsoft-intune
translationtype: Human Translation
ms.sourcegitcommit: 7d9c38008b5b47ea41ff331f1de763de5c119c5e
ms.openlocfilehash: fb4062531b8b202fb22ffcb0fbba390879be89cd


---

# <a name="device-monitoring-options"></a>Opciones de supervisión de dispositivos

>[!NOTE]
>Este tema forma parte de una guía de consideraciones de diseño más extensa. Si desea comenzar por el principio de la guía, consulte el [tema principal](mdm-design-considerations-guide.md). Para obtener una copia descargable de toda esta guía, visite la [Galería de TechNet](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582).

La supervisión y comprensión del estado y la configuración de todos los dispositivos móviles administrados por su organización le ayudan a detectar problemas e incumplimientos, y administran el inventario de dispositivos. Sin informes detallados acerca del estado de la conformidad, el hardware y el software, es imposible asegurarse de que las directivas de dispositivos estén realmente en el sitio y funcionando correctamente. La supervisión proactiva ayuda a mitigar los problemas pequeños antes de que sean más grandes y supongan un mayor coste.

[Intune](/Intune/deploy-use/monitoring-and-reports-with-microsoft-intune), [MDM para Office 365](https://technet.microsoft.com/library/faa7d8e5-645d-4d59-839c-c8d4c1869e4a(v=technet.10).aspx) y las [implementaciones híbridas](https://technet.microsoft.com/library/gg699377.aspx) de Intune y Configuration Manager incluyen supervisión e informes para ayudar a administrar dispositivos y usuarios, así como compatibilidad con los procedimientos y directivas de la organización. Utilice informes incorporados con informes personalizados para supervisar la administración de dispositivos móviles en áreas como las siguientes:

- Informes de actualizaciones de software
- Informes de inventario de software
- Informes de inventario de hardware
- Informes de licencias
- Informes de no conformidad

Dependiendo de cómo esté configurada su infraestructura, es posible que pueda crear una variedad de informes para ayudarle a supervisar su organización. Las funcionalidades de supervisión e informes basadas en Intune son la red troncal de los informes en MDM para Office 365 y las implementaciones de Intune independiente. Estos informes también pueden integrarse estrechamente con las funcionalidades de informes de Configuration Manager cuando se conecta a Intune en una implementación híbrida. Cada producto, como se muestra a continuación, tiene capacidades de informes de distintas pero complementarias. Es importante explorar los matices de las capacidades de informes de cada solución de administración de dispositivos móviles para ayudar a asegurarse de que elige una solución que tenga los informes que necesita.

![Informes y supervisión de dispositivos móviles integrados](./media/MDM_Figure_05.png)

**Informes y supervisión de dispositivos móviles integrados**

Las respuestas que dio a las preguntas en Tarea 2 pueden ayudarle a determinar las necesidades de informes y supervisión para los dispositivos móviles. La tabla siguiente muestra las ventajas y desventajas de las características de supervisión e informes en cada solución MDM.

## <a name="intune-standalone"></a>Intune (independiente)

**Ventajas**

- Panel/información general de supervisión
- Genera una alerta cuando se detectan errores en dispositivos de red administrados en directo
- Una fuente RSS de servicio de Intune puede notificarle acerca de problemas con el servicio y el mantenimiento próximo.
- Tres niveles de alertas (crítico, advertencia e informativo) con umbrales y notificaciones de alerta de correo electrónico
- Puede filtrar las alertas por tipo de dispositivo
- Puede revisar el estado de cualquier dispositivo administrado
- Proporciona informes de dispositivos que no cumplen la directiva de TI.
- Puede supervisar los detalles en las áreas siguientes:
 - System
 - Sistema operativo
 - Almacenamiento
 - Exchange ActiveSync
 - Revestimiento de hardware del sistema
 - Network (Red)
 - Servicio

**Desventajas**

- Solo alertas de correo electrónico, no alertas de voz ni basadas en texto

## <a name="mdm-for-office-365"></a>MDM para Office 365

**Ventajas**

- Panel/información general de supervisión
- Tres niveles de alertas (crítico, advertencia e informativo) con umbrales y notificaciones de alerta de correo electrónico
- Puede filtrar las alertas por tipo de dispositivo
- Puede revisar el estado de cualquier dispositivo administrado
- Proporciona informes de dispositivos que no cumplen la directiva de TI.

**Desventajas**

- Solo informes de estado de conformidad de dispositivos móviles

## <a name="hybrid-intune-with-configmgr"></a>Híbridas (Intune con Configuration Manager)

**Ventajas**

- Todas las características de informes y supervisión de Intune independiente, además de las siguientes:
 - Informes y supervisión consolidados, basados en umbrales y completos para todos los dispositivos de la organización, incluidos los dispositivos inscritos que no son de Intune y que no son móviles.
 - Capacidades de informes avanzadas de SQL Server Reporting Services (SSRS) y la amplia experiencia de creación que ofrece el Generador de informes de Reporting Services

**Desventajas**

- Requiere opciones de configuración adicionales para conectar Intune con la infraestructura de Configuration Manager local.
- Para las organizaciones que no tienen una infraestructura de Configuration Manager en estos momentos, habrá que planificarla, instalarla y configurarla antes de su integración con Intune.

Explore los detalles acerca de las opciones de supervisión de dispositivos móviles revisando lo siguiente:

- Intune: **[supervisión de dispositivos móviles](https://technet.microsoft.com/library/jj733634.aspx)** y [administración de informes](/Intune/deploy-use/monitoring-and-reports-with-microsoft-intune)
- Configuration Manager: [supervisión de dispositivos móviles](https://technet.microsoft.com/library/gg682128.aspx) y [administración de informes](https://technet.microsoft.com/library/gg699377.aspx)
- MDM para Office 365: [información general y tareas de administración de dispositivos](https://technet.microsoft.com/en-us/library/ms.o365.cc.devicepolicy.aspx)



<!--HONumber=Nov16_HO4-->


