---
title: "Identificación de necesidades de integración de infraestructura de soluciones de SaaS"
description: 
keywords: 
author: andredm7
manager: swadhwa
ms.date: 05/31/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 26b15471-b496-4404-934d-67e621655bca
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 73c37109735567642ff1dc11f9729e3ab3affd3b
ms.openlocfilehash: 7e43f590182e6a2eacfa60114290848de0b24baa


---

# Identificación de necesidades de integración de infraestructura de soluciones de SaaS

>[!NOTE]
>Este tema forma parte de una guía de consideraciones de diseño más extensa. Si desea comenzar por el principio de la guía, consulte el [tema principal](mdm-design-considerations-guide.md). Para obtener una copia descargable de toda esta guía, visite la [Galería de TechNet](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582).

Una de las decisiones principales que deben realizarse al considerar la administración de dispositivos móviles con una solución de SaaS son:

- ¿Cómo se integran las cuentas de directorio locales de dispositivos y usuarios existentes con la solución de SaaS?
- ¿Necesita integrar la solución de SaaS con las plataformas de administración de cliente locales existentes?

Las decisiones que tome en estas dos áreas afectarán significativamente a las experiencias de usuario final, administración e implementación generales para la solución de administración de dispositivos móviles.

## Identidad y conectividad de directorios

La conexión y sincronización del directorio de cuentas de dispositivos y usuarios locales con la solución de SaaS es realmente el elemento aglutinante que conecta verdaderamente a los usuarios, dispositivos móviles, aplicaciones móviles y la administración de dispositivos móviles. Conocer al usuario (identidad) y asociar la identidad a los dispositivos móviles específicos es fundamental en la administración del acceso a los datos y los recursos de la compañía desde el dispositivo móvil. En muchos sentidos, maximizar la forma en la que se conectan estas áreas a la solución de SaaS determina el valor general para usted y los usuarios de los dispositivos móviles.  Una conectividad ubicua implica que las personas y los dispositivos pueden utilizar dispositivos y aplicaciones en cualquier lugar, y es fundamental que la administración de identidades de usuario mantenga el ritmo de las demandas de esa conectividad. Cabe destacar de nuevo que la forma en la que administre la autenticación de usuarios y la identidad es fundamental para el éxito de su solución de administración de dispositivos móviles.

La sincronización de los servicios de directorios locales en la solución de SaaS es otra zona clave que tener en cuenta cuando se define la estrategia de administración de dispositivos móviles. La mayoría de las organizaciones prefieren mantener una infraestructura de directorios de dispositivos y usuarios locales, pero tienen que extender sus cuentas a una variedad de servicios basados en la nube. Esto puede incluir solo una solución de administración de dispositivos móviles basados en SaaS, pero en la mayoría de los escenarios, las organizaciones tienen que integrar las cuentas de usuarios y dispositivos en distintos tipos de servicios basados en la nube. Esto puede incluir servicios web de terceros, datos y aplicaciones basadas en la nube. Mantener sus cuentas de directorio de dispositivos y usuarios sincronizadas es la piedra angular de una solución de administración de identidades bien diseñada. Una vez que integre su directorio local con el directorio en la nube, puede también habilitar el inicio de sesión único (SSO) para permitir a los usuarios iniciar sesión en todos los servicios con las credenciales locales. <token>Intune</token> y Office 365 pueden aprovechar esta integración para habilitar SSO con aplicaciones de SaaS que la organización puede querer usar.

### Preguntas sobre identidad y conectividad de directorios

Como parte de la planificación del ciclo de vida de la administración de SaaS, querrá responder a las siguientes preguntas de planificación acerca de la conectividad de directorios y de administración de identidades:

