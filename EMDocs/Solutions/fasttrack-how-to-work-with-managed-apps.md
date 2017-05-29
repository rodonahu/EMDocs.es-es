---
title: "Cómo usar aplicaciones móviles administradas por la organización"
description: "Cómo usar aplicaciones móviles administradas por la organización"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 174348f0-dbc6-4204-8626-3c6f38b7bbde
ms.reviewer: 
ms.suite: ems
ms.translationtype: Human Translation
ms.sourcegitcommit: 07aeaee067dbd6c827992b9d613d7716b5d57954
ms.openlocfilehash: 187f733bf091fc337440c245fa95fb58ddfc1196
ms.contentlocale: es-es
ms.lasthandoff: 05/29/2017


---

# <a name="how-to-use-mobile-apps-managed-by-your-organization"></a>Cómo usar aplicaciones móviles administradas por la organización

## <a name="accessing-onedrive-on-an-ios-device"></a>Acceso a OneDrive en un dispositivo iOS

En esta sección se usa OneDrive para la Empresa como ejemplo para demostrar la manera en que la experiencia del usuario puede cambiar ligeramente en una aplicación administrada por Intune.

1.    Inicie la aplicación **OneDrive para la Empresa** para abrir la página de inicio de sesión.

  ![Captura de pantalla en la cual se muestra la página de inicio de sesión de OneDrive para la Empresa para iOS.](./media/ft-useMngdApps-1-launchOnedrive.png)
> [!NOTE]
> En un dispositivo personal, normalmente el usuario final descargaría la aplicación. Si el dispositivo está administrado por una solución MDM, puede implementar la aplicación en el dispositivo.

2.    Escriba su nombre de usuario de la cuenta profesional. Se le redirigirá a la página de **Autenticación de O365** para especificar las credenciales de trabajo.

  ![Captura de pantalla en la cual se muestra un usuario de iOS escribiendo sus credenciales en la página de inicio de sesión de Office 365.](./media/ft-useMngdApps-2-enterName.png)
3.    Una vez que Azure AD haya autenticado correctamente sus credenciales, se aplicarán las directivas de MAM y se le solicitará que reinicie la aplicación **OneDrive para la Empresa**.

  ![Captura de pantalla en la cual se muestra que OneDrive se debe reiniciar.](./media/ft-useMngdApps-3-restart.png)
> [!NOTE]
> El cuadro de diálogo de reinicio necesario se muestra solo en dispositivos que no están inscritos en Intune.

4.    Vuelva a iniciar la aplicación **OneDrive para la Empresa**. La aplicación se inicia con las directivas de MAM activadas. Ahora se le solicitará establecer un **PIN** para la aplicación. (si se configuró la directiva para esto).

  ![Captura de pantalla en la cual se solicita al usuario de iOS que defina un PIN para la aplicación.](./media/ft-useMngdApps-4-enterPIN.png)
5.    En cuanto establezca el PIN y lo confirme, podrá acceder a los archivos de **OneDrive para la Empresa**.

  ![Captura de pantalla en la cual se muestra los diversos archivos a los cuales se puede acceder desde OneDrive para la Empresa en iOS.](./media/ft-useMngdApps-5-accessFiles.png)
> [!NOTE]
> Al cambiar una directiva implementada, los cambios se aplicarán la próxima vez que abra la aplicación.

## <a name="accessing-onedrive-on-an-android-device"></a>Acceso a OneDrive en un dispositivo Android
En esta sección se usa OneDrive para la Empresa como ejemplo para demostrar la manera en que la experiencia del usuario puede cambiar ligeramente en una aplicación administrada por Intune.
1.    Inicie la aplicación **OneDrive para la Empresa** para abrir la página de inicio de sesión.
> [!NOTE]
> En un dispositivo personal, normalmente el usuario final descargaría la aplicación. Si el dispositivo está administrado por una solución MDM, puede implementar la aplicación en el dispositivo.

2.    Escriba su nombre de usuario de la cuenta profesional. Se le redirigirá a la página de Autenticación de O365 para que especifique las credenciales de trabajo.

  ![Captura de pantalla en la cual se muestra un usuario de Android escribiendo sus credenciales en la página de inicio de sesión de Office 365.](./media/ft-useMngdApps-6-enterCreds.png)
3.    Una vez que Azure AD autentique correctamente sus credenciales, verá un mensaje con instrucciones para instalar la aplicación de portal de empresa, si no se encuentra ya instalada en el dispositivo. Pulse **Obtener la aplicación** para continuar.
> [!NOTE]
> La aplicación de portal de empresa es necesaria en todas las aplicaciones asociadas a directivas de MAM en los dispositivos Android. En el caso de los dispositivos no inscritos en Intune, la aplicación debe estar instalada en el dispositivo, pero no es necesario abrirla ni iniciar sesión en ella.

4.    Ahora accederá a la tienda **Google Play** , donde podrá descargar e instalar la aplicación **Portal de empresa** .

  ![Captura de pantalla en la cual se solicita al usuario de Android que se dirija a Google Play Store para descargar la aplicación Portal de empresa de Intune.](./media/ft-useMngdApps-7-installPortal.png)

 La aplicación de Portal de empresa ayuda a proteger los datos.
![Captura de pantalla en la que se solicita al usuario de Android que instale la aplicación Portal de empresa de Intune](./media/ft-useMngdApps-8-intunePortal.png)
5.    Una vez haya completado la instalación, elija **Aceptar** para aceptar los términos.
6.    La aplicación **OneDrive para la Empresa** se iniciará automáticamente.
7.    La próxima vez que abra OneDrive para la Empresa verá el aviso para establecer un **PIN**, siempre y cuando la configuración de las directivas esté establecida para solicitar un PIN para acceder a la aplicación **OneDrive para la Empresa**.

  ![Captura de pantalla en la cual se solicita al usuario de Android que defina un PIN para la aplicación.](./media/ft-useMngdApps-9-setNewPIN.png)
8.    Una vez que establezca y confirme el PIN, podrá seguir usando **OneDrive para la Empresa**, que ahora estará administrado por directivas de aplicaciones.

### <a name="want-to-learn-more"></a>¿Desea obtener más información?
Consulte [Enterprise Mobility + Security](https://www.microsoft.com/en-us/server-cloud/enterprise-mobility/overview.aspx).

