---
title: "Escenarios de productividad móvil administrada"
description: "El enfoque moderno de Microsoft con EMM proporciona una administración inigualable de las aplicaciones de Office 365 y permite que su equipo realice su mejor trabajo en cualquier dispositivo mientras se mantienen seguros los datos de la empresa."
keywords: 
author: jeffgilb
manager: swadhwa
ms.date: 09/16/2016
ms.topic: article
ms.prod: 
ms.service: ems
ms.technology: 
ms.assetid: 452d7991-fa90-4100-afc4-47c4e7b18949
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e90ab882127f59e73eb739f073b96d80f4c0e429
ms.openlocfilehash: 72bed249099bd40a15e06d0ef7250ac87364cf1b


---

# Escenarios de productividad móvil administrada de EMS
Microsoft Enterprise Mobility + Security adopta un enfoque moderno de la administración de la movilidad y proporciona una administración inigualable de las aplicaciones de Office 365 para permitir que su equipo realice su mejor trabajo en cualquier dispositivo mientras se mantienen seguros los datos de la empresa. Por supuesto, antes de iniciar las tareas de implementación, debe saber lo que quiere hacer. Para comenzar a implementar EMS para escenarios de productividad móvil, necesitará tener algunos objetivos empresariales bien definidos y comprender cómo pueden ayudarle las características y servicios de EMS a cumplirlos. Esto es fundamental cuando se es totalmente profano en Enterprise Mobility o al migrar desde otro producto.

La mejor manera de ponerse de acuerdo en torno a las tareas de implementación de EMS con objetivos empresariales es expresar lo que se pretende lograr en lo relativo a los escenarios que se quieren habilitar para los empleados, partners y TI.  A continuación, se muestra una breve introducción de los escenarios más comunes de productividad móvil administrada que se basan en Intune, junto con los vínculos para obtener más información sobre cómo implementar realmente cada uno de ellos.

