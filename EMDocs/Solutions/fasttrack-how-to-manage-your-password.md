---
title: "Cómo administrar su contraseña"
description: "Cómo administrar su propia contraseña"
keywords: 
author: NathBarn
ms.author: NathBarn
manager: angrobe
ms.date: 02/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 162e59f3-33a2-44b5-a59f-24612dc743f3
ms.reviewer: 
ms.suite: ems
ms.openlocfilehash: 1bf552e92104a7872099e555df12993dd4258293
ms.sourcegitcommit: 0541e4aa400a818551469fe9df8929c25c2dd918
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/25/2017
---
# <a name="how-to-manage-your-own-password"></a>Cómo administrar su propia contraseña

Si es usted un usuario (no un administrador) de una organización que usa Office 365 o cuentas de Microsoft para acceder a recursos de trabajo, lea las secciones siguientes para aprender a corregir problemas comunes relacionados con su contraseña.

## <a name="how-to-register-for-password-reset"></a>Cómo registrarse para restablecer la contraseña
La forma más rápida de registrarse para restablecer la contraseña es ir a [http://aka.ms/ssprsetup](http://aka.ms/ssprsetup).

1.  Vaya a [http://aka.ms/ssprsetup](http://aka.ms/ssprsetup).
2.  Escriba su nombre de usuario y su contraseña.
3.  Elija una opción para registrarse haciendo clic en **Configurarlo ahora**. En este caso, haré una demostración registrando mi **teléfono de autenticación**.
![Captura de pantalla en la que se muestra blabla](./media/ft-mngPW-1-setup.png)
4.  Seleccione el código de país en la lista desplegable y escriba su número de teléfono completo con el código de área.
![Captura de pantalla en la que se muestra cómo seleccionar un código de país ](./media/ft-mngPW-2-enterNumber.png)![Captura de pantalla en la que se muestra dónde indicar un número de teléfono](./media/ft-mngPW-3-enterNumber2.png)
5.  Seleccione una de las opciones, **Enviarme un mensaje de texto** o **Llamarme por teléfono**. En este caso, seleccionaré **Enviarme un mensaje de texto**, de modo que se enviará un código de 6 dígitos a mi teléfono. Espere a que el código llegue a su teléfono.
![Captura de pantalla en la que se muestra un código de 6 dígitos que se ha enviado a un teléfono](./media/ft-mngPW-4-textCode.png)
6.  Cuando reciba el código, escríbalo en el cuadro de entrada y haga clic en "Comprobar".
7.  Cuando vea **Gracias**, ya habrá finalizado. Ahora puede usar la opción que ha registrado para restablecer la contraseña en cualquier momento desde [https://passwordreset.microsoftonline.com](https://passwordreset.microsoftonline.com).
![Captura de pantalla en la que se muestra el mensaje de agradecimiento recibido al completar el registro](./media/ft-mngPW-5-thanks.png)

> [!IMPORTANT]
> Si el administrador le permite registrar más de una opción, se recomienda que también registre una opción de copia de seguridad por si pierde su teléfono o no puede acceder a su correo electrónico.

## <a name="how-to-reset-your-password"></a>Cómo restablecer la contraseña
Siga los pasos que se indican a continuación para restablecer la contraseña de su cuenta profesional o educativa desde cualquier pantalla de inicio de sesión en una cuenta profesional o educativa.

> [!IMPORTANT]
> Esta característica solo está disponible si el administrador la ha activado. Si no está activada, verá un mensaje que le indica que la cuenta no está habilitada para esta característica. En este caso, puede usar el vínculo "Póngase en contacto con el administrador" para ponerse en contacto con su administrador y desbloquear la cuenta.
>
Si el administrador ha habilitado esta característica para usted, debe registrarse para poder usarla. Puede hacerlo desde aquí: [http://aka.ms/ssprsetup](http://aka.ms/ssprsetup).

1.  En la página de inicio de sesión de la cuenta profesional o educativa, haga clic en el vínculo "Can't access your account?" (¿No puede acceder a la cuenta?) o "¿Ha olvidado la contraseña?", o bien vaya directamente a [https://passwordreset.microsoftonline.com](https://passwordreset.microsoftonline.com).
![Captura de pantalla en la que se muestra el primer mensaje que un usuario recibe si no se reconoce su identificador de usuario o su contraseña](./media/ft-mngPW-6-resetPWbegin.png)
2.  En la página para identificarse, escriba el identificador de su cuenta profesional o educativa y demuestre que no es un robot superando el CAPTCHA.
![Captura de pantalla en la que se solicita al usuario que escriba su identificador de usuario y el código captcha que se muestra](./media/ft-mngPW-7-enterID.png)
3.  Haga clic en **Siguiente**.
4.  Elija una opción para restablecer su contraseña. Según cómo haya configurado el sistema el administrador, podría ver una o varias de las opciones siguientes:
 - **Enviar un mensaje de correo electrónico a mi dirección alternativa**: envía un correo electrónico con un código de 6 dígitos a su correo electrónico alternativo o a su correo electrónico de autenticación (usted decide).
  - **Enviar mensaje de texto a mi teléfono móvil**: envía un mensaje de texto con un código de 6 dígitos a su teléfono móvil o a su correo electrónico de autenticación (usted decide).
  - **Llamar a mi teléfono móvil**: se realiza una llamada a su teléfono móvil o a su teléfono de autenticación (usted decide). Pulse la tecla # para comprobar la llamada.
 - **Llamar a mi teléfono del trabajo**: se realiza una llamada a su teléfono del trabajo. Pulse la tecla # para comprobar la llamada.
 - **Responder a mis preguntas de seguridad**: se muestran las preguntas de seguridad previamente registradas para que las responda.
 ![Captura de pantalla en la que se solicita al usuario que elija el método mediante el que quiere ponerse en contacto para la verificación](./media/ft-mngPW-8-answerQuestions.png)
5.  Usaremos como ejemplo la opción **Enviar mensaje de texto a mi teléfono móvil**. Si usa una opción de tipo telefónico, tendrá que comprobar su número de teléfono antes de que se le envíe un mensaje de texto. Escriba su número de teléfono completo y, después, haga clic en **Siguiente** para comprobar que es correcto y que se envíe un mensaje de texto.
![Captura de pantalla en la que se muestra que el usuario debe indicar el número de teléfono donde recibirá el mensaje de texto de verificación](./media/ft-mngPW-9-textNumber.png)
6.  Cuando reciba el mensaje de texto, asegúrese de que usa el código de comprobación incluido en el cuerpo del mensaje, no el número desde el que se envió el código. Es posible que el mensaje de texto tarde unos minutos en llegar, por lo que puede realizar otra tarea mientras tanto.
![Captura de pantalla en la que se muestra el código de verificación que se ha recibido](./media/ft-mngPW-10-verificationCode.png)
7.  Ahora, escriba el código que ha recibido en el teléfono en el cuadro de entrada de la página.
![Captura de pantalla en la que se muestra que el usuario debe escribir el código de verificación que acaba de recibir](./media/ft-mngPW-11-enterCode.png)
8.  El administrador podría solicitar un segundo paso de comprobación, en cuyo caso tendrá que repetir el paso 4 con otra opción seleccionada.
9.  En la pantalla "elegir una contraseña nueva", seleccione una contraseña nueva, confirme la opción y haga clic en **Finalizar**.
![Captura de pantalla en la que se muestra que el usuario debe escribir la contraseña nueva y, después, confirmarla](./media/ft-mngPW-12-clickFinish.png)
10. Cuando vea la página en la que se le indica que lo ha hecho correctamente, habrá finalizado. Ahora puede iniciar sesión con la contraseña nueva.
![Captura de pantalla en la que se muestra que el proceso de restablecimiento de la contraseña se ha completado](./media/ft-mngPW-13-success.png)
¿Ha experimentado algún problema al restablecer la contraseña? Lea la información relacionada con los [problemas comunes y sus soluciones](https://azure.microsoft.com/en-us/documentation/articles/active-directory-passwords-update-your-own-password/#common-problems-and-their-solutions).

### <a name="want-to-learn-more"></a>¿Desea obtener más información?
Consulte [Enterprise Mobility + Security](https://www.microsoft.com/en-us/server-cloud/enterprise-mobility/overview.aspx).
