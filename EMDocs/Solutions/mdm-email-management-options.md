---
title: "Opciones de administración de correo electrónico"
description: 
keywords: 
author: andredm7
manager: swadhwa
ms.date: 05/31/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 9b89da63-039f-4831-b204-28c0681478fe
ms.reviewer: 
ms.suite: ems
ms.sourcegitcommit: 73c37109735567642ff1dc11f9729e3ab3affd3b
ms.openlocfilehash: 208b478068e7757673edb76ff6f21b488c4559e2


---

# Opciones de administración de correo electrónico

>[!NOTE]
>Este tema forma parte de una guía de consideraciones de diseño más extensa. Si desea comenzar por el principio de la guía, consulte el [tema principal](mdm-design-considerations-guide.md). Para obtener una copia descargable de toda esta guía, visite la [Galería de TechNet](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582).

La razón principal para implementar una solución de administración de dispositivos móviles es normalmente proporcionar un acceso administrado al correo electrónico corporativo desde dispositivos móviles. Por ejemplo, en MDM para Office 365, puede crear una [directiva de seguridad](https://technet.microsoft.com/library/ms.o365.cc.newdevicepolicy.aspx) que proporcione acceso administrado básico a buzones de correo electrónico hospedados en Exchange Online o acceso a través de aplicaciones de Office (en iOS y Android). Esta directiva aplica la configuración de conformidad de dispositivos móviles básicos, como el requerimiento de una contraseña del dispositivo y el cifrado del dispositivo, para que el dispositivo pueda conectarse a un buzón de usuario.

Siga un proceso similar para configurar las opciones de administración de correo electrónico en Intune y las implementaciones híbridas de Intune y Configuration Manager. La principal diferencia es que puede implementar opciones más avanzadas de administración de correo electrónico en comparación con MDM para Office 365. Por ejemplo, mediante Intune independiente, puede configurar el acceso de correo electrónico condicional para permitir el acceso a los buzones alojados en Exchange Online y Exchange local, y configurar perfiles de correo electrónico personalizados. Intune habilita estas características mediante el uso de directivas de cumplimiento y configuración.  Las implementaciones híbridas de Intune y Configuration Manager también admiten el acceso de correo electrónico condicional, pero solo para buzones alojados en Exchange Online.

En el escenario que se muestra a continuación en la ilustración 6, el usuario se ha inscrito el dispositivo en Intune y ahora está tratando de obtener acceso a su correo electrónico corporativo con Office 365 o Exchange local. Según la configuración definida por el administrador de TI en su empresa, Intune ejecuta un proceso de comprobación de la directiva. En este escenario, se concede el acceso del usuario si el dispositivo está cifrado, se establece un código de acceso y no se ha aplicado el descifrado o el descodificado al dispositivo. Si un usuario obtener acceso a correo electrónico corporativo y su dispositivo no está inscrito, o no es conforme según la configuración definida por el administrador de TI, el usuario recibirá un correo electrónico que explicará el motivo por el que se ha bloqueado su acceso junto con los pasos para resolver el problema. 

![Acceso condicional](./media/MDM_Figure_06.png)

**Acceso condicional**

Las respuestas a las preguntas del paso 1 pueden ayudarle a determinar cómo desea que los dispositivos se administren en la solución de administración de dispositivos móviles. La lista siguiente describe ventajas y desventajas de la administración de correo electrónico en cada solución MDM.

## Intune (independiente)

**Ventajas**

- Admite la a
dministración de correo electrónico para todos los sistemas operativos de dispositivos móviles principales (Android, iOS, Windows 10, Windows 8.x y Windows Phone)
- Puede aprovechar las aplicaciones de correo electrónico de dispositivos móviles nativas mediante la integración con Exchange ActiveSync.
- Integración con Exchange Online a través del conector de servicio a servicio para permitir la supervisión e informes multiplataforma entre Intune y Office 365.
- Admite la configuración de perfiles de correo electrónico para la administración de la configuración basada en Exchange ActiveSync en dispositivos móviles.
- Acceso condicional de correo electrónico a los recursos

**Desventajas**

- No se admiten los perfiles de correo electrónico para dispositivos móviles basados en Android

## MDM para Office 365

**Ventajas**

- Permite la compatibilidad de Exchange ActiveSync con contraseña, cifrado y cumplimiento del dispositivo liberado.
- Permite las directivas de administración de dispositivos y la inscripción necesaria de dispositivos antes de que se conceda el acceso a las aplicaciones OneDrive para la Empresa y Office (Android e iOS)
- Acceso condicional de correo electrónico a los recursos

**Desventajas**

- No se admiten algunas opciones de administración de correo electrónico avanzadas 
- La implementación de perfiles de correo electrónico no es compatible (excepto iOS)

## Híbridas (Intune con Configuration Manager)

**Ventajas**

- Conector local de Intune para la conectividad híbrida con Exchange Online.
- Integración con Exchange ActiveSync (se aplica la configuración de directiva más estricta).
- Perfiles de correo electrónico
- Acceso condicional para restringir el acceso de correo electrónico a Exchange Online.
- Las directivas de conformidad para definir las reglas y la configuración del dispositivo deben cumplirse para que se permita el acceso a los servicios
- Las directivas de acceso condicional para cada servicio definen las reglas de grupos de seguridad, grupos de Intune y la forma en la que se administran los dispositivos no inscritos

**Desventajas**

- Acceso administrado solo al correo electrónico disponible para buzones hospedados en Exchange Online, no buzones hospedados en Exchange local.
- La configuración del conector de servicio a servicio no debe configurarse si habilita el acceso condicional para Exchange Online y Exchange local.

Explore los detalles acerca de las opciones de administración de la configuración de correo electrónico de dispositivos móviles revisando lo siguiente:

- Intune: cómo [habilitar perfiles de correo electrónico](/Intune/deployuse/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune) y el [acceso a correo electrónico condicional](/Intune/deployuse/restrict-access-to-email-and-o365-services-with-microsoft-intune)
- Configuration Manager: habilitación de [perfiles de correo electrónico](https://technet.microsoft.com/library/dn554227.aspx) y [acceso a correo electrónico condicional](https://technet.microsoft.com/library/dn919655.aspx)
- MDM para Office 365: [funcionalidades de administración de dispositivos móviles](https://technet.microsoft.com/library/ms.o365.cc.devicepolicysupporteddevice.aspx)


<!--HONumber=Jun16_HO1-->


