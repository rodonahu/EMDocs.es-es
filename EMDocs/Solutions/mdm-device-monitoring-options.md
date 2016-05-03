---
# required metadata

title: Opciones de supervisión de dispositivos
description:
keywords:
author: robmazz
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: 23cfc12a-fa96-4fb3-8de1-af4569e8cb71

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: 
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Opciones de supervisión de dispositivos

>[!NOTE]
>Este tema forma parte de una guía de consideraciones de diseño más extensa. Si desea comenzar por el principio de la guía, consulte el [tema principal](mdm-design-considerations-guide.md). Para obtener una copia descargable de toda esta guía, visite la [Galería de TechNet](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582).

La supervisión y comprensión del estado y la configuración de todos los dispositivos móviles administrados por su organización le ayudan a detectar problemas e incumplimientos, y administran el inventario de dispositivos. Sin informes detallados acerca del estado de la conformidad, el hardware y el software, es imposible asegurarse de que las directivas de dispositivos estén realmente en el sitio y funcionando correctamente. La supervisión proactiva ayuda a mitigar los problemas pequeños antes de que sean más grandes y supongan un mayor coste.

[Intune](/Intune/deployuse/monitoring-and-reports-with-microsoft-intune), [MDM para Office 365](https://technet.microsoft.com/library/faa7d8e5-645d-4d59-839c-c8d4c1869e4a(v=technet.10).aspx) y una [implementación híbrida](https://technet.microsoft.com/library/gg699377.aspx) de Intune y Configuration Manager incluyen supervisión e informes para ayudar a administrar dispositivos y usuarios, así como al cumplimiento con los procedimientos y directivas de su organización. Utilice informes incorporados con informes personalizados para supervisar la administración de dispositivos móviles en áreas como las siguientes:

- Informes de actualizaciones de software
- Informes de inventario de software
- Informes de inventario de hardware
- Informes de licencias
- Informes de no conformidad

Dependiendo de cómo esté configurada su infraestructura, es posible que pueda crear una variedad de informes para ayudarle a supervisar su organización. Las funcionalidades de supervisión e informes basadas en Intune son la red troncal de los informes en MDM para Office 365 y las implementaciones de Intune independiente. Estos informes también pueden integrarse estrechamente con las funcionalidades de informes de Configuration Manager cuando se conecta a Intune en una implementación híbrida. Cada producto, como se muestra a continuación, tiene capacidades de informes de distintas pero complementarias. Es importante explorar los matices de las capacidades de informes de cada solución de administración de dispositivos móviles para ayudar a asegurarse de que elige una solución que tenga los informes que necesita.

![Informes y supervisión de dispositivos móviles integrados](./media/MDM_Figure_05.png)

**Informes y supervisión de dispositivos móviles integrados**

Las respuestas que dio a las preguntas en Tarea 2 pueden ayudarle a determinar las necesidades de informes y supervisión para los dispositivos móviles. La tabla siguiente muestra las ventajas y desventajas de las características de supervisión e informes en cada solución MDM.

## Intune (independiente)

**Ventajas**

- Panel/información general de supervisión
- Genera una alerta cuando se detectan errores en dispositivos de red administrados en directo
- Una fuente RSS de servicio de Intune puede notificarle acerca de problemas con el servicio y el mantenimiento próximo.
- Tres niveles de alertas (crítico, advertencia e informativo) con umbrales y notificaciones de alerta de correo electrónico
- Puede filtrar las alertas por tipo de dispositivo
- Puede revisar el estado de cualquier dispositivo administrado
- Proporciona informes de dispositivos que no cumplen la directiva de TI.
- Puede supervisar los detalles en las áreas siguientes:
 - System (Sistema)
 - Sistema operativo
 - Almacenamiento
 - Exchange ActiveSync
 - Revestimiento de hardware del sistema
 - Network (Red)
 - Servicio

**Desventajas**

- Solo alertas de correo electrónico, no alertas de voz ni basadas en texto

## MDM para Office 365

**Ventajas**

- Panel/información general de supervisión
- Tres niveles de alertas (crítico, advertencia e informativo) con umbrales y notificaciones de alerta de correo electrónico
- Puede filtrar las alertas por tipo de dispositivo
- Puede revisar el estado de cualquier dispositivo administrado
- Proporciona informes de dispositivos que no cumplen la directiva de TI.

**Desventajas**

- Solo informes de estado de conformidad de dispositivos móviles

## Híbridas (Intune con Configuration Manager)

**Ventajas**

- Todas las características de informes y supervisión de Intune independiente, además de las siguientes:
 - Informes y supervisión consolidados, basados en umbrales y completos para todos los dispositivos de la organización, incluidos los dispositivos inscritos que no son de Intune y que no son móviles.
 - Capacidades de informes avanzadas de SQL Server Reporting Services (SSRS) y la amplia experiencia de creación que ofrece el Generador de informes de Reporting Services

**Desventajas**

- Requiere opciones de configuración adicionales para conectar Intune con la infraestructura de Configuration Manager local.
- Para las organizaciones que no tienen una infraestructura de Configuration Manager en estos momentos, habrá que planificarla, instalarla y configurarla antes de su integración con Intune.

Explore los detalles acerca de las opciones de supervisión de dispositivos móviles revisando lo siguiente:

- Intune: **[supervisión de dispositivos móviles](https://technet.microsoft.com/library/jj733634.aspx)** y [administración de informes](/Intune/deployuse/monitoring-and-reports-with-microsoft-intune)
- Configuration Manager: [supervisión de dispositivos móviles](https://technet.microsoft.com/library/gg682128.aspx) y [administración de informes](https://technet.microsoft.com/library/gg699377.aspx)
- MDM para Office 365: [información general y tareas de administración de dispositivos](https://technet.microsoft.com/en-us/library/ms.o365.cc.devicepolicy.aspx)

<!--HONumber=Apr16_HO2-->


