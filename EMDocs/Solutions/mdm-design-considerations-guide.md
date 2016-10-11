---
title: "Guía de las consideraciones de diseño de administración de dispositivos móviles"
description: 
keywords: 
author: andredm7
manager: swadhwa
ms.date: 10/3/2016
ms.topic: solution
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 7083b6b8-27a3-427b-b505-25d007d63cdd
ms.reviewer: 
ms.suite: ems
ms.custom: microsoft-intune
translationtype: Human Translation
ms.sourcegitcommit: 0808c833aa2b6f36baa8d8f48ce797cc9f18aafa
ms.openlocfilehash: 8f279f528cab2a747f12d5e372ec7e9442bd87e4


---

# Guía de las consideraciones de diseño de administración de dispositivos móviles

Con todos los diseños y las opciones de configuración que existen para las soluciones de administración de dispositivos móviles (MDM), a veces es difícil decidir qué solución va a satisfacer mejor las necesidades de una organización. Con esta guía sobre el diseño, podrá comprender mejor los distintos requisitos de diseño de MDM y dispondrá de una serie de pasos y tareas que puede seguir para diseñar la solución MDM más adecuada para las necesidades empresariales y tecnológicas de su organización. 

## Introducción

A lo largo de los pasos y las tareas, esta guía presentará las posibles características y tecnologías relevantes disponibles para que las organizaciones cubran sus necesidades funcionales y de calidad de servicios (por ejemplo, disponibilidad, escalabilidad, rendimiento, capacidad de administración y seguridad).

Específicamente, el objetivo de esta guía es ayudarle a responder las siguientes preguntas:

- ¿Qué preguntas tengo que contestar para impulsar la adopción de una solución de administración de dispositivos móviles se ajuste mejor a las necesidades de mi empresa?
- ¿Cuál es la secuencia de actividades que debo completar para diseñar una solución de administración de dispositivos móviles para mi organización?
- ¿Qué opciones de configuración y tecnología de administración de movilidad de Microsoft están disponibles para ayudarme a satisfacer mis necesidades, y cuáles son las ventajas entre esas?

**¿A quién está destinada esta guía?** Los profesionales y arquitectos de la tecnología de la información responsables del diseño de una solución de administración de dispositivos móviles para organizaciones medianas o grandes.

**¿Cómo puede ayudarle esta guía?** Puede utilizar esta guía para saber cómo diseñar una solución de administración de dispositivos móviles que pueda administrar dispositivos propiedad de la compañía, así como dispositivos propiedad del usuario en distintos factores de forma.

![Ejemplo de una solución MDM de Intune y System Center Configuration Manager híbrida](./media/MDM_Figure_01.png)
**Ejemplo de una solución MDM de Intune y System Center Configuration Manager híbrida**

La ilustración siguiente es un ejemplo de una solución de administración híbrida, donde se aprovechan los servicios en la nube para integrarse con funcionalidades locales con el fin de administrar todos los tipos de dispositivos, independientemente de su ubicación. Aunque esto es un escenario muy común, el diseño de MDM de las organizaciones puede ser distinto del ejemplo debido a los requisitos de administración exclusivos de cada organización.
 
Esta guía detalla una serie de pasos y tareas que debe seguir para que le resulte más fácil diseñar una solución MDM personalizada que se adapte a los requisitos únicos de su organización. A lo largo de los pasos y las tareas siguientes, esta guía tratará las opciones de características y las tecnologías relevantes que se encuentran disponibles para cumplir los requisitos de nivel de calidad de servicio y funcionalidad de MDM. 

A pesar de que esta guía sirve para diseñar una solución MDM, en ella no se abordan las opciones de operaciones o implementación específicas para las soluciones de administración, ni tampoco cómo migrar desde una solución MDM de terceros existente. Encontrará pasos detallados de implementación y configuración de [Microsoft Intune](/Intune/), [Administración de dispositivos móviles para Office 365](https://technet.microsoft.com/library/ms.o365.cc.devicepolicy.aspx) y [Microsoft System Center Configuration Manager](https://technet.microsoft.com/library/cc507089.aspx) en las bibliotecas de TechNet y docs.microsoft.com. Use para ello los vínculos disponibles en la sección **Pasos siguientes y recursos adicionales** al final de esta guía.

[Aquí](https://blogs.technet.microsoft.com/intunesupport/2016/02/10/new-guide-on-how-to-migrate-from-other-mdm-technologies-to-microsoft-intune/) encontrará también instrucciones sobre cómo migrar desde otras soluciones MDM a Microsoft Intune.

**Suposiciones:** tiene cierta experiencia con Microsoft Intune, System Center 2012 R2 Configuration Manager (ConfigMgr), Windows Server 2012 R2 y dispositivos móviles que ejecutan Windows Phone, iOS y Android. Es posible que incluso haya implementado una de estas soluciones en una prueba de MDM inicial o limitado el entorno de producción. En esta guía, se asume que busca la manera en la que estas soluciones pueden satisfacer mejor las necesidades empresariales por su cuenta o con una solución integrada.

## Consideraciones de diseño de MDM
Está guía incluye un conjunto de pasos y tareas que puede seguir para diseñar la solución que cumpla mejor sus requisitos. Los pasos se presentan en una secuencia ordenada. Sin embargo, las consideraciones de diseño que aprenderá en los pasos posteriores pueden solicitarle que cambie las decisiones que tomó en los pasos anteriores, ya que su diseño ha evolucionado o debido a elecciones de diseño que entran en conflicto. Le avisaremos de los posibles conflictos de diseño a lo largo de esta guía.

Desarrollará el diseño de administración de dispositivos móviles que mejor se adapte a sus necesidades después de recorrer en iteración los pasos siguientes tantas veces como sea necesario para incorporar todas las consideraciones incluidas en esta guía: 

- [Paso 1: identificación de los requisitos de administración de dispositivos móviles](mdm-step-1-identify-your-mobile-device-management-requirements.md)
- [Paso 2: planeación para administrar dispositivos móviles](mdm-step-2-plan-for-mobile-device-management.md)
- [Paso 3: planeación para proteger dispositivos móviles](mdm-step-3-plan-enhancing-mobile-devices-protection.md)
- [Paso 4: planeación de administración de dispositivos móviles de software como servicio](mdm-step-4-plan-for-software-as-a-service-mobile-device-management.md)
- [Pasos siguientes y recursos adicionales](mdm-next-steps-and-additional-resources.md)
        
## ¿Busca una versión descargable?
Obtenga una copia descargable de toda esta guía en la [Galería de TechNet](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582).



<!--HONumber=Oct16_HO1-->


