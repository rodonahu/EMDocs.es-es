---
title: "Desarrollo de la estrategia de adopción de administración de dispositivos móviles"
description: "En este artículo se proporciona una serie de consideraciones de diseño para adoptar la administración de dispositivos móviles en su organización."
keywords: 
author: YuriDio
ms.author: yurid
manager: swadhwa
ms.date: 11/28/2016
ms.topic: solution
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 10172816-b52d-4a55-8803-6a6805126fab
ms.reviewer: 
ms.suite: ems
ms.custom: microsoft-intune
translationtype: Human Translation
ms.sourcegitcommit: 5adb7f68efacdfa20d78c3cf5853fa374793140a
ms.openlocfilehash: 925d3c462ff0010f3aea03dd35a5ba6f78bf9894


---

# <a name="develop-your-mobile-device-management-adoption-strategy"></a>Desarrollo de la estrategia de adopción de administración de dispositivos móviles

>[!NOTE]
>Este tema forma parte de una guía de consideraciones de diseño más extensa. Si desea comenzar por el principio de la guía, consulte el [tema principal](mdm-design-considerations-guide.md). Para obtener una copia descargable de toda esta guía, visite la [Galería de TechNet](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582).

En esta tarea, desarrollará la estrategia de adopción de administración de dispositivos móviles que satisfará los requisitos empresariales identificados en las Tareas 1 y 2. 

## <a name="device-ownership"></a>Propiedad del dispositivo

Después de revisar la directiva actual y la estrategia de la organización para administrar dispositivos, debe tener una lista de escenarios que su organización tiene previsto implementar. La sección siguiente le ayudará a comprender las ventajas y desventajas de cada escenario:

## <a name="employee-owns-the-device-byod"></a>El empleado posee el dispositivo (BYOD)

**Ventajas** 

- La compañía no necesita comprar dispositivos móviles para los empleados
- Por lo general, permite que los empleados sean más productivos, ya que van a usar el dispositivo móvil que elijan
- Los costes de soporte técnico pueden reducirse puesto que la organización tendrá un soporte técnico limitado sobre los dispositivos móviles

**Desventajas**

- Aumenta la cantidad de consideraciones de seguridad para proteger los datos de la compañía que se encuentran en dispositivos personales
- Aumenta la probabilidad de pérdida de datos, especialmente cuando los controles de seguridad adecuados no están en su lugar
- Capacidad de administración limitada debido a restricciones de privacidad

## <a name="company-owned-device"></a>Dispositivo propiedad de la compañía

**Ventajas** 

- Capacidad de administración completa, incluidos los controles de seguridad y refuerzo de dispositivo
- Más control de los dispositivos móviles
- Capacidad de definir qué dispositivos móviles usarán los empleados

**Desventajas**

- Posibles aumentos en los costes de soporte técnico, ya que la organización mantendrá los dispositivos móviles
- Menos flexibilidad para los usuarios finales, que puede afectar a su productividad
- Incremento de los costes, ya que la organización tendrá que comprar los dispositivos móviles

En algunos escenarios, las organizaciones adoptarán ambos modelos: BYOD y dispositivos propiedad de la compañía. En ese caso, la plataforma de administración de dispositivos debe ser capaz de administrar múltiples plataformas mientras se integra con la infraestructura local actual. Si su organización se ajusta en este escenario, asegúrese también de que las directivas de seguridad puedan abarcar ambos modelos desde la perspectiva de cumplimiento. Pueden aplicarse requisitos diferentes en cada modelo y la solución de administración de dispositivos móviles tiene que poder controlar los dos modelos al mismo tiempo que permitir mantener el control del departamento de TI.

## <a name="supported-mobile-device-platforms"></a>Plataformas de dispositivos móviles compatibles

La decisión adoptada con respecto a la propiedad del dispositivo le ayudará a identificar qué plataformas de dispositivos móviles serán compatibles. La solución de administración de dispositivos móviles que elija tendrá que dar cabida a esta decisión. En un escenario de plataforma de dispositivo móvil, la elección de plataforma no será tan relevante como en el escenario de multiplataforma. Utilice la siguiente sección para ayudarle a elegir la solución de administración de dispositivos móviles para un escenario multiplataforma:

