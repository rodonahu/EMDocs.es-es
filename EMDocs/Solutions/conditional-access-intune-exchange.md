---
title: Use el acceso condicional con Intune y Exchange Server local
description: "Implemente Exchange local con la solución de Intune."
keywords: 
author: craigcaseyMSFT
ms.author: v-craic
manager: swadhwa
ms.date: 01/10/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2a64e898-4c60-48bf-ae14-b05e091e0533
ms.reviewer: 
ms.suite: ems
ms.openlocfilehash: 042bc3afbb5e0ce919b3a07dcbdba6ae27cacaa7
ms.sourcegitcommit: 0541e4aa400a818551469fe9df8929c25c2dd918
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/25/2017
---
# <a name="deploy-exchange-on-premises-with-intune"></a>Implementación de Exchange local con Intune

Ahora que ha leído la [Guía de arquitectura para proteger los documentos y correos electrónicos de la empresa](architecture-guidance-for-protecting-company-email-and-documents.md), ya puede continuar con la implementación de una solución.

Para que Intune administre dispositivos móviles directamente, los usuarios tendrán que inscribir los dispositivos en esta plataforma.

## <a name="deployment-steps"></a>Pasos de implementación
Siga estos pasos para implementar la solución Exchange Server local con Intune:

### <a name="step-1-install-and-configure-the-microsoft-intune-on-premises-exchange-server-connector"></a>Paso 1: instale y configure el conector de Exchange Server local de Microsoft Intune.

Para los dispositivos móviles que los usuarios no inscriban se puede habilitar la administración de Exchange ActiveSync mediante Exchange Connector. Exchange Connector conecta con su implementación de Exchange y permite administrar los dispositivos móviles a través de la consola de Intune.

Siga los pasos de [Configurar Microsoft Intune On-Premises Connector para Exchange local o Hosted Exchange](/intune/deploy-use/intune-on-premises-exchange-connector) para descargar, instalar y configurar Microsoft Intune Exchange Connector.

> [!IMPORTANT]
> Solo puede configurar una conexión de Exchange por cuenta de Intune. Si intenta configurar una conexión adicional, se reemplazará la conexión original con la nueva.

### <a name="step-2-create-compliance-policies-and-deploy-to-users"></a>Paso 2: cree directivas de cumplimiento e impleméntelas para los usuarios.
Las directivas de cumplimiento definen las reglas y los valores de configuración que un dispositivo debe cumplir para que se le considere conforme a las directivas de acceso condicional. Siga los pasos de [Crear una directiva de cumplimiento normativo de dispositivos en Microsoft Intune](/intune/deploy-use/create-a-device-compliance-policy-in-microsoft-intune) para crear e implementar directivas de cumplimiento.

Si quiere tener la capacidad de quitar todos los mensajes de correo corporativo de un dispositivo iOS cuando este deje de formar parte de la empresa, tiene que crear e implementar un perfil de correo electrónico. Luego, establezca una directiva de cumplimiento que especifique que Intune administra los perfiles de correo electrónico. Debe implementar el perfil de correo electrónico en el mismo conjunto de usuarios al que va dirigido esta directiva de cumplimiento.
![Captura de pantalla que muestra la sección “Perfiles de correo” en la pestaña General del asistente Crear directiva de Intune, donde puede especificar que Intune debe administrar un perfil de correo electrónico.](./media/ProtectEmail/intune-create-policy-email-profile.PNG)

Si se especifica esta directiva de cumplimiento, un usuario que ya haya configurado su cuenta de correo electrónico tendrá que eliminarla manualmente y, luego, Intune la agregará de nuevo en el proceso de registro descrito en [Experiencia de acceso condicional del usuario final](end-user-experience-conditional-access.md).

> [!IMPORTANT]
> Si no ha implementado una directiva de cumplimiento y habilitado la directiva de acceso condicional a Exchange, se permitirá el acceso a todos los dispositivos destinatarios.

### <a name="step-3-identify-users-who-will-be-impacted-by-conditional-access-policy"></a>Paso 3: identifique los usuarios que se verán afectados por la directiva de acceso condicional.
Cuando el conector de Exchange Server se haya configurado correctamente, comenzará a inventariar los dispositivos que no están inscritos en Intune, pero que están conectados a los recursos de Exchange mediante Exchange Active Sync.  

Siga las instrucciones de [Evaluar el impacto de la directiva de acceso condicional](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune#configure-conditional-access) para identificar los usuarios que se verán afectados por la directiva de acceso condicional.


### <a name="step-4-configure-user-groups-for-the-conditional-access-policy"></a>Paso 4: configure grupos de usuarios para la directiva de acceso condicional.
El destino de las directivas de acceso condicional se define en distintos grupos de usuarios en función de los tipos de directiva. Estos grupos contienen los usuarios de destino o exentos de la directiva. Cuando un usuario es destinatario de una directiva, cada dispositivo que use debe ser conforme con el fin de obtener acceso al correo electrónico.

Para obtener más información, vea [Configurar grupos de usuarios para la directiva de acceso condicional](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune#configure-conditional-access).

### <a name="step-5-configure-conditional-access-policy"></a>Paso 5: configure la directiva de acceso condicional.
El siguiente flujo lo emplean las directivas de acceso condicional de un entorno de Exchange Server local para evaluar si se permitirá o bloqueará el acceso a los dispositivos.

![Diagrama de flujo que muestra cómo las directivas de acceso condicional de Exchange Server local evalúan si se permitirá o bloqueará el acceso a los dispositivos](./media/ProtectEmail/conditional-access-8-2.png)

Siga la información proporcionada en [Configurar una directiva de acceso condicional](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune#configure-conditional-access) para configurar la directiva de acceso condicional.

## <a name="reporting"></a>Generación de informes

### <a name="monitor-the-compliance-and-conditional-access-policies"></a>Supervisar el cumplimiento y las directivas de acceso condicional
Para ver los dispositivos que tienen bloqueado el acceso a Exchange, siga estos pasos:

En el panel de Intune, haga clic en el icono **Dispositivos bloqueados de Exchange** para que se muestren el número de dispositivos bloqueados y los vínculos para obtener más información.
![Captura de pantalla que muestra el icono "Dispositivos bloqueados de Exchange" del panel de Intune](./media/ProtectEmail/intune-sa-6blocked-devices.PNG)

## <a name="where-to-go-from-here"></a>Próximos pasos
Cuando haya implementado una solución para proteger el correo electrónico corporativo y los datos de correo electrónico de los dispositivos móviles, puede obtener más información sobre la [experiencia de acceso condicional del usuario final](end-user-experience-conditional-access.md). Esto le ayudará a prepararse para problemas que podrían surgir al inscribir sus dispositivos específicos.
