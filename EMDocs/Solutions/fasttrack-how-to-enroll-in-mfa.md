---
title: "Cómo inscribirse en la autenticación multifactor"
description: "Cómo configurar el método preferido para la comprobación de seguridad adicional"
keywords: 
author: craigcaseyMSFT
manager: jeffgilb
ms.date: 09/28/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 06e21ca9-ed6a-4f6e-a7e2-5445aaeb3552
ROBOTS: noindex
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c704180f9c607e39c27d75676eec30afa1a1730c
ms.openlocfilehash: b349cae1f73c4dab5dbce45937b91a8aaca7c052


---

# Cómo configurar el método preferido para la comprobación de seguridad adicional



Se usa la configuración de comprobación de seguridad adicional cuando un administrador ha configurado su cuenta para requerir que se usen tu contraseña y una respuesta desde tu teléfono para comprobar tu identidad. Si un administrador ha configurado su cuenta para que requiera una comprobación de seguridad adicional, no podrá iniciar sesión hasta que haya finalizado el proceso de inscripción automática.

La primera vez que inicie sesión después de que se haya configurado su cuenta, se le pedirá que inicie el proceso de inscripción automática. Puede empezar este proceso haciendo clic en Configurarlo ahora.

![Captura de pantalla en la que se le pide al usuario que se inscriba en la comprobación de seguridad adicional de su cuenta.](./media/ft-enrollMFA-1-beginProcess.png)

Mediante el proceso de inscripción, podrá especificar su método preferido de comprobación de identidad. Puede ser cualquiera de las opciones que aparecen en la tabla siguiente. Para obtener información adicional, incluido un tutorial, simplemente haga clic en uno de los métodos.


|Método|Descripción|
|------------|----------------------------------|
|Llamada de teléfono móvil|Realiza una llamada de voz automatizada al número de teléfono de autenticación. El usuario responde a la llamada y pulsa la # del teclado del teléfono para autenticarse. Este número de teléfono no se sincronizará con Active Directory local.|
|Mensaje de texto en el teléfono móvil|Envía al usuario un mensaje de texto que contiene un código de comprobación. Se le pide al usuario o bien que responda al mensaje de texto con el código de comprobación o bien que lo escriba en la interfaz de inicio de sesión.|
|Llamada al teléfono del trabajo|Establece una llamada de voz automática al usuario. El usuario responde a la llamada y pulsa la # del teclado del teléfono para autenticarse.|
|Aplicación móvil|Inserta una notificación en la aplicación móvil de Azure Authenticator en el smartphone o la tableta del usuario. El usuario pulsa "Comprobar" en la aplicación para autenticarse. Como alternativa, también se puede usar la aplicación como un token OTP para proceder a la autenticación sin conexión. El usuario escribe el token en la pantalla de inicio de sesión para autenticarse.|

_La aplicación de Azure Authenticator puede operar en dos modos diferentes para proporcionar la seguridad adicional que un servicio de autenticación multifactor puede proporcionar. Son los siguientes:_

- **Notificación**: en este modo, la aplicación Azure Authenticator evita el acceso no autorizado a las cuentas y detiene las transacciones fraudulentas. Este proceso se lleva a cabo mediante una notificación de inserción en su teléfono o en el dispositivo que tengas registrado. Lo único que tiene que hacer es consultar la notificación y, si es legítima, seleccione **Autenticar**. De lo contrario, puede elegir **Denegar** o bien denegar e informar sobre la notificación fraudulenta. Para más información sobre generar informes de notificaciones fraudulentas, consulte Cómo usar la función Denegar e Informar de fraudes para autenticación multifactor.
- **Contraseña de un solo uso**: en este modo, la aplicación Azure Authenticator se puede usar como token de software para generar un código de comprobación OATH. Después, este código de comprobación se puede escribir junto con el nombre de usuario y la contraseña a fin de proporcionar una segunda forma de autenticación.

