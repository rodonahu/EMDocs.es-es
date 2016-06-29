---
# required metadata

title: Opciones de administración de conectividad de red
description:
keywords:
author: andredm7
manager: swadhwa
ms.date: 05/31/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: bc7cdb8f-3485-45ae-9493-f840ad9ed3ea

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: 
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Opciones de administración de conectividad de red

>[!NOTE]
>Este tema forma parte de una guía de consideraciones de diseño más extensa. Si desea comenzar por el principio de la guía, consulte el [tema principal](mdm-design-considerations-guide.md). Para obtener una copia descargable de toda esta guía, visite la [Galería de TechNet](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582).

Dependiendo de la infraestructura, los dispositivos móviles podrían conectarse a recursos corporativos desde una variedad de servicios de conectividad de Internet, que normalmente están protegidos mediante extremos con VPN.

Mediante [Intune](/Intune/deployuse/wi-fi-connections-in-microsoft-intune) o una [implementación híbrida](https://technet.microsoft.com/library/dn261221.aspx) con Configuration Manager, puede implementar perfiles de Wi-Fi para realizar el aprovisionamiento de redes Wi-Fi, por lo que un dispositivo puede conectarse automáticamente a la red cuando se encuentra en el intervalo. Por ejemplo, los dispositivos móviles pueden configurarse para conectarse a una red Wi-Fi segmentada en una sala de conferencias, pero después cambie la conexión a un segmento de red Wi-Fi al desplazarse a una ubicación diferente. Los usuarios no tienen que escribir contraseñas ni elegir una red; la conexión funciona automáticamente.

[Intune](/Intune/deployuse/vpn-connections-in-microsoft-intune) y [Configuration Manager](https://technet.microsoft.com/library/dn261217.aspx) también pueden implementar perfiles de VPN directamente en dispositivos móviles para que el usuario pueda obtener acceso a recursos corporativos internos sin un trabajo manual o una configuración adicionales. Además, Intune puede configurar dispositivos móviles para iniciar automáticamente una conexión VPN basada en el recurso de tipo o el método de acceso. Sin embargo, tenga en cuenta que existen distintos requisitos de configuración para hacer esto en diferentes tipos de sistemas operativos de dispositivos móviles.

Las respuestas a las preguntas en Tarea 3 pueden ayudarle a determinar cómo desea que los dispositivos se conecten a recursos corporativos. Tenga en cuenta que, actualmente, <token>MDM para Office 365</token> no admite la administración inalámbrica y recursos de red VPN para dispositivos móviles.

La lista siguiente enumera las ventajas y desventajas de la administración inalámbrica y las redes VPN con implementaciones independientes de Intune e híbridas de Intune con Configuration Manager.

## Intune (independiente)

**Ventajas**

- Admite los perfiles de VPN e inalámbricos para todos los sistemas operativos de dispositivos móviles principales (Android, iOS, Windows 10, Windows 8.x y Windows Phone) 
- Admite los tipos de conexión VPN líderes del sector, incluidos Cisco, Juniper, Dell SonicWall y Checkpoint entre otros
- Los perfiles de VPN e inalámbricos pueden integrarse con perfiles de certificados SCEP para disponer de una mayor seguridad
- Admite la configuración de perfiles de VPN e inalámbricos personalizados para diferentes tipos de usuarios, dispositivos, sistemas operativos de dispositivos, o grupos de usuarios y roles
- Compatibilidad de iniciación basada en nombres DNS con Windows 10, Windows 8.1, Windows Phone 8.1 e iOS.
- Compatibilidad de iniciación basada en el identificador de aplicación para Windows 10 y Windows 8.1
- Puede seleccionar aplicaciones que se conecten automáticamente a la red corporativa a través de VPN en perfiles VPN.

**Desventajas**

- Para admitir los perfiles de VPN, deberá implementar y mantener una infraestructura VPN local

## MDM para Office 365

Las directivas VPN y Wi-Fi no son compatibles con MDM para Office 365.

## Híbridas (Intune con Configuration Manager)

**Ventajas**

- Todas las ventajas de Intune independiente, además de las siguientes:
    - Los perfiles de VPN son compatibles con la infraestructura VPN empresarial local existente

**Desventajas**

- Para admitir los perfiles de VPN, deberá implementar y mantener una infraestructura VPN local 
- Para administrar [perfiles de Wi-Fi](https://technet.microsoft.com/library/dn408646.aspx) y [perfiles VPN](https://technet.microsoft.com/library/dn408643.aspx) en Configuration Manager, se deben conceder determinados permisos de seguridad.

Explore los detalles acerca de las opciones de administración de la configuración de correo electrónico de dispositivos móviles revisando lo siguiente:

- Intune: habilitación de perfiles [VPN](/Intune/deployuse/vpn-connections-in-microsoft-intune) e [inalámbricos](/Intune/deployuse/wi-fi-connections-in-microsoft-intune)
- Configuration Manager: habilitación de perfiles [VPN](https://technet.microsoft.com/library/dn261217.aspx) e [inalámbricos](https://technet.microsoft.com/library/dn261221.aspx)

<!--HONumber=Jun16_HO1-->