### <a name="intune-standalone"></a>Intune (independiente)

**Ventajas**

- Servicio siempre en la nube que es compatible con las últimas características MDM y actualizaciones
- Admite el aprovisionamiento de todos los sistemas operativos de dispositivos móviles principales (Android, iOS, Windows 8, Windows 10 y Windows Phone).
- Le permite administrar cualquier dispositivo móvil desde cualquier ubicación
- Opciones de administración más avanzadas para dispositivos móviles
- [Administración de aplicaciones móviles](http://blogs.technet.com/b/microsoftintune/archive/2015/06/18/now-available-intune-mobile-application-management-and-conditional-access-for-outlook.aspx)

**Desventajas**

- La falta de integración con la solución de administración de dispositivos actual con ubicación local incorporará una interfaz de administración adicional que puede usar
- Las directivas creadas con la solución MDM local no se replican en el servicio en la nube

### <a name="mdm-for-office-365"></a>MDM para Office 365

**Ventajas**

- Se integra con Office 365.
- Si ya está usando Office 365, se aprovechan fácilmente las funcionalidades de MDM para administrar dispositivos móviles.
- Si ya usa Office 365, no tendrá que utilizar otra consola para administrar dispositivos móviles.

**Desventajas**

- Conjunto de capacidades limitado (consulte la nota que sigue a esta tabla) para administrar dispositivos móviles
- La falta de integración con la solución de administración de dispositivos actual con ubicación local incorporará una interfaz de administración adicional que puede usar

### <a name="hybrid-intune-with-configmgr"></a>Híbridas (Intune con Configuration Manager)

**Ventajas**

- Integración nativa entre Intune y Configuration Manager.
- Le permite usar una consola centralizada para implementar directivas y administrar PC locales, servidores y dispositivos móviles

**Desventajas** 

- Requiere realizar más pasos de configuración para conectar Intune y Configuration Manager.
- Si la organización no dispone de una infraestructura de Configuration Manager local en estos momentos, habrá que planificar, instalar y configurar esta plataforma antes de la integración.

Si solo necesita administrar el acceso para trabajar con correos electrónicos, calendarios, contactos y tareas de los dispositivos móviles, consulte [Directivas de Exchange ActiveSync para administrar dispositivos en Office 365](https://technet.microsoft.com/library/dn792010.aspx#tasks).

## <a name="application-requirements"></a>Requisitos de aplicaciones

En función de los requisitos que se definieron en Tarea 1, puede elegir qué solución de administración de dispositivos móviles se adapta mejor a su organización. Use la siguiente tabla para comparar las opciones de MDM, así como las ventajas y desventajas de cada opción.


### <a name="intune-standalone"></a>Intune (independiente)

**Ventajas**

- Le permite administrar aplicaciones móviles a través de su ciclo de vida, incluida la implementación aplicaciones desde los archivos de instalación y las tiendas de aplicaciones, una supervisión detallada del estado de las aplicaciones y la eliminación de las aplicaciones. Para obtener más información, consulte Implementar aplicaciones en dispositivos móviles en Microsoft Intune.
- Le permite especificar una lista de aplicaciones compatibles que los usuarios pueden instalar y aplicaciones no compatibles, que los usuarios no deben instalar. Para obtener más información, consulte Configuración de directivas de configuración de iOS en Microsoft Intune.
- Permite configurar restricciones para las aplicaciones mediante una directiva de administración de aplicaciones móviles. Esto contribuye a aumentar la seguridad de los datos de su empresa mediante la restricción de operaciones como la funcionalidad de copiar y pegar, la realización de copias de seguridad externas de los datos y la transferencia de datos entre las aplicaciones. Para obtener más información, consulte Proteger datos mediante las directivas de administración de aplicaciones móviles con Microsoft Intune.
- Es compatible con distintas plataformas móviles. Obtenga información sobre los dispositivos móviles que admiten funcionalidades de administración de dispositivos móviles en Microsoft Intune.
- Se puede controlar qué aplicaciones están disponibles para los usuarios de VPN. Puede seleccionar las aplicaciones que se conectan automáticamente a la red corporativa a través de VPN mediante la creación de una lista de aplicaciones al configurar el perfil de VPN
- Admite directivas de administración de aplicaciones móviles (MAM) que ayudan a evitar que los datos corporativos se filtren a las aplicaciones o los servicios de los consumidores.
- Intune MAM ayuda al departamento de TI a permitir el acceso seguro a los datos corporativos de SaaS (como Office 365) para partners, contratistas y proveedores sin tener que administrar sus dispositivos.


**Desventajas**

- Falta de integración con soluciones de administración de dispositivos locales, que incluye una interfaz de administración adicional que puede usar cuando administre dispositivos móviles si dispone de una solución local. 
- Las directivas creadas con la plataforma MDM local no se replican en el servicio en la nube, que requiere dos conjuntos de directivas de administración y cumplimiento (si tiene una solución MDM local).


### <a name="mdm-for-office-365"></a>MDM para Office 365

**Ventajas**

- Proporciona funcionalidades MDM en plataformas de sistema operativo, como requisitos de contraseña.                                                                                                                                                                                                                                                                                                                                                           

**Desventajas**

- Conjunto limitado de capacidades para controlar las aplicaciones
- Falta de integración con soluciones de administración de dispositivos locales, que incluye una interfaz de administración adicional que puede usar cuando administre dispositivos móviles si dispone de una solución local.
- No se pueden implementar aplicaciones y aplicar funcionalidades de administración de aplicaciones móviles.


### <a name="hybrid-intune-with-configmgr"></a>Híbridas (Intune con Configuration Manager)

**Ventajas**

- Hereda la configuración de control de aplicaciones de Intune independiente.
- Proporciona una experiencia de administración integrada (entre Intune y Configuration Manager).
- Aprovecha las capacidades de administración de aplicaciones de Configuration Manager. Para obtener más información, consulte Administración de aplicaciones en Configuration Manager.
- Aprovecha las capacidades de administración de aplicaciones de Configuration Manager. Para obtener más información, consulte Administración de aplicaciones en Configuration Manager.
- Le permite usar una única consola para implementar directivas y administrar directivas de aplicación para dispositivos móviles, servidores y PC locales.
- Se puede controlar qué aplicaciones están disponibles para los usuarios de VPN. Puede seleccionar las aplicaciones que se conectan automáticamente a la red corporativa a través de VPN mediante la creación de una lista de aplicaciones al configurar el perfil de VPN.

**Desventajas**

- Requiere realizar más pasos para configurar la integración.
- Si la organización no dispone de una infraestructura de Configuration Manager local en estos momentos, habrá que planificar, instalar y configurar primero la plataforma de Configuration Manager.
- Sin integración con Intune, Configuration Manager tiene una solución de administración de dispositivos móviles limitada, basada en las plataformas de dispositivo móvil compatibles. Para obtener más información, consulte Determinar cómo administrar dispositivos móviles en Configuration Manager.


## <a name="track-requirements"></a>Seguimiento de los requisitos

Comprender el comportamiento del usuario e identificar su ubicación son factores importantes que incluir en su estrategia de administración de dispositivos móviles. ¿Cómo variarán los dispositivos de los que se realiza el seguimiento según las necesidades y requisitos empresariales?  Existen capacidades de seguimiento diferentes en cada sistema operativo móvil, por lo que las plataformas de dispositivos móviles que elija para que sean compatibles afectarán a sus opciones. Por ejemplo, los requisitos de cumplimiento pueden influir en dar prioridad a la adopción de plataformas de dispositivos móviles que permiten realizar un seguimiento de la ubicación del usuario y usar el perímetro.

>[!TIP] 
> El perímetro le permite supervisar una ubicación geográfica del dispositivo móvil y habilitar o deshabilitar recursos de red y del dispositivo según la ubicación. Por ejemplo, Windows 8.1 permite que una aplicación defina una región geográfica y que el sistema alerte a la aplicación cuando el dispositivo se ejecute en esa área o entre o salga de ella. Para obtener más información acerca de esta característica en Windows 8.1, consulte [Geovalla, de principio a fin (XAML)](https://msdn.microsoft.com/library/windows/apps/xaml/dn342943.aspx). 





<!--HONumber=Nov16_HO4-->


