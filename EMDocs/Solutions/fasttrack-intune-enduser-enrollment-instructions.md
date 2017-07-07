---
title: "Instrucciones de inscripción de Intune de usuario final para los administradores de TI"
description: "Instrucciones de inscripción de Intune de usuario final para los administradores de TI"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5c13446e-aa31-47df-ad9d-373be7660197
ms.reviewer: 
ms.suite: ems
ms.translationtype: Human Translation
ms.sourcegitcommit: c3b2ab326254602425d5f8149e5d456e578b989c
ms.openlocfilehash: 395ed9dafde409d2357bfe7f72283bb7eff24820
ms.contentlocale: es-es
ms.lasthandoff: 07/07/2017


---

# <a name="end-user-intune-enrollment-instructions-for-it-administrators"></a>Instrucciones de inscripción de Intune de usuario final para los administradores de TI

Este documento contiene instrucciones de inscripción que puede personalizar y entregar a los usuarios para ayudarles a inscribir sus dispositivos iOS y Android en Microsoft Intune™ (en el caso de dispositivos Windows, consulte Usar un dispositivo Windows con Intune). Le recomendamos que copie las secciones de este documento que considere más apropiadas para los usuarios. Por ejemplo, puede que le interese crear un documento único para cada plataforma de dispositivo o agregar más capturas de pantalla.

A parte de estas instrucciones escritas, puede incluir hipervínculos a los vídeos de usuario final de Intune, que se encuentran en [https://channel9.msdn.com/Series/IntuneEnrollment](https://channel9.msdn.com/Series/IntuneEnrollment).

> [!NOTE]
> Microsoft, Intune y Office 365 son marcas comerciales de Microsoft Corporation. iPhone, Mac y Apple son marcas comerciales de Apple, Inc. Android es una marca comercial de Google Inc. Samsung KNOX es una marca comercial de Samsung Electronics Co., Ltd.

## <a name="why-enroll-in-intune"></a>¿Por qué inscribirse en Intune?
A la hora de inscribirse, puede usar su dispositivo móvil para acceder a archivos y datos profesionales o educativos. Además, permite al departamento de TI administrar esos recursos profesionales o educativos y mantenerlos protegidos, al mismo tiempo que usted puede usar su dispositivo preferido para realizar su trabajo.

Para usar el dispositivo en el trabajo, inscríbalo en Intune mediante el portal de empresa. Después podrá encontrar fácilmente aplicaciones de empresa para instalar, ver otros dispositivos agregados y encontrar los datos de contacto del administrador de TI. Además, le proporciona al administrador de TI permiso para administrar el dispositivo, a fin de ayudar a proteger la información de la empresa en el dispositivo. Antes de iniciar la inscripción, asegúrese de que tiene una buena conexión Wi-Fi o móvil a Internet.

## <a name="enroll-your-android-device-in-intune-using-the-intune-company-portal-app"></a>Inscribir un dispositivo Android en Intune mediante la aplicación de portal de empresa de Intune

Estos pasos de inscripción son adecuados para dispositivos Android de Samsung Knox y dispositivos Android "nativos" (distintos de Samsung Knox). Para saber si tiene un dispositivo Samsung Knox, vaya a **Ajustes > Acerca del teléfono**. Si no ve la palabra "Knox" en la lista, significa que el suyo es un dispositivo Android nativo. Las pantallas que se muestran en el dispositivo pueden parecer ligeramente diferentes de las de esta sección.

Si recibe un error al intentar inscribir el dispositivo en Intune, consulte [Enviar errores de inscripción al administrador de TI](https://technet.microsoft.com/en-US/library/mt502762(TechNet.10).aspx#BKMK_andr_send_enroll_errors).

Antes o después de la inscripción, se le pedirá que elija una categoría que describa de la mejor forma posible cómo usar el dispositivo. El administrador de TI usa esta categoría para ayudar a determinar a qué aplicaciones tiene acceso.
1.  Instale la aplicación gratuita de portal de empresa de Microsoft Intune en el dispositivo desde [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal).
2.  Abra la aplicación de portal de empresa de Microsoft Intune.
3.  En la pantalla de **inicio de sesión** del Portal de empresa, pulse **Iniciar sesión** y luego inicie sesión con su cuenta profesional o educativa.

  ![Captura de pantalla en la que se muestra la pantalla de inicio de sesión del portal de empresa de Intune en un dispositivo Android.](./media/ft-userEnrollAndroid-1-signUp.png)

4.  Si el administrador de TI configuró los términos y condiciones, pulse **ACEPTAR** para aceptar los términos.

  ![Captura de pantalla en la que se le solicita al usuario que acepte los términos y condiciones en un dispositivo Android.](./media/ft-userEnrollAndroid-2-accept.png)
5.  Si usa un dispositivo Android 6.0 o de una versión posterior, lleve a cabo este paso. En caso contrario, vaya al paso siguiente.

  Si el administrador de TI ha configurado algunas directivas, puede que aparezca uno de los mensajes siguientes o ambos:

  - Si ve el mensaje **Allow Company Portal to access your contacts?** (¿Permitir que el portal de empresa tenga acceso a los contactos?), pulse **PERMITIR**. Pulsar PERMITIR no entraña riesgos, puesto que Microsoft nunca accede a sus contactos. Google controla el texto del mensaje, por lo que Microsoft no puede cambiarlo. Al permitir el acceso, lo único que ocurre es que la aplicación de portal de empresa puede tener acceso a los registros de datos para ayudar a solucionar problemas con el dispositivo.

        ![Captura de pantalla donde se solicita al usuario que permita al portal el acceso a los contactos en un dispositivo Android](./media/ft-userEnrollAndroid-3-accessContacts.png)
  - Si ve el mensaje **Allow Company Portal to access your contacts?** (¿Permitir que el portal de empresa realice y administre llamadas telefónicas?), pulse **PERMITIR**. Pulsar PERMITIR no entraña riesgos, puesto que Microsoft nunca realiza ni controla sus llamadas de teléfono. Google controla el texto del mensaje, por lo que Microsoft no puede cambiarlo. Cuando se permite el acceso, lo único que se permite es que la aplicación de portal de empresa vea el número de teléfono y un identificador denominado IMEI.

        ![Captura de pantalla donde se solicita al usuario que permita al portal administrar las llamadas telefónicas en un dispositivo Android](./media/ft-userEnrollAndroid-4-manageCalls.png)

  Si pulsa **RECHAZAR**, los mensajes aparecerán de nuevo la próxima vez que inicie sesión en la aplicación de portal de empresa, pero puede desactivar los mensajes futuros si pulsa la casilla **No volver a preguntar**. Si más adelante decide permitir el acceso, vaya a **Ajustes > Aplicaciones > Portal de empresa > Permisos > Teléfono** y active el permiso.
6.  Inicie sesión en la aplicación de portal de empresa con su cuenta profesional o educativa y contraseña correspondiente y, luego, pulse en **Iniciar sesión**.

  ![Captura de pantalla en la que se le solicita al usuario que inicie sesión en el portal de empresa en un dispositivo Android.](./media/ft-userEnrollAndroid-5-signIn.png)
7.  En la página Configuración de acceso a la empresa, pulse **EMPEZAR**.

  ![Captura de pantalla en la que se muestra la página Configuración de acceso a la empresa en un dispositivo Android.](./media/ft-userEnrollAndroid-6-beginSetup.png)
8.  Lea lo que podrá hacer cuando inscriba el dispositivo y luego pulse **CONTINUAR**.

  ![Captura de pantalla en la que se muestra información sobre por qué se debe inscribir un dispositivo Android.](./media/ft-userEnrollAndroid-7-whyEnroll.png)
9.  Consulte la lista sobre lo que el administrador de TI puede y no puede ver en el dispositivo inscrito y pulse **CONTINUAR**.

  ![Captura de pantalla en la que se muestra la directiva de privacidad en un dispositivo Android.](./media/ft-userEnrollAndroid-8-privacy.png)
10. Revise algunas de las cosas que es posible que vea cuando pulse Inscribirse. Cuando termine de leer, pulse **INSCRIBIR**.

  ![Captura de pantalla en la que se muestran los pasos de inscripción siguientes en un dispositivo Android.](./media/ft-userEnrollAndroid-9-whatNext.png)
11. En la pantalla para activar el administrador del dispositivo, pulse **ACTIVAR**.

  ![Captura de pantalla en la que se le pide al usuario que active el administrador de dispositivos en un dispositivo Android.](./media/ft-userEnrollAndroid-10-activateAdmin.png)
12. Siga las instrucciones para escribir un PIN o contraseña. Si ya ha configurado un PIN o una contraseña en este dispositivo, no verá esta pantalla y no deberá escribir un PIN o contraseña nueva.

  ![Captura de pantalla en la que se le pide al usuario que escriba su PIN en un dispositivo Android.](./media/ft-userEnrollAndroid-11-enterPIN.png)
13. Siga las instrucciones correspondientes al tipo de dispositivo que use (Android nativo o Samsung Knox). Si no tiene un dispositivo Samsung Knox, siga las instrucciones para Android nativo. Para saber si tiene un dispositivo Samsung Knox, vaya a **Ajustes > Acerca del teléfono**. Si no ve la palabra "Knox" en la lista, significa que el suyo es un dispositivo Android nativo.
 - Dispositivo nativo (distinto de Samsung Knox): en la pantalla **Name the certificate** (Nombre del certificado), pulse **Aceptar** para aceptar el certificado predeterminado.

        ![Screenshot prompting the user to accept the default certificate on a native Android device](./media/ft-userEnrollAndroid-12-android.png)
 - Dispositivo Samsung KNOX: pulse **CONFIRMAR**.

        ![Screenshot prompting the user to confirm the privacy policy for a Samsung Knox device](./media/ft-userEnrollAndroid-13-knox.png)

 Aparecerá el siguiente mensaje en la pantalla mientras Intune inscribe el dispositivo.

  ![Captura de pantalla en la que se muestra que se está inscribiendo el dispositivo Android.](./media/ft-userEnrollAndroid-14-enrollingDevice.png)
14.  En la pantalla **Configuración de acceso a la empresa**, pulse **CONTINUAR**. Si el administrador de TI ha configurado más requisitos de seguridad (como establecer obligatoriamente una contraseña), siga las instrucciones en pantalla y pulse **CONTINUAR** cuando regrese a la pantalla Configuración de acceso a la empresa.

  ![Captura de pantalla en la que se muestra que el dispositivo Android es conforme y se le pide al usuario que continúe.](./media/ft-userEnrollAndroid-15-coAccessSetup.png)
15. Pulse **LISTO**.

  ![Captura de pantalla en la cual se muestra que se ha completado la configuración de acceso a la empresa en un dispositivo Android](./media/ft-userEnrollAndroid-16-SetupComplete.png)
16. El dispositivo ya está inscrito en Intune. Se le dirigirá de nuevo a la aplicación de portal de empresa.
17. Antes de intentar instalar aplicaciones de empresa, vaya a **Ajustes > Seguridad** y active **Fuentes desconocidas**. Si no activa esta opción antes de intentar instalar aplicaciones, verá el mensaje "Instalación bloqueada. Por motivos de seguridad, el teléfono está configurado para bloquear las instalaciones de aplicaciones procedentes de orígenes desconocidos.". Puede pulsar **Configuración** en el cuadro de diálogo del error para ir a la opción **Orígenes desconocidos**.

## <a name="enroll-your-ios-device-in-intune"></a>Inscriba el dispositivo iOS en Intune
Siga estas instrucciones para inscribir el dispositivo iOS en Intune. Para obtener más información sobre la inscripción, consulte [¿Qué ocurre si instala la aplicación de Portal de empresa e inscribe el dispositivo iOS o Mac OS X en Intune?](https://technet.microsoft.com/library/mt598622(TechNet.10).aspx#BKMK_ios_what_happ_enroll). Si recibe un error al intentar inscribir el dispositivo en Intune, consulte [Enviar errores de inscripción al administrador de TI](https://technet.microsoft.com/library/mt598622(TechNet.10).aspx#BKMK_ios_error_enrolling_tbl).

Antes o después de la inscripción, se le pedirá que elija una categoría que describa de la mejor forma posible cómo usar el dispositivo. El administrador de TI usa esta categoría para ayudar a determinar a qué aplicaciones tiene acceso.
1.  Instale la aplicación gratuita de portal de empresa de Microsoft Intune en el dispositivo desde la Tienda de aplicaciones.
2.  Abra la aplicación de portal de empresa de Microsoft Intune.
3.  En la pantalla de **inicio de sesión** del Portal de empresa, pulse **Iniciar sesión** y luego inicie sesión con su cuenta profesional o educativa.

  ![Captura de pantalla en la que se muestra la pantalla de inicio de sesión del portal de empresa de Intune en un dispositivo iOS.](./media/ft-userEnrollIOS-1-signUp.png)
4.  Si el administrador de TI configuró los términos y condiciones de la empresa, pulse **Aceptar** para aceptar los términos.
5.  En la página Configuración de acceso a la empresa, pulse **Empezar**.

  ![Captura de pantalla en la que se le pide al usuario que empiece el proceso de inscripción en un dispositivo iOS.](./media/ft-userEnrollIOS-2-coAccessSetup.png)
6.  Lea lo que podrá hacer cuando inscriba el dispositivo y luego pulse **Continuar**.

  ![Captura de pantalla en la que se muestra información sobre por qué se debe inscribir un dispositivo iOS.](./media/ft-userEnrollIOS-3-whyEnroll.png)
7.  Consulte la lista sobre lo que el administrador de TI puede y no puede ver en el dispositivo inscrito y pulse **Continuar**.

  ![Captura de pantalla en la que se muestra la directiva de privacidad en un dispositivo iOS.](./media/ft-userEnrollIOS-4-privacy.png)
8.  Revise algunas de las cosas que es posible que vea cuando pulse Inscribirse. Cuando termine de leer, pulse **Inscribir**.

  ![Captura de pantalla en la que se muestran los pasos de inscripción siguientes en un dispositivo iOS.](./media/ft-userEnrollIOS-5-whatNext.png)
9.  En la pantalla Instalar perfil, pulse **Instalar** y escriba su contraseña, si se le pide.

  ![Captura de pantalla en la que se le pide al usuario que instale el perfil de administración de un dispositivo iOS.](./media/ft-userEnrollIOS-6-installProfile.png)
10. Pulse **Instalar**.

  ![Captura de pantalla en la que se le pide al usuario que pulse el botón Instalar para instalar el perfil en un dispositivo iOS.](./media/ft-userEnrollIOS-7-tapInstall.png)
11. Pulse **Instalar** para indicar que ha leído la advertencia.

  ![Captura de pantalla en la que se le pide al usuario que indique que ha leído la advertencia de administración de perfiles en un dispositivo iOS.](./media/ft-userEnrollIOS-8-readWarning.png)
12. Pulse **Confiar**.

  ![Captura de pantalla en la que se le pide al usuario que compruebe el origen del perfil en un dispositivo iOS.](./media/ft-userEnrollIOS-9-tapTrust.png)
13. Cuando la pantalla cambie para indicar que el perfil ha terminado de instalarse, pulse **Listo**. Aparece el mensaje "Inscribiendo el dispositivo" en pantalla.

  ![Captura de pantalla en la que se muestra que el perfil se ha instalado en un dispositivo iOS.](./media/ft-userEnrollIOS-10-profileInstalled.png)
14. Cuando se muestre un mensaje en el que se le pregunte si quiere abrir la página en el portal de empresa, pulse en **Abrir**.

  ![Captura de pantalla en la que se le pide al usuario que abra la página en el portal de empresa en un dispositivo iOS.](./media/ft-userEnrollIOS-11-openPage.png)
- En la pantalla Configuración de acceso a la empresa, pulse **Continuar**. Si el administrador de TI ha configurado más requisitos de seguridad (como establecer obligatoriamente una contraseña), siga las instrucciones en pantalla hasta satisfacer todos los requisitos de cumplimiento y pulse **Continuar** cuando regrese a la pantalla Configuración de acceso a la empresa.

  ![Captura de pantalla en la que se muestra que el dispositivo iOS es confirme y se le pide al usuario que continúe.](./media/ft-userEnrollIOS-12-coAccessSetup.png)
15. Pulse **Listo**.

  ![Captura de pantalla en la que se muestra que se ha completado la configuración de acceso a la empresa en un dispositivo iOS.](./media/ft-userEnrollIOS-13-setupComplete.png)

El dispositivo ya está inscrito en Intune. Se le dirigirá de nuevo a la aplicación de portal de empresa.

## <a name="enroll-your-mac-os-x-device-in-intune"></a>Inscribir el dispositivo Mac OS X en Intune
1.  Con un explorador Safari, abra el [Sitio web del Portal de empresa](https://portal.manage.microsoft.com/) y pulse en la barra de notificación.
2.  Pulse en **Este dispositivo no está inscrito o el Portal de empresa no lo identifica**.

  ![Captura de pantalla en la que se muestra que el portal de empresa no puede identificar un dispositivo Mac OS X.](./media/ft-userEnrollMacOSx-1-enrollBegin.png)
3.  Puntee en **Instalar** para iniciar la inscripción del dispositivo.

  ![Captura de pantalla en la que se le pide al usuario que inscriba el dispositivo Mac OS X.](./media/ft-userEnrollMacOSx-2-enrollDevice.png)
4.  En el cuadro de diálogo Install "Management Profile" (Instalar el perfil de administración), pulse **Instalar**. Si se abre un cuadro de diálogo que le pide que escriba sus credenciales, escriba el nombre de usuario y la contraseña y, luego, pulse **Continuar > Instalar**.

  ![Captura de pantalla en la cual se solicita al usuario que instale el perfil de administración en un dispositivo Mac OS X.](./media/ft-userEnrollMacOSx-3-installProfile.png)

Cuando termine la inscripción, verá una página de perfil de administración en la que se muestra que se ha verificado el perfil.

  ![Captura de pantalla en la que se muestra que se ha comprobado el perfil de administración en un dispositivo Mac OS X.](./media/ft-userEnrollMacOSx-4-profileVerified.png)

### <a name="want-to-learn-more"></a>¿Desea obtener más información?
Consulte [Enterprise Mobility + Security](https://www.microsoft.com/en-us/server-cloud/enterprise-mobility/overview.aspx).

