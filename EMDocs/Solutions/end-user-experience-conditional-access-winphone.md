---
# required metadata

title: Experiencia de acceso condicional del usuario final en Windows Phone
description:
keywords:
author: craigcaseyMSFT
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: 906566e0-f05e-4af5-b4d5-0efb083dca76

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer:
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Windows Phone

El proceso de inscripción y las pantallas que ve el usuario pueden variar ligeramente en función de la versión del sistema operativo que se ejecuta en el dispositivo del usuario final.  En este tema se describe la experiencia del usuario final en Windows Phone.

## Inscripción

1.  Si un usuario ya está inscrito en Intune y es compatible, no verá ninguna diferencia en los dispositivos Windows; seguirá pudiendo obtener acceso al correo electrónico. Los usuarios que aún no se hayan inscrito en Intune recibirán un correo electrónico de cuarentena parecido al de este ejemplo:

    ![Captura de pantalla que muestra el correo electrónico de cuarentena que recibe un usuario en un dispositivo Windows Phone](./media/ProtectEmail/EUX-Windows-quarantineEmail.png)

    El usuario hace clic en **Empezar ahora** para comenzar la inscripción del dispositivo.

2.  En la pantalla Configuración de acceso a la empresa, el usuario hace clic en **Empezar** para iniciar la configuración de su dispositivo y comprobar si es compatible.

    ![Captura de pantalla que muestra la pantalla Configuración de acceso a la empresa en un dispositivo Windows Phone](./media/ProtectEmail/EUX-Windows1-company-Access-Setup.png)

3.  En la pantalla Inscribir un dispositivo, el usuario hace clic en **Confirmar inscripción** para iniciar la inscripción de su dispositivo.

    ![Captura de pantalla que muestra la pantalla Inscripción de dispositivos en un dispositivo Windows Phone](./media/ProtectEmail/EUX-Windows3-enroll-Device.png)

    Durante la inscripción, se instala el perfil de administración de dispositivos móviles, que permite al administrador de TI administrar el dispositivo de forma remota. Podría pedirse al usuario que acepte un certificado que autoriza la Unión al área de trabajo.

    ![Captura de pantalla que muestra Unión al lugar de trabajo en un dispositivo Windows Phone](./media/ProtectEmail/EUX-Windows4-workplaceJoin1.png)

4.  El usuario inicia sesión con la dirección de correo electrónico que usa con Office. Después de iniciar la sesión, es posible que tenga que hacer clic en **Confirmar inscripción** otra vez para continuar con la inscripción del dispositivo.

    ![Captura de pantalla que muestra Unión al lugar de trabajo en curso en un dispositivo Windows Phone](./media/ProtectEmail/EUX-Windows5-workplaceJoin2.png)

    Se comprueba el dispositivo para garantizar que se ha inscrito.

    ![Captura de pantalla que muestra que se inicia la inscripción de dispositivos en un dispositivo Windows Phone](./media/ProtectEmail/EUX-Windows6-checking-Enrollment.png)

5.  Luego, el usuario completa el proceso de inscripción seleccionando su dispositivo y haciendo clic en **Seleccionar**. Si el dispositivo no aparece, puede seleccionar **Mi dispositivo no está en la lista** para intentarlo de nuevo.

    ![Captura de pantalla que muestra que el usuario debe confirmar sus dispositivos para un dispositivo Windows Phone](./media/ProtectEmail/EUX-Windows7-confirm-Device.png)

    El dispositivo se comprueba para garantizar su conformidad con las directivas de la empresa.

    ![Captura de pantalla que muestra que se está comprobando el cumplimiento de un dispositivo Windows Phone](./media/ProtectEmail/EUX-Windows9-checking-Compliance.png)

6.  Si hay un problema de cumplimiento, se pedirá al usuario que resuelva el problema (por ejemplo, creando una contraseña válida) y que haga clic en **Comprobar cumplimiento** para continuar.

    ![Captura de pantalla que muestra que el usuario debe resolver los problemas de cumplimiento en un dispositivo Windows Phone](./media/ProtectEmail/EUX-Windows13-resolve-Compliance.png)

    Después de comprobar el cumplimiento, el usuario verá que la inscripción se está activando.

    ![Captura de pantalla que muestra que se inicia la activación de la inscripción en un dispositivo Windows Phone](./media/ProtectEmail/EUX-Windows10-activating-Enrollment.png)

7.  Se activa la inscripción y el usuario hace clic en **Continuar** para completar el proceso. Luego, el usuario hace clic en **Listo** para salir de la instalación.

    ![Captura de pantalla que muestra que se ha completado la configuración de acceso a la empresa en un dispositivo Windows Phone](./media/ProtectEmail/EUX-Windows11-COMPLETE.png)

    Después de inscribir al usuario y de comprobar el cumplimiento, el acceso al correo electrónico debería estar disponible en cuestión de minutos.

Si el usuario sigue estos pasos para inscribirse y comprobar el cumplimiento, pero sigue sin tener acceso al correo electrónico en su dispositivo móvil, puede seguir estos pasos adicionales para intentar solucionar el problema:

-   En primer lugar, compruebe que el dispositivo está inscrito. De lo contrario, el usuario seguirá los pasos ya descritos.

-   Compruebe que el dispositivo cumple las normas haciendo clic en **Comprobar cumplimiento**. Si se identifica un error de cumplimiento, el usuario puede seguir las instrucciones sobre cómo resolverlo específicas para su dispositivo móvil como, por ejemplo, de qué manera restablecer la contraseña.

-   Llame al departamento de soporte técnico.

## Problemas y soluciones
Cada 8 horas, de forma predeterminada, se comprueban los dispositivos para garantizar que siguen cumpliendo las normas. Si un dispositivo que cumplía las normas pasa a considerarse no conforme (por ejemplo, si se agrega o se modifica una directiva de cumplimiento), el usuario puede seguir estos pasos para volver al cumplimiento:

1.  El usuario recibe la notificación, en el correo electrónico o en el dispositivo, que indica que el dispositivo no cumple las normas. En este momento, el dispositivo se pone en cuarentena en Exchange.

2.  Si el usuario intenta obtener acceso al correo electrónico, se le redirige a la pantalla Configuración de acceso a la empresa desde el portal de empresa de Intune, donde se muestra la falta de cumplimiento.

    ![Captura de pantalla que muestra que el dispositivo Windows Phone no es compatible](./media/ProtectEmail/EUX-Windows14-OutOfCompliance.png)

3.  El usuario hace clic en **Continuar** y aparece el problema de cumplimiento que impide el acceso al correo electrónico.

4.  Una vez solucionado el problema, el usuario hace clic en **Comprobar cumplimiento** para comprobar que se ha resuelto el problema.

5.  Si el problema está solucionado, el usuario hace clic en **Continuar** para completar el proceso. El correo electrónico debería estar disponible de nuevo tras unos minutos.

### Próximos pasos
La experiencia del usuario final es ligeramente diferente en otros dispositivos móviles. Puede obtener más información sobre la experiencia del usuario final en [Android](end-user-experience-conditional-access-android.md) e
[iOS](end-user-experience-conditional-access-ios.md).


<!--HONumber=Apr16_HO4-->


