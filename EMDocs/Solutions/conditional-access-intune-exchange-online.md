---
title: Uso del acceso condicional con Microsoft Intune y Exchange Online
description: "Implemente Exchange Online con la solución de Intune."
keywords: 
author: craigcaseyMSFT
ms.author: v-craic
manager: swadhwa
ms.date: 01/10/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8cfe421b-52c9-4d44-8df1-15c82375c335
ms.reviewer: 
ms.suite: ems
ms.translationtype: Human Translation
ms.sourcegitcommit: 0be1ad609016303572b67676c03f544d88fb5576
ms.openlocfilehash: c4743cb8fba4db7072d6af13a2ac4943bd35a423
ms.contentlocale: es-es
ms.lasthandoff: 07/07/2017


---

# <a name="deploy-exchange-online-with-intune"></a>Implementación de Exchange Online con Intune

Ahora que ha leído la [Guía de arquitectura para proteger los documentos y correos electrónicos de la empresa](architecture-guidance-for-protecting-company-email-and-documents.md), ya puede continuar con la implementación de una solución.

Para que Intune administre dispositivos móviles directamente, los usuarios deben inscribir los dispositivos en esta plataforma.

## <a name="deployment-steps"></a>Pasos de implementación
Siga estos pasos para implementar la solución Exchange Online con Intune:

### <a name="step-1-create-compliance-policies-and-deploy-to-users"></a>Paso 1: cree directivas de cumplimiento e impleméntelas a los usuarios.
Las directivas de cumplimiento definen las reglas y los valores de configuración que un dispositivo debe cumplir para que se le considere conforme a las directivas de acceso condicional. Siga los pasos de [Crear una directiva de cumplimiento normativo de dispositivos en Microsoft Intune](/intune/deploy-use/create-a-device-compliance-policy-in-microsoft-intune) para crear e implementar directivas de cumplimiento.

Si quiere tener la capacidad de quitar todos los mensajes de correo corporativo de un dispositivo iOS cuando este deje de formar parte de la empresa, tiene que crear e implementar un perfil de correo electrónico. Luego, establezca una directiva de cumplimiento que especifique que Intune administra los perfiles de correo electrónico. Debe implementar el perfil de correo electrónico en el mismo conjunto de usuarios al que va dirigido esta directiva de cumplimiento.

![Captura de pantalla que muestra la sección “Perfiles de correo” en la pestaña General del asistente Crear directiva de Intune, donde puede especificar que Intune debe administrar un perfil de correo electrónico.](./media/ProtectEmail/intune-create-policy-email-profile.PNG)

Si se especifica esta directiva de cumplimiento, un usuario que ya haya configurado su cuenta de correo electrónico tendrá que eliminarla manualmente y, luego, Intune la agregará de nuevo en el proceso de registro descrito en [Experiencia de acceso condicional del usuario final](end-user-experience-conditional-access.md).

> [!IMPORTANT]
> Si no ha implementado una directiva de cumplimiento y habilitado la directiva de acceso condicional a Exchange, se permitirá el acceso a todos los dispositivos destinatarios.

### <a name="step-2-evaluate-the-effect-of-the-conditional-access-policy"></a>Paso 2: evalúe el impacto de la directiva de acceso condicional.
Si ha configurado una conexión entre Intune y Exchange mediante [Microsoft Intune Service To Service Connector](/intune/deploy-use/intune-service-to-service-exchange-connector), puede usar los **informes de inventario de dispositivos móviles** para identificar los clientes de correo de EAS que tendrán el acceso bloqueado a Exchange después de configurar la directiva de acceso condicional.

Siga las instrucciones de [Evaluar el impacto de la directiva de acceso condicional](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune#configure-conditional-access) para identificar los usuarios que se verán afectados por la directiva de acceso condicional.

### <a name="step-3-configure-user-groups-for-the-conditional-access-policy"></a>Paso 3: configure grupos de usuarios para la directiva de acceso condicional.
El destino de las directivas de acceso condicional se define en distintos grupos de usuarios en función de los tipos de directiva. Estos grupos contienen los usuarios de destino o exentos de la directiva. Cuando un usuario es destinatario de una directiva, cada dispositivo que use debe ser conforme con el fin de obtener acceso al correo electrónico.

Para obtener más información, vea [Configurar grupos de usuarios para la directiva de acceso condicional](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune#configure-conditional-access).

### <a name="step-4-configure-conditional-access-policy"></a>Paso 4: configure la directiva de acceso condicional.
Las directivas de acceso condicional de Exchange Online utilizan el siguiente flujo para evaluar si se permitirá o bloqueará el acceso a los dispositivos.

![Diagrama de flujo que muestra cómo las directivas de acceso condicional de Exchange Online evalúan si se permitirá o bloqueará el acceso a los dispositivos](./media/ProtectEmail/conditional-access-8-1.png)

Siga la información proporcionada en [Configurar la directiva de acceso condicional](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune#configure-conditional-access) para configurar la directiva de acceso condicional.



## <a name="reporting"></a>Generación de informes

### <a name="monitor-the-compliance-and-conditional-access-policies"></a>Supervisar el cumplimiento y las directivas de acceso condicional
Para ver los dispositivos que tienen bloqueado el acceso a Exchange, siga estos pasos:

En el panel de Intune, haga clic en el icono **Dispositivos bloqueados de Exchange** para que se muestren el número de dispositivos bloqueados y los vínculos para obtener más información.
![Captura de pantalla que muestra el icono "Dispositivos bloqueados de Exchange" del panel de Intune](./media/ProtectEmail/intune-sa-6blocked-devices.PNG)



## <a name="where-to-go-from-here"></a>Próximos pasos
Cuando haya implementado una solución para proteger el correo electrónico corporativo y los datos de correo electrónico de los dispositivos móviles, puede obtener más información sobre la [experiencia de acceso condicional del usuario final](end-user-experience-conditional-access.md). Esto le ayudará a prepararse para problemas que podrían surgir al inscribir sus dispositivos específicos.

