---
title: Privacidad de clientes
description: "En este artículo se proporciona un conjunto de consideraciones de diseño para la privacidad de clientes que debe usarse en un escenario de administración de dispositivos móviles."
keywords: 
author: YuriDio
ms.author: yurid
manager: swadhwa
ms.date: 11/28/2016
ms.topic: solution
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: c799a6c4-fe0a-4148-8e75-29e6ffdb7e6e
ms.reviewer: 
ms.suite: ems
ms.custom: microsoft-intune
translationtype: Human Translation
ms.sourcegitcommit: 5adb7f68efacdfa20d78c3cf5853fa374793140a
ms.openlocfilehash: 916404d1aaad5b4db01dff84c544e3364b7ec6ee


---

#<a name="client-privacy"></a>Privacidad de clientes

>[!NOTE]
>Este tema forma parte de una guía de consideraciones de diseño más extensa. Si desea comenzar por el principio de la guía, consulte el [tema principal](mdm-design-considerations-guide.md). Para obtener una copia descargable de toda esta guía, visite la [Galería de TechNet](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582).

Cuando su empresa implementa administración de dispositivos móviles, es importante tener en cuenta los límites entre la privacidad del usuario y la privacidad de la organización. Idealmente, su organización ya debe tener una directiva de privacidad clara que indique lo que se espera de los usuarios con respecto a la privacidad de los datos. Puesto que los dispositivos móviles podrían almacenar los datos de la empresa y estos dispositivos viajarán con el usuario, es importante que los límites estén bien definidos, y que los usuarios sepan por adelantado que su rol es mantener la privacidad de su organización.
  
Otra consideración es cómo se asegurará de que los usuarios sean conscientes de lo que pueden esperar cuando inscriban sus dispositivos en la solución MDM de su organización. Utilice el [Portal de empresa de Microsoft Intune](https://technet.microsoft.com/library/dn646957.aspx) para personalizar la declaración de privacidad de su compañía e incluir una dirección URL con la descripción de lo que recopilarán los usuarios cuando utilicen dispositivos administrados.
 
También puede publicar los términos y condiciones que los usuarios verán al usar por primera vez el portal de empresa desde sus dispositivos, tanto si el dispositivo está o no inscrito en la solución MDM. Los usuarios deben aceptar los términos para poder obtener acceso al portal de empresa. Cuando actualice los términos y condiciones, y desee que los usuarios vean y acepten los nuevos términos, puede marcar los nuevos términos y condiciones como una nueva versión y los usuarios realizarán el mismo proceso de aceptación la próxima vez que visite el portal de empresa. 

La misma funcionalidad para exigir la aceptación de los términos y condiciones también está disponible si dispone de un entorno híbrido con Configuration Manager conectado con Intune. Además, Configuration Manager puede utilizar la configuración de cumplimiento para determinar si los dispositivos cumplen con los elementos de configuración implementados utilizando líneas base de configuración. Algunas configuraciones pueden solucionarse automáticamente si están fuera del cumplimiento de las normas. 

El punto de administración envía información de compatibilidad al servidor del sitio y la almacena en la base de datos del sitio. La información se cifra cuando los dispositivos la envían al punto de administración, pero no se almacena en formato cifrado en la base de datos del sitio. La información se guarda en la base de datos hasta que la tarea de mantenimiento del sitio * Eliminar datos antiguos de administración de configuración* la elimina cada 90 días.  También tiene la capacidad de configurar el intervalo de eliminación. Esta información de compatibilidad no se envía a Microsoft.

Puesto que Intune y Office 365 son servicios basados en la nube, es posible que los usuarios también deseen saber cómo Microsoft se ocupa de la privacidad del usuario en estos servicios. Puede proporcionar punteros a la información de privacidad de estos servicios, como los siguientes:

- Centro de confianza de Office 365
- Centro de confianza de Microsoft Intune

La privacidad es importante para los usuarios y su organización, y la solución MDM que utilice debe equilibrar adecuadamente las necesidades de privacidad, así como informar a los usuarios sobre la política de privacidad y las expectativas de su organización. La siguiente tabla compara las opciones de asistencia en materia de requisitos de privacidad de diferentes soluciones MDM para ayudarle a elegir la opción de MDM que mejor se adapte a los requisitos de privacidad de su organización.

## <a name="intune-standalone"></a>Intune (independiente)

**Ventajas**

- Utiliza el portal de empresa de Intune para publicar la declaración de privacidad de su organización.

**Desventajas**

- No tiene una plantilla para una directiva de privacidad. Existe una suposición de que su organización tiene una directiva de privacidad en el lugar y el portal de empresa solo va a anunciar esta directiva que se almacena en otra ubicación

## <a name="office-365-with-mdm"></a>Office 365 con MDM

**Ventajas**

- No existen características para la publicación de declaraciones de privacidad

**Desventajas**

- No existen características para la publicación de declaraciones de privacidad

## <a name="hybrid-intune-with-configmgr"></a>Híbridas (Intune con Configuration Manager)

**Ventajas**

- Utiliza el portal de empresa de Intune para publicar la declaración de privacidad de su organización.
- Consola de administración única para dispositivos móviles registrados a partir de dispositivos locales y en la nube

**Desventajas**

- Si la organización no dispone de una infraestructura de Configuration Manager local en estos momentos, habrá que planificar, instalar y configurar esta plataforma antes de la integración.




<!--HONumber=Nov16_HO4-->