>[!NOTE]
>¿Quiere saber cómo el equipo de TI de Microsoft usa Intune para permitir que los empleados de Microsoft tengan acceso a los recursos corporativos en sus dispositivos móviles y, al mismo tiempo, tener protegidos los datos corporativos? [Lea este caso práctico técnico](https://www.microsoft.com/itshowcase/Article/Content/588) para ver en detalle cómo el equipo de TI de Microsoft usa Intune y otros servicios para administrar identidades, dispositivos, aplicaciones y datos.

## Acceso seguro y proteger los datos empresariales de Office 365 en dispositivos administrados con Microsoft Intune
Usar Intune para proteger los datos corporativos almacenados en Office 365 (correo electrónico, documentos, mensajes instantáneos, etc.) no podría ser más fácil ni más fluido para los usuarios. Intune proporciona una solución de acceso condicional integrada de forma única que garantiza que ningún usuario puede tener acceso a los datos de Office 365 a menos que reúna los requisitos de cumplimiento de la empresa (como pueda ser realizar una autenticación multifactor (MFA), inscribir su dispositivo en Intune, usar aplicaciones administradas, una versión de sistema operativo compatible, un PIN de dispositivo, etc.). Las aplicaciones móviles de Office 365 que están disponibles en sus respectivas tiendas de aplicaciones incluyen características de contención de datos diseñadas específicamente para configurarse con Intune. Estas características le permiten evitar que los datos se compartan en las aplicaciones (por ejemplo, aplicación de correo electrónico nativa) y en las ubicaciones de almacenamiento (por ejemplo, Dropbox) que no se administran mediante TI. Toda esta funcionalidad se crea directamente en Office 365 de forma que no tenga que implementar ni administrar ninguna infraestructura adicional para obtener este valor.

Más información: [Acceso seguro y proteger los datos empresariales de Office 365 con Intune](https://docs.microsoft.com/intune/understand/secure-office365-data-with-intune).


## Acceso seguro y proteger los datos empresariales locales con Intune
La mayoría de las estrategias de movilidad empresarial comienzan con un plan para permitir que los dispositivos móviles de los empleados tengan acceso de forma segura al correo electrónico de la empresa y a los datos locales almacenados en los servidores de aplicaciones, como Microsoft Exchange, que se hospedan en su red corporativa. Intune proporciona una solución de acceso condicional integrada de manera exclusiva para Exchange Server que garantiza que ninguna aplicación móvil puede tener acceso al correo electrónico hasta que el dispositivo esté inscrito con Intune y cumpla las directivas de la empresa. Y lo hace sin tener que implementar otro equipo de la puerta de enlace en el extremo de la red corporativa.

Además del correo electrónico, Intune permite el acceso a aplicaciones móviles que precisan de un acceso seguro a datos locales, como puede ser una línea de servidor de aplicaciones de negocio. Esto se suele realizar mediante certificados administrados por Intune para el control de acceso, combinado con un proxy o una puerta de enlace de VPN estándar en el perímetro (como, por ejemplo, el proxy de aplicación de Microsoft Azure AD). En estos casos, la única manera de tener acceso a los datos corporativos es inscribir el dispositivo en la administración. Una vez inscrito, Intune garantiza que los dispositivos que tienen acceso a los datos corporativos cumplan con las directivas en vigor.  También se puede usar el SDK de aplicaciones y la herramienta de ajuste de aplicaciones de Intune para contener los datos a los que se ha tenido acceso dentro de la aplicación de línea de negocio, de forma que no se puedan pasar a servicios o aplicaciones de consumidor sin administrar.

<!-- Learn more -->


## Acceso seguro y proteger los datos empresariales de Office 365 en dispositivos no administrados con Intune
Una práctica común de implementación de Office 365 es exigir que los dispositivos estén inscritos en la administración si se tienen que aprovisionar completamente con configuraciones de aplicaciones/certificados/Wi-Fi/VPN corporativos, que suele ser el caso de los dispositivos de propiedad corporativa. En cambio, si el usuario simplemente necesita tener acceso a los documentos y al correo electrónico de la empresa, que es normalmente el caso de los dispositivos de propiedad personal, pueden usar las aplicaciones móviles de Office 365 y omitir por completo la inscripción de su dispositivo. En esta situación, Intune puede usarse para permitir que sus empleados, proveedores y partners tengan acceso de manera segura y sin esfuerzo a los datos de la empresa desde sus dispositivos no administrados.

Las directivas de restricción de datos de Intune para los dispositivos no administrados le ayudan a mantener el control de quién y qué aplicaciones pueden tener acceso a los datos de Office 365 con las eficaces funcionalidades de prevención de pérdida de datos. No importa si el dispositivo ya está siendo administrado por una solución MDM que no sea de Microsoft. De hecho, puede seguir usándola si quiere y seguir agregando las funcionalidades avanzadas de prevención de pérdida de datos y control de acceso de las aplicaciones móviles de Office 365 que Intune proporciona en la parte superior. De cualquier manera, al proteger los datos de la empresa sin necesidad de inscripción, ahorrará dinero sin necesitar mantener los servidores y también conseguirá un porcentaje superior de usuarios que cumplan con las directivas de la empresa sin que tengan que permitir que TI administre sus dispositivos personales.

<!-- Learn more -->


## Habilitar un programa BYOD en su organización
BYOD es cada vez más popular entre las organizaciones como forma de reducir los costos de hardware o de aumentar las opciones de productividad móvil de los empleados. A día de hoy, casi todo el mundo tiene un smartphone personal, así que, ¿qué necesidad hay de darles otro? El desafío más importante ha sido siempre convencer a los empleados para que inscriban sus propios dispositivos personales en la administración, ya que temen que el departamento de TI pueda verlos y controlarlos. Cuando la inscripción de dispositivos no es una opción viable, Intune ofrece un método alternativo de BYOD con el que simplemente se administran las aplicaciones que contengan datos corporativos. Intune protege los datos corporativos incluso cuando la aplicación en cuestión tiene acceso a datos personales y a datos corporativos, como ocurre en las aplicaciones móviles de Office.  Como administrador, puede obligar a que los usuarios tengan acceso a Office 365 desde las aplicaciones móviles de Office, así como configurar las aplicaciones con directivas que mantengan los datos protegidos (cifrados, protegidos con PIN, etc.).

<!-- Learn more -->


## Administrar los dispositivos propiedad de la empresa con Intune
Hoy en día, la mayoría de los trabajadores de información son móviles y necesitan ser productivos al usar los dispositivos móviles propiedad de la empresa. Estos empleados necesitan un acceso ininterrumpido a todos los datos y aplicaciones corporativas, en cualquier momento y lugar, mientras que usted necesita garantizar que los datos corporativos son seguros y los costos administrativos se mantienen bajos.

Para TI, intentar mantenerse mediante la inscripción manual de muchos dispositivos móviles propiedad de la empresa, de uno en uno, puede suponer un reto difícil. Para solucionar este problema, Intune ofrece soluciones de aprovisionamiento masivo y administración que se integran con las plataformas de administración de dispositivos corporativos más importantes del mercado; incluidos el Programa de inscripción de dispositivos de Apple y la plataforma de seguridad móvil Samsung KNOX.  La creación centralizada de configuraciones de dispositivos con Intune hace posible que el aprovisionamiento de dispositivos corporativos se automatice en un alto grado y le ahorre mucho tiempo.

Intune le facilita que proporcione un nuevo dispositivo de marca propiedad de la empresa a un empleado que le guíe a través del flujo de configuración de marca corporativa al activarlo y que configure sin problemas el dispositivo con directivas de seguridad para proteger los recursos empresariales (cifrar el disco duro, PIN del dispositivo, etc.), las directivas de configuración que ayuden a que sea productivo (correo electrónico/Wi-Fi/VPN/perfiles de certificado) y un conjunto de aplicaciones de línea base. Tras ello, el empleado puede usar la aplicación de portal de empresa de Intune para tener acceso a una serie de aplicaciones corporativas opcionales disponibles. Y lo mejor es que todo esto se realiza sin que tenga que hacer nada después de entregárselo.

<!-- Learn more -->

## Alinear una implementación de EMS Windows 10 y una estrategia de administración con necesidades empresariales
EMS le proporciona la flexibilidad, mediante procesos de ciclo de vida de administración tradicional y moderna, para elegir cómo implementar y administrar mejor Windows 10 en su organización. Puede seguir usando System Center Configuration Manager para implementar y administrar dispositivos de Windows 10 con controles de directiva avanzada o administrarlos desde la nube solo con Intune para una administración de dispositivos modernos. De hecho, incluso puede usarlos con MDM híbrida y tener algunos dispositivos que usan la administración basada en un agente con Configuration Manager mientras otros se administran por Intune mediante OMA-DM y MDM.

<!-- Learn more -->


## Habilitar una solución de dispositivos compartidos de uso limitado con Intune
A veces, los empleados necesitan usar dispositivos, aplicaciones o exploradores que no se pueden administrar, como los equipos públicos de ferias y hoteles. ¿Conviene dejar que los empleados tengan acceso al correo electrónico corporativo desde esos equipos? Los trabajadores de tareas también usan las tecnologías móviles cada vez más. Por ejemplo, ahora las tabletas compartidas están al orden del día entre los empleados de los comercios al por menor. Proteger los datos empresariales y la simplicidad de la experiencia del usuario es fundamental en estos casos. Por este motivo, las tabletas se suelen entregar a los empleados en un modo de uso limitado, de forma que solo puedan interactuar con una única aplicación de línea de negocio. Intune permite aprovisionar de forma masiva, proteger y administrar centralmente estas tabletas de iOS y Android compartidas o de tipo quiosco configurándolas para que funcionen en este modo de uso limitado.

<!-- Learn more -->

### Obtener más información



<!--HONumber=Oct16_HO1-->


