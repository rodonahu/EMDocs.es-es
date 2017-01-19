---
title: Experiencia del usuario final de acceso condicional en dispositivos Android
description: La experiencia del usuario final al inscribir un dispositivo Android.
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0b5e4330-6fa5-445c-b73e-86ce5b9c7964
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 2342889a686db8a6496c97979cb222af8347241a
ms.openlocfilehash: fc06debb97cdbd3be1a241a711f36f6c530d65cf


---

# <a name="android"></a>Android

El proceso de inscripción y las pantallas que ve el usuario pueden variar ligeramente en función de la versión del sistema operativo que se ejecuta en el dispositivo del usuario final. En este tema se describe la experiencia del usuario final al inscribir dispositivos Android.

## <a name="enrolling"></a>Inscripción

1.  Al intentar obtener acceso al correo electrónico, el usuario recibe por primera vez un correo electrónico de cuarentena parecido al de este ejemplo:

    ![Captura de pantalla que muestra el correo electrónico de cuarentena que recibe un usuario en un dispositivo Android](./media/ProtectEmail/EUX-Android-quarantine-Email.png)

    El usuario hace clic en **Empezar ahora** para comenzar la inscripción del dispositivo.

    > [!NOTE]
    > Si un usuario no ha establecido un explorador predeterminado para su dispositivo, se le pedirá durante la inscripción del dispositivo y durante la activación de la inscripción que permita que un vínculo abra una ventana del explorador. Debe seleccionar el mismo explorador cada vez que se le pida o se producirá un error en el proceso de inscripción.

2.  Se pedirá al usuario que instale la aplicación Portal de empresa de Intune desde la tienda de aplicaciones correspondiente.

    ![Captura de pantalla que muestra el Portal de empresa de Intune en un dispositivo Android](./media/ProtectEmail/EUX-Android-Portal.png)

    Después, el usuario abre la aplicación e inicia la sesión con las credenciales de empresa.

3.  En la pantalla Configuración de acceso a la empresa, el usuario hace clic en **Empezar** para iniciar la configuración de su dispositivo y comprobar si es compatible.

    ![Captura de pantalla que muestra la pantalla Configuración de acceso a la empresa en un dispositivo Android](./media/ProtectEmail/EUX-Android-company-Access-Setup.PNG)

4.  En la pantalla Inscripción de dispositivos, el usuario hace clic en **Inscripción** para iniciar la inscripción de su dispositivo.

    ![Captura de pantalla que muestra la pantalla Inscripción de dispositivos en un dispositivo Android](./media/ProtectEmail/EUX-Android-device-Enroll.png)

5.  Los usuarios tienen que activar el administrador de dispositivos. Para ello, solo tienen que hacer clic en **Activar** cuando se le pida. De lo contrario, se cancelará el procedimiento de inscripción de dispositivos.

    ![Captura de pantalla que muestra que el usuario debe activar el administrador de dispositivos en un dispositivo Android](./media/ProtectEmail/EUX-Android-activate-DeviceAdmin.PNG)

    Empieza la inscripción de dispositivos En función del dispositivo, durante la inscripción puede aparecer un mensaje de instalación del certificado o un mensaje de directiva de privacidad de Samsung KNOX. Todo esto es necesario para que el administrador de TI pueda administrar el dispositivo de forma remota. El dispositivo está inscrito en Intune y establece una identidad de dispositivo con Azure Active Directory.

    ![Captura de pantalla que muestra que se inicia la inscripción de dispositivos en un dispositivo Android](./media/ProtectEmail/EUX-Android-enrolling-Device.png)

6.  Una vez completada correctamente la inscripción, el usuario hace clic en **Continuar** para empezar la comprobación de cumplimiento en el dispositivo.

    ![Captura de pantalla que muestra que la inscripción de dispositivos es correcta en un dispositivo Android](./media/ProtectEmail/EUX-Android-enroll-Success.png)

    Si hay un problema de cumplimiento, se pedirá al usuario que resuelva el problema (por ejemplo, creando una contraseña válida) y que haga clic en **Comprobar cumplimiento** para continuar.

    ![Captura de pantalla que muestra que el usuario debe resolver los problemas de cumplimiento en un dispositivo Android](./media/ProtectEmail/EUX-Android-resolve-Compliance-Issues.png)

