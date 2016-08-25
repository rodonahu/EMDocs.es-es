---
title: "Protección de documentos y del correo electrónico corporativos"
description: "Permita que solo los dispositivos que cumplan las especificaciones tengan acceso al correo electrónico de la empresa y protejan el contenido del correo electrónico y los datos adjuntos."
keywords: 
author: craigcaseyMSFT
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 78d8368e-1bfe-4ac4-991d-467321a76ed7
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 55a3dbe32e3b5e10e21a6d99bc101ec76fc51f5e
ms.openlocfilehash: cc6844a9329cafd14d7902ec1d677c5bea685b86


---

# Protección de documentos y del correo electrónico corporativos
La protección del correo electrónico corporativo implica dos objetivos principales:

-   Permitir que solo los dispositivos que cumplan las normas accedan al correo de la empresa

-   Proteger el contenido del correo y los datos adjuntos

## Permitir que solo los dispositivos que cumplan las normas accedan al correo de la empresa
Un paso importante para proteger los datos corporativos es restringir el acceso a los dispositivos que no utilizan una contraseña segura, sin jailbreak o sin cifrar. Microsoft Intune ofrece la capacidad de establecer las condiciones que los usuarios deben cumplir para obtener acceso a los recursos de la empresa. Esto se conoce como acceso condicional.

El acceso condicional viene determinado por dos tipos de directivas que se pueden definir en Intune:

Las**directivas de cumplimiento** determinan el cumplimiento de un dispositivo. Evalúan la configuración y las condiciones, como:

-   **PIN y contraseñas**: el departamento de TI puede crear reglas, entre otras cosas, para solicitar contraseñas antes de desbloquear un dispositivo, para establecer la complejidad de la contraseña y la fecha de expiración.

-   **Cifrado**: el departamento de TI puede restringir el acceso a los dispositivos cifrados.

-   **El dispositivo no está liberado o modificado**: Intune puede detectar si un dispositivo ha sido liberado mediante jailbreak, por lo que el departamento de TI puede establecer una directiva para bloquear el acceso a estos dispositivos.

**Las directivas de acceso condicional** se configuran para un servicio determinado, como Exchange Online o SharePoint Online. Para cada servicio, puede definir a qué grupos de usuarios se deben aplicar estas directivas. Por ejemplo, puede asegurarse de que todas las personas del departamento de finanzas solo puedan acceder al correo electrónico de la empresa desde dispositivos inscritos y de conformidad.

## Experiencia de alto nivel del usuario final
Después de implementar la solución, los usuarios finales solo podrán obtener acceso al correo de la empresa mediante dispositivos administrados y que cumplan los requisitos establecidos. Una vez que tengan acceso al correo electrónico en sus dispositivos, los datos de la empresa estarán protegidos y se guardarán en el ecosistema de la aplicación, por lo que solo estarán disponibles para ciertos usuarios. El acceso se puede revocar en cualquier momento si el dispositivo no cumple con los requisitos establecidos.

En concreto, las directivas de acceso condicional de Intune garantizan que los dispositivos solo puedan tener acceso al correo electrónico si cumplen con las directivas de cumplimiento establecidas. Acciones tales como copiar y pegar o guardar datos en servicios personales en la nube, pueden restringirse mediante directivas de administración de aplicaciones móviles. El servicio Azure Rights Managements puede usarse para garantizar que solo los destinatarios puedan leer los datos de los correos electrónicos confidenciales y los datos adjuntos reenviados. La experiencia del usuario final se describe con más detalle en [Experiencia de acceso condicional del usuario final](end-user-experience-conditional-access.md).


