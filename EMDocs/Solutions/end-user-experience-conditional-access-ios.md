---
title: Experiencia de acceso condicional del usuario final en dispositivos iOS
description: 
keywords: 
author: craigcaseyMSFT
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 3c641ea8-2c0e-490e-b1de-831336f46d19
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 5f1c98cc916bee9bb83249a16a52a5fdd3810142
ms.openlocfilehash: 6ff6f8c66e5b4ed838c72dd06f200118c6461cb0


---

# iOS

El proceso de inscripción y las pantallas que ve el usuario pueden variar ligeramente en función de la versión del sistema operativo que se ejecuta en el dispositivo del usuario final. En este tema se describe la experiencia del usuario final en dispositivos iOS.

## Inscripción

1.  Si un usuario ya está inscrito en Intune y cumple las normas, no verá ninguna diferencia en los dispositivos iOS; seguirá pudiendo obtener acceso al correo electrónico. Si el usuario todavía no está inscrito, verá un mensaje de cuarentena similar al siguiente al iniciar la aplicación de correo electrónico:

    ![Captura de pantalla que muestra el correo electrónico de cuarentena que recibe un usuario en un dispositivo iOS](./media/ProtectEmail/EUX-iOS-Get-Started.PNG)

    El usuario hace clic en **Empezar ahora** para comenzar la inscripción del dispositivo.

2.  Se pedirá al usuario que instale la aplicación Portal de empresa de Intune desde la tienda de aplicaciones correspondiente.

    ![Captura de pantalla que muestra el Portal de empresa de Intune en un dispositivo iOS](./media/ProtectEmail/EUX-iOS-intune-Company-Portal.png)

    Después, el usuario abre la aplicación e inicia la sesión con las credenciales de empresa.

3.  En la pantalla Configuración de acceso a la empresa, el usuario hace clic en **Empezar** para iniciar la configuración de su dispositivo y comprobar si es compatible.

    ![Captura de pantalla que muestra la pantalla Configuración de acceso a la empresa en un dispositivo iOS](./media/ProtectEmail/EUX-iOS-company-AccessSetup.png)

4.  En la pantalla Inscripción de dispositivos, el usuario hace clic en **Inscripción** para iniciar la inscripción de su dispositivo.

    ![Captura de pantalla que muestra la pantalla Inscripción de dispositivos en un dispositivo iOS](./media/ProtectEmail/EUX-iOS-device-Enrollment.png)

    Durante la inscripción, se instala el perfil de administración de dispositivos móviles, que permite al administrador de TI administrar el dispositivo de forma remota. El usuario escribe su contraseña si se le solicita.

5.  En la pantalla Configuración de acceso a la empresa, el usuario hace clic en **Continuar** para iniciar la comprobación de cumplimiento en el dispositivo.

    ![Captura de pantalla que muestra que la inscripción de dispositivos es correcta en un dispositivo iOS y que el usuario necesita comprobar el cumplimiento](./media/ProtectEmail/EUX-iOS-device-Compliance-Check.png)

    Si hay un problema de cumplimiento, se pedirá al usuario que resuelva el problema (por ejemplo, creando una contraseña válida) y que haga clic en **Comprobar cumplimiento** para continuar.

    ![Captura de pantalla que muestra que el usuario debe resolver los problemas de cumplimiento en un dispositivo iOS](./media/ProtectEmail/EUX-iOS-check-Compliance.png)

6.  Cuando el dispositivo cumpla todas las normas, el usuario hará clic en **Continuar** para seguir.

    ![Captura de pantalla que muestra que el dispositivo iOS es compatible y que se ha completado la configuración](./media/ProtectEmail/EUX-iOS-compliance-Check-Completed.png)

    Después de inscribir al usuario y de comprobar el cumplimiento, el acceso al correo electrónico debería estar disponible en cuestión de minutos.

Si el usuario sigue estos pasos para inscribirse y comprobar el cumplimiento, pero sigue sin tener acceso al correo electrónico en su dispositivo móvil, puede seguir estos pasos adicionales para intentar solucionar el problema:

-   En primer lugar, compruebe que el dispositivo está inscrito. De lo contrario, el usuario seguirá los pasos ya descritos.

-   Compruebe que el dispositivo cumple las normas haciendo clic en **Comprobar cumplimiento**. Si se identifica un error de cumplimiento, el usuario puede seguir las instrucciones sobre cómo resolverlo específicas para su dispositivo móvil como, por ejemplo, de qué manera restablecer la contraseña.

-   Llame al departamento de soporte técnico.

## Problemas y soluciones
Cada 8 horas, de forma predeterminada, se comprueban los dispositivos para garantizar que siguen cumpliendo las normas. Si un dispositivo que cumplía las normas pasa a considerarse no conforme (por ejemplo, si se agrega o se modifica una directiva de cumplimiento), el usuario puede seguir estos pasos para volver al cumplimiento:

1.  El usuario recibe la notificación, en el correo electrónico o en el dispositivo, que indica que el dispositivo no cumple las normas. En este momento, el dispositivo se pone en cuarentena en Exchange.

2.  Si el usuario intenta obtener acceso al correo electrónico, se le redirige a la pantalla Configuración de acceso a la empresa desde el portal de empresa de Intune, donde se muestra la falta de cumplimiento.

    ![Captura de pantalla que muestra que el dispositivo iOS no es compatible](./media/ProtectEmail/EUX-iOS-fallOut-Compliance.png)

3.  El usuario hace clic en **Continuar** y aparece el problema de cumplimiento que impide el acceso al correo electrónico.

    ![Captura de pantalla que muestra que el usuario debe resolver los problemas de cumplimiento en un dispositivo iOS](./media/ProtectEmail/EUX-iOS-check-Compliance.png)

4.  Una vez solucionado el problema, el usuario hace clic en **Comprobar cumplimiento** para comprobar que se ha resuelto el problema.

5.  Si el problema está solucionado, el usuario hace clic en **Continuar** para completar el proceso.

    ![Captura de pantalla que muestra que el dispositivo iOS es compatible y que se ha completado la configuración](./media/ProtectEmail/EUX-iOS-compliance-Check-Completed.png)

    El correo electrónico debería estar disponible de nuevo tras unos minutos.

### Próximos pasos
La experiencia del usuario final es ligeramente diferente en otros dispositivos móviles. Puede obtener más información sobre la experiencia del usuario final en [Android](end-user-experience-conditional-access-android.md) y [Windows Phone](end-user-experience-conditional-access-winphone.md).



<!--HONumber=Jun16_HO4-->