- ¿La solución de SaaS es compatible con los servicios de autenticación de usuarios integrados? Si es así, ¿es compatible con el tipo de servicios de directorio que usa en la infraestructura local?
- ¿Necesita admitir una autenticación de dispositivos móviles y de usuarios para servicios o aplicaciones internas o locales?
- ¿La solución de SaaS es compatible con la autenticación de dispositivos móviles y de usuarios para terceros u otros servicios o aplicaciones basados en SaaS externos?
- ¿Cómo administra la solución de SaaS las anormalidades y amenazas relacionadas con la identidad?
- ¿La solución de SaaS es compatible con la implementación y administración de la autenticación multifactor (MFA?
- ¿Qué tipos de objetos de servicios de directorio necesita extender a la solución de SaaS? ¿La solución de SaaS tiene alguna restricción para determinados tipos de objetos?
- ¿Qué requisitos locales son necesarios para extender los servicios de directorio a la solución de SaaS?
- Una vez conectado a la solución de SaaS, ¿cómo se replican o sincronizan los objetos de directorio de dispositivos móviles y usuarios con el servicio en la nube? ¿La configuración de la sincronización es personalizable o se puede solucionar?
- ¿Todos los atributos de objeto de directorio se sincronizan con la solución de SaaS? ¿Necesita sincronizar los atributos de objeto de directorio personalizados?
- ¿Los servicios de directorio locales se hospedan en una única ubicación o grupo lógico? Si no es así, ¿la solución de SaaS es compatible con la sincronización de varios servicios de directorio a partir de varias ubicaciones y grupos lógicos?

## Conexión con las plataformas de administración de clientes existentes

La mayoría de las organizaciones tienen una plataforma de administración de clientes local existente para administrar servidores y equipos de escritorio. Es probable que la forma de integrar la administración de dispositivos móviles en este sistema tenga un impacto sustancial en los costes de infraestructura de la TI, los procesos de administración de dispositivos, la compatibilidad de los informes y el inventario de dispositivos y la integración general con otros servicios y aplicaciones cruciales para la empresa. Mediante la conexión de estas dos plataformas, las organizaciones pueden aprovechar las economías de escala de una plataforma de administración única e unificada.

### Preguntas sobre conexión con las plataformas de administración de clientes existentes

Como parte de la planificación del ciclo de vida de administración de SaaS, querrá responder a las siguientes preguntas de planificación acerca de la conexión de la solución de SaaS con las plataformas de administración de clientes existentes:

- ¿La plataforma de administración de clientes local es compatible con la integración con la solución de SaaS? Si es así, existen:
 - ¿Limitaciones en el tipo de solución de SaaS?
 - ¿Limitaciones en los tipos de dispositivos compatibles?
- ¿Cuáles son los requisitos para conectar la plataforma de administración de clientes local a la solución de SaaS? Específicamente, existen:
 - ¿Requisitos de dispositivos o servidor físicos?
 - ¿Requisitos de esquema de directorios o servicios de directorio?
 - ¿Requisitos de servicios de nombres de dominio (DNS)?
 - ¿Requisitos de identidad?
 - ¿Requisitos de configuración o actualizaciones de la plataforma de administración de clientes?
 - ¿Requisitos de configuración de la seguridad de red o conectividad de red?
- ¿La información de configuración de dispositivos o clientes existentes (directivas, perfiles y configuración) puede compartirse o aprovecharse en la solución de SaaS? ¿Tendrá que volverse a crear esta información?
- Una vez conectadas las dos plataformas, ¿cómo se administran los clientes? ¿Existen distintos tipos de clientes administrados en un sistema de administración unificado o se administran por separado?
- ¿Cómo son las actualizaciones y los cambios en la solución de SaaS integrada con la plataforma de administración de clientes local? ¿Esto es un proceso de configuración manual o automático?

>[!TIP]
>Asegúrese de que toma las notas de cada respuesta y de que comprende la lógica subyacente en la respuesta. Más adelante, las tareas tratarán las opciones disponibles, y las ventajas y desventajas de cada opción.  Responder a estas preguntas le ayudará a seleccionar la opción que mejor se adapte a sus necesidades empresariales.


<!--HONumber=Jul16_HO3-->


