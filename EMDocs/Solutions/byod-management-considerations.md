---
title: "Consideraciones para la administración"
description: "En este artículo se proporciona un conjunto de consideraciones de diseño de administración que debe usarse en un escenario de Bring Your Own Device."
keywords: 
author: YuriDio
ms.author: yurid
manager: swadhwa
ms.date: 11/28/2016
ms.topic: solution
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: ba8cc256-2075-457f-a827-7ec9213c5235
ms.reviewer: 
ms.suite: ems
ms.custom: microsoft-intune
translationtype: Human Translation
ms.sourcegitcommit: 5adb7f68efacdfa20d78c3cf5853fa374793140a
ms.openlocfilehash: da1652d5bb9a7b7176c74482bfc814aaf8902c3f


---

# <a name="management-considerations"></a>Consideraciones para la administración

Es imprescindible contar con un dominio de administración en una infraestructura que admita un modelo de BYOD. Para satisfacer por completo las exigencias de BYOD, es preciso que el dominio de administración permita al departamento de TI supervisar los recursos, proporcionar funcionalidades para la generación de informes, administrar los recursos de cálculo y almacenamiento, habilitar la configuración de dispositivos y la automatización, y administrar la implementación de aplicaciones y el aprovisionamiento.

## <a name="monitoring"></a>Seguimiento

Uno de los roles del dominio de administración es supervisar la configuración de cumplimiento de la normativa, no solo para los activos corporativos, sino también para los dispositivos móviles que pertenecen a los usuarios. Se deben evaluar los aspectos relativos al cumplimiento de la normativa de acuerdo a la línea de negocio de la compañía. Es posible que algunas empresas dejen que los datos residan en los dispositivos de los usuarios solo si están cifrados. El departamento de TI debe controlar la configuración de la seguridad para aplicar esas directivas.

El nivel de administración en los dispositivos de los usuarios variará según la directiva de la empresa y la infraestructura de BYOD que esta adopte. Si la empresa establece que es necesario proporcionar capacidad de borrado íntegro para tener acceso a sus recursos, el departamento de TI debe aplicar esta configuración en todos los dispositivos supervisados. Asimismo, el departamento de TI necesita capacidad para restablecer los dispositivos según los valores predeterminados del fabricante, eliminar toda la configuración personal y los datos si fuera necesario. Mediante la siguiente sección, podrá determinar las opciones de supervisión necesarias para la infraestructura de BYOD.

### <a name="monitoring-options-advantages-and-disadvantages"></a>Opciones de supervisión: ventajas y desventajas

Mediante la siguiente lista, podrá conocer las ventajas y desventajas de las opciones de supervisión:

- Agente de administración instalado en los dispositivos de los usuarios
    - Ventajas
        - Ofrece un mayor control de los dispositivos de los usuarios.
        - Incluye la función de borrado remoto.
        - Incluye la función de borrado selectivo.
        - La administración del ciclo de vida y de la implementación de las aplicaciones es más rápida.
    - Desventajas
        - Se necesita instalar un agente de administración en los dispositivos de los usuarios.
        - Resulta más intrusivo desde la perspectiva de los usuarios.
        - Requiere una infraestructura de administración back-end para admitir el agente.
- Agente de administración no instalado
    - Ventajas
        - No se instala ningún agente de administración en los dispositivos de los usuarios.
        - Solo se pueden aplicar las directivas desde la perspectiva de la aplicación (por ejemplo, ActiveSync).
    - Desventaja
        - Las opciones de las que dispone el departamento de TI para administrar los dispositivos son limitadas.

Como se observa en la tabla anterior, al diseñar la solución de infraestructura de BYOD, necesitará tener un agente instalado en los dispositivos de los usuarios si quiere aplicar la directiva de la empresa.

Si la empresa opta por ofrecer compatibilidad a distintos tipos de dispositivos, deberá saber cuáles son las capacidades de los dispositivos como, por ejemplo, el cifrado para el almacenamiento, las opciones de conectividad VPN y lenguajes de programación compatibles. Evalúe aquello que se puede implementar para cumplir las directivas de la empresa. La supervisión de los dispositivos con el fin de satisfacer los requisitos de cumplimiento de la normativa se puede llevar a cabo mediante la aplicación de directivas. Piense en poder habilitar el cifrado de dispositivos mientras los datos están almacenados en los dispositivos de los usuarios; esto le puede ayudar con la estrategia de fuga de datos. La implantación de directivas como el desbloqueo de contraseñas, el historial de contraseñas y las contraseñas seguras puede aportar el mismo grado de protección en el entorno local y en los dispositivos móviles.

