---
title: Experiencia del usuario final de MAM
description: "Experiencia del usuario final de directivas de administración de aplicaciones móviles."
keywords: 
author: craigcaseyMSFT
manager: swadhwa
ms.date: 05/12/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: bbc9f6ea-fc92-468d-bb5b-60c67949ca28
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 55a3dbe32e3b5e10e21a6d99bc101ec76fc51f5e
ms.openlocfilehash: 38a642c24e506d1528f0e79ad26fa77a50a4fed6


---

# Experiencia del usuario final de directivas de administración de aplicaciones móviles
Las directivas MAM solo se aplican cuando se usan aplicaciones en el contexto de trabajo. Lea los siguientes escenarios de ejemplo para ayudar a educar a los usuarios de modo que entiendan cómo funcionan las aplicaciones administradas.

En esta sección se proporcionan ejemplos de las siguientes experiencias de usuario final:

- Escenario: acceso a OneDrive en un dispositivo iOS
- Escenario: acceso a OneDrive en un dispositivo Android

Para más información sobre otras experiencias específicas de usuarios finales, consulte los artículos siguientes:

- [Uso de aplicaciones con compatibilidad con varias identidades](https://docs.microsoft.com/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#using-apps-with-multi-identity-support)
- [Administración de cuentas de usuario](https://docs.microsoft.com/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#managing-user-accounts)
- [Ver archivos multimedia con la aplicación Rights Management sharing](https://docs.microsoft.com/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#viewing-media-files-with-the-rights-management-sharing-app)

## Escenario: acceso a OneDrive en un dispositivo iOS

1. El usuario inicia la aplicación **OneDrive** para abrir la página de inicio de sesión.
> [!NOTE]
> En un dispositivo personal, normalmente el usuario final descargaría la aplicación. Si el dispositivo está administrado por una solución MDM, puede implementar la aplicación en el dispositivo.

2. El usuario escribe el nombre de usuario de la cuenta de trabajo y se le redirige a la página de **autenticación de O365** para que especifique las credenciales de trabajo.

  Una vez que Azure AD ha autenticado correctamente las credenciales, se aplican las directivas MAM.
3. Se pide al usuario que establezca un **PIN** para la aplicación (si configuró la directiva para esto).

4.  Una vez el PIN está establecido y confirmado, el usuario puede obtener acceso a los archivos de **OneDrive para la Empresa**.
> [!NOTE]
> Cuando se modifica una directiva implementada, los cambios se aplican la siguiente vez que se abre la aplicación.

## Escenario: acceso a OneDrive en un dispositivo Android
1. El usuario inicia la aplicación **OneDrive** para abrir la página de inicio de sesión.
> [!NOTE]
> En un dispositivo personal, normalmente el usuario final descargaría la aplicación. Si el dispositivo está administrado por una solución MDM, puede implementar la aplicación en el dispositivo.

2.  El usuario escribe el nombre de usuario de la cuenta de trabajo y se le redirige a la página de **autenticación de O365** para que especifique las credenciales de trabajo.

  Una vez que Azure AD ha autenticado correctamente las credenciales, se aplican las directivas MAM.

3.  La aplicación **OneDrive** se inicia automáticamente y se pide al usuario que establezca un **PIN**, siempre que la configuración de las directivas esté establecida para solicitar un **PIN** para acceder a la aplicación **OneDrive**.

4.  Una vez que el PIN está establecido y confirmado, puede seguir usando **OneDrive**, que ahora estará administrado por directivas de aplicaciones.

## Próximos pasos
Hay otras experiencias de usuario final sobre las que puede obtener más información, como [Uso de aplicaciones con compatibilidad con varias identidades](https://docs.microsoft.com/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#using-apps-with-multi-identity-support), [Administración de cuentas de usuario](https://docs.microsoft.com/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#managing-user-accounts) y [Ver archivos multimedia con la aplicación Rights Management sharing](https://docs.microsoft.com/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#viewing-media-files-with-the-rights-management-sharing-app).



<!--HONumber=Aug16_HO1-->