Mire [este](https://www.youtube.com/watch?feature=player_embedded&v=lYx3YIezccg) vídeo de cuatro minutos para ver cómo afecta el acceso condicional a los usuarios finales.

## Por qué importa la arquitectura
Los diferentes componentes de EMS y Office 365 se han creado y diseñado para ejecutarse en la nube. Esto aporta todas las ventajas que ofrece la nube: escalabilidad, flexibilidad y facilidad de administración.

Dado que las empresas diferentes tienen requisitos diferentes, EMS se ha diseñado para integrarse con la infraestructura local existente, como Active Directory, Exchange Server o System Center Configuration Manager. Esto le permite usar las credenciales ya establecidas en la red para los recursos locales y en la nube.

En las secciones siguientes se describe la arquitectura diseñada para ejecutarse en la nube y se describe brevemente la opción local.

### Flujo de acceso a correo electrónico
En función del tipo de aplicación de correo electrónico que utilice para acceder a Exchange Online, la ruta para establecer un acceso seguro al correo electrónico puede ser ligeramente diferente. Sin embargo, la de los componentes clave Azure Active Directory (Azure AD), Office 365/Exchange Online y Microsoft Intune, es la misma. La experiencia en TI y la experiencia del usuario final también son similares. Actualmente, EMS admite aplicaciones de correo electrónico nativas y la aplicación de Microsoft Outlook para iOS y Android.

### Flujo de control de acceso para las aplicaciones de correo electrónico nativas
Los clientes de Exchange ActiveSync (EAS) que intentan acceder al correo electrónico de Exchange Online se evaluarán respecto a las siguientes propiedades:

-   ¿El dispositivo se administra mediante Intune?

-   ¿El dispositivo está registrado con Azure Active Directory?

-   ¿Cumple las normas el dispositivo?

-   ¿Está el Id. de EAS de cliente asignado a un dispositivo registrado?

Para llegar a un estado de cumplimiento, el dispositivo en el que se ejecuta el cliente EAS debe:

-   Inscribirse con Intune

-   Registrarse con [Azure Active Directory](https://msdn.microsoft.com/6a14cb1f-a058-4453-8ede-d9f4a66a7073.aspx) y

-   Cumplir las directivas de dispositivo que ha establecido el administrador de TI.

En la mayoría de plataformas, el registro del dispositivos en Azure Active Directory se hace automáticamente durante la inscripción Intune anota los estados de dispositivo en Azure Active Directory y Exchange Online los lee la próxima vez que el cliente EAS intenta obtener correo electrónico. Si el dispositivo no está registrado, el usuario recibirá un mensaje en su bandeja de entrada con instrucciones para registrarse (o inscribirse). Si el dispositivo no cumple las normas, el usuario obtendrá un correo electrónico diferente que le redirigirá al portal web de Intune, donde podrá obtener más información sobre el problema de cumplimiento y la forma de corregirlo.

**Azure AD**autentica el usuario y el dispositivo, Microsoft Intune administra las directivas de cumplimiento y acceso condicional y **Exchange Online** administra el acceso al correo electrónico en función del estado del dispositivo.

![Gráfico que muestra el flujo de control de acceso correspondiente a aplicaciones de correo electrónico nativas de dispositivos iOS y Android](./media/ProtectEmail/Access-Control-Flow-For-Native-Email-Apps.png)

### Flujo de control de acceso para aplicaciones de Outlook
De forma similar al cliente EAS, la aplicación de correo electrónico de Outlook que intente tener acceso al correo electrónico de Exchange Online se evaluará respecto a las siguientes propiedades:

-   ¿El dispositivo se administra mediante Intune?

-   ¿El dispositivo está registrado con Azure Active Directory?

-   ¿Cumple las normas el dispositivo?

El cumplimiento del dispositivo se establece en gran parte de la misma manera que se describe en el flujo de control de acceso de cliente de EAS. Sin embargo, para las aplicaciones de Outlook, el flujo entre los componentes es ligeramente diferente. Cuando la aplicación de Outlook intenta recibir correo electrónico, se redirige a Azure AD. Azure AD emite un token de seguridad si, según la evaluación, el dispositivo está inscrito y es compatible. A continuación, el token de seguridad se usa para obtener el correo electrónico corporativo de Exchange Online. La sincronización de correo electrónico pasa por el servicio en la nube de Outlook, que recibe un token de acceso al servicio de EAS en nombre del usuario para completar la autenticación y entrega el correo electrónico.

![Gráfico que muestra el flujo de control de acceso correspondiente a la aplicación de Outlook](./media/ProtectEmail/Access-Control-Flow-For-Outlook-App.png)

## La experiencia de administración de TI:
No se necesita ninguna instalación compleja de infraestructura para Azure AD o Exchange. Los administradores de TI:

-   Configure e implemente las directivas de cumplimiento que se usan para evaluar el estado de cumplimiento del dispositivo.

-   Configure la directiva de acceso condicional de Exchange Online y especifique qué grupos de seguridad de Azure AD se verán afectados por estas directivas y cuáles estarán exentos.

-   Elija permitir o bloquear los dispositivos que no puedan inscribirse en Intune. La lista de sistemas operativos compatibles para dispositivos móviles se muestra más adelante.

Hay una fase de configuración opcional que puede ser necesaria. Los informes que se utilizan para administrar y supervisar el estado y el acceso a los dispositivos requieren la configuración del conector de servicio a servicio de Microsoft Intune.

## Experiencia del usuario final:
Cuando el usuario intenta tener acceso al correo electrónico en el dispositivo por primera vez o sincronizar posteriormente, se comprueba el estado de cumplimiento de normas y la inscripción del dispositivo. El proceso de inscripción o corrección de problemas de cumplimiento de normas es una experiencia guiada. Se muestran al usuario final los pasos necesarios para inscribir su dispositivo y que esté conforme con las normas sin necesidad de llamar al servicio de asistencia de TI:

-   **Si el dispositivo no está inscrito**, aparecerá un mensaje de acceso denegado en la página de inicio de sesión y se solicitará la inscripción. En la inscripción, el dispositivo se registra automáticamente en Azure Active Directory. Intune comprueba el cumplimiento de normas del dispositivo y proporciona los pasos de corrección para solucionar los problemas de incumplimiento. Una vez que el dispositivo cumple las normas, Intune establece el estado de cumplimiento del dispositivo con Azure Active Directory.

-   **Si el dispositivo está inscrito, pero no cumple las normas**, se envía un vínculo con los pasos para solucionar los problemas al dispositivo. Cuando el usuario final corrige el problema (por ejemplo, define la contraseña, cifrado), Intune, que administra las directivas de cumplimiento, actualiza el estado de cumplimiento del dispositivo en Azure AD.

Una vez que el dispositivo se evalúa como inscrito y conforme a las normas, la sincronización de correo electrónico debe realizarse en pocos minutos.

## Próximos pasos
Ahora que sabe cómo proteger los documentos y el correo electrónico corporativos, puede consultar cómo [proteger los datos adjuntos del correo](protect-email-attachments.md). O, si ya cuenta con los conocimientos necesarios, puede obtener más información sobre la [implementación de una solución para proteger el correo corporativo](implement-solution.md).



<!--HONumber=Aug16_HO1-->


