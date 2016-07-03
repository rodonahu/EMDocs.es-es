---
title: "Desarrollo de una estrategia de administración de dispositivos móviles de SaaS"
description: 
keywords: 
author: andredm7
manager: swadhwa
ms.date: 05/31/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: b3cefcc5-b045-48f9-91f5-6d282a4428f3
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 73c37109735567642ff1dc11f9729e3ab3affd3b
ms.openlocfilehash: 91d1498db006b387ff524b2b26c715c3a109dd8a


---

# Desarrollo de una estrategia de administración de dispositivos móviles de SaaS

>[!NOTE]
>Este tema forma parte de una guía de consideraciones de diseño más extensa. Si desea comenzar por el principio de la guía, consulte el [tema principal](mdm-design-considerations-guide.md). Para obtener una copia descargable de toda esta guía, visite la [Galería de TechNet](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582).

## Identificación de los requisitos de la solución de SaaS

Según como haya respondido a las preguntas de Tarea 1, podrá determinar qué necesita la solución de SaaS para ser compatible con la solución de administración de dispositivos. La tabla 20 siguiente le ayudará a comprender las ventajas y desventajas de cada escenario de la solución de SaaS:

## Intune (independiente)

**Ventajas**

- Se ofrece como arquitectura en la nube pública y multiinquilino
- Se escala para admitir hasta 50.000 dispositivos móviles
- No requiere ninguna inversión adicional en el software, hardware o infraestructura locales
- Las actualizaciones y mejoras de las características se realizan a diario. Las mejoras de las funcionalidades y características más importantes se realizan mensualmente.
- Los servicios se pueden asignar a los centros de datos en ubicaciones geográficas específicas
- Las conmutaciones por error de los centros de datos pueden restringirse a ubicaciones geográficas específicas
- Certificación y conformidad con la mayoría de las normas gubernamentales y del sector, el contrato de nivel de servicio (SLA) se encuentra respaldado financieramente. Si el servicio o las características no están disponibles, se condonan los gastos mensuales.

**Desventajas**

- Las instancias en la nube privada no son compatibles
- Si necesita ofrecer más de 50 000 dispositivos móviles, tendrá que conectar Intune a Configuration Manager para administrar los dispositivos adicionales.

## MDM para Office 365

**Ventajas**

- Ofrece una integración estrecha con inquilinos comerciales de Office 365, lo que proporciona una consola de administración única para dispositivos móviles y servicios de inquilinos de Office 365 (SharePoint Online y Skype Empresarial Online).
- Se ofrece en tipos de plataforma privada (dedicada) o multiinquilino (pública) de Office 365.
- Sin costes de licencia de dispositivos o usuarios adicionales, incluido de forma predeterminada en los planes (Business, Enterprise, Education y Government) comerciales de Office 365.

**Desventajas**

- No admite la administración de los sistemas operativos que no son móviles.
- Interfaz de administración adicional para el aprovisionamiento de dispositivos móviles (solo) si se usa una plataforma de administración local para dispositivos que no son móviles.

## Híbridas (Intune con Configuration Manager)

**Ventajas**

- Todas las ventajas de Intune independiente, además de las siguientes: integración nativa entre Intune (servicio de administración de dispositivos basada en la nube) con Configuration Manager (plataforma de administración de dispositivos locales).
- Admite opciones de aprovisionamiento de dispositivos avanzadas para dispositivos móviles a través de la conectividad de Intune.
- Nuevas funcionalidades y características de servicio de Intune extendidas a la infraestructura de Configuration Manager local a través de las extensiones de la plataforma, ya sea de forma automática o personalizada.

**Desventajas**

- Requiere requisitos de configuración adicionales para conectar Intune con la infraestructura de Configuration Manager local.
- Para las organizaciones que no tienen una infraestructura de Configuration Manager en estos momentos, habrá que planificarla, instalarla y configurarla antes de su integración con Intune.

Asegúrese de leer el artículo **[Ayude a proteger sus datos mediante la eliminación remota, el bloqueo remoto o el restablecimiento de código de acceso mediante Microsoft Intune](https://technet.microsoft.com/library/jj676679.aspx)** para comprender qué datos se quitan y el efecto en los datos que permanece en el dispositivo después de un borrado selectivo por plataforma. Si cuenta con un entorno híbrido, consulte el artículo [Borrado remoto de dispositivos móviles mediante Configuration Manager](https://technet.microsoft.com/library/dn956981.aspx) para comprender cómo Configuration Manager puede usarse para llevar a cabo esta tarea.

Para obtener más información sobre los requisitos y la funcionalidad de la solución de SaaS, asegúrese de revisar el tema de **[descripción del servicio de Microsoft Intune](https://technet.microsoft.com/library/dn600286.aspx)** para comprender las diferencias en la compatibilidad de SaaS en [MDM para Office 365](https://technet.microsoft.com/library/faa7d8e5-645d-4d59-839c-c8d4c1869e4a(v=technet.10).aspx) y en una infraestructura [híbrida](https://technet.microsoft.com/library/jj884158.aspx) de Intune y Configuration Manager.


<!--HONumber=Jul16_HO1-->


