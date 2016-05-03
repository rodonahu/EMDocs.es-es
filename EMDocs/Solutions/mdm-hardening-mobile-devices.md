---
# required metadata

title: Protección de dispositivos móviles
description:
keywords:
author: YuriDio
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: ade57c73-a8a2-497f-ad8d-5dfc3cba9e70

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: 
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Protección de dispositivos móviles

>[!NOTE]
>Este tema forma parte de una guía de consideraciones de diseño más extensa. Si desea comenzar por el principio de la guía, consulte el [tema principal](mdm-design-considerations-guide.md). Para obtener una copia descargable de toda esta guía, visite la [Galería de TechNet](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582).

Cuando cree una referencia de configuración para dispositivos móviles para proteger sus capacidades de acuerdo con sus necesidades empresariales, asegúrese de que equilibra la facilidad de uso con la seguridad. Una plantilla de protección muy estricta puede provocar facilidad de uso y problemas de acceso para los empleados, por lo que fracasará en el propósito de ayudar a los usuarios ser productivos mediante el acceso a recursos de la compañía con sus dispositivos. 

Además, tenga en cuenta que no todas las directivas de seguridad están disponibles para todas las plataformas de dispositivos móviles. Puede que necesite equilibrar las prioridades para permitir las plataformas de dispositivos móviles en su organización con los requisitos de cumplimiento de seguridad para la protección de dispositivos.
Una manera de enfocar la protección de los dispositivos móviles es tener diferentes niveles de seguridad. Los valores de configuración que están disponibles para cada nivel también pueden variar, según la solución MDM. La siguiente figura muestra un ejemplo de cómo se puede configurar este enfoque por niveles.

![Niveles de seguridad](./media/MDM_Figure_12.png)

## Diferentes áreas de la protección de dispositivos móviles

Cada capa se puede utilizar para las áreas de grupos que deben satisfacer los requisitos de seguridad de su empresa. Por ejemplo, puede configurar Intune para implementar las [directivas de seguridad](/intune/deployuse/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies) de los dispositivos que se emplean concretamente para reforzar la configuración del sistema y habilitar el cifrado. Las directivas también pueden ayudar a garantizar que solo estén disponibles las [aplicaciones conformes](https://technet.microsoft.com/library/dn818906.aspx) para instalarse en dispositivos móviles mediante la creación de una lista blanca de acceso.

En los dispositivos BYOD que ejecutan Windows 8.1 Enterprise, AppLocker puede permitir o bloquear una aplicación en función de su ruta de acceso de archivo, hash o propiedades que persistan en las actualizaciones de la aplicación (por ejemplo, el nombre del publicador, el nombre de producto, el nombre de archivo y la versión del archivo). En Windows 10, se agregó nuevo proveedor de servicios de configuración de AppLocker para poder habilitar las reglas de AppLocker mediante un servidor MDM. Consulte [AppLocker CSP](https://msdn.microsoft.com/library/windows/hardware/dn920019(v=vs.85).aspx) (CSP de AppLocker) para obtener más información sobre esta nueva funcionalidad de Windows 10.

Otra área que debe controlarse es la experiencia de exploración de los usuarios móviles. Una directiva de explorador administrada incluye una lista de permitidos o bloqueados que restringe los sitios web que pueden visitar los usuarios del explorador administrado. Consulte [Administrar el acceso a Internet mediante directivas de explorador administrado con Microsoft Intune](/intune/deployuse/manage-internet-access-using-managed-browser-policies) para obtener más información sobre cómo configurar estas directivas en Intune.

En un entorno híbrido con Configuration Manager local, puede crear un [línea base de configuración](https://technet.microsoft.com/library/gg712268.aspx?WT.mc_id=Blog_EntMob_Showcase_PCIT) para definir un estado de protección básica en los dispositivos móviles administrados. Puede personalizar esta línea base para incluir toda la configuración necesaria e implementarla luego en los dispositivos móviles. Las opciones de configuración de cumplimiento variarán según el proveedor, así que consulte [Configuración general para dispositivos móviles en Configuration Manager](https://technet.microsoft.com/library/dn376523.aspx) para obtener más información sobre las opciones disponibles para cada plataforma de dispositivos móviles.

[MDM para Office 365](https://technet.microsoft.com/library/ms.o365.cc.devicepolicy.aspx) también tiene un conjunto de capacidades para ayudarlo a proteger los dispositivos móviles en las siguientes categorías:

- Seguridad
- Cifrado
- Descodificado
- Perfil de correo electrónico administrado

Lea el artículo [Capacidades de administración de dispositivos móviles integrada para Office 365](https://technet.microsoft.com/library/ms.o365.cc.devicepolicysupporteddevice.aspx) para obtener más información sobre cómo configurar directivas de seguridad para aplicar estas opciones.

La protección de la plataforma de dispositivos móviles desempeña un rol importante en el mantenimiento de la protección de los datos de la compañía a la vez que permite a los usuarios utilizar sus dispositivos móviles sin que la seguridad se ponga en peligro. Utilice la siguiente tabla como referencia para ayudarlo a elegir la opción de MDM que mejor se adapte a los requisitos de protección de datos de su organización.

## Intune (independiente)

**Ventajas**

- Permite aplicar directivas para dispositivos inscritos: cifrado, malware, aplicaciones, correos electrónicos, perfiles de correo electrónico, dispositivos liberados, sistemas y seguridad.
- Admite la implementación de directivas para plataformas de dispositivos móviles importantes, incluidos Android, iOS, Windows 10, Windows 8.x y Windows Phone.

**Desventajas**

- La falta de integración con la plataforma MDM local actual incorporará una interfaz de administración adicional que podrá usar para administrar dispositivos móviles
- Puede que algunas directivas no estén disponibles para algunas plataformas móviles

## MDM para Office 365

**Ventajas**

- Permite aplicar directivas para dispositivos inscritos: cifrado, aplicaciones, desbloqueado y seguridad.
- Admite la implementación de directivas para plataformas de dispositivos móviles importantes, incluidos Android, iOS, Windows 10, Windows 8.x y Windows Phone.

**Desventajas**

- La falta de integración con la plataforma MDM local actual incorporará una interfaz de administración adicional que podrá usar para administrar dispositivos móviles
- Puede que algunas directivas no estén disponibles para algunas plataformas móviles
- No permitir tanta granularidad como Intune.

## Híbridas (Intune con Configuration Manager)

**Ventajas**

- Permite aplicar directivas para dispositivos inscritos: cifrado, malware, aplicaciones, correos electrónicos, dispositivos liberados, sistemas y seguridad.
- Admite la implementación de directivas para plataformas de dispositivos móviles importantes, incluidos Android, iOS, Windows 10, Windows 8.x y Windows Phone.
- Consola de administración única para dispositivos móviles registrados a partir de dispositivos locales y en la nube

**Desventajas**

- Si la compañía no dispone de una infraestructura de Configuration Manager local en estos momentos, habrá que planificar, instalar y configurar esta plataforma antes de la integración.

>[ Obtenga más información sobre la configuración de administración de dispositivos móviles que se puede configurar en una directiva de seguridad de dispositivos móviles de Microsoft Intune en [!TIP]Configuración de directiva de administración de dispositivos móviles para Microsoft Intune](https://technet.microsoft.com/library/dn913730.aspx). 


<!--HONumber=Apr16_HO2-->


