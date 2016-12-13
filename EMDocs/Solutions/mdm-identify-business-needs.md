---
title: "Identificación de las necesidades empresariales"
description: "En este artículo se proporcionan instrucciones sobre la identificación de las necesidades empresariales que son necesarias para justificar la adopción de la administración de dispositivos móviles."
keywords: 
author: YuriDio
ms.author: yurid
manager: swadhwa
ms.date: 11/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 85783069-14fb-4ead-a159-657d694eb1a7
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 5adb7f68efacdfa20d78c3cf5853fa374793140a
ms.openlocfilehash: 35c9101de6df041b906660743654a8b137d4a542


---

# <a name="identify-your-business-needs"></a>Identificación de las necesidades empresariales

>[!NOTE]
>Este tema forma parte de una guía de consideraciones de diseño más extensa. Si desea comenzar por el principio de la guía, consulte el [tema principal](mdm-design-considerations-guide.md). Para obtener una copia descargable de toda esta guía, visite la [Galería de TechNet](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582).

Cada empresa tendrá requisitos diferentes. Aunque estas empresas forman parte del mismo sector, los requisitos empresariales reales pueden variar. Puede seguir aprovechando las prácticas recomendadas del sector, pero en última instancia, serán las necesidades empresariales de la compañía las que identificarán los requisitos para la solución de administración de dispositivos móviles.
Para ayudar a identificar las necesidades del negocio, responda a las preguntas siguientes:

- **Usuario:** uno de los puntos principales en la adopción de la movilidad es poner al usuario en el centro de la solución de movilidad y permitir que el usuario sea más productivo, a la vez que hace que los datos de la compañía sigan siendo seguros y estén disponibles. Esto es importante para comprender cuáles son los requisitos del usuario.
    - ¿El usuario podrá traer su propio dispositivo y obtener acceso a los recursos de la compañía?
        - En caso afirmativo, ¿cuáles son los requisitos para obtener acceso a los recursos de la empresa?
    - ¿Su empresa tiene necesidades de usuario distintas?
        - En caso afirmativo, ¿cómo el perfil de cada usuario afecta a la estrategia de movilidad?
    - ¿Los usuarios podrán disponer de acceso a todas las aplicaciones a las tienen acceso en el entorno local a través del dispositivo móvil?
        - Si no es así, ¿qué aplicaciones estarán disponibles para los usuarios?
            - ¿Las aplicaciones estarán disponibles para todas las plataformas de dispositivos móviles compatibles?
            - ¿Será necesario modificar o actualizar las aplicaciones para poder ejecutarlas en todas las plataformas de dispositivos móviles compatibles?
    - ¿Los usuarios solo necesitan acceso básico a las características de correo electrónico (incluido el calendario, los contactos y las tareas)?

- **Propiedad del dispositivo:** debe entender la directiva de la propiedad de dispositivos para su compañía.
    - ¿A quién pertenece el dispositivo móvil?
        - ¿Al empleado?
        - ¿A la compañía?  
        - ¿A ambos?
- **Plataforma:** comprender qué sistemas operativos de dispositivos móviles usará la empresa es muy importante para las decisiones de compatibilidad y de adopción.
    - ¿Se admitirán los sistemas operativos de dispositivos móviles?
        - ¿Android?
        - ¿iOS?
        - Windows?,
        - ¿Windows Phone?
        - ¿Todos ellos?
        - ¿Una combinación de las opciones anteriores?
    - ¿Se admitirá la versión de sistema operativo móvil?
        - ¿Solo la versión más reciente?
        - ¿Actual -1 (versión actual más la versión anterior)?
- **Aplicaciones**: puesto que la razón principal para adoptar la movilidad es aumentar la productividad, las aplicaciones utilizadas por los empleados deben ser capaces de ejecutarse en todos los sistemas operativos de dispositivos móviles que se usan en su organización. Este es un punto importante que tener en cuenta, ya que mientras algunas compañías pueden tener sus aplicaciones más importantes de manera totalmente portátil para ejecutarlas en un entorno móvil, es posible que otras tengan que entender qué opciones disponibles hay que puedan ayudarles a implementar sus aplicaciones en dispositivos móviles. Para ayudarlo a identificar los requisitos de aplicaciones individuales, hágase las siguientes preguntas.
    - ¿Las aplicaciones requieren que se acceda a Internet desde los dispositivos de los usuarios?
    - ¿Las aplicaciones recopilan información personal del usuario?
        - Si es así, ¿las aplicaciones informan a los usuarios sobre las cuestiones de privacidad y la recopilación de datos al instalarse?
    - ¿Las aplicaciones requieren integración con servicios en la nube?
        - ¿Las aplicaciones se desarrollaron para ejecutarse en un sistema operativo en concreto o se pueden ejecutar en cualquier sistema operativo?
    - ¿Tiene pensado permitir que los usuarios utilicen aplicaciones con Escritorio remoto desde sus propios dispositivos?
    - ¿Las aplicaciones requieren acceso a tiempo completo a los recursos corporativos o se pueden ejecutar en modo sin conexión?
    - ¿Las aplicaciones tienen algún tipo de integración con redes sociales?
    - ¿Las aplicaciones estarán disponibles para los usuarios BYOD?
    - ¿Cómo tiene pensado implementar estas aplicaciones en los dispositivos de los usuarios?
    - ¿Cuáles son las opciones de implementación de estas aplicaciones?
    - ¿Los requisitos de instalación varían según el dispositivo de destino o son iguales en todos los casos?
    - ¿Cuánto espacio es necesario tener en el dispositivo de destino para instalar cada aplicación?
    - ¿Las aplicaciones cifran los datos antes de transmitirlos por la red desde los dispositivos de los usuarios hasta el servidor de aplicaciones del back-end?
    - ¿Las aplicaciones se pueden desinstalar de forma remota a través de la red o es necesario desinstalarlas con las consolas de los dispositivos?
    - ¿Su empresa necesita proporcionar acceso a datos de aplicaciones de SaaS para sus partners?
    - ¿Las aplicaciones funcionan en redes de latencia baja?
    - ¿Las aplicaciones proporcionan funcionalidades de autenticación?
        - Si lo hacen, ¿qué método de autenticación usan las aplicaciones?

Durante esta tarea, también debe evaluar si la empresa tiene directivas de cumplimiento y de administración existentes en su lugar para dispositivos móviles y cómo estas directivas pueden afectar a la selección de soluciones de administración de dispositivos móviles.

>[!TIP]
> Asegúrese de que toma las notas de cada respuesta y de que comprende la lógica subyacente en la respuesta. La siguiente sección tratará las opciones disponibles, así como las ventajas y desventajas de cada opción.  Con las respuestas a estas preguntas, podrá seleccionar qué solución se adapta mejor a sus necesidades empresariales.



<!--HONumber=Nov16_HO4-->


