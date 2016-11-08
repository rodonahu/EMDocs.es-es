---
title: "Especificación de los requisitos de acceso"
description: "Requisitos comunes de acceso para el escenario de administración de dispositivos móviles."
keywords: 
author: YuriDio
manager: swadhwa
ms.date: 10/18/2016
ms.topic: solution
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 1cdc3cdf-cb71-46d5-99fd-05ec96771b81
ms.reviewer: 
ms.suite: ems
ms.custom: microsoft-intune
translationtype: Human Translation
ms.sourcegitcommit: cc449bca094772759983cc924b3294a4f6b44d83
ms.openlocfilehash: d95a2d9432bde2ef911802abcbe91637088c9adc


---

# Especificación de los requisitos de acceso

>[!NOTE]
>Este tema forma parte de una guía de consideraciones de diseño más extensa. Si desea comenzar por el principio de la guía, consulte el [tema principal](mdm-design-considerations-guide.md). Para obtener una copia descargable de toda esta guía, visite la [Galería de TechNet](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582).

Un dispositivo móvil que no puede utilizar aplicaciones u obtener acceso a datos de la compañía que son necesarios para realizar el trabajo no es útil para los empleados. Por lo tanto, es muy importante comprender cómo viajarán los datos desde la ubicación de origen (local o en la nube) al dispositivo móvil. 

Los datos se transmitirán entre los dispositivos móviles, y las consideraciones que deben aplicarse en cada ruta. Muchas compañías que tienen directivas de seguridad en su lugar no han tenido en cuenta cómo los dispositivos móviles pueden aumentar la probabilidad de que se produzca una pérdida en los datos de la compañía. Por lo tanto, revise las directivas de la compañía actual para asegurarse de que los requisitos que desarrolla para la autenticación, autorización y control de acceso se alineen con sus requisitos empresariales.
 
Responda a las preguntas siguientes para ayudar a determinar los requisitos de acceso para dispositivos móviles:

- Autenticación y autorización: como parte de la estrategia para permitir que los usuarios obtengan acceso a los datos de la compañía desde dispositivos móviles, debe identificar qué usuarios son aptos para el acceso. Algunas compañías deciden permitir inicialmente el acceso a datos solo a una parte de sus usuarios y, a continuación, conceder acceso a otros empleados a medida que lo solicitan, según las necesidades del negocio. Para restringir el acceso, la solución se debe autenticar (identificar que el usuario es quien dice ser) y autorizar (evaluar si el usuario debe tener acceso a los datos que solicitan) según la directiva de la compañía. 

Cuando diseñe la solución MDM, tenga en cuenta lo siguiente:

- ¿Su organización tiene un servicio de directorio actual que se utiliza para la autenticación y la autorización?
    - Si es así, ¿la solución MDM se integra con el servicio de directorio para autenticar y autorizar el acceso a los recursos?
    - ¿Su organización necesita tener una autenticación centralizada o puede ser híbrida?
    - ¿La organización planea disponer de la autenticación multifactor para usuarios móviles?
    - ¿Su organización utiliza una infraestructura de clave pública (PKI) local para emitir certificados?
        - Si es así, ¿la solución MDM tiene la capacidad de realizar la autenticación mediante certificados digitales?
            - Si es así, ¿la solución MDM tiene la capacidad de integrarse con una PKI local existente?
- ¿Su organización necesita utilizar los servicios de directorio actuales para autenticar a los usuarios que obtienen acceso a aplicaciones de terceros?
    - Si es así, ¿la solución MDM permite a los usuarios utilizar el inicio de sesión único (SSO) para realizar la autenticación en aplicaciones de terceros?


**Control de acceso**: una vez que un usuario está autenticado y autorizado, las solicitudes de acceso a un recurso deben validarse con el nivel de acceso del usuario. Este recurso solicitado puede ser datos o una aplicación. Cuando diseñe la solución, tenga en cuenta lo siguiente:

- ¿Su compañía debe tener un nivel diferente de control para que administre los dispositivos móviles y la solución MDM?
    - Si es así, ¿la solución MDM admite el Control de acceso basado en roles (RBAC)?
- ¿Necesita su compañía tener diferentes niveles de acceso según la ubicación del usuario?
    - Si es así, ¿la solución MDM le permite crear restricciones de control de acceso de acuerdo con la ubicación del usuario?
- ¿Su compañía necesita controlar el acceso a las aplicaciones?
    - Si es así, ¿la solución MDM le permite controlar el acceso a las aplicaciones instaladas en el dispositivo móvil?
- ¿Su compañía necesita controlar el acceso de acuerdo con un conjunto de condiciones?
    - Si es así, ¿la solución MDM le permite tener control de acceso condicional?
    - En caso afirmativo, ¿la solución MDM permite habilitar o deshabilitar la característica de la aplicación según la identidad del usuario?
    - En caso afirmativo, ¿la solución MDM permite administrar la atestación de dispositivo?

Lea [Acceso seguro a los recursos de la empresa desde cualquier lugar y en cualquier dispositivo](https://technet.microsoft.com/library/dn550982) para comprender mejor cómo aprovechar las funcionalidades de Windows Server 2012 R2 integradas con Configuration Manager para proporcionar acceso a los recursos de la compañía. 



<!--HONumber=Oct16_HO3-->


