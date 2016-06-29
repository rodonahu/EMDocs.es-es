---
# required metadata

title: Experiencia de acceso condicional del usuario final
description:
keywords:
author: craigcaseyMSFT
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: 3e186dd2-e17c-40d8-b160-48038b2c6593

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer:
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Experiencia de acceso condicional del usuario final
Cuando el usuario intenta tener acceso al correo electrónico en el dispositivo por primera vez o sincronizar posteriormente, se comprueba el estado de cumplimiento de normas y la inscripción del dispositivo. El proceso de inscripción o corrección de problemas de cumplimiento de normas es una experiencia guiada. Se muestran al usuario final los pasos necesarios para inscribir su dispositivo y que esté conforme con las normas sin necesidad de llamar al servicio de asistencia de TI:

-   **Si el dispositivo no está inscrito**, aparecerá un mensaje de acceso denegado en la página de inicio de sesión y se solicitará la inscripción. En la inscripción, el dispositivo se registra automáticamente en Azure Active Directory. Intune comprueba el cumplimiento de normas del dispositivo y proporciona los pasos de corrección para solucionar los problemas de incumplimiento. Una vez que el dispositivo cumple las normas, Intune establece el estado de cumplimiento del dispositivo con Azure Active Directory.

-   **Si el dispositivo está inscrito, pero no cumple las normas**, se envía un vínculo con los pasos para solucionar los problemas al dispositivo. Cuando el usuario final corrige el problema (por ejemplo, define la contraseña, cifrado), Intune, que administra las directivas de cumplimiento, actualiza el estado de cumplimiento del dispositivo en Azure AD.

Una vez que el dispositivo se evalúa como inscrito y conforme a las normas, la sincronización de correo electrónico debe realizarse en pocos minutos.

## Android

En [este tema](end-user-experience-conditional-access-android.md) se describe la experiencia de inscripción después de que se habilite el acceso condicional y de que un usuario final trate de acceder al correo electrónico en su dispositivo móvil Android.

## iOS

En [este tema](end-user-experience-conditional-access-ios.md) se describe la experiencia del usuario después de que se habilite el acceso condicional y de que un usuario final trate de acceder al correo electrónico en su dispositivo móvil iOS.

## Windows Phone

En [este tema](end-user-experience-conditional-access-winphone.md) se describe la experiencia del usuario final después de que se habilite el acceso condicional y de que un usuario final trate de acceder al correo electrónico en su dispositivo móvil Windows Phone.


<!--HONumber=Apr16_HO4-->


