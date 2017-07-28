---
title: Experiencia de acceso condicional del usuario final
description: La experiencia del usuario final al inscribir un dispositivo o solucionar problemas de cumplimiento.
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3e186dd2-e17c-40d8-b160-48038b2c6593
ms.reviewer: 
ms.suite: ems
ms.openlocfilehash: 1daeb790d5e01f0b59829231ce0e0401a9ff749d
ms.sourcegitcommit: 0541e4aa400a818551469fe9df8929c25c2dd918
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/25/2017
---
# <a name="end-user-experience-of-conditional-access"></a>Experiencia de acceso condicional del usuario final
Cuando el usuario intenta tener acceso al correo electrónico en el dispositivo por primera vez o sincronizar posteriormente, se comprueba el estado de cumplimiento de normas y la inscripción del dispositivo. El proceso de inscripción o corrección de problemas de cumplimiento de normas es una experiencia guiada. Se muestran al usuario final los pasos necesarios para inscribir su dispositivo y que esté conforme con las normas sin necesidad de llamar al servicio de asistencia de TI:

-   **Si el dispositivo no está inscrito**, aparecerá un mensaje de acceso denegado en la página de inicio de sesión y se solicitará la inscripción. En la inscripción, el dispositivo se registra automáticamente en Azure Active Directory. Intune comprueba el cumplimiento de normas del dispositivo y proporciona los pasos de corrección para solucionar los problemas de incumplimiento. Una vez que el dispositivo cumple las normas, Intune establece el estado de cumplimiento del dispositivo con Azure Active Directory.

-   **Si el dispositivo está inscrito, pero no cumple las normas**, se envía un vínculo con los pasos para solucionar los problemas al dispositivo. Cuando el usuario final corrige el problema (por ejemplo, define la contraseña, cifrado), Intune, que administra las directivas de cumplimiento, actualiza el estado de cumplimiento del dispositivo en Azure AD.

Una vez que el dispositivo se evalúa como inscrito y conforme a las normas, la sincronización de correo electrónico debe realizarse en pocos minutos.

## <a name="android"></a>Android

En [este tema](end-user-experience-conditional-access-android.md) se describe la experiencia de inscripción después de que se habilite el acceso condicional y de que un usuario final trate de acceder al correo electrónico en su dispositivo móvil Android.

## <a name="ios"></a>iOS

En [este tema](end-user-experience-conditional-access-ios.md) se describe la experiencia del usuario después de que se habilite el acceso condicional y de que un usuario final trate de acceder al correo electrónico en su dispositivo móvil iOS.

## <a name="windows-phone"></a>Windows Phone

En [este tema](end-user-experience-conditional-access-winphone.md) se describe la experiencia del usuario final después de que se habilite el acceso condicional y de que un usuario final trate de acceder al correo electrónico en su dispositivo móvil Windows Phone.
