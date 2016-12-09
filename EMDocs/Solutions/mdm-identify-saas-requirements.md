---
title: "Identificación de requisitos de SaaS"
description: "En este artículo se proporciona información sobre la identificación de los requisitos de software como servicio al planear y diseñar una administración de dispositivos móviles con Microsoft mediante soluciones de Enterprise Mobility + Security."
keywords: 
author: andredm7
ms.author: andredm
manager: swadhwa
ms.date: 10/3/2016
ms.topic: solution
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 5380e56c-9c48-459e-aea5-95ad90dbb7d1
ms.reviewer: 
ms.suite: ems
ms.custom: microsoft-intune
translationtype: Human Translation
ms.sourcegitcommit: 7d9c38008b5b47ea41ff331f1de763de5c119c5e
ms.openlocfilehash: 68a42159dfbf6b0d435b0543466d4cec26e55b67


---

# <a name="identify-saas-requirements"></a>Identificación de requisitos de SaaS

>[!NOTE]
>Este tema forma parte de una guía de consideraciones de diseño más extensa. Si desea comenzar por el principio de la guía, consulte el [tema principal](mdm-design-considerations-guide.md). Para obtener una copia descargable de toda esta guía, visite la [Galería de TechNet](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582).

Cada solución de SaaS dispondrá de distintos requisitos, características de administración de dispositivos móviles y niveles de integración con plataformas y redes locales. Muchas soluciones de SaaS ofrecen servicios o inquilinos de prueba para que evalúe sus características y funcionalidad, que es una parte importante para la determinación de qué solución cumple realmente sus necesidades. Sin embargo, muchas soluciones de SaaS tienen diferencias sutiles en las características y en la funcionalidad, según el tipo de plataforma.

La mayoría de las soluciones de SaaS se basan en tres tipos de nube:

- Varios inquilinos
- Privado (dedicado)
- Híbrida

Antes de tomar decisiones sobre cómo usará una solución de SaaS para administrar los dispositivos móviles, también necesitará examinar las diferencias entre estos tipos de arquitecturas de plataforma en la nube y elegir la que mejor se adapte a las necesidades generales de su organización. Las soluciones de SaaS individuales tienen distintos niveles de compatibilidad para áreas como la personalización, configuración de características, integración y funcionalidad de colaboración.

## <a name="cloud-types"></a>Tipos de nube

Las soluciones de SaaS *multiinquilino* son las que normalmente se denominan "infraestructuras de nube pública". Se aplican cuando la arquitectura de software del servicio se encuentra en una única instancia, pero ofrece servicio a varios inquilinos u organizaciones. La solución está diseñada para proporcionar a cada inquilino un recurso compartido reservado de sus servicios, como la compatibilidad de datos, configuración, administración de dispositivos o usuarios. Los servicios y cuentas de inquilinos están casi separados, con cada inquilino que obtiene acceso a la infraestructura de plataforma en instancias independientes. Las soluciones de SaaS multiinquilino también ofrece ahorros en costes que se obtienen a partir del uso compartido de la infraestructura y la distribución de los costes generales entre varios inquilinos. La mayoría de las plataformas de administración de dispositivos móviles se ofrecen en una infraestructura de plataforma de SaaS multiinquilino.
                
*Privada*, o los servicios en la nube dedicados son instancias de soluciones de SaaS que operan para un inquilino o una organización únicos. Pueden ser servicios en la nube privada hospedados por la organización o los servicios en la nube privada hospedados por un proveedor de terceros. Las soluciones en la nube privada también ofrecen normalmente más oportunidades de personalización, tanto en las áreas de seguridad como de servicios. Algunas soluciones de SaaS dedicadas ofrecen servicios de administración de dispositivos móviles como parte de las opciones de inquilino de nube privada más grandes.

Las soluciones de SaaS *híbridas* pueden ofrecer una combinación de infraestructuras en la nube privada y multiinquilino, o una combinación de infraestructuras en la nube locales y hospedadas (privada o multiinquilino). Una infraestructura híbrida también puede incluir el aprovechamiento de una solución de SaaS en la nube externa para ofrecer determinados tipos de servicios (como aplicaciones), pero aprovechando los recursos internos para otros tipos de servicios. La mayoría de soluciones de SaaS ofrecen la capacidad de admitir una configuración de nube híbrida, pero pueden variar considerablemente en la profundidad y la integridad de la integración con plataformas en la nube locales o con otras plataformas en la nube hospedadas.

