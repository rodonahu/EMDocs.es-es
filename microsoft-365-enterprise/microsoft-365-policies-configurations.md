---
title: Directivas y configuraciones de seguridad recomendadas - Microsoft 365 Enterprise | Microsoft Docs
description: "Explica recomendaciones y conceptos básicos de Microsoft para implementar directivas y configuraciones seguras de correo electrónico, documentos y aplicaciones."
author: dougeby
manager: dougeby
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 08/30/2017
ms.author: barlan
ms.reviewer: jsnow
ms.custom: it-pro
ms.openlocfilehash: a7f6ab6765be5462c652feb006839f0839b1136e
ms.sourcegitcommit: 8d42bd1ec3d7bf5f873a7b681b0fea73a748b413
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2018
---
# <a name="recommended-security-policies-and-configurations"></a>Directivas y configuraciones de seguridad recomendadas

## <a name="introduction"></a>Introducción
Aunque no hay una única recomendación óptima para todos los entornos de cliente, los procedimientos recomendados y las recomendaciones de este documento describen recomendaciones generales de Microsoft para aplicar directivas y configuraciones de la nube de Microsoft con el fin de garantizar la seguridad y la productividad de los empleados.  

**Audiencia prevista** Estas recomendaciones van dirigidas a arquitectos de infraestructura de empresa y profesionales de TI familiarizados con [Office 365](https://technet.microsoft.com/library/dn127064(v=office.14).aspx) y [Microsoft Enterprise Mobility + Security](http://microsoft.com/ems), lo que incluye, entre otros, Azure Active Directory (identidad), Microsoft Intune (administración de dispositivos) y Azure Information Protection (protección de datos).

**Entorno de cliente** Las directivas recomendadas son aplicables a organizaciones empresariales que operan completamente en la nube de Microsoft y a clientes con la infraestructura implementada en local y en la nube de Microsoft.

**Suposiciones** Muchas de las recomendaciones proporcionadas se basan en servicios disponibles solamente con suscripciones de Enterprise Mobility + Security (EMS) E5. Las recomendaciones presentadas dan por hecho que se dispone de la totalidad de las capacidades de la suscripción de EMS E5.

**Advertencias** La organización puede estar sujeta a requisitos regulatorios o de cumplimiento, incluidas las recomendaciones específicas que puedan exigir la aplicación de directivas que divergen de estas configuraciones recomendadas.  Estas configuraciones recomiendan controles de uso que históricamente no han estado disponibles.  Estos controles se recomiendan porque se cree que representan un equilibrio entre la seguridad y la productividad.  

Aunque se ha realizado un esfuerzo por tener en cuenta una amplia variedad de requisitos de protección de empresa, no se ha podido incluir todos los posibles requisitos ni para todos los aspectos exclusivos de la organización. Siga estas recomendaciones como guía sobre cómo piensan Microsoft y el equipo de empresa productiva segura que hay que aplicar correctamente las directivas.  

>[!NOTE]
>Para obtener una introducción a los conceptos básicos necesarios para comprender las capacidades de protección descritas en estas recomendaciones, vea la [página principal de documentación de Microsoft 365 Enterprise](index.md).
>

## <a name="core-concepts"></a>Conceptos principales
Todas las medidas de seguridad del mundo no importan cuando los usuarios, que experimentan una fricción innecesaria al intentar realizar su trabajo, omiten las directivas de seguridad de la organización. El inicio de sesión único (SSO) de Azure AD intenta minimizar la carga sobre los usuarios. De esta forma los usuarios pueden mantener su productividad a la vez que cumplen las directivas de control de acceso de la organización.

### <a name="single-sign-on-authentication"></a>Autenticación de inicio de sesión único

El siguiente diagrama muestra un flujo típico de autenticación de SSO:

![Experiencia de inicio de sesión único de usuario final](./media/policies-configurations/authentication-flow.png)

Para empezar la autenticación, el cliente envía las credenciales (por ejemplo, el nombre de usuario y la contraseña) o cualquier artefacto de SSO obtenido en el pasado a Azure AD. Un artefacto de SSO puede ser un token de sesión para un explorador o un token de actualización para aplicaciones enriquecidas.

Una vez comprobadas las credenciales o el artefacto de SSO en Azure AD, y una vez evaluadas todas las directivas aplicables, se emite un token de acceso para el proveedor de recursos (Office 365 en el diagrama anterior). Azure AD además emite un artefacto de SSO como parte de la respuesta para permitir a los clientes el SSO en solicitudes posteriores. El cliente almacena el artefacto de SSO y envía el token de acceso como prueba de identidad al proveedor de recursos. Una vez que Office 365 comprueba el token de acceso y realiza las comprobaciones necesarias, permite el acceso del cliente a los documentos.

#### <a name="single-sign-on-sso-refresh-tokens"></a>Tokens de actualización de inicio de sesión único (SSO)
El SSO se puede realizar de varias maneras. Por ejemplo, las cookies de un proveedor de identidad pueden usarse como artefacto de SSO para almacenar el estado de inicio de sesión de un usuario en un explorador. Después es posible intentar iniciar sesión de forma silenciosa (sin ninguna solicitud de credenciales) en las aplicaciones con el mismo proveedor de identidad.

Cuando un usuario se autentica con Azure AD, se establece una sesión de SSO con Azure AD y el explorador del usuario. El token de SSO, en forma de cookie, representa esta sesión. Azure AD usa dos tipos de tokens de sesión de SSO: persistentes y no persistentes. Los tokens de sesión persistentes se almacenan como cookies persistentes en los exploradores si la casilla **Mantener la sesión iniciada** está activada durante el inicio de sesión. Los tokens de sesión no persistentes se almacenan como cookies de sesión y se destruyen al cerrar el explorador.

En las aplicaciones sólidas capaces de usar protocolos de autenticación moderna, como [OpenId Connect](http://openid.net/specs/openid-connect-core-1_0.html) y [OAuth 2.0](https://tools.ietf.org/html/rfc6749), el SSO está habilitado con tokens de actualización como artefactos de SSO (además de las cookies de SSO descritas anteriormente). Los tokens de actualización se presentan a un servidor de autorización cuando una aplicación solicita un nuevo token de acceso. El token de actualización contiene notificaciones y atributos sobre el tipo de métodos de autenticación usados al autenticar a los usuarios. Por ejemplo, si un usuario se ha autenticado correctamente con varios métodos (nombre de usuario y contraseña y autenticación basada en el teléfono), hay una notificación de Multi-Factor Authentication (MFA) en el token de actualización. Además, puede haber notificaciones adicionales que contienen datos como la duración de la validez MFA.

Los tokens de actualización permiten al cliente obtener un nuevo token de acceso sin necesidad de realizar otra autenticación interactiva. Los tokens de actualización tienen una duración mucho mayor que los tokens de acceso y se pueden canjear para obtener un nuevo par de tokens de acceso y actualización. Después, los tokens de actualización recién obtenidos se pueden usar continuamente para obtener otro conjunto de tokens de acceso y actualización. El cliente sigue este proceso de SSO hasta que expiran el valor de tiempo inactivo máximo y la antigüedad máxima del token de actualización o cambian los requisitos de la directiva de autenticación y autorización. Este cambio se produce en el momento en que se ha emitido el token de actualización original. Los cambios de atributos de usuario significativos, por ejemplo, un restablecimiento de contraseña, también exigen la generación de un nuevo token de autenticación. El cliente debe realizar una nueva autenticación interactiva para continuar. Básicamente esto supone una interrupción del proceso de SSO que el cliente no ha experimentado hasta el momento.

#### <a name="conditional-access"></a>Acceso condicional
Azure AD, que actúa como un servicio de autorización para las aplicaciones, determina si se van a emitir tokens de acceso en función de una evaluación de las directivas de acceso condicional aplicadas al recurso al que está intentando acceder. Si se cumplen los requisitos de la directiva, se emiten un token de acceso y un token de actualización actualizado. Si no se cumple la directiva, el usuario recibe instrucciones para cumplirla o debe realizar pasos adicionales que incluyen Multi-Factor Authentication (MFA). Una vez realizada la autenticación mediante MFA, la notificación de MFA se agrega al token de actualización resultante.  

Las notificaciones del token de actualización se van acumulando. Algunas de ellas tienen escalas de tiempo de expiración, tras lo cual ya no se tienen en cuenta durante las comprobaciones de autorización. A veces esto puede causar resultados inesperados. Por ejemplo, si una directiva de acceso condicional se configura de modo que se exija MFA para los intentos de autenticación procedentes de ubicaciones de extranet. En este caso, los usuarios a veces pueden no recibir la solicitud de MFA esperada al acceder a un recurso desde una extranet. Una posible razón de esto es que el usuario se haya autenticado anteriormente mediante MFA poco antes de salir de la intranet. Por lo tanto, tiene una notificación de MFA válida en su token de acceso. Esta notificación de MFA satisface el requisito de la directiva y, por tanto, Azure AD no muestra al usuario ninguna solicitud de MFA adicional.

#### <a name="token-lifetime-policy"></a>Directiva de duración de tokens
Más allá de la expiración de las notificaciones individuales de un token, los propios tokens tienen tiempos de expiración. Como se ha indicado antes, los tokens expirados son un motivo por el que se puede ver interrumpida la experiencia de SSO. Puede establecer la duración de un token emitido por Azure AD mediante [directivas de duración de tokens](https://docs.microsoft.com/azure/active-directory/active-directory-configurable-token-lifetimes). Como puede deducirse de lo anterior, la definición de los límites de una sesión de SSO es más difícil de capturar. Por ejemplo, las aplicaciones enriquecidas y distintos factores aparentemente desconectados pueden afectar a la duración de una sesión de SSO.

>[!NOTE]
>Los administradores globales de Azure AD pueden controlar los períodos de inactividad y validez de los tokens de actualización. Información sobre tokens de acceso y notificaciones mediante la configuración descrita en el artículo [Vigencia de tokens configurables de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-configurable-token-lifetimes).
>

#### <a name="primary-refresh-tokens"></a>Tokens de actualización principales
Hasta ahora, en este artículo se ha explicado el funcionamiento del SSO en el contexto de un solo cliente, pero esto no es suficiente para experimentar el SSO en una sola aplicación. Hoy en día, los usuarios se someten a flujos de trabajo interactivos que abarcan varias aplicaciones del mismo conjunto de aplicaciones, como Microsoft Office. Los usuarios también necesitan acceder a aplicaciones no relacionadas, incluidas aplicaciones de línea de negocio (LOB) desarrolladas internamente.

Tradicionalmente, los dispositivos Windows unidos a dominio, mediante la autenticación integrada de Windows (Kerberos), logran un alto grado de experiencia de SSO en varias aplicaciones y recursos. Estas aplicaciones incluyen exploradores compatibles como Internet Explorer o Edge. Hay un análogo para el dominio de Azure AD en forma de token de actualización principal (PRT). Este token con privilegios solo está disponible para un conjunto seleccionado de entidades cliente (por ejemplo, los componentes del sistema de plataforma). Luego las entidades pueden permitir el acceso de autenticación de intermediación a otras aplicaciones cliente, por lo que también pueden ofrecer una experiencia de SSO sin problemas. Para los usuarios de Office 365 en dispositivos [iOS](https://docs.microsoft.com/azure/active-directory/develop/active-directory-sso-ios) y [Android](https://docs.microsoft.com/azure/active-directory/develop/active-directory-sso-android), se ha realizado un esfuerzo adicional para reducir el número de autenticaciones necesarias mediante la aplicación de la funcionalidad de agente de autenticación. Esta funcionalidad está integrada en las aplicaciones Microsoft Authenticator y Portal de empresa de Intune.

>[!NOTE]
>Las recomendaciones descritas en este documento dan por hecho que una de estas aplicaciones (Microsoft Authenticator o Portal de empresa de Intune) se ha implementado en los dispositivos Android o iOS de los usuarios.

### <a name="multi-factor-authentication"></a>Multi-factor Authentication
Multi-Factor Authentication (MFA) proporciona un alto nivel de confianza sobre el sujeto de autenticación, dado que este proporciona varias pruebas o evidencias sobre su identidad. Las pruebas pueden ser secretos establecidos previamente que solo conocen el sujeto y la entidad de certificación o una entidad física que solo debe poseer el sujeto. MFA normalmente se realiza en fases. Primero se establece la identidad que usa las contraseñas y luego se exige un método de autenticación diferente (menos propenso a ataques malintencionados) como segundo factor, o viceversa.

Las diferentes entidades de certificación pueden tener una interpretación ligeramente distinta de MFA, o autenticación segura. Por ejemplo, algunas entidades (o más específicamente los administradores que configuran las directivas en dichas entidades) pueden interpretar la autenticación basada en tarjeta inteligente física como MFA. Esto puede ocurrir, aunque, estrictamente hablando, la autenticación por tarjeta inteligente es una autenticación de una sola fase.

La combinación de exigir una tarjeta inteligente física y el requisito de escribir un PIN (secreto) para usar la tarjeta inteligente se puede interpretar como MFA. Pero las organizaciones pueden optar por ser más flexibles en cuanto a la frecuencia para realizar métodos de autenticación más onerosos. En estos casos, las autenticaciones normales, que tienen lugar entre autenticaciones más seguras, pueden considerarse válidas para los recursos que normalmente exigen autenticación segura. Por ejemplo, en algunas organizaciones puede ser aceptable exigir a un usuario que realice MFA cada pocas horas o días. El tiempo depende de la confidencialidad de los recursos que se protegen y siempre que la ubicación física del usuario que intenta acceder a un recurso no cambie.

Azure AD y AD FS usan la notificación de MFA para indicar si la autenticación se realiza con MFA. De forma predeterminada, Azure AD emite tokens con notificación de MFA cuando la autenticación se realiza con [Azure MFA](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started-cloud) o [Windows Hello para empresas](https://docs.microsoft.com/windows/access-protection/hello-for-business/hello-identity-verification). En escenarios de federación, Azure AD respeta la notificación de MFA de proveedores de identidad federados como AD FS y transmite la notificación de MFA en los tokens.

## <a name="recommended-client-configurations"></a>Configuraciones de cliente recomendadas
En esta sección se tratan las configuraciones de cliente de plataforma predeterminadas que se recomiendan para proporcionar la mejor experiencia de SSO a los usuarios, además de los requisitos técnicos previos para el acceso condicional.

### <a name="windows-devices"></a>Dispositivos Windows
Se recomienda Windows 10 (versión 1703 o posterior), ya que Azure se ha diseñado para proporcionar la experiencia de SSO más uniforme para local y Azure AD. Los dispositivos emitidos por una empresa o centro educativo deben configurarse para unirse a Azure AD directamente o, si la organización usa la unión a un dominio de AD local, para [registrarse de forma automática y silenciosa con Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup).

En el caso de los dispositivos Windows BYOD, los usuarios pueden usar "Agregar cuenta profesional o educativa". Tenga en cuenta que los usuarios del explorador Chrome en Windows 10 tienen que [instalar una extensión](https://chrome.google.com/webstore/detail/windows-10-accounts/ppnbnpeolgkicgegkbkbjmhlideopiji?utm_source=chrome-app-launcher-info-dialog) para poder obtener la misma experiencia de inicio de sesión uniforme que los de Edge o IE. Además, si la organización tiene dispositivos Windows 7 unidos a dominio, puede instalar Microsoft Workplace Join para que los equipos que no sean Windows 10 [empaqueten para registrar](https://www.microsoft.com/download/details.aspx?id=53554) los dispositivos con Azure AD.

### <a name="ios-devices"></a>Dispositivos iOS
Se recomienda instalar la [aplicación Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) en los dispositivos de usuario antes de implementar directivas MFA o de acceso condicional. Como mínimo, la aplicación debe estar instalada cuando [se pide a los usuarios que registren el dispositivo](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/multi-factor-authentication-end-user-first-time) con Azure AD al agregar una cuenta profesional o educativa, o cuando instalan la aplicación Portal de empresa de Intune para inscribir sus dispositivos en la administración. Esto depende de la directiva de acceso condicional configurada.

### <a name="android-devices"></a>Dispositivos Android
Se recomienda que los usuarios instalen la [aplicación Portal de empresa de Intune](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal&hl=en
) y la [aplicación Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) antes de que se implementen las directivas de acceso condicional o cuando sea necesario durante determinados intentos de autenticación. Después de la instalación de la aplicación, se puede pedir a los usuarios que se registren con Azure AD o que inscriban su dispositivo con Intune. Esto depende de la directiva de acceso condicional configurada.

También se recomienda que los dispositivos corporativos (COD) estén estandarizados en los OEM y que las versiones que admiten Android for Work o Samsung Knox permitan que las cuentas de correo electrónico sean administradas y protegidas mediante directivas de MDM de Intune.

## <a name="security-guidelines"></a>Instrucciones de seguridad
Esta sección contiene instrucciones generales de seguridad que se deben seguir al implementar cualquiera de las recomendaciones proporcionadas en secciones posteriores.

### <a name="security-and-productivity-trade-offs"></a>Equilibrio entre seguridad y productividad
Hay que buscar el equilibrio entre la seguridad y la productividad. Para ayudar a entender este equilibrio, se usa la tríada de seguridad Seguridad-Funcionalidad-Facilidad de uso (SFU):

![Equilibrio entre seguridad y productividad](./media/policies-configurations/security-triad.png)

Las recomendaciones que se proporcionan se basan en los siguientes principios de la tríada de seguridad SFU:

* Conozca a la audiencia: sea flexible según la función de trabajo o el baremo de seguridad
* Aplique la directiva de seguridad justo a tiempo y asegúrese de que tenga sentido

### <a name="administrators-versus-users"></a>Administradores frente a usuarios
Se recomienda crear grupos de seguridad que contengan a todos los usuarios con cuentas administrativas o que cumplan los requisitos para recibir privilegios de cuenta administrativa de forma temporal. Estos grupos de seguridad luego deben usarse para definir directivas de acceso condicional específicas para Azure AD y los administradores de Office 365.  

Las recomendaciones de directivas proporcionadas tienen en cuenta los privilegios asociados a una cuenta. Los roles de [administrador de Office 365](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d) tienen muchos más privilegios para los servicios de Office 365. Por lo tanto, las recomendaciones de directivas para estas cuentas son más estrictas que para las cuentas de usuario normales. Todas las directivas que hacen referencia a los administradores indican la directiva recomendada para cuentas administrativas de Office 365.

### <a name="reduce-the-number-of-accounts-with-persistent-admin-access"></a>Reduzca el número de cuentas con acceso de administrador persistente
Use Azure AD Privileged Identity Management para reducir el número de cuentas administrativas persistentes. Además, se recomienda que los administradores de Office 365 tengan una cuenta de usuario independiente para uso no administrativo y solo usen la cuenta administrativa cuando sea necesario para realizar una tarea asociada a su función de trabajo.

## <a name="tiers-of-security-and-protection"></a>Niveles de seguridad y protección
La mayoría de las organizaciones tienen requisitos concretos relacionados con la seguridad y la protección de datos. Estos requisitos varían dentro de las organizaciones según el segmento sectorial y las funciones de trabajo. Por ejemplo, el departamento jurídico y los administradores de Office 365 pueden necesitar seguridad adicional y controles de protección de la información en torno a la correspondencia de correo electrónico que no son necesarios para usuarios de otras unidades de negocio.

Cada sector además tiene su propio conjunto de normas especializadas. En lugar de proporcionar una lista de todas las posibles opciones de seguridad o una recomendación por función de trabajo o segmento sectorial, se han proporcionado recomendaciones para los tres distintos niveles de seguridad y protección que se pueden aplicar en función de la granularidad de las necesidades: [base de referencia, confidencial y extremadamente regulado](https://go.microsoft.com/fwlink/p/?linkid=841656).  

**Base de referencia**. Se recomienda establecer un estándar mínimo para proteger los datos, así como las identidades y los dispositivos que acceden a los datos. Se pueden seguir las recomendaciones de base de referencia para proporcionar una protección segura predeterminada que satisfaga las necesidades de la mayoría de las organizaciones.

**Confidencial**. Algunos clientes tienen un subconjunto de datos que se debe proteger a niveles superiores o que exige que todos los datos se protejan a estos niveles superiores. Puede aplicar una mayor protección a todos los conjuntos de datos o a conjuntos concretos en el entorno de Office 365. Se recomienda proteger las identidades y los dispositivos que acceden a información confidencial con niveles de seguridad comparables.

**Extremadamente regulado**. Algunas organizaciones pueden tener una cantidad muy pequeña de datos extremadamente clasificados, un secreto comercial o datos regulados. Microsoft proporciona capacidades para ayudar a las organizaciones a cumplir estos requisitos, incluida protección adicional para identidades y dispositivos.

### <a name="default-protection-mechanism-recommendations"></a>Recomendaciones de mecanismo de protección predeterminadas
La tabla siguiente contiene recomendaciones de mecanismo de protección predeterminadas para cada uno de los niveles de protección y seguridad definidos previamente:

|Mecanismo de protección|Línea de base|Confidencial|Extremadamente regulado|
|:-------------------|:-------|:--------|:---------------|
|**Exigir MFA**|En riesgo de inicio de sesión medio o superior|En riesgo de inicio de sesión bajo o superior|En todas las sesiones nuevas|
|**Exigir cambio de contraseña**|Para usuarios de riesgo alto|Para usuarios de riesgo alto|Para usuarios de riesgo alto|
|**Exigir Intune Application Protection**|Sí|Sí|Sí|
|**Exigir inscripción de Intune (COD)**|Exigir un dispositivo compatible o unido a dominio|Exigir un dispositivo compatible o unido a dominio|Exigir un dispositivo compatible o unido a dominio|

### <a name="device-ownership"></a>Propiedad del dispositivo
La tabla anterior refleja la tendencia de muchas organizaciones a admitir una mezcla de dispositivos corporativos (COD) y de dispositivos personales o Bring Your Own Device (BYOD) para permitir la productividad móvil de su plantilla. Las directivas de Intune App Protection garantizan que el correo electrónico esté protegido frente a filtraciones desde la aplicación móvil de Outlook y otras aplicaciones móviles de Office, tanto en dispositivos COD como BYOD.  

Los dispositivos corporativos se deben administrar mediante Intune o estar unidos a dominio para aplicar protecciones y controles adicionales.  En función de la confidencialidad de los datos, la organización puede optar por no permitir dispositivos BYOD para grupos de usuarios concretos o determinadas aplicaciones.

## <a name="next-steps"></a>Pasos siguientes

 [Implementar directivas comunes de acceso a dispositivos e identidad](identity-access-policies.md)
