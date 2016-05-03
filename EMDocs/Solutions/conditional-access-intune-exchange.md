---
# required metadata

title: Uso del acceso condicional con Microsoft Intune y Exchange Server local
description:
keywords:
author: craigcaseyMSFT
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: 2a64e898-4c60-48bf-ae14-b05e091e0533

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: 
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Implementación de Exchange local con Intune

Ahora que ha leído la [guía de arquitectura para proteger los documentos y correos electrónicos de la empresa](../Solutions/architecture-guidance-for-protecting-company-email-and-documents.md), ya puede continuar con la implementación de una solución.

Para que Intune administre dispositivos móviles directamente, los usuarios tendrán que inscribir los dispositivos en esta plataforma.

## Pasos de implementación
Siga estos pasos para implementar la solución Exchange Server local con Intune:

### Paso 1: instale y configure el conector de Exchange Server local de Microsoft Intune.

Para los dispositivos móviles que los usuarios no inscriban se puede habilitar la administración de Exchange ActiveSync mediante Exchange Connector. Exchange Connector conecta con su implementación de Exchange y permite administrar los dispositivos móviles a través de la consola de Intune.

Siga los pasos de [Configurar Microsoft Intune On-Premises Connector para Exchange local u Hosted Exchange](https://stage.docs.microsoft.com/en-us/intune/deployuse/intune-on-premises-exchange-connector) para descargar, instalar y configurar Microsoft Intune Exchange Connector.

> [!IMPORTANT]
> Solo puede configurar una conexión de Exchange por cuenta de Intune. Si intenta configurar una conexión adicional, se reemplazará la conexión original con la nueva.

### Paso 2: cree directivas de cumplimiento e impleméntelas para los usuarios.
Las directivas de cumplimiento definen las reglas y los valores de configuración que un dispositivo debe cumplir para que se le considere conforme a las directivas de acceso condicional. Siga los pasos de [Crear una directiva de cumplimiento en Microsoft Intune](https://stage.docs.microsoft.com/en-us/intune/deployuse/create-a-device-compliance-policy-in-microsoft-intune) para crear e implementar directivas de cumplimiento.

Si quiere tener la capacidad de quitar todos los mensajes de correo corporativo de un dispositivo iOS cuando este deje de formar parte de la empresa, tiene que crear e implementar un perfil de correo electrónico. Luego, establezca una directiva de cumplimiento que especifique que Intune administra los perfiles de correo electrónico. Debe implementar el perfil de correo electrónico en el mismo conjunto de usuarios al que va dirigido esta directiva de cumplimiento.
![Captura de pantalla que muestra la página "Reglas" del Asistente para crear directivas de cumplimiento, donde puede especificar que un perfil de correo electrónico debe administrarse mediante Intune](./media/ProtectEmail/Hybrid-Onprem-ExchSrvr-Wizard6.PNG)

Si se especifica esta directiva de cumplimiento, un usuario que ya haya configurado su cuenta de correo electrónico tendrá que eliminarla manualmente y, luego, Intune la agregará de nuevo en el proceso de registro descrito en [Experiencia de acceso condicional del usuario final](../Solutions/end-user-experience-conditional-access.md).

> [!IMPORTANT]
> Si no ha implementado una directiva de cumplimiento y habilitado la directiva de acceso condicional a Exchange, se permitirá el acceso a todos los dispositivos destinatarios.

### Paso 3: identifique los usuarios que se verán afectados por la directiva de acceso condicional.
Cuando el conector de Exchange Server se haya configurado correctamente, comenzará a inventariar los dispositivos que no están inscritos en Intune, pero que están conectados a los recursos de Exchange mediante Exchange Active Sync.  

Siga las instrucciones de [Paso 2: evalúe el impacto de la directiva de acceso condicional](https://stage.docs.microsoft.com/en-us/intune/deployuse/restrict-access-to-exchange-online-with-microsoft-intune#configure-conditional-access) para identificar los usuarios que se verán afectados por la directiva de acceso condicional.


### Paso 4: configure grupos de usuarios para la directiva de acceso condicional.
El destino de las directivas de acceso condicional se define en distintos grupos de usuarios en función de los tipos de directiva. Estos grupos contienen los usuarios de destino o exentos de la directiva. Cuando un usuario es destinatario de una directiva, cada dispositivo que use debe ser conforme con el fin de obtener acceso al correo electrónico.

Para obtener más información, consulte [Paso 3: configure grupos de usuarios para la directiva de acceso condicional](https://stage.docs.microsoft.com/en-us/intune/deployuse/restrict-access-to-exchange-online-with-microsoft-intune#configure-conditional-access).

### Paso 5: configure la directiva de acceso condicional.
El siguiente flujo lo emplean las directivas de acceso condicional de un entorno de Exchange Server local para evaluar si se permitirá o bloqueará el acceso a los dispositivos.

![Diagrama de flujo que muestra cómo las directivas de acceso condicional de Exchange Server local evalúan si se permitirá o bloqueará el acceso a los dispositivos](./media/ProtectEmail/conditional-access-8-2.png)

Siga la información proporcionada en [Configurar una directiva de acceso condicional](https://stage.docs.microsoft.com/en-us/intune/deployuse/restrict-access-to-exchange-onpremises-with-microsoft-intune#-a-name-bkmk_enablexchngonprem-a-configure-a-conditional-access-policy) para establecer la directiva de acceso condicional.

## Generación de informes

### Supervisar el cumplimiento y las directivas de acceso condicional
Para ver los dispositivos que tienen bloqueado el acceso a Exchange, siga estos pasos:

En el panel de Intune, haga clic en el icono **Dispositivos bloqueados de Exchange** para que se muestren el número de dispositivos bloqueados y los vínculos para obtener más información.
![Captura de pantalla que muestra el icono "Dispositivos bloqueados de Exchange" del panel de Intune](./media/ProtectEmail/intune-sa-6blocked-devices.PNG)

## Próximos pasos
Cuando haya implementado una solución para proteger el correo electrónico corporativo y los datos de correo electrónico de los dispositivos móviles, puede obtener más información sobre [la experiencia del usuario final de acceso condicional](../Solutions/end-user-experience-conditional-access.md). Esto le ayudará a prepararse para problemas que podrían surgir al inscribir sus dispositivos específicos.


<!--HONumber=Apr16_HO2-->


