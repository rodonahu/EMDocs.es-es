---
title: "Planeación para mejorar la protección de dispositivos móviles"
description: "En este artículo se proporcionan consideraciones de diseño para proteger dispositivos móviles en un escenario de administración de dispositivos móviles."
keywords: 
author: YuriDio
ms.author: yurid
manager: swadhwa
ms.date: 11/28/2016
ms.topic: solution
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: a4504456-a241-4380-ab92-3bc14c91347c
ms.reviewer: 
ms.suite: ems
ms.custom: microsoft-intune
translationtype: Human Translation
ms.sourcegitcommit: 5adb7f68efacdfa20d78c3cf5853fa374793140a
ms.openlocfilehash: bbef17c4d072706a5704c871eee490fba5c9052c


---

# <a name="plan-for-enhancing-mobile-devices-protection"></a>Planeación para mejorar la protección de dispositivos móviles

>[!NOTE]
>Este tema forma parte de una guía de consideraciones de diseño más extensa. Si desea comenzar por el principio de la guía, consulte el [tema principal](mdm-design-considerations-guide.md). Para obtener una copia descargable de toda esta guía, visite la [Galería de TechNet](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582).

Mientras que los usuarios remotos y locales pueden ser más productivos mediante la obtención de acceso a recursos de la compañía en sus dispositivos móviles, permitirles que lo hagan también aumenta las amenazas de seguridad que tendrá que mitigar para ayudar a proteger los datos de su compañía y mantener la privacidad de los usuarios. Su compañía puede tener requisitos específicos acerca de cómo equilibrar estas necesidades. Las reglas de cumplimiento pueden variar según el sector en el que opere su compañía, por ejemplo, pueden dar lugar a decisiones de diseño diferentes.
 
Sin embargo, hay algunos aspectos generales de seguridad de la administración de dispositivos móviles que explorar y cumplir, independientemente del sector. Se muestran en la ilustración siguiente.

![Funcionalidades de seguridad para la plataforma MDM](./media/MDM_Figure_08.png)

## <a name="security-capabilities-in-a-mdm-solution"></a>Funcionalidades de seguridad en una solución MDM

Este diagrama muestra las principales capacidades de seguridad necesarias en cualquier solución MDM. Las áreas clave a tener en cuenta son los siguientes:

1. Consideraciones para la protección de datos en el nivel de dispositivos móviles:
    - Cifrado de datos
    - Clasificación de datos
    - Privacidad de clientes
    - Contenedorización
    - Cumplimiento de directivas
    - Directivas de cumplimiento
    - Protección
2. Consideraciones para la protección de datos mientras están en tránsito:
    - Cifrado de datos
    - Autenticación
    - Autorización
3. Consideraciones para la protección de datos mientras están en reposo en la organización local:
    - Cifrado de datos
    - Autenticación
    - Autorización
4. Consideraciones para la protección de datos mientras están en reposo en la nube:
    - Cifrado de datos
    - Autenticación
    - Autorización

Las tareas que se describen en las siguientes secciones pueden ayudarle a entender cómo las necesidades de seguridad específicas influirán en su decisión acerca de la mejor solución MDM para sus requisitos empresariales.

## <a name="about-this-step"></a>Acerca de este paso

Esta sección de la guía contiene 12 pasos. El tiempo total para leer las secciones es de aproximadamente 36 minutos, aunque también puede avanzar a una sección concreta.

- [Recopilación de los requisitos de protección de datos](mdm-gather-data-protection-requirements.md)
- [Especificación de los requisitos de privacidad](mdm-specify-privacy-requirements.md)
- [Especificación de los requisitos de acceso](mdm-specify-your-access-requirements.md)
- [Desarrollo de los requisitos de respuesta a incidentes](mdm-develop-incident-response-requirements.md)
- [Planeación para cifrar datos](mdm-data-encryption.md)
- [Planeación para segregar datos](mdm-data-segregation.md)
- [Protección de dispositivos móviles](mdm-hardening-mobile-devices.md)
- [Privacidad de clientes](mdm-client-privacy.md)
- [Clasificación de datos](mdm-data-classification.md)
- [Autenticación y autorización](mdm-authentication-authorization.md)
- [Control de acceso a los recursos](mdm-access-control-resources.md)





<!--HONumber=Nov16_HO4-->