La aplicación Azure Authenticator está disponible para [Windows Phone](http://www.windowsphone.com/en-us/store/app/azure-authenticator/03a5b2bf-6066-418f-b569-e8aecbc06e50), [Android](https://play.google.com/store/apps/details?id=com.azure.authenticator) e [iOS](https://itunes.apple.com/us/app/azure-authenticator/id983156458).

## Teléfono móvil (mensaje de texto o llamada)
Si quiere usar el teléfono móvil como método de contacto principal, lleve a cabo los pasos siguientes. Le indicarán cómo configurar la autenticación multifactor para usar el teléfono móvil como método de contacto, ya sea mediante una llamada o un mensaje de texto.

1. En **Step 1: How should we contact you?** (Paso 1: ¿Cómo debemos ponernos en contacto con usted?) seleccione **Teléfono de autenticación**.

  ![Captura de pantalla en la que se muestra que el usuario quiere ser contactado por teléfono.](./media/ft-enrollMFA-2-securityVerification.png)
2.  En el cuadro **País o región**, seleccione un valor de la lista desplegable. Es posible que ya se muestre un valor predeterminado.
3.  En el cuadro situado junto a **País o región**, escriba su número de teléfono móvil. Incluya el código de área.
Se permiten los espacios, pero no los caracteres de puntuación. Por ejemplo, puede escribir 5554445555 y 555 444 5555, pero no 555-444-5555 ni (555) 444 5555.
4.  Seleccione el modo que prefiera usar con su teléfono móvil: mensaje de texto o llamada.
5.  Haga clic en **Siguiente**.
6.  Haga clic en el botón **Comprobar ahora**. De este modo, se establecerá una llamada o se enviará un mensaje de texto a su teléfono móvil. Asegúrese de que tiene a mano el teléfono. En función del modo que haya seleccionado (mensaje de texto o llamada), la respuesta será diferente.
 - Si ha seleccionado el modo de mensaje de texto, se le enviará un código de 6 dígitos. Escribe este código en el cuadro que aparecerá en el explorador.

        ![Screenshot asking user to enter the code that was texted to them](./media/ft-enrollMFA-3-textCode.png)
 - Si has seleccionado el modo llamada, recibirás un llamada de teléfono. Responde a la llamada con el signo # del teléfono.

        ![Screenshot prompting user to answer their phone to continue enrollment process](./media/ft-enrollMFA-4-phoneCode.png)
7. Haga clic en **Siguiente**.
8.  Llegado a este punto, ya ha configurado el método de contacto. Ahora es el momento de configurar las contraseñas de aplicación para aplicaciones sin explorador, como Outlook 2010 o versiones anteriores. Si no usa estas aplicaciones, haga clic en **Listo**. En caso contrario, **continúe** con el siguiente paso.
9. Si usa estas aplicaciones, **copie** la contraseña de aplicación proporcionada.

  ![Captura de pantalla en la que se le pide al usuario que escriba la contraseña de aplicación.](./media/ft-enrollMFA-5-copyPW.png)
10. Pega la contraseña que copiaste al portapapeles en tu aplicación sin explorador.
11. Haga clic en **Listo**.

## Llamada al teléfono del trabajo
En esta sección del documento se le mostrará cómo configurar Azure Multi-Factor Authentication para usar el teléfono del trabajo como método de contacto principal.
1. Seleccione Teléfono del trabajo en la lista desplegable.

  ![Captura de pantalla en la que se muestra que el usuario quiere ser contactado a través del teléfono del trabajo.](./media/ft-enrollMFA-6-officePhone.png)
2.  Especifique el país en la lista desplegable y escriba el número del teléfono del trabajo.
3.  Haga clic en **Ponerse en contacto conmigo**. De este modo se establecerá una llamada a tu teléfono del trabajo. Asegúrese de que se encuentra cerca del teléfono.
4.  Haga clic en **Siguiente**.
5.  Llegado a este punto, ya ha configurado el método de contacto. Ahora es el momento de configurar las contraseñas de aplicación para aplicaciones sin explorador, como Outlook 2010 o versiones anteriores. Si no usa estas aplicaciones, haga clic en **Listo**. En caso contrario, **continúe** con el siguiente paso.
7.  Si usa estas aplicaciones, copie la contraseña de aplicación proporcionada.
8.  Pega la contraseña que copiaste al portapapeles en tu aplicación sin explorador.

  ![Captura de pantalla en la que se le pide al usuario que escriba la contraseña de aplicación.](./media/ft-enrollMFA-7-pastePW.png)
9.  Haga clic en **Listo**.

## Aplicación móvil
En esta sección del artículo se le mostrará cómo configurar Azure Multi-Factor Authentication para usar la aplicación móvil como método de contacto principal.

La aplicación Azure Authenticator está disponible para Windows Phone, Android e iOS.

1. Seleccione **Aplicación móvil** en la lista desplegable.

  ![Captura de pantalla en la que se muestra que el usuario quiere ser contactado a través de una aplicación móvil.](./media/ft-enrollMFA-8-mobileApp.png)
2.  Seleccione Notificación o Contraseña de un solo uso y haga clic en **Configurar**.
3.  En el teléfono que tenga instalada la aplicación Azure Authenticator, inicie la aplicación y haga clic en **Digitalizar código de barras**.

  ![Captura de pantalla en la que se le pide al usuario que seleccione la opción Digitalizar código de barras.](./media/ft-enrollMFA-9-scanBarcode.png)
4.  Escanea la imagen de código de barras que ha aparecido con la pantalla para configurar aplicación móvil. Haga clic en **Listo** para cerrar la pantalla del código de barras. Si no puede digitalizar el código de barras, puede escribir la información manualmente.

  ![Captura de pantalla en la que se le pide al usuario que digitalice el código de barras que apareció en la aplicación móvil.](./media/ft-enrollMFA-9-scanBarcode2.png)
5.  En el teléfono, comenzará a activarse. Una vez que se haya completado, haga clic en **Ponerse en contacto conmigo**. Se enviará una notificación o un código de comprobación a su teléfono. Haga clic en **Comprobar**.

  ![Captura de pantalla en la que se pide al usuario que compruebe el código enviado a su teléfono.](./media/ft-enrollMFA-10-verifyActivation.png)
6.  Haga clic en **Cerrar**. En este punto, la comprobación se debe haber realizado correctamente.
7.  Se recomienda que escriba ahora su número de teléfono móvil por si pierde el acceso a la aplicación móvil.
8.  Especifique el país en la lista desplegable y escriba su número de teléfono móvil en el cuadro situado junto al país. Haga clic en **Siguiente**.
9.  Llegado a este punto, ya ha configurado el método de contacto. Ahora es el momento de configurar las contraseñas de aplicación para aplicaciones sin explorador, como Outlook 2010 o versiones anteriores. Si no usa estas aplicaciones, haga clic en **Listo**. En caso contrario, **continúe** con el siguiente paso.
10. Si usa estas aplicaciones, copie la contraseña de aplicación proporcionada.
11. Pega la contraseña que copiaste al portapapeles en tu aplicación sin explorador.

  ![Captura de pantalla en la que se le pide al usuario que escriba la contraseña de aplicación.](./media/ft-enrollMFA-11-securityVerification.png)
12. Haga clic en **Listo**.

### ¿Desea obtener más información?
Consulte [Enterprise Mobility Suite](https://www.microsoft.com/en-us/server-cloud/enterprise-mobility/overview.aspx).



<!--HONumber=Sep16_HO4-->


