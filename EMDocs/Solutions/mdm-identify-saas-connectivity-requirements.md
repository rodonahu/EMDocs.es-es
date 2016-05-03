---
# required metadata

title: Identificación de los requisitos de conectividad de SaaS
description:
keywords:
author: robmazz
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: 6afbce4c-7500-4387-a19c-dff52c152097

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: 
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Identificación de los requisitos de conectividad de SaaS

>[!NOTE]
>Este tema forma parte de una guía de consideraciones de diseño más extensa. Si desea comenzar por el principio de la guía, consulte el [tema principal](mdm-design-considerations-guide.md). Para obtener una copia descargable de toda esta guía, visite la [Galería de TechNet](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582).

La forma en la que conecta su infraestructura local afectará a la forma en la que se administra la identidad del dispositivo y del usuario con soluciones de MDM: Intune, MDM para Office 365, e implementaciones híbridas de Intune y Configuration Manager. Intune y MDM para Office 365 aprovechan la arquitectura de servicios de directorio que proporcionan los Servicios de Azure Active Directory. Esta integración con Azure proporciona una gran flexibilidad cuando diseña la compatibilidad de administración de identidades en su solución de administración de dispositivos móviles.

Como se muestra en la lista siguiente, la conexión con los servicios de directorio locales con Azure es el requisito clave para la habilitación del inicio de sesión único y la administración de cuentas de directorios unificada. El inicio de sesión único hace que los usuarios puedan conectarse mucho más fácilmente a los recursos de la compañía en local y en la nube. Es mucho más fácil para los administradores tener un único lugar en el que administrar cuentas. Para el acceso móvil, la sincronización de credenciales y atributos de cuenta de directorios entre Azure y servicios de directorios locales permite a los usuarios realizar la autenticación en los dispositivos móviles para obtener acceso a los recursos administrador por MDM para Office 365 o Intune.

![Información general de la administración de identidades integrada](./media/MDM_Figure_15.png)

**Información general de la administración de identidades integrada**

Según como haya respondido a las preguntas de Tarea 2, podrá determinar la forma en la que la solución de SaaS necesita conectarse a la plataforma de administración de clientes local para la solución de administración de dispositivos móviles. Las listas siguientes le ayudarán a comprender las ventajas y desventajas de la conexión a la infraestructura local con la solución de SaaS.

## Intune (independiente)

**Ventajas**

- Integración estrecha con Azure Active Directory para la administración de la autenticación y la identidad de dispositivos y usuarios.
- Compatible con experiencias de inicio de sesión único y administración automática de credenciales de usuario que pueden aprovechar las credenciales de cuentas locales existentes
- Compatible con el acceso de inicio de sesión único a miles de aplicaciones de SaaS preintegradas.
- Compatible con la seguridad de acceso de la aplicación aplicando la autenticación multifactor (MFA) basada en reglas para aplicaciones en la nube y locales

**Desventajas**

- Las funcionalidades y características de conectividad de servicios de directorios avanzada requieren una sincronización con Azure Active Directory Premium.

## MDM para Office 365

**Ventajas**

- Se integra con los inquilinos de Office 365, que utilizan la red troncal de Azure Active Directory para administrar la autenticación e identidad de usuarios y dispositivos.
- Se pueden conectar servicios de directorio locales como parte de los servicios de conexión con Office 365.
- Compatible con experiencias de inicio de sesión único y administración automática de usuarios que pueden aprovechar las credenciales de cuentas locales existentes
- Admite la autorización multifactor de inscripciones de dispositivos mediante el servicio Azure MFA.

**Desventajas**

- No compatible con la integración de la administración de aplicaciones móviles con otras aplicaciones o soluciones de SaaS

## Híbridas (Intune con Configuration Manager)

**Ventajas**

- Todas las ventajas de Intune independiente, además de las siguientes:
 - Integración directa con servicios de directorio locales a través de la infraestructura de Configuration Manager.

**Desventajas**

- Para las organizaciones que no tienen una infraestructura de Configuration Manager en estos momentos, habrá que planificarla, instalarla y configurarla antes de su integración con Intune.
- Requiere los requisitos de implementación locales y cambios de configuración para las organizaciones con Configuration Manager.

<!--HONumber=Apr16_HO2-->


