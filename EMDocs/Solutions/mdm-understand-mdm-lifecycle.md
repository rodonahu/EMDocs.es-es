---
# required metadata

title: El ciclo de vida de MDM
description:
keywords:
author: robmazz
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: 901b52bf-2340-4847-aaff-c94fec9ee925

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: 
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# El ciclo de vida de MDM

>[!NOTE]
>Este tema forma parte de una guía de consideraciones de diseño más extensa. Si desea comenzar por el principio de la guía, consulte el [tema principal](mdm-design-considerations-guide.md). Para obtener una copia descargable de toda esta guía, visite la [Galería de TechNet](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582).

Es importante entender las diferentes áreas de administración de dispositivos móviles cuando se diseña la solución de administración de dispositivos móviles. La figura siguiente describe las fases del ciclo de vida de administración de dispositivos móviles generales. Cada fase tiene preguntas y requisitos únicos que hay que tener en cuenta al planear su solución. Comenzaremos con la fase de inscripción en esta sección y las otras fases se tratarán con más detalle a lo largo de esta guía.

![Fases del ciclo de vida de administración de dispositivos móviles](./media/MDM_Figure_03.png)

**Fases del ciclo de vida de administración de dispositivos móviles**

## Inscripción y configuración de dispositivos
La administración de dispositivos móviles comienza con la inscripción y la configuración iniciales de dispositivos en su solución de administración de dispositivos móviles. La simplicidad, la facilidad de registro y la inscripción son factores clave para el éxito del ciclo de vida de administración de dispositivos móviles. Si la inscripción inicial de dispositivos es complicada o demasiado confusa, usted y sus usuarios pueden ser reacios a continuar con una solución de administración de dispositivos móviles, desaprovechando las características, beneficios y mecanismos de protección que puede ofrecer tal solución.

La inscripción de dispositivos móviles en soluciones de administración de dispositivos móviles se inicia normalmente de dos formas:

- Inscripción por administrador
- Autoinscripción por usuario/propietario
 
La inscripción controlada por un administrador ofrece una experiencia administrada centralmente. Normalmente, es una operación masiva con varios dispositivos donde se usa una cuenta de directorio único. Esto resulta útil si necesita inscribir muchos dispositivos propiedad de la compañía en la solución de administración de dispositivos móviles.

Con la autoinscripción, el propietario/usuario del dispositivo inscribe su dispositivo en la solución de administración de dispositivos móviles. Se utiliza normalmente en escenarios "Bring Your Own Device" (BYOD), aunque se puede usar en escenarios en los que el dispositivo es propiedad de la compañía. Este tipo de inscripción normalmente usa un modelo de inscripción de "inserción", donde los dispositivos se activan automáticamente para inscribirse en la solución de administración de dispositivos móviles cuando el usuario intenta conectarse a la red corporativa o al recurso de red desde el dispositivo. Los usuarios a veces también pueden elegir inscribir sus dispositivos antes de conectarse a recursos o a la red de la organización.

La inscripción y configuración de dispositivos móviles incluyen lo siguiente:

- Implementación, acceso, y administración de servicios y aplicaciones internos y externos
- Aplicación de configuraciones de seguridad y acceso del dispositivo
- Protección de los dispositivos frente a amenazas de seguridad

En la mayoría de los casos, cuando un dispositivo móvil está inscrito en una solución de administración de dispositivos móviles, se asignan al dispositivo las directivas y permisos que se han asociado a la cuenta del directorio del usuario del dispositivo o al grupo al que el propio dispositivo está asociado en los servicios de directorio. Según la solución de administración de dispositivos móviles, la mayor parte de la configuración y el aprovisionamiento de los permisos y directivas de dispositivos se realiza antes de la inscripción del dispositivo. Después, la configuración de cumplimiento y directiva surte efecto tan pronto como se realiza la inscripción de los dispositivos, eliminando el vacío entre la inscripción y el cumplimiento.

## Preguntas de planeación de configuración e inscripción de dispositivos

Para planear la administración del ciclo de vida de MDM, responda a las siguientes preguntas de planeamiento de la inscripción y configuración de dispositivos:

