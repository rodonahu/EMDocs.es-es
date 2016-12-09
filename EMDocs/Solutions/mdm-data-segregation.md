---
title: "Segregación de datos"
description: "En este artículo se proporciona un conjunto de consideraciones de diseño para la segregación de datos que debe usarse en un escenario de administración de dispositivos móviles."
keywords: 
author: YuriDio
ms.author: yurid
manager: swadhwa
ms.date: 11/28/2016
ms.topic: solution
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 50bd37fe-30b5-4a45-9c36-0b907dd13cc2
ms.reviewer: 
ms.suite: ems
ms.custom: microsoft-intune
translationtype: Human Translation
ms.sourcegitcommit: 5adb7f68efacdfa20d78c3cf5853fa374793140a
ms.openlocfilehash: 030d0c1dca506ac7757e8c26910ea4725a1b9c2c


---

# <a name="data-segregation"></a>Segregación de datos

>[!NOTE]
>Este tema forma parte de una guía de consideraciones de diseño más extensa. Si desea comenzar por el principio de la guía, consulte el [tema principal](mdm-design-considerations-guide.md). Para obtener una copia descargable de toda esta guía, visite la [Galería de TechNet](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582).

La segregación de datos es importante, no solo para su organización, sino también para mantener la privacidad de la información personal del usuario. La segregación de datos le ayuda a quitar todos los datos y las aplicaciones de la compañía de un dispositivo que pertenece a un usuario, sin que afecte a los datos personales del usuario (consulte la siguiente figura):

![Segregación de datos](./media/MDM_Figure_10.png)

## <a name="users-personal-data-is-isolated-from-companys-data"></a>Los datos personales del usuario se aíslan de los datos de la empresa,

Mediante la separación de todas las aplicaciones, datos de la compañía y directivas implementadas por la solución MDM, puede quitarse del dispositivo si fuese necesario sin afectar a las aplicaciones y al contenido personal del usuario usando el borrado selectivo. 

>[!TIP] 
> Consulte [Ayudar a proteger los datos con el borrado selectivo o completo mediante Microsoft Intune](/intune/deploy-use/use-remote-wipe-to-help-protect-data-using-microsoft-intune) para obtener más información sobre cómo se comportará el borrado remoto en otras plataformas como iOS y Android. 

El borrado selectivo para la administración de datos de dispositivos móviles se incluye en Windows Server 2012 R2 y Windows 8.1. Funciona mediante la vinculación de recursos que ayudan a los administradores de Exchange Server y Microsoft Intune a administrar los datos empresariales en dispositivos y a desarrollar aplicaciones que pueden usar las funcionalidades del [borrado selectivo de Windows](https://technet.microsoft.com/library/dn486874.aspx).  Windows Phone 8 y las versiones posteriores permiten separar los datos en el almacenamiento interno.

![Segregación de datos](./media/MDM_Figure_11.png)

Obtenga más información sobre las funcionalidades de seguridad de Windows Phone 8.1 descargando [Windows Phone 8.1 Security Overview](http://www.microsoft.com/download/details.aspx?id=42509) (Información general de seguridad de Windows Phone 8.1).

La segregación de datos puede ser complicada si los usuarios cambian entre cuentas personales y cuentas corporativas en sus dispositivos móviles. En un escenario BYOD, es habitual que los usuarios utilicen varias credenciales para realizar diferentes tareas en su dispositivo. 

Protección de datos de empresa (EDP) proporciona una separación de datos, pero ni usa contenedores ni requiere una versión especial de una aplicación para acceder a los datos empresariales y, luego, una segunda instancia de ella para acceder a los datos personales. No hay contenedores, particiones o carpetas especiales para separar físicamente datos empresariales y personales. En su lugar, Windows 10 Mobile es el agente de control de acceso, que identifica los datos de empresa debido a que están cifrados para la empresa. 

EDP proporciona una separación de datos en virtud de cifrar los datos de empresa. Lectura [Enterprise data protection (EDP) overview](https://technet.microsoft.com/library/dn985838.aspx) (Información general de protección de datos de empresa [EDP]) para obtener más información. Las directivas de EDP Intune administrarán la lista de aplicaciones protegidas por EDP, las ubicaciones de red de la empresa, el nivel de protección y la configuración de cifrado.

Cuando un usuario instala e inicia sesión en una aplicación que admite varias identidades (múltiple identidad), un dispositivo administrado por Intune, como Outlook, Intune comprueba si la cuenta que usa coincide con la cuenta administrada en el dispositivo. Si se administra la cuenta, y también hay una directiva para la aplicación y el usuario, la configuración de la directiva protege los datos en esa cuenta. Cuando el usuario agrega cuentas personales a la aplicación, esas cuentas están fuera de la protección y administración de Intune. Esto permite el uso personal de la aplicación sin poner en peligro la protección corporativa. Consulte [Proteger datos de aplicación mediante directivas de administración de aplicaciones móviles con Microsoft Intune](/intune/deploy-use/configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console) para obtener más información sobre la funcionalidad de varias identidades en Intune. 

En la tabla siguiente se comparan las características de borrado selectivo disponibles con las diferentes soluciones MDM para ayudarle a elegir la solución MDM que mejor se adapte a los requisitos de segregación de datos de su organización.

## <a name="intune-standalone"></a>Intune (independiente)

**Ventajas**

- Permite realizar borrados selectivos para quitar solo los datos de la compañía ubicados en dispositivos móviles
- Permite realizar el restablecimiento de fábrica y borrar completamente los dispositivos móviles
- Compatibilidad con aplicaciones de identidades múltiples

**Desventajas**

- No incluye el cifrado nativo para el almacenamiento del dispositivo móvil
- La falta de integración con la plataforma MDM local actual significa que debe usar una interfaz de administración adicional

## <a name="office-365-with-mdm"></a>Office 365 con MDM

**Ventajas**

- Permite realizar el restablecimiento de fábrica y borrar al completo dispositivos Android, Windows Phone y iOS
- Permite realizar borrados selectivos en Android, Windows Phone y dispositivos iOS para quitar solo los datos de la compañía de los dispositivos móviles

**Desventajas**

- La falta de integración con la plataforma MDM local actual significa que debe usar una interfaz de administración adicional

## <a name="hybrid-intune-with-configmgr"></a>Híbridas (Intune con Configuration Manager)

**Ventajas**

- Permite realizar borrados selectivos para quitar solo los datos de la compañía de los dispositivos móviles
- Permite realizar el restablecimiento de fábrica y borrar completamente los dispositivos móviles
- Compatibilidad con aplicaciones de identidades múltiples
- Consola de administración única para administrar los dispositivos móviles locales y en la nube

**Desventajas**

- Si la organización no dispone de una infraestructura de Configuration Manager local en estos momentos, habrá que planificar, instalar y configurar esta plataforma antes de la integración.

Asegúrese de leer el artículo [Ayudar a proteger los datos con el borrado selectivo o completo mediante Microsoft Intune](/intune/deploy-use/use-remote-wipe-to-help-protect-data-using-microsoft-intune) para comprender cómo se quitan y conservan los datos después de un borrado selectivo en cada plataforma de dispositivo móvil. Si cuenta con un entorno híbrido, consulte el artículo [Borrado remoto de dispositivos móviles mediante Configuration Manager](https://technet.microsoft.com/library/dn956981.aspx) para comprender cómo Configuration Manager puede usarse para llevar a cabo esta tarea.



<!--HONumber=Nov16_HO4-->


