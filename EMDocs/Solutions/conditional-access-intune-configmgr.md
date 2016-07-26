---
title: Usar acceso condicional con Intune y Configuration Manager
description: "Implemente la solución de Intune con Configuration Manager."
keywords: 
author: craigcaseyMSFT
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: e65a0662-33ff-4e8c-9305-a21e80ea0f69
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 7c389de59d0ca6b33fbd4d872cb77236930d55bf
ms.openlocfilehash: af8afd71d87bbe608e1b392278c9d08756619618


---

# Usar acceso condicional con Intune y Configuration Manager
En este tema se da por hecho que ya usa System Center Configuration Manager y Microsoft Exchange Server (local, Exchange Online o una implementación híbrida de ambos) en su empresa para administrar el acceso al correo electrónico. Esta solución combina su entorno existente de Configuration Manager con Intune para administrar el acceso al correo electrónico en todos los tipos de dispositivos, independientemente de su ubicación, de forma segura.

> [!TIP]
> Obtenga una copia descargable de este tema completo en la [Galería de TechNet](https://gallery.technet.microsoft.com/Deploying-Enterprise-16499404).

## Antes de comenzar
Antes de empezar a utilizar el acceso condicional, asegúrese de que tiene los requisitos adecuados en su lugar:

## En el caso de Exchange Online
El acceso condicional a Exchange Online admite dispositivos que ejecutan:

-   Windows 8.1 y versiones posteriores (cuando están inscritos en Intune)

-   Windows 7.0 o posterior (si están unidos a un dominio)

-   Windows Phone 8.1 y versiones posteriores

-   iOS 7.1 y versiones posteriores

-   Android 4.0 y versiones posteriores, Samsung Knox Standard 4.0 y versiones posteriores

Además, los dispositivos deben registrarse con el servicio de registro de dispositivos de Azure Active Directory (AAD DRS).

AAD DRS se activará automáticamente para los clientes de Intune y Office 365. Los clientes que ya hayan implementado el servicio de registro de dispositivos de ADFS no podrán ver los dispositivos registrados en la instancia local de Active Directory.

-   Debe utilizar una suscripción de Office 365 que incluya Exchange Online (por ejemplo, E3) y los usuarios deben tener licencia para Exchange Online.

-   El **conector de servicio a servicio de Microsoft Intune** opcional conecta Intune con Microsoft Exchange Online y facilita la administración de la información de dispositivos a través de la consola de Intune (consulte [Administración de dispositivos móviles con Exchange ActiveSync en Microsoft Intune](/intune/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune)). No necesita usar el conector para utilizar directivas de cumplimiento ni de acceso condicional, pero sí para ejecutar informes que ayuden a evaluar el impacto del acceso condicional.

    Si configura el conector, algunas directivas de Exchange ActiveSync de Intune pueden verse en la consola de Office, pero no se establecen como directivas predeterminadas y no afectarán a los dispositivos.

    > [!IMPORTANT]
    > No configure el conector de servicio a servicio si piensa utilizar el acceso condicional para Exchange Online y Exchange Server local.

    Ahora ya puede obtener información sobre cómo [implementar Exchange Online con Intune](conditional-access-intune-exchange-online.md).

## Para Exchange Server local
El acceso condicional a Exchange Server local admite los siguientes sistemas operativos:

-   Windows 8 y versiones posteriores (cuando están inscritos en Intune)

-   Windows Phone 8 y versiones posteriores

-   Cualquier dispositivo iOS que utilice un cliente de correo electrónico de Exchange ActiveSync (EAS)

-   Android 4 y versiones posteriores

Además:

-   Su versión de Exchange debe ser Exchange 2010 o posterior. Se admite la configuración del servidor de acceso de cliente (CAS) del servidor de Exchange.

    > [!TIP]
    > Si su entorno de Exchange se encuentra en una configuración de servidor CAS, debe configurar el conector de Exchange Server local de modo que apunte a uno de los servidores CAS.

-   Exchange ActiveSync se puede configurar con autenticación basada en certificados o con la introducción de credenciales de usuario.

-   Debe utilizar el **conector de Exchange Server local** que conecta Intune a Microsoft Exchange Server local. De esta forma, podrá administrar dispositivos a través de la consola de Intune (consulte [Administración de dispositivos móviles con Exchange ActiveSync en Microsoft Intune](/intune/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune)).

  > [!IMPORTANT]
> Asegúrese de que está usando la versión más reciente de Exchange Connector local. El conector de Exchange local que tiene disponible en la consola de Intune es específico para su inquilino de Intune y no puede usarlo con otro inquilino. Asimismo, también debe asegurarse de que el conector de Exchange de su inquilino está instalado en un solo equipo y no en varios.

  Ahora ya puede obtener más información sobre cómo [implementar Exchange Server local con Intune](conditional-access-intune-exchange.md).

Si su entorno incluye Exchange Online y Exchange Server local, puede obtener información sobre cómo [implementar Exchange Online y Exchange local con Microsoft Intune y Configuration Manager](conditional-access-intune-configmgr-coexist.md).



<!--HONumber=Jul16_HO3-->


