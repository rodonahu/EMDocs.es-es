---
title: "Recopilación de los requisitos de protección de datos"
description: "En este artículo se proporciona un conjunto de requisitos comunes que debe usarse para la protección de datos en un escenario de administración de dispositivos móviles."
keywords: 
author: YuriDio
ms.author: yurid
manager: swadhwa
ms.date: 11/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 98f7bd00-4be7-478e-82ea-6046813f1556
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 5adb7f68efacdfa20d78c3cf5853fa374793140a
ms.openlocfilehash: 9cf26f4ead50e00580fc5abe1983ba88ee4c8ce9


---

# <a name="gather-your-data-protection-requirements"></a>Recopilación de los requisitos de protección de datos

>[!NOTE]
>Este tema forma parte de una guía de consideraciones de diseño más extensa. Si desea comenzar por el principio de la guía, consulte el [tema principal](mdm-design-considerations-guide.md). Para obtener una copia descargable de toda esta guía, visite la [Galería de TechNet](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582).

Para ayudar a definir los requisitos de protección de datos de su organización para dispositivos móviles, ayuda a pensar primero en los requisitos de protección de datos que su organización ya tiene en su lugar. Por ejemplo, quizás su compañía debe cumplir normas específicas, o puede que ya tenga una directiva relativa a la protección de datos.

Tome nota de estos requisitos de alto nivel primero y, a continuación, tendrá una base para formular preguntas más granulares que le ayudarán a tomar mejor las decisiones para su solución MDM.  Cuando defina estos requisitos, tenga en cuenta lo siguiente:

- Cifrado de datos en reposo: como se muestra en la ilustración 8, los datos de la compañía se almacenarán en el dispositivo móvil del usuario. Tenga en cuenta si lo siguiente es importante en su compañía:
    - ¿La solución MDM admite el cifrado en todo el disco del dispositivo móvil y las tarjetas SD?
        - Si es así, ¿para qué sistemas operativos?
    - ¿La solución MDM admite el cifrado de datos de aplicaciones?
        - Si es así, ¿para qué sistemas operativos?
        - Si es así, ¿para qué aplicaciones?
- Cifrado de datos en tránsito: independientemente de quién sea el propietario de los datos, en algún momento durante la comunicación de datos, los datos están en tránsito entre el dispositivo móvil y un servidor (o servicio web) de la compañía. Debe entender qué capacidades tiene la solución MDM para proteger los datos en tránsito. Tenga en cuenta si lo siguiente es importante en su compañía:
    - ¿La solución MDM admite el cifrado de datos en tránsito?
        - Si es así, ¿para qué sistemas operativos?
        - Si es así, ¿qué capacidades están disponibles?
    - ¿Qué opciones tiene la solución MDM para proteger los datos cuando estén en tránsito?
- Segregación de datos: también es importante saber si los datos de su compañía deben tratarse de manera distinta de los datos del usuario. "Segregación", "separación" o "aislamiento" son algunos de los términos que se pueden utilizar para describir esta capacidad. Cuando diseñe la solución MDM, tenga en cuenta lo siguiente:
    - ¿La solución MDM admite la separación datos?
        - Si es así, ¿es posible borrar los datos de su compañía a la vez que se conservan los datos del usuario del dispositivo móvil?
    - ¿La capacidad de separación de datos de MDM garantiza que solo las aplicaciones de confianza pueden obtener acceso a datos ubicados en el dispositivo móvil?
    - ¿Las soluciones MDM admiten la separación de datos según la identidad del usuario?
    - ¿La solución MDM admite la contenedorización?
        - Si es así, ¿es posible cifrar los datos ubicados en un contenedor determinado?
- Protección de dispositivos móviles: puesto que pueden usarse distintas plataformas de dispositivos móviles en su organización, debe entender qué capacidades de protección están disponibles en cada plataforma de dispositivos móviles. Cada plataforma de dispositivos móviles puede controlar y proteger dispositivos mediante distintos métodos y en diferentes niveles de granularidad. Si un conjunto de dispositivos móviles tiene un conjunto de configuración más granular que los demás, necesitará un conjunto común de opciones para proteger los dispositivos durante el uso de directivas personalizadas para mejorar la seguridad para cada plataforma de dispositivos móviles que admita su organización.

La siguiente lista incluye opciones comunes que deben ser compatibles con la solución MDM para proteger los dispositivos móviles:

- Solicitud de una contraseña para desbloquear dispositivos móviles
- Solicitud de un tipo de contraseña: número mínimo de caracteres y tipos de caracteres
- Longitud mínima de la contraseña
- Número de errores de inicio de sesión repetidos permitidos antes de que se borren los datos del dispositivo móvil
- Minutos de inactividad antes de que se apague la pantalla del dispositivo
- Recordatorio del historial de contraseñas: se impide la reutilización de contraseñas anteriores
- Caducidad de contraseña (días)
- Solicitud de cifrado en el dispositivo móvil
- Solicitud de cifrado en tarjetas de almacenamiento
- Permiso de vuelta del estado de inactividad sin una contraseña

>[!TIP]
> En Windows Phone 8.1, puede configurarse la directiva Permitir devolución inactiva sin contraseña mediante el [Protocolo de administración de dispositivos de Windows Phone 8.1 Enterprise](http://download.microsoft.com/download/C/A/0/CA091018-1A43-4063-B70B-20B9901F4D10/Windows Phone 8.1 MDM Protocol.pdf).



<!--HONumber=Nov16_HO4-->