La configuración del cumplimiento de la normativa en Configuration Manager hace posible que el departamento de TI administre la configuración y el cumplimiento de la normativa de los servidores, los equipos portátiles, los equipos de escritorio y los dispositivos móviles en la empresa. Piense en usar la configuración predeterminada para el cumplimiento de la normativa que se incorpora en Configuration Manager para dispositivos móviles como referencia y, a partir de ahí, personalícela según las necesidades de su empresa. Para obtener más información sobre la configuración de cumplimiento en Configuration Manager, consulte [Introducción a la configuración de cumplimiento en Configuration Manager](https://technet.microsoft.com/library/gg682139.aspx).

Si usa la eliminación selectiva de Windows, el departamento de TI podrá proteger los datos corporativos de la empresa que están dispersos en los dispositivos personales o corporativos. Los programadores pueden crear aplicaciones para usar una directiva de eliminación selectiva de Windows que se aplique a los datos y protegerlos en un dominio de Internet que pertenezca a la empresa. Para obtener más información sobre la función de borrado selectivo de Windows, consulte Windows Selective Wipe for Device Data Management (Borrado selectivo de Windows para la administración de datos de dispositivos).

## <a name="reporting"></a>Generación de informes

Para poder controlar los dispositivos conocidos, es fundamental que el departamento de TI realice informes sobre las capacidades de los dispositivos, o simplemente conozca el funcionamiento de los dispositivos. Los informes se pueden usar para tener una mejor comprensión del entorno actual. Estas son algunas preguntas que van a surgir cuando se intenta entender no solo el entorno, sino también las capacidades de algunos dispositivos móviles:

- ¿Cuántos dispositivos con iOS se usan en la organización?
- ¿Cuáles son las versiones de iOS que se ejecutan en estos dispositivos?
- ¿Qué aplicaciones corporativas están instaladas en los dispositivos?
- ¿Hay dispositivos pirateados en la organización?

Piense en usar una solución de administración que pueda proporcionar un inventario de los dispositivos e informes personalizables. Si elige esta opción, el departamento de TI podrá aplicar un enfoque más flexible cuando necesite detectar más información sobre los dispositivos de los usuarios. Es preciso que el departamento de TI pueda disponer de informes sobre todos los dispositivos que se hubieran registrado localmente y en la nube. La funcionalidad de elaboración de informes para el sistema de administración puede ubicarse localmente o en la nube, o bien puede ser una combinación de ambas, lo cual se denomina una solución híbrida. Use la siguiente tabla para determinar qué opción de elaboración de informes es la adecuada para su empresa.

### <a name="reporting-options-advantages-and-disadvantages"></a>Opciones de creación de informes: ventajas y desventajas

Mediante la siguiente lista, podrá conocer las ventajas y desventajas de las opciones relativas a la creación de informes:

- Local
    - Ventajas
        - Los informes se crean de forma centralizada.
        - El departamento de TI controla el proceso completo.
        - Se puede personalizar.
        - Los controles de seguridad se administran de forma local.
    - Desventajas
        - No se pueden enumerar de manera nativa los dispositivos que se encuentren en ubicaciones externas.
        - Se genera una mayor sobrecarga administrativa, en comparación con las soluciones basadas en la nube.
- Basado en la nube
    - Ventajas
        - Permite crear informes sobre los dispositivos que se hayan unido al servicio en la nube.
        - Resulta rentable.
        - Puede crear y ver los informes desde cualquier lugar.
        - El coste administrativo es inferior al de una solución local.
    - Desventajas
        - No se pueden enumerar de manera nativa los dispositivos que se encuentren en ubicaciones locales.
        - Normalmente, se requiere una suscripción mensual al servicio.
- Híbrido
    - Ventajas
        - Permite crear informes sobre los dispositivos que se hayan unido al servicio en la nube.
        - Resulta rentable.
        - Puede crear y ver los informes desde cualquier lugar.
        - Permite la integración con soluciones de administración locales.
    - Desventajas
        - Normalmente, se requiere una suscripción mensual al servicio.

Mediante la combinación de Microsoft Intune con System Center 2012 R2, puede crear informes desde dispositivos locales y basados en la nube. Configuration Manager incluye muchos informes listos para su uso e integrados para UDM, incluso informes de inventario de aplicaciones y de hardware y sobre la administración de la configuración. No se necesita crear informes personalizados o informes independientes para PC y administración de dispositivos móviles; estas funciones se pueden integrar.

Para obtener más información sobre las opciones de creación de informes de Configuration Manager, consulte [Introducción a los informes en Configuration Manager](https://technet.microsoft.com/library/gg682105.aspx).

## <a name="compute-and-storage"></a>Cálculo y almacenamiento

Después de desarrollar nuevas aplicaciones y de que los usuarios tengan acceso remoto a ellas a través de sus propios dispositivos, el rendimiento de la aplicación puede verse afectado si la solución no se han planeado correctamente. Aunque las indicaciones en esta guía de diseño no pretenden dar detalles minuciosos respecto al rendimiento, se debe dar respuesta a las preguntas sobre la infraestructura de administración:

- La solución de administración actual que usa la empresa ¿puede administrar los recursos de almacenamiento y cálculo para la plataforma que contiene las aplicaciones a las que se tiene acceso desde los dispositivos de los usuarios? 
- La solución de administración actual que usa la empresa ¿tiene la capacidad de aumentar los recursos de cálculo y almacenamiento para la plataforma que admite el acceso a las aplicaciones desde los dispositivos según un conjunto de reglas preestablecidas?
Si la solución de administración actualmente implementada no es capaz de abordar estos dos requisitos, piense en usar una solución de administración que pueda administrar el cálculo y el almacenamiento mediante la aplicación de los dos requisitos principales que se muestran en la siguiente tabla.

### <a name="compute-and-storage-management-capabilities-advantages-and-disadvantages"></a>Funciones de administración del cálculo y el almacenamiento: ventajas y desventajas

Mediante la siguiente lista, podrá conocer las ventajas y desventajas de las funciones de administración del almacenamiento:

- Agrupación de recursos
    - Ventajas
        - Puede asignar recursos agrupados para el cálculo y el almacenamiento desde distintas ubicaciones.
        - Alto nivel de disponibilidad.
        - Resulta más sólida que las soluciones incapaces de aprovechar la agrupación de recursos.
    - Desventajas
        - Pocas soluciones de administración pueden aprovechar la agrupación de recursos.
        - Es posible que la sobrecarga inicial para la implementación sea más alta si la empresa no usa aún principios de informática en la nube en su centro de datos.
- Elasticidad
    - Ventajas
        - Puede asignar de forma dinámica recursos agrupados para el cálculo y el almacenamiento en función de la demanda.
        - Ofrece un alto nivel de disponibilidad.
        - Resulta más fácil de administrar después de su implementación.
    - Desventajas
        - Pocas soluciones de administración pueden aprovechar la función de elasticidad.
        - Es posible que la sobrecarga inicial para la implementación sea más alta si la empresa no usa aún principios de informática en la nube en su centro de datos.

System Center 2012 R2 tiene la capacidad de usar la agrupación de recursos y la elasticidad para administrar el almacenamiento y el cálculo. System Center 2012 R2 también integra un almacenamiento con optimización de discos para reducir los requisitos de almacenamiento, ya que permite compartir un gran porcentaje de los datos del disco entre varios discos virtuales, lo que optimiza los costos de almacenamiento. Los servidores que se virtualizan mediante System Center 2012 R2 y que usarán las aplicaciones que utilizan los usuarios remotos pueden aprovechar esta tecnología.

Para obtener más información sobre las funciones de almacenamiento de System Center 2012 R2, consulte [Novedades de VMM en System Center 2012 R2](https://technet.microsoft.com/library/dn246490.aspx). 

## <a name="automation"></a>Automatización

Se puede aplicar la automatización para modificar los dispositivos que no cumplan la normativa y el departamento de TI puede asignar diferentes niveles de gravedad de incumplimiento. Es necesario tener en cuenta el uso de la automatización en las diferentes áreas de BYOD; por ejemplo, ¿cómo debería automatizar la implementación de nuevos servicios que usen los dispositivos móviles? Y ¿cómo debería automatizar el proceso de autorización para dispositivos móviles?

Pese a que comprobará que todos los subdominios de BYOD presentados pueden beneficiarse de la automatización, la responsabilidad de automatizar los recursos recae sobre el subdominio de administración. La automatización se puede integrar en el sistema operativo; sin embargo, la solución de administración que adopte la empresa es responsable de extender estas capacidades y aportar métodos para facilitar las tareas diarias del departamento de TI a la vez que supervisa los resultados de la automatización y genera informes al respecto.
La opción de automatización más eficaz en System Center 2012 R2 es Windows PowerShell. Para obtener más información sobre la automatización de System Center 2012 R2, consulte [Automatización de System Center con Windows PowerShell](https://technet.microsoft.com/library/dn507037(v=sc.20).aspx). Sin embargo, hay otra opción que proporciona una forma más sencilla, pero no muy fiable de automatizar tareas: la secuencia de tareas. Use la siguiente tabla para evaluar las ventajas y desventajas de cada opción.

### <a name="automation-options-advantages-and-disadvantages"></a>Opciones de automatización: ventajas y desventajas

Mediante la siguiente lista, podrá conocer las ventajas y desventajas de las opciones de automatización:

- Windows PowerShell
    - Ventaja
        - Se integra con el sistema operativo Windows.
        - Ofrece una mayor fiabilidad que la secuencia de tareas.
        - Se pueden usar scripts.
        - Puede usar principios de programación, como procedimientos, bucles y matrices.
        - Incluye funciones que se pueden usar fuera de la plataforma de administración.
    - Desventajas
        - Requiere un mayor conocimiento técnico para su uso.
        - En función de la tarea que se esté realizando, es posible que se necesite más tiempo para desarrollar el script de automatización inicial.
- Secuencia de tareas
    - Ventajas
        - Su uso resulta sencillo.
        - Se pueden utilizar funciones nativas en System Center.
    - Desventajas
        - La funcionalidad es limitada.
        - No admite scripts.
        - Las funciones se encuentran limitadas a algunas tareas del propio System Center.

## <a name="deployment-and-provisioning"></a>Implementación y aprovisionamiento

El siguiente paso es conocer las indicaciones para la implementación y el aprovisionamiento de aplicaciones en dispositivos remotos. Se debe dar respuesta a dos preguntas claves:

- ¿Cómo obtendrán acceso los usuarios a las aplicaciones desde sus propios dispositivos?
- ¿Cómo aprovisionará el departamento de TI estas aplicaciones para los usuarios de forma eficaz y descriptiva?

La solución de administración que adopte la empresa también debe ocuparse de la distribución y aprovisionamiento del software, independientemente de la plataforma que esté utilizando el usuario. Los usuarios podrán obtener un acceso seguro a las ubicaciones centralizadas desde sus dispositivos e instalar las aplicaciones que estén autorizados a usar para realizar su trabajo.

En este sentido, se presenta la dificultad de poder administrar plataformas diferentes con una interfaz de administración centralizada que permita al departamento de TI identificar rápidamente los dispositivos que estén conectados en entornos locales y en la nube. Debe tener en cuenta la adopción de una plataforma de administración que pueda consolidar ambos entornos (local y nube), así como una plataforma de administración que sea capaz de administrar sistemas de Windows y que no sean de Windows.

Para la administración centralizada local, puede usar Configuration Manager. Con esta opción, el equipo de TI podrá aprovechar la funcionalidad de inscripción Enterprise para inscribir dispositivos con el servidor de Configuration Manager de la empresa. Para obtener más información sobre cómo administrar dispositivos con Configuration Manager, consulte [Administrar dispositivos móviles con Configuration Manager y Microsoft Intune](https://technet.microsoft.com/library/jj884158.aspx).

Para administrar otras plataformas que no sean dispositivos basados en Windows, puede aprovechar el servicio en la nube Microsoft Intune. Se puede usar el portal de empresa de Microsoft Intune para inscribir, administrar e instalar aplicaciones con licencia. Los usuarios pueden obtener acceso fácilmente a las aplicaciones e instalarlas en sus dispositivos. 

>[!TIP] 
>Para obtener más información sobre Microsoft Intune, consulte la [página de Microsoft Intune](/intune/understand-explore/introduction-to-microsoft-intune). 

Pese a que se trata de dos opciones diferentes, puede integrar ambas para llevar a cabo la implementación y el aprovisionamiento de aplicaciones desde una sola ubicación. Use la siguiente tabla para identificar qué opciones se adaptan a su diseño BYOD.

| **Requisitos de diseño**                                             | **Opciones de implementación y aprovisionamiento**                |
|---------------------------------------------------------------------|--------------------------------------------------------|
| Implemente y aprovisione aplicaciones en dispositivos ubicados solo localmente.      | Microsoft System Center 2012                           |
| Implemente y aprovisione aplicaciones en dispositivos ubicados solo exteriormente.   | Microsoft Intune                                       |
| Implemente y aprovisione aplicaciones en dispositivos que no son de Windows.                   | Microsoft Intune                                       |
| Implemente y aprovisione aplicaciones en dispositivos ubicados solo en el entorno local, que se encuentren fuera de la empresa o que no sean de Windows.       | Integración de Microsoft Intune en Configuration Manager
                                                                    



<!--HONumber=Nov16_HO4-->