- ¿Quién realizará la inscripción de los dispositivos móviles: usted, los usuarios o ambos?
- ¿Necesita la capacidad de inscripción masiva de dispositivos móviles?
- ¿Cuál es la cantidad de máxima de dispositivos que tendrá que inscribir de forma masiva?
- ¿Las plataformas del sistema operativo móvil en su organización requieren recursos y requisitos de inscripción masiva diferentes?
- ¿Cuántos dispositivos usará y tendrá que inscribir cada usuario normalmente?
- ¿La solución de administración de dispositivos móviles tiene un límite de inscripción de dispositivos por usuario?
- ¿Cuáles son los requisitos (conectividad, aplicación, agente de administración, portal de empresa y soporte técnico) para que los usuarios autoinscriban dispositivos?
-  ¿Son distintos de los requisitos para la inscripción controlada por un administrador?
-  ¿Cuáles son los requisitos de inscripción para cada sistema operativo de dispositivo que debe admitir?
-  ¿Los sistemas operativos de dispositivos móviles en su organización necesitan requisitos de inscripción especiales o únicos?
-  ¿La solución de administración de dispositivos móviles admite las inscripciones móviles y conectadas?
-  ¿Cuáles son los requisitos de hardware (si los hubiera) para admitir las inscripciones de dispositivos?
-  ¿Cuáles son los requisitos de seguridad de red y conectividad de red para admitir inscripciones de dispositivo?
-  ¿Necesita que se apliquen directivas de cumplimiento de dispositivos específicas a los dispositivos tras la inscripción inicial?
-  ¿Necesita directivas de seguridad de dispositivos específicas aplicadas a dispositivos una vez realizada la inscripción inicial?
-  ¿Necesita la capacidad de configurar o establecer un límite de tiempo máximo o mínimo para el aprovisionamiento de directivas de dispositivos después de la inscripción inicial?
-  ¿Necesita que se activen automáticamente directivas de aprovisionamiento especiales en caso de errores en la inscripción?

##Administración de dispositivos
El modo en que se administran los dispositivos móviles, tanto para usted como para el usuario del dispositivo, es un componente clave de una solución de administración de dispositivos móviles.

Por ejemplo, puede que desee integrar la forma en la que se administran los dispositivos móviles con la forma en la que se administran los dispositivos que no son móviles (servidores, equipos de escritorio, otros dispositivos de red). Dependiendo de la organización, es posible que las soluciones de administración de dispositivos que no son móviles existiesen mucho antes de que se empezaran a usar los dispositivos móviles en la organización. Esto puede haber supuesto un costo considerable, así como inversiones a largo plazo en estas soluciones de administración.

Un conocimiento profundo del modo en que su organización puede integrar las soluciones de administración de dispositivos móviles con las soluciones de administración de dispositivos no móviles existentes es probablemente una de las actividades más importantes al diseñar una solución de administración de dispositivos móviles que satisfaga las necesidades de su organización.

La administración de dispositivos móviles normalmente implica varias áreas administrativas:

- **Configuración y seguridad de dispositivos**: la seguridad de los dispositivos móviles incluye una gran variedad de configuraciones que puede implementar en dispositivos administrados en su organización. La configuración puede incluir la especificación del tiempo, la expiración y las características necesarias para el acceso mediante código de acceso de dispositivo, el cifrado de dispositivos y el borrado de los datos de dispositivos perdidos o robados. Encontrará más información sobre seguridad y configuración en el tema [Paso 3: planeación para proteger dispositivos móviles](mdm-step-3-plan-enhancing-mobile-devices-protection.md).
- **Administración de aplicaciones:** esta área incluye la administración de la implementación de aplicaciones, la instalación, la actualización y la administración de estado, y la eliminación de las aplicaciones. También puede administrar restricciones en ciertas aplicaciones no compatibles, que pueden ser importantes para una estrategia de seguridad y cumplimiento general. También pueden existir escenarios de administración de aplicaciones donde necesite administrar aplicaciones en dispositivos móviles, pero no desea inscribir los dispositivos en la plataforma de administración de dispositivos móviles.
- **Acceso a los recursos de la compañía**: MDM también puede ayudar a administrar el acceso a recursos de red locales, como servidores de correo electrónico, redes Wi-Fi y recursos de VPN. Esto tiene el doble propósito de ayudar a garantizar el cumplimiento de la seguridad y facilitar que los usuarios de dispositivos móviles tengan acceso a recursos de la compañía según la directiva de la empresa. Si el acceso a los recursos de la organización es demasiado complejo o difícil para los usuarios de dispositivos móviles, pueden decidir usar recursos de la compañía no aprobados para almacenar datos de la compañía, ya que es más sencillo.
- **Inventario e informes:** al administrar dispositivos móviles, deseará registrar y analizar los eventos de plataforma y dispositivos móviles para realizar un seguimiento del cumplimiento con las directivas de administración de su organización. Los informes detallados pueden también proporcionar datos y estadísticas en tiempo real para que pueda tomar con mayor rapidez mejores decisiones basadas en el estado de los dispositivos móviles y los usuarios de dispositivos móviles. Se incluye más información acerca del inventario y los informes en una sección posterior.

### Preguntas de planeación de administración de dispositivos
Por ahora, céntrese únicamente en los aspectos clave de administración mientras siga definiendo los requisitos. Puede ajustar estos requisitos a medida que itera su plan y comprende mejor las necesidades generales de su organización.</para><para>Responda a las siguientes preguntas de planificación acerca de la administración de dispositivos:

- ¿Necesita directivas de administración específicas aplicadas a grupos de usuarios, grupos de dispositivos o grupos de sistemas operativos de dispositivos?
- ¿Necesita las directivas de administración específicas para diferentes tipos de dispositivos? ¿Por ejemplo, separar las directivas para dispositivos propiedad del usuario o de la empresa, o dispositivos móviles y dispositivos que no son móviles?
- ¿Necesita separar los derechos de administración de dispositivos y los permisos entre varias posiciones o roles de TI? Si es así:
 - ¿Qué separación de niveles de permiso es necesaria?
 - ¿Los niveles de permiso que proporciona la solución tienen que personalizarse?
 - ¿Los permisos tienen que integrarse en los servicios de directorio de cuenta existentes?
- ¿Necesita la capacidad de implementar manual y automáticamente el software o los agentes de la solución de administración de dispositivos móviles?
- ¿Necesita la funcionalidad de administrar aplicaciones en dispositivos móviles, pero no quiere inscribirlos en una plataforma de administración de dispositivos móviles (nueva o existente)?
- ¿Desea integrar la administración de los dispositivos móviles con una solución de administración de dispositivos no móviles existente? Si es así:
 - ¿Desea administrar todos los dispositivos desde un portal o una consola de administración unificada?
 - ¿Cuáles son los requisitos de integración para la solución de administración de dispositivos no móviles?
 - ¿En qué grado la solución de administración de dispositivos no móviles existente es compatible con los permisos y los roles de administración necesarios?
 - ¿Existen requisitos de red o hardware para conectar servicios de administración entre las soluciones de administración de dispositivos móviles y no móviles?
 - ¿Ambas soluciones disponen de sistemas de informes e inventario de integración o independientes?
- ¿La solución de administración de dispositivos móviles tiene un portal de empresa para que los usuarios instalen sus aplicaciones?
- ¿La solución de administración de dispositivos móviles cumple los requisitos de escalabilidad de la compañía?
- ¿La solución de administración de dispositivos móviles admite la administración remota?
- ¿La solución de administración de dispositivos móviles admite la automatización?

## Administración de aplicaciones

En algunos casos, puede que no quiera inscribir un dispositivo móvil en un sistema de administración de dispositivos, pero que todavía necesite administrar aplicaciones en el dispositivo para impedir que los datos de la compañía se filtren a otras aplicaciones o servicios de consumidores en el dispositivo. Esto podría aplicarse a los empleados que usan dispositivos personales para acceder a los recursos de empresa en un escenario de BYOD, o incluso en escenarios donde necesita administrar dispositivos móviles en una plataforma de administración de dispositivos y aplicaciones en otra plataforma de este tipo.

### Preguntas de planeación de administración de aplicaciones

Para planear las consideraciones de administración de aplicaciones, responda a las siguientes preguntas de planeación:

- ¿Es necesario que los datos de empresa estén aislados de los datos de consumidores en las aplicaciones de dispositivos móviles?
- ¿Necesita impedir que los datos se compartan a través de acciones de cortar, copiar y pegar en las aplicaciones personales y corporativas de dispositivos móviles?
- ¿Necesita impedir que las aplicaciones realicen copias de seguridad o guarden datos en otras aplicaciones o servicios?
- ¿Necesita habilitar directivas de prevención de pérdida de datos por aplicación?
- ¿Necesita restringir el contenido web que se muestra en un explorador administrado?

##Cancelación de la inscripción/retirada de los dispositivos

Cuando los usuarios abandonan la organización o se retiran o reemplazan los dispositivos móviles, debe asegurarse de que no se comprometan o se pierdan los datos corporativos. Normalmente, las soluciones de administración de dispositivos móviles admiten la cancelación de la inscripción y los restablecimientos de dispositivos administrados por usuarios y por la TI. Con la mayoría de dispositivos móviles, la cancelación de la inscripción comienza por restablecer el dispositivo a los valores predeterminados de fábrica o realizar una eliminación selectiva de todos los datos corporativos y aplicaciones. A continuación, se quita la conexión de la inscripción de dispositivos a la solución de administración. Sin embargo, el proceso varía entre los fabricantes de dispositivos móviles y las plataformas de sistema operativo del dispositivo.

### Preguntas de planeación de cancelación de inscripción o retirada de dispositivos

Responda a las siguientes preguntas de planeación sobre la cancelación de inscripción o retirada de dispositivos

- ¿Necesita la capacidad de los usuarios y de la TI para cancelar la inscripción de dispositivos móviles?
- Si un dispositivo se borra de forma selectiva, ¿debe cancelarse la inscripción automática desde la solución de administración de dispositivos móviles?
- Si los usuarios de dispositivos móviles pueden cancelar la inscripción de los dispositivos móviles, ¿cómo se comprobará la eliminación de las aplicaciones y datos corporativos?
 - ¿Es distinto en los dispositivos que se eliminan selectivamente y los que se restablecen a la configuración predeterminada de fábrica?

>[!TIP]
>Asegúrese de que toma las notas de cada respuesta y de que comprende la lógica subyacente en la respuesta. Más adelante, las tareas tratarán las opciones disponibles, y las ventajas y desventajas de cada opción.  Responder a estas preguntas le ayudará a seleccionar la opción que mejor se adapte a sus necesidades empresariales.

<!--HONumber=Apr16_HO2-->