### <a name="cloud-questions"></a>Preguntas de la nube

Como parte de la planificación del ciclo de vida de la administración de SaaS, querrá responder a las siguientes preguntas de planificación acerca de los tipos de nube:

- ¿Qué nivel de seguridad necesito para los datos de dispositivos móviles almacenados en mi solución de SaaS?
- ¿Cómo administra la solución de SaaS la detección de las intrusiones y la prevención de la pérdida de datos para los dispositivos móviles?
- ¿Su organización tiene que cumplir con algún requisito de cumplimiento, certificación o regulación para dispositivos móviles o datos almacenados en dispositivos móviles? Si es así, ¿requieren un nivel específico de seguridad, personalización, escalabilidad o resistencia? ¿Cómo se audita y notifica el cumplimiento?
- ¿La solución SaaS necesita conectividad con otras plataformas o servicios en la nube que vayan a administrar dispositivos móviles? Si es así, esta conectividad:
 - ¿Está preconfigurada o estandarizada?
 - ¿Se puede personalizar?
 - ¿Es compatible con las plataformas a la que necesita conectarse?
- ¿Necesita conectarse a la solución de SaaS con una infraestructura de administración de dispositivos locales existentes? Si es así, esta conectividad:
 - ¿Es compatible con la plataforma de administración de dispositivos locales?
 - ¿Es compatible con la solución de SaaS?
 - ¿Es compatible sin la necesidad de recursos físicos locales adicionales?
- ¿Los servicios basados en la nube, las aplicaciones y procesos para los dispositivos móviles requieren distintos niveles de seguridad, personalización, escalabilidad y resistencia?

## <a name="scalability"></a>Escalabilidad

La facilidad de escalabilidad es una de las razones principales para considerar o implementar una solución de SaaS para la administración de dispositivos móviles en su organización. Por definición, las soluciones de SaaS públicas normalmente ofrecen una capacidad prácticamente ilimitada para admitir cualquier cantidad de usuarios o dispositivos móviles. Las soluciones de SaaS privadas e híbridas pueden estar sujetas a límites de escalado en función de los recursos de la organización disponibles. El aumento o disminución del escalado para admitir un número mayor o menor de usuarios o dispositivos depende normalmente de un modelo de licencias específico o de un paquete de precios por usuario/dispositivo para nubes públicas.

### <a name="scalability-questions"></a>Preguntas de escalabilidad

Como parte de la planificación del ciclo de vida de la administración de SaaS, querrá responder a las siguientes preguntas de planificación sobre de la escalabilidad en la nube:

- ¿Qué tipo de planes a corto y largo plazo tiene su organización para el crecimiento o reducción en la infraestructura de compatibilidad de aplicaciones y dispositivos móviles?
- ¿Con qué rapidez su organización tendrá que escalar los servicios de compatibilidad de administración de dispositivos móviles hacia arriba o hacia abajo?
- ¿Cuál es el número inicial de dispositivos móviles o usuarios que necesitan compatibilidad en la solución de SaaS? ¿Cómo es de probable que cambie este número en el próximo año? ¿En los próximos 3 años? ¿En los próximos 5 años?
- ¿El número de dispositivos móviles que necesita una solución de SaaS admite el cambio en una frecuencia regular (como estacional)? ¿Cambia de acuerdo con el número de proyectos de la organización activos o inactivos?
- ¿El rendimiento de la solución de SaaS cambia según la escala de los usuarios y dispositivos móviles compatibles? Si es así, ¿en qué áreas? (nodos, datos, procesamiento, etc.) ¿Cómo se mide, notifica y audita el rendimiento del escalado?

## <a name="accessibility"></a>Accesibilidad

El acceso sencillo a la solución de SaaS es otro componente clave de la arquitectura de SaaS. Puesto que la solución de SaaS se hospeda en una infraestructura basada en la nube, los administradores, usuarios y dispositivos pueden obtener acceso desde cualquier ubicación con acceso a Internet. La administración de dispositivos móviles se realiza a través de un explorador. Puesto que muchos proveedores de soluciones de SaaS operan en centros de datos diversos geográficamente, los usuarios y dispositivos pueden obtener acceso a la plataforma "localmente", por lo que se evita a menudo la latencia y los retrasos que pueden asociarse a la conexión a extremos distantes geográficamente. La accesibilidad también puede expandirse normalmente mediante la integración de la solución de SaaS con plataformas de administración de dispositivos locales.