7.  Cuando el dispositivo cumpla todas las normas, el usuario hará clic en **Continuar** para iniciar la activación de la inscripción. Así, se conectará la identidad del dispositivo AAD con el EASID ofrecido por Exchange.

    > [!NOTE]
    > En Android, el explorador predeterminado aparecerá durante unos segundos mientras se activa la inscripción. Si el usuario no ha elegido ya un explorador predeterminado, se le pedirá que elija un explorador. Mientras completa la Configuración de acceso a la empresa, el usuario tiene que elegir el mismo explorador siempre que se le pida.

    ![Captura de pantalla que muestra que el dispositivo Android es compatible](./media/ProtectEmail/EUX-Android-compliance-Successful.PNG)

8.  La activación de la inscripción se completa y el usuario hace clic en **Listo** para salir del proceso de inscripción y comprobación del cumplimiento.

    ![Captura de pantalla que muestra que se ha completado la configuración de acceso a la empresa en un dispositivo Android](./media/ProtectEmail/EUX-Android-all-Successful2.PNG)

    Después de inscribir al usuario y de comprobar el cumplimiento, el acceso al correo electrónico debería estar disponible en cuestión de minutos.

Si el usuario sigue estos pasos para inscribirse y comprobar el cumplimiento, pero sigue sin tener acceso al correo electrónico en su dispositivo móvil, puede seguir estos pasos adicionales para intentar solucionar el problema:

1.  En primer lugar, compruebe que el dispositivo está inscrito. De lo contrario, el usuario seguirá los pasos ya descritos.

2.  Compruebe que el dispositivo cumple las normas haciendo clic en **Comprobar cumplimiento**. Si se identifica un error de cumplimiento, el usuario puede seguir las instrucciones sobre cómo resolverlo específicas para su dispositivo móvil como, por ejemplo, de qué manera restablecer la contraseña.

3.  Llame al departamento de soporte técnico.

## <a name="issues-and-solutions"></a>Problemas y soluciones
Cada 8 horas, de forma predeterminada, se comprueban los dispositivos para garantizar que siguen cumpliendo las normas. Si un dispositivo que cumplía las normas pasa a considerarse no conforme (por ejemplo, si se agrega o se modifica una directiva de cumplimiento), el usuario puede seguir estos pasos para volver al cumplimiento:

1.  El usuario recibe la notificación, en el correo electrónico o en el dispositivo, que indica que el dispositivo no cumple las normas. En este momento, el dispositivo se pone en cuarentena en Exchange.

2.  Cuando el usuario intente obtener acceso al correo electrónico, verá un correo electrónico de cuarentena que le informa de que, para poder obtener acceso, es necesario solucionar los problemas de cumplimiento. Cuando el usuario hace clic en el hipervínculo del correo electrónico de cuarentena, llega a la pantalla Configuración de acceso a la empresa en el portal de empresa de Intune (mediante el explorador predeterminado y Google Play), donde se muestra que el dispositivo no cumple las normas.

    ![Captura de pantalla que muestra que el dispositivo Android no es compatible](./media/ProtectEmail/EUX-Android-outOfCompliance.png)

3.  El usuario hace clic en **Continuar** y aparece el problema de cumplimiento que impide el acceso al correo electrónico.

    ![Captura de pantalla que muestra que el usuario debe resolver los problemas de cumplimiento en un dispositivo Android](./media/ProtectEmail/EUX-Android-resolve-Compliance-Issues.png)

4.  Una vez solucionado el problema, el usuario hace clic en **Comprobar cumplimiento** para comprobar que se ha resuelto el problema.

5.  Si el problema está solucionado, el usuario hace clic en **Continuar** para completar el proceso. El correo electrónico debería estar disponible de nuevo tras unos minutos.

### <a name="where-to-go-from-here"></a>Próximos pasos
La experiencia del usuario final es ligeramente diferente en otros dispositivos móviles. Puede obtener más información sobre la experiencia del usuario final para [iOS](end-user-experience-conditional-access-ios.md) y [Windows Phone](end-user-experience-conditional-access-winphone.md).



<!--HONumber=Jan17_HO1-->


