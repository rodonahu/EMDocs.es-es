---
title: "Implementación de Office 365 ProPlus con Microsoft Intune - Microsoft 365 Enterprise | Microsoft Docs"
description: "Aquí se describe cómo implementar Microsoft Office 365 ProPlus con Microsoft Intune."
author: jeffgilb
manager: femila
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 08/10/2017
ms.author: jeffgilb
ms.reviewer: jsnow
ms.custom: it-pro
ms.openlocfilehash: e631ca9282fc937279c7e2d639f1ecf509ceeab5
ms.sourcegitcommit: a5900174df584bee2f94086668cb0eff53bd5ed0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/15/2017
---
# <a name="deploy-office-365-proplus-with-microsoft-intune"></a>Implementación de Office 365 ProPlus con Microsoft Intune
Microsoft 365 Enterprise es una solución moderna para empresas con la que los usuarios pueden ser creativos y colaborar en su trabajo de forma segura. Las soluciones de Microsoft 365 Enterprise son el resultado de una estrecha colaboración entre los equipos de Enterprise Mobility + Security (EMS), Office 365 y Windows 10. Fruto de esta colaboración son algunas soluciones innovadoras, como la capacidad de implementar aplicaciones de Office 365 ProPlus en dispositivos con Windows 10 con Intune. 

Ahora es más fácil que nunca seleccionar determinadas aplicaciones de Office 365 ProPlus (usando Hacer clic y ejecutar), implementarlas en dispositivos inscritos que ejecuten Windows 10 Creators Update y ver las métricas de implementación a través del nuevo portal de Intune en Azure. Este método funciona muy bien con Windows AutoPilot para poner a punto los dispositivos de los empleados con solo proporcionar las credenciales de la compañía durante la configuración rápida (OOBE), mientras Azure AD e Intune funcionan conjuntamente en segundo plano para registrar el dispositivo, implementar las configuraciones necesarias y ahora también instalar aplicaciones de Office 365 ProPlus.

![Simplificar la administración de Windows 10 y reducir el costo total de propiedad con EMS](./media/deploy-office-proplus-intune/windows-10-management-ems.png)

Puede [descargar esta infografía aquí](https://gallery.technet.microsoft.com/Infographic-Simplify-37e77674).

## <a name="deploy-office-365-proplus-with-intune"></a>Implementar Office 365 ProPlus con Intune 
Veamos cómo configurar una implementación de Office 365 ProPlus con Intune.

Con el nuevo portal de Intune, ahora es muy fácil agregar y personalizar las implementaciones de Office 365 ProPlus. Después de elegir el tipo de aplicación del **Conjunto de aplicaciones de Office 365 ProPlus (Windows 10)**, puede personalizar la implementación de aplicaciones de Office en tres sencillos pasos.

Primero, elija las aplicaciones que quiere instalar en dispositivos de usuario final:

![Elegir aplicaciones para implementar](./media/deploy-office-proplus-intune/Configure-App-Suite.png)

Después, configure la información del conjunto de aplicaciones. Por ejemplo, recomendamos agregar una breve descripción de las aplicaciones incluidas en este conjunto de aplicaciones para mostrarla en el Portal de empresa de Intune:

![Configurar información del conjunto de aplicaciones](./media/deploy-office-proplus-intune/App-Suite-Information.png)

Por último, configure algunas opciones de instalación, como la arquitectura del sistema o el canal de actualización:

![Configurar opciones de instalación](./media/deploy-office-proplus-intune/App-Suite-Settings.png)

Los usuarios finales pueden instalar aplicaciones de Office a través del portal de empresa de Intune (si las ha puesto a su disposición). Si no es el caso, los usuarios simplemente realizan una instalación silenciosa. Una vez que Office está instalado en sus dispositivos, los usuarios pueden iniciar sesión, activar el producto y disfrutar de las características más recientes, ya que [el servicio mantiene actualizado Office automáticamente](https://support.office.com/article/Overview-of-update-channels-for-Office-365-ProPlus-9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4).

> [!NOTE]
> Actualmente, este tipo de implementación de Office 365 ProPlus solo se admite en dispositivos que no tengan instalada ninguna versión de Office. Para dispositivos con versiones existentes de Office, se recomienda quitar todas las versiones de Office antes de la inscripción. Estamos trabajando con los equipos de Windows y Office en futuras mejoras para admitir dispositivos con implementaciones existentes de Office.

## <a name="learn-more"></a>Obtener más información
Para obtener instrucciones detalladas, vea [Deploy Office 365 apps for Windows 10 with Intune](https://docs.microsoft.com/intune/apps-add-office365) (Implementación de aplicaciones de Office 365 para Windows 10 con Intune).