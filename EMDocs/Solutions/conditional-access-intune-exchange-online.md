---
# required metadata

title: Uso del acceso condicional con Microsoft Intune y Exchange Online
description:
keywords:
author: craigcaseyMSFT
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: 8cfe421b-52c9-4d44-8df1-15c82375c335

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: 
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Implementación de Exchange Online con Intune

Ahora que ha leído la [guía de arquitectura para proteger los documentos y correos electrónicos de la empresa](../Solutions/architecture-guidance-for-protecting-company-email-and-documents.md), ya puede continuar con la implementación de una solución.

Para que Intune administre dispositivos móviles directamente, los usuarios deben inscribir los dispositivos en esta plataforma.

## Pasos de implementación
Siga estos pasos para implementar la solución Exchange Online con Intune:

### Paso 1: cree directivas de cumplimiento e impleméntelas a los usuarios.
Las directivas de cumplimiento definen las reglas y los valores de configuración que un dispositivo debe cumplir para que se le considere conforme a las directivas de acceso condicional. Siga los pasos de [Crear una directiva de cumplimiento en Microsoft Intune](https://stage.docs.microsoft.com/en-us/intune/deployuse/create-a-device-compliance-policy-in-microsoft-intune) para crear e implementar directivas de cumplimiento.

Si quiere tener la capacidad de quitar todos los mensajes de correo corporativo de un dispositivo iOS cuando este deje de formar parte de la empresa, tiene que crear e implementar un perfil de correo electrónico. Luego, establezca una directiva de cumplimiento que especifique que Intune administra los perfiles de correo electrónico. Debe implementar el perfil de correo electrónico en el mismo conjunto de usuarios al que va dirigido esta directiva de cumplimiento.

![Captura de pantalla que muestra la página "Reglas" del Asistente para crear directivas de cumplimiento, donde puede especificar que un perfil de correo electrónico debe administrarse mediante Intune](./media/ProtectEmail/Hybrid-Onprem-ExchSrvr-Wizard6.PNG)

Si se especifica esta directiva de cumplimiento, un usuario que ya haya configurado su cuenta de correo electrónico tendrá que eliminarla manualmente y, luego, Intune la agregará de nuevo en el proceso de registro descrito en [Experiencia de acceso condicional del usuario final](../Solutions/end-user-experience-conditional-access.md).

> [!IMPORTANT]
> Si no ha implementado una directiva de cumplimiento y habilitado la directiva de acceso condicional a Exchange, se permitirá el acceso a todos los dispositivos destinatarios.

### Paso 2: evalúe el impacto de la directiva de acceso condicional.
Si ha configurado una conexión entre Intune y Exchange mediante el [conector de servicio a servicio de Microsoft Intune](https://stage.docs.microsoft.com/en-us/intune/deployuse/intune-service-to-service-exchange-connector), puede usar los **informes de inventario de dispositivos móviles** para identificar los clientes de correo de EAS que tendrán el acceso bloqueado a Exchange después de configurar la directiva de acceso condicional.

Siga las instrucciones de [Paso 2: evalúe el impacto de la directiva de acceso condicional](https://stage.docs.microsoft.com/en-us/intune/deployuse/restrict-access-to-exchange-online-with-microsoft-intune#configure-conditional-access) para identificar los usuarios que se verán afectados por la directiva de acceso condicional.

### Paso 3: configure grupos de usuarios para la directiva de acceso condicional.
El destino de las directivas de acceso condicional se define en distintos grupos de usuarios en función de los tipos de directiva. Estos grupos contienen los usuarios de destino o exentos de la directiva. Cuando un usuario es destinatario de una directiva, cada dispositivo que use debe ser conforme con el fin de obtener acceso al correo electrónico.

Para obtener más información, consulte [Paso 3: configure grupos de usuarios para la directiva de acceso condicional](https://stage.docs.microsoft.com/en-us/intune/deployuse/restrict-access-to-exchange-online-with-microsoft-intune#configure-conditional-access).

### Paso 4: configure la directiva de acceso condicional.
Las directivas de acceso condicional de Exchange Online utilizan el siguiente flujo para evaluar si se permitirá o bloqueará el acceso a los dispositivos.

![Diagrama de flujo que muestra cómo las directivas de acceso condicional de Exchange Online evalúan si se permitirá o bloqueará el acceso a los dispositivos](./media/ProtectEmail/conditional-access-8-1.png)

Siga la información proporcionada en [Configurar la directiva de acceso condicional](https://stage.docs.microsoft.com/en-us/intune/deployuse/restrict-access-to-exchange-online-with-microsoft-intune#configure-conditional-access) para establecer la directiva de acceso condicional.



## Generación de informes

### Supervisar el cumplimiento y las directivas de acceso condicional
Para ver los dispositivos que tienen bloqueado el acceso a Exchange, siga estos pasos:

En el panel de Intune, haga clic en el icono **Dispositivos bloqueados de Exchange** para que se muestren el número de dispositivos bloqueados y los vínculos para obtener más información.
![Captura de pantalla que muestra el icono "Dispositivos bloqueados de Exchange" del panel de Intune](./media/ProtectEmail/intune-sa-6blocked-devices.PNG)



## Próximos pasos
Cuando haya implementado una solución para proteger el correo electrónico corporativo y los datos de correo electrónico de los dispositivos móviles, puede obtener más información sobre [la experiencia del usuario final de acceso condicional](../Solutions/end-user-experience-conditional-access.md). Esto le ayudará a prepararse para problemas que podrían surgir al inscribir sus dispositivos específicos.


<!--HONumber=Apr16_HO2-->