### <a name="accessibility-questions"></a>Preguntas de accesibilidad

Como parte de la planificación del ciclo de vida de la administración de SaaS, querrá responder a las siguientes preguntas de planificación acerca de la accesibilidad en la nube:

- ¿Existen requisitos de explorador de dispositivos móviles específicos en su organización? Si es así, ¿la solución de SaaS admite los exploradores necesarios?
- ¿Los usuarios de dispositivos móviles tienen algún requisito de accesibilidad especial para las aplicaciones o los servicios?
- ¿La organización tiene que obtener acceso a la infraestructura de SaaS ubicada en la misma ubicación geográfica que los dispositivos de usuario o su infraestructura local? ¿Existen consecuencias legales si los datos del dispositivo móvil se almacenan o traspasan las fronteras internacionales?

## <a name="resiliency"></a>Resistencia

Puesto que la infraestructura de SaaS está basada en la nube y hospedada en varios centros de datos, la resistencia está normalmente sujeta a menos inestabilidad y cortes que los servicios hospedados locales tradicionales. Los hosts de servicio de múltiples ubicaciones ofrecen protección frente a las interrupciones de servicios y cortes geográficos mediante los procesos y la infraestructura de conmutación por error para replicar datos en los nodos de varios centros de datos. Dependiendo de la solución de SaaS, el acceso al servicio puede mantenerse o no en la zona geográfica original durante una conmutación por error.

### <a name="resiliency-questions"></a>Preguntas de resistencia
 
Como parte de la planificación del ciclo de vida de la administración de SaaS, querrá responder a las siguientes preguntas de planificación sobre la resistencia en la nube:

- En el caso de una conmutación por error de la solución de SaaS principal, ¿cómo afectará a los servicios de administración de dispositivos móviles?
- ¿Cómo se almacenarán los datos de dispositivos móviles en la solución de SaaS en la infraestructura basada en la nube?
- Si el centro de datos de SaaS del dispositivo móvil principal no está disponible, ¿se consideran los centros de datos de conmutación por error de la misma región geográfica el centro de datos principal? ¿Es correcto que los centros de datos de conmutación por error se encuentren fuera de las fronteras internacionales desde las que están operando los dispositivos móviles?
- ¿La solución de SaaS ha definido un contrato de nivel de servicio (SLA) que indique la compatibilidad de la administración de dispositivos móviles?


## <a name="up-to-date-services"></a>Servicios actualizados

Las soluciones de SaaS también pueden mantener las aplicaciones y servicios actualizados con las correcciones de errores, actualizaciones de seguridad, características y versiones de la aplicación más recientes. Normalmente estas actualizaciones se publican muy rápidamente. A veces, incluso en un día. Según la solución de SaaS, las actualizaciones pueden estar disponibles de manera instantánea para todos los clientes o publicarse por fases para grupos reducidos de clientes. Una de las mayores ventajas es que cuando se soluciona un error para un cliente, la solución puede aplicarse fácilmente a todos los clientes que usan el servicio.

### <a name="services-questions"></a>Preguntas sobre los servicios

Preguntas de servicios: como parte de la planificación del ciclo de vida de la administración de SaaS, querrá responder a las siguientes preguntas de planificación sobre los servicios en la nube:

- ¿Con qué frecuencia se actualizan las funcionalidades y características de administración de dispositivos móviles en el servicio de SaaS?
- ¿Qué impacto tendrán las actualizaciones de las funcionalidades y características en los servicios y aplicaciones de dispositivos móviles críticas?
- ¿Las actualizaciones de funcionalidades y características de soluciones de SaaS se implementan en los clientes con una programación planificada o ad hoc?
- ¿La solución de SaaS admite exenciones de actualizaciones en todo el servicio para organizaciones individuales?
- ¿La solución de SaaS tiene distintas programaciones de actualización de servicios para aplicaciones de dispositivos móviles y funcionalidades y características de administración de dispositivos móviles?

>[!TIP]
>Asegúrese de que toma las notas de cada respuesta y de que comprende la lógica subyacente en la respuesta. Más adelante, las tareas tratarán las opciones disponibles, y las ventajas y desventajas de cada opción.  Responder a estas preguntas le ayudará a seleccionar la opción que mejor se adapte a sus necesidades empresariales.



<!--HONumber=Nov16_HO4-->


