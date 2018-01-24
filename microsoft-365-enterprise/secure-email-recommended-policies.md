---
title: "Directivas recomendadas para proteger el correo electrónico - Microsoft 365 Enterprise | Microsoft Docs"
description: "Describe las directivas recomendadas por Microsoft para aplicar directivas y configuraciones de correo electrónico."
author: barlanmsft
manager: angrobe
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 01/18/2018
ms.author: barlan
ms.reviewer: jsnow
ms.custom: it-pro
ms.openlocfilehash: c86f8f86d134d77e45ab7a59564b9f0d4821ed38
ms.sourcegitcommit: eb3521981c5dec164ce2a14b4d4d53830b5ba461
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/18/2018
---
# <a name="policy-recommendations-for-securing-email"></a>Recomendaciones de directivas para proteger el correo electrónico

En este artículo se describen directivas recomendadas para ayudar a proteger el correo electrónico de la organización, así como los clientes de correo electrónico que admiten la autenticación moderna y el acceso condicional. Estas recomendaciones se suman a las [recomendaciones comunes sobre directivas de acceso e identidad](identity-access-policies.md).

Las siguientes recomendaciones se basan en tres capas diferentes de seguridad y protección para el correo electrónico que se pueden aplicar en función de la granularidad de sus necesidades:

- **Base de referencia**: Microsoft recomienda establecer un estándar mínimo para proteger los datos, así como las identidades y los dispositivos que acceden a los datos. Microsoft proporciona una protección segura de forma predeterminada que satisface las necesidades de la mayoría de las organizaciones. Algunas organizaciones requieren más funcionalidades para satisfacer los requisitos de su base de referencia.
- **Confidencial**: algunos clientes tienen un subconjunto de datos que deben disponer de mayor protección. Puede aplicar una mayor protección a conjuntos concretos en su entorno de Office 365. Microsoft recomienda proteger las identidades y los dispositivos que acceden a información confidencial con niveles de seguridad comparables. 
- **Extremadamente regulado**: algunas organizaciones pueden tener una cantidad muy pequeña de datos extremadamente clasificados, un secreto comercial o datos regulados. Microsoft proporciona capacidades para ayudar a las organizaciones a cumplir estos requisitos, incluida protección adicional para identidades y dispositivos.

Consulte el tema de [introducción a las directivas y configuraciones de seguridad recomendadas](microsoft-365-policies-configurations.md) para ver más detalles.

> [!IMPORTANT]
> Todos los grupos de seguridad creados como parte de estas recomendaciones deben crearse con las características de Office habilitadas. Esto es especialmente importante para la implementación de Azure Information Protection (AIP) al proteger documentos en SharePoint Online.
>
>![Características de Office habilitadas para grupos de seguridad](./media/security-group.png)
>

## <a name="baseline"></a>Línea de base
Para crear una directiva de acceso condicional, haga lo siguiente: 

1. Vaya al [Azure Portal](https://portal.azure.com) e inicie sesión con sus credenciales. Después de iniciar sesión, verá el Panel de Azure.

2. En el menú de la izquierda, seleccione **Azure Active Directory**.

3. En la sección **Seguridad**, seleccione **Acceso condicional**.

4. Seleccione **Nueva directiva**, tal y como se muestra en la siguiente captura de pantalla:

![Directiva de acceso condicional de base de referencia](./media/secure-email/CA-EXO-policy-1.png)

En las tablas siguientes se describe la configuración correcta necesaria para expresar las directivas requeridas para cada nivel de protección.

### <a name="medium-and-above-risk-requires-mfa"></a>El riesgo medio y superior exige MFA

En la tabla siguiente se describe la configuración de directiva de acceso condicional que se debe implementar para esta directiva.

|Categories|Tipo|Propiedades|Valores|Notas|
|:---------|:---|:---------|:-----|:----|
|**Asignaciones**|Usuarios y grupos|Incluir|Seleccionar usuarios y grupos: selecciona un grupo de seguridad específico que contiene usuarios de destino|Comience con el grupo de seguridad que incluye usuarios de prueba.|
|||Excluir|Grupo de seguridad de excepción; cuentas de servicio (identidades de aplicación)|Pertenencia modificada de forma temporal según necesidad|
||Aplicaciones en la nube|Incluir|Seleccionar aplicaciones: selecciona Office 365 Exchange Online||
||Condiciones|Configurado|Sí|Configuración específica del entorno y las necesidades|
||Riesgo de inicio de sesión|Nivel de riesgo|Alto, medio|Comprobar ambos|
|**Controles de acceso**|Conceder|Conceder acceso|True|Seleccionado|
|||Exigir MFA|True|Check|
|||Exigir dispositivos compatibles|False||
|||Exigir dispositivos unidos a dominio|False||
|||Exigir todos los controles seleccionados|True|Seleccionado|
|**Habilitar directiva**|||Activado|Implementa una directiva de acceso condicional|

### <a name="require-a-compliant-or-domain-joined-device"></a>Exigir un dispositivo compatible o unido a dominio

Para crear una directiva de acceso condicional para Exchange Online, haga lo siguiente:

1. Vaya al [Azure Portal](https://portal.azure.com) e inicie sesión con sus credenciales. Después de iniciar sesión, verá el Panel de Azure.

2. En el menú de la izquierda, seleccione **Azure Active Directory**.

3. En la sección **Seguridad**, seleccione **Acceso condicional**.

4. Pulse **Nueva directiva**.

5. Escriba un nombre de directiva y seleccione los **Usuarios y grupos** a los que quiera que se aplique la directiva.

6. Seleccione **Aplicaciones en la nube**.

7. Elija **Seleccionar aplicaciones** y **Office 365 Exchange Online** en la lista **Aplicaciones en la nube** y haga clic en **Seleccionar**. Una vez haya seleccionado la aplicación **Office 365 Exchange Online**, haga clic en **Listo**.

8. Pulse **Conceder** en la sección **Controles de acceso**.

9. Seleccione **Conceder acceso**, seleccione **Requerir que el dispositivo esté marcado como compatible** y **Requerir dispositivo unido al dominio (Azure AD híbrido)** y, finalmente, haga clic en **Seleccionar**.

10. Haga clic en **Crear** para crear la directiva de acceso condicional de Exchange Online.

    > [!NOTE]
    > A partir de Intune en Azure, tiene que crear todas las directivas de acceso condicional en la carga de trabajo de Azure Active Directory. Intune proporciona un vínculo a la carga de trabajo de directivas de acceso condicional de Azure AD desde el portal para que sea más cómodo.

    > [!IMPORTANT]
    > Si necesita asistencia para migrar directivas de acceso condicional creadas anteriormente en el portal clásico de Intune a Intune en Azure Portal, vea el tema [Reasignar directivas de acceso condicional desde el Portal de Intune clásico a Azure Portal](https://docs.microsoft.com/intune/conditional-access-intune-reassign). 

### <a name="app-based-conditional-access-for-exchange-online"></a>Acceso condicional basado en la aplicación para Exchange Online

Puede agregar una capa de seguridad adicional mediante el establecimiento de una directiva de acceso condicional basada en la aplicación para Exchange Online en Intune en Azure Portal. Al aplicar un acceso condicional basado en la aplicación para Exchange Online, requiere que los usuarios usen una aplicación específica (p. ej., la aplicación de Microsoft Outlook) para acceder al correo electrónico corporativo.

Para agregar una directiva de acceso condicional basado en la aplicación, siga estos pasos:

1. Vaya a [Azure Portal](https://portal.azure.com) e inicie sesión con sus credenciales de Intune. Después de iniciar sesión, verá el Panel de Azure.

2. Seleccione **Más servicios** en el menú izquierdo y, luego, escriba **Intune**.

3. Elija **Protección de aplicaciones de Intune**.

4. En la hoja **Administración de aplicaciones móviles de Intune**, elija **Toda la configuración**.

5. Seleccione **Exchange Online** en la sección **Acceso condicional**.

6. Seleccione **Permitir aplicaciones que admiten las directivas de aplicación de Intune** y seleccione la aplicación (p. ej., Microsoft Outlook).

7. Seleccione **Grupos de usuarios restringidos**, **Seleccionar grupos**, elija el usuario o grupo al que quiera aplicar la directiva y haga clic en **Seleccionar**.

## <a name="sensitive"></a>Confidencial

### <a name="low-and-above-risk-requires-mfa"></a>El riesgo bajo y superior exige MFA
En la tabla siguiente se describe la configuración de directiva de acceso condicional que se debe implementar para las directivas de riesgo bajo y superior.

|Categories|Tipo|Propiedades|Valores|Notas|
|:---------|:---|:---------|:-----|:----|
|**Asignaciones**|Usuarios y grupos|Incluir|Seleccionar usuarios y grupos: selecciona un grupo de seguridad específico que contiene usuarios de destino|Comenzar con el grupo de seguridad que incluye usuarios de prueba|
|||Excluir|Grupo de seguridad de excepción; cuentas de servicio (identidades de aplicación)|Pertenencia modificada de forma temporal según necesidad|
||Aplicaciones en la nube|Incluir|Seleccionar aplicaciones: selecciona Office 365 Exchange Online||
||Condiciones|Configurado|Sí|Configuración específica del entorno y las necesidades|
||Riesgo de inicio de sesión|Configurado|Sí|Configuración específica del entorno y las necesidades|
|||Nivel de riesgo|Bajo, medio, alto|Marcar los tres|
|**Controles de acceso**|Conceder|Conceder acceso|True|Seleccionado|
|||Exigir MFA|True|Check|
|||Exigir dispositivos compatibles|False||
|||Exigir dispositivo unido a dominio|False||
|||Exigir todos los controles seleccionados|True|Seleccionado|
|**Habilitar directiva**|||Activado|Implementa una directiva de acceso condicional|

### <a name="require-a-compliant-or-domain-joined-device"></a>Exigir un dispositivo compatible o unido a dominio
(Vea las instrucciones de base de referencia)

### <a name="app-based-conditional-access-for-exchange-online"></a>Acceso condicional basado en la aplicación para Exchange Online

(Vea las instrucciones de base de referencia)

#### <a name="apply-to"></a>Aplicar a

Una vez que se ha completado el proyecto de prueba, se deben aplicar estas directivas a los usuarios de la organización que necesitan acceso al correo electrónico considerado confidencial.

## <a name="highly-regulated"></a>Extremadamente regulado
### <a name="mfa-required"></a>MFA obligatorio

En la tabla siguiente se describe la configuración de directiva de acceso condicional que se debe implementar para la directiva extremadamente regulada.

|Categories|Tipo|Propiedades|Valores|Notas|
|:---------|:---|:---------|:-----|:----|
|**Asignaciones**|Usuarios y grupos|Incluir|Seleccionar usuarios y grupos: selecciona un grupo de seguridad específico que contiene usuarios de destino|Comenzar con el grupo de seguridad que incluye usuarios de prueba|
|||Excluir|Grupo de seguridad de excepción; cuentas de servicio (identidades de aplicación)|Pertenencia modificada de forma temporal según necesidad|
||Aplicaciones en la nube|Incluir|Seleccionar aplicaciones: selecciona Office 365 Exchange Online||
|**Controles de acceso**|Conceder|Conceder acceso|True|Seleccionado|
|||Exigir MFA|True|Check|
|||Exigir dispositivos compatibles|False|Check|
|||Exigir dispositivo unido a dominio|False||
|||Exigir todos los controles seleccionados|True|Seleccionado|
|**Habilitar directiva**|||Activado|Implementa una directiva de acceso condicional|

### <a name="require-a-compliant-or-domain-joined-device"></a>Exigir un dispositivo compatible o unido a dominio
(Vea las instrucciones de base de referencia)
### <a name="app-based-conditional-access-for-exchange-online"></a>Acceso condicional basado en la aplicación para Exchange Online
(Vea las instrucciones de base de referencia)
#### <a name="apply-to"></a>Aplicar a
Una vez que se ha completado el proyecto de prueba, se deben aplicar estas directivas a los usuarios de la organización que necesitan acceso al correo electrónico considerado extremadamente regulado.

### <a name="high-risk-users-policy"></a>Directiva de usuarios de alto riesgo
Para asegurarse de que se obligue a todas las cuentas comprometidas de usuarios de alto riesgo a realizar un cambio de contraseña al iniciar sesión, se debe aplicar la directiva siguiente.

Inicie sesión en [Microsoft Azure Portal (http://portal.azure.com)](http://portal.azure.com/) con las credenciales de administrador y luego vaya a **Azure AD Identity Protection > Directiva de riesgo de usuario**.

|Categories|Tipo|Propiedades|Valores|Notas|
|:---------|:---|:---------|:-----|:----|
|**Asignaciones**|Usuarios|Incluir|Todos los usuarios|Seleccionado|
|||Excluir|Ninguno||
||Condiciones|Riesgo de usuario|Alto|Seleccionado|
|**Controles**|Acceso|Permitir acceso|True|Seleccionado|
||Acceso|Exigir cambio de contraseña|True|Check|
|**Revisar**|No aplicable|No aplicable|No aplicable|No aplicable|
|**Aplicar directiva**|||Activado|Comienza a aplicar la directiva|


## <a name="additional-configurations"></a>Configuraciones adicionales
Además de las directivas anteriores, debe configurar las siguientes opciones de administración de dispositivos y aplicaciones móviles de esta sección.

### <a name="intune-mobile-application-management"></a>Administración de aplicaciones móviles de Intune

Para asegurarse de que el correo electrónico se protege mediante las recomendaciones de directivas indicadas anteriormente para cada nivel de seguridad y protección de datos, debe crear directivas de protección de aplicaciones de Intune desde Azure Portal.

Para crear una nueva directiva de protección de aplicaciones, inicie sesión en el portal de Microsoft Azure con las credenciales de administrador y, luego, vaya a **Intune App Protection > Directiva de aplicaciones**.

Agregue una nueva directiva (+Agregar) como se muestra en la siguiente captura de pantalla:

![Administración de aplicaciones móviles de Intune](./media/secure-email/CA-EXO-policy-2.png)

>[!NOTE]
>Hay ligeras diferencias en las opciones de directiva de protección de aplicaciones entre iOS y Android. La siguiente directiva es específicamente para Android.
>

En las tablas siguientes se describe la configuración de la directiva de protección de aplicaciones de Intune recomendada:

|Categories|Tipo|Propiedades|Valores|Notas|
|:---------|:---|:---------|:-----|:----|
|**General**|Correo electrónico|Nombre|Directiva de correo electrónico segura para Android|Escribir un nombre de directiva|
|||Descripción||Escriba texto que describa la directiva|
|||Plataforma|Android|Hay ligeras diferencias en las opciones de directiva de protección de aplicaciones entre iOS y Android; esta directiva es específicamente para Android|
|**Aplicaciones**|Aplicaciones|Aplicaciones|Outlook|Seleccionado (lista)|
|**Configuración**|Reubicación de datos|Impedir copias de seguridad de Android|Sí|En iOS esto específicamente llama a iTunes e iCloud|
||||Permitir que la aplicación transfiera datos a otras aplicaciones|Aplicaciones administradas por directivas||
|||Permitir a la aplicación recibir datos de otras aplicaciones|Aplicaciones administradas por directivas||
|||Impedir "Guardar como"|Sí||
|||Restringir cortar, copiar y pegar con otras aplicaciones|Aplicaciones administradas por directivas||
|||Restringir contenido web para mostrar en Managed Browser|No||
|||Cifrar datos de aplicación|Sí|En iOS, seleccione la opción: Cuando el dispositivo está bloqueado|
|||Deshabilitar la sincronización de contactos|No||
||Acceso|Requerir PIN para acceder|Sí||
|||Número de intentos antes de restablecimiento del PIN|3||
|||Permitir PIN sencillo|No||
|||Longitud del PIN|6||
|||Permitir desbloqueo mediante huellas digitales en lugar de mediante PIN|Sí||
|||Requerir credenciales corporativas para el acceso|No||
|||Bloquear la ejecución de aplicaciones administradas en dispositivos liberados o modificados|Sí||
|||Volver a comprobar los requisitos de acceso después de (minutos)|30||
|||Período de gracia sin conexión|720||
|||Intervalo sin conexión (días) antes de que se borren los datos de la aplicación|90||
|||Bloquear captura de pantalla y asistente de Android|No|En iOS esta opción no está disponible|

Cuando haya finalizado, recuerde hacer clic en "Crear". Repita los pasos anteriores y reemplace la plataforma seleccionada (desplegable) por iOS. Esto crea dos directivas de aplicación, por lo que una vez creada la directiva, asígnele grupos e impleméntela.

- Para obtener información, consulte [Creación y asignación de directivas de protección de aplicaciones](https://docs.microsoft.com/intune/app-protection-policies).

### <a name="intune-mobile-device-management"></a>Administración de dispositivos móviles de Intune
Puede crear las siguientes directivas de cumplimiento de dispositivos y de perfiles de configuración de dispositivos si inicia sesión en [Intune en Azure Portal](https://portal.azure.com) con sus credenciales de Azure.

#### <a name="ios-email-profile"></a>Perfil de correo electrónico iOS
En [Intune en Azure Portal](https://portal.azure.com), puede crear los siguientes perfiles de configuración del dispositivo en **Configuración del dispositivo > Perfiles > Crear perfil > Plataforma (iOS) > Tipo de perfil (correo electrónico)**.

|Categories|Tipo|Propiedades|Valores|Notas|
|:---------|:---|:---------|:-----|:----|
|**Perfil de correo electrónico**|Exchange Active Sync|Host (#)|Outlook.office365.com||
|||Nombre de cuenta (#)|SecureEmailAccount|Elección de administrador|
|||Nombre de usuario|Nombre principal de usuario|Seleccionado: desplegable|
|||Dirección de correo electrónico|Dirección SMTP principal|Seleccionado: desplegable|
|||Método de autenticación|Nombre de usuario y contraseña|Seleccionado: desplegable|
|||Utilizar S/MIME|False||
||Configuración de sincronización|Número de días de correo electrónico para sincronizar|Dos semanas|Seleccionado: desplegable|
|||Usar SSL|True|Check|
|||Permitir que los mensajes se muevan a otras cuentas de correo electrónico|False||
|||Permitir el envío de correo electrónico desde aplicaciones de terceros|True||
|||Sincronizar las direcciones de correo electrónico usadas recientemente|True|Check|

#### <a name="android-email-profile"></a>Perfil de correo electrónico de Android
En [Intune en Azure Portal](https://portal.azure.com), puede crear los siguientes perfiles de configuración del dispositivo en **Configuración del dispositivo > Perfiles > Crear perfil > Plataforma (Android) > Tipo de perfil (correo electrónico)**.

|Categories|Tipo|Propiedades|Valores|Notas|
|:---------|:---|:---------|:-----|:----|
|**Perfil de correo electrónico**|Exchange Active Sync|Host (#)| Outlook.office365.com|
|||Nombre de cuenta (#)|SecureEmailAccount|Elección de administrador|
|||Nombre de usuario|Nombre principal de usuario|Seleccionado: desplegable|
|||Dirección de correo electrónico|Dirección SMTP principal|Seleccionado: desplegable|
|||Método de autenticación|Nombre de usuario y contraseña|Seleccionado: desplegable|
|||Utilizar S/MIME|False||
||Configuración de sincronización|Número de días de correo electrónico para sincronizar|Dos semanas|Seleccionado: desplegable|
|||Programación de sincronización|No configurado|Seleccionado: desplegable|
|||Usar SSL|True|Check|
|||Tipo de contenido para sincronizar|||
|||Correo electrónico|True|Check (bloqueado)|
|||Contactos|True|Check|
|||Calendario|True|Check|
|||Tareas|True|Check|
|||Notas|True|Check|

#### <a name="android-for-work-email-profile"></a>Perfil de correo electrónico de Android for Work
En [Intune en Azure Portal](https://portal.azure.com), puede crear los siguientes perfiles de configuración del dispositivo en **Configuración del dispositivo > Perfiles > Crear perfil > Plataforma (Android for Work) > Tipo de perfil (correo electrónico)**.

|Categories|Tipo|Propiedades|Valores|Notas|
|:---------|:---|:---------|:-----|:----|
|**Perfil de correo electrónico**|Exchange Active Sync|Host(#)| Outlook.office365.com|
|||Nombre de cuenta(#)|SecureEmailAccount|Elección de administrador|
|||Nombre de usuario|Nombre principal de usuario|Seleccionado: desplegable|
|||Dirección de correo electrónico|Dirección SMTP principal|Seleccionado: desplegable|
|||Método de autenticación|Nombre de usuario y contraseña|Seleccionado: desplegable|
||Configuración de sincronización|Número de días de correo electrónico para sincronizar|Dos semanas|Seleccionado: desplegable|
|||Usar SSL|True|Check|

#### <a name="device-compliance-policy"></a>Directiva de cumplimiento de dispositivos
En [Intune en Azure Portal](https://portal.azure.com), puede crear los siguientes perfiles de cumplimiento del dispositivo en **Configuración del dispositivo > Perfiles > Crear perfil > Plataforma (iOS, Android u otras) > Configuración**.

|Categories|Tipo|Propiedades|Valores|Notas|
|:---------|:---|:---------|:-----|:----|
|**Seguridad del sistema**|Contraseña|Requerir una contraseña para desbloquear dispositivos móviles (...)|Sí|Seleccionado: desplegable|
|||Permitir contraseñas sencillas (...)|No|Seleccionado: desplegable|
|||Longitud mínima de la contraseña (...)|6|Seleccionado: lista|
||Configuración avanzada de contraseñas|Todos|No configurado||
||Cifrado|Requerir cifrado en el dispositivo móvil (...)|Sí|Seleccionado: desplegable|
||Perfiles de correo electrónico|Intune debe administrar la cuenta de correo electrónico (iOS 8.0+)|Sí| Seleccionado: desplegable|
|||Seleccionar (#)||Debe seleccionar la directiva de configuración de correo electrónico para iOS: directiva de correo electrónico de iOS (vea las directivas de configuración anteriores)|
|**Estado de dispositivos**|Atestación del mantenimiento de dispositivos Windows|Requerir que se informe del estado correcto de los dispositivos (Windows 10 Escritorio y Mobile y versiones posteriores)|Sí||
||Configuración de seguridad del dispositivo|Todos|No configurado||
||Protección contra amenazas del dispositivo|Todos|No configurado||
||Jailbreak|El dispositivo no debe tener Jailbreak o rooting (iOS 8.0+, Android 4.0+)|Sí||
|**Propiedades del dispositivo**|Versión del sistema operativo|Todos|No configurado|||

Para que todas las directivas anteriores se consideren implementadas, deben establecerse como destinos en los grupos de usuarios. Puede hacerlo al crear la directiva (al guardar) o después, al seleccionar Administrar la implementación en la sección Directiva (mismo nivel que Agregar).

## <a name="remediating-medium-or-high-risk-access-events"></a>Corrección de eventos de acceso de riesgo medio o alto
Si un usuario informa de que ahora se espera que realice MFA cuando esto no era necesario anteriormente, el equipo de soporte técnico puede revisar su estado desde una perspectiva de riesgo.  

Los usuarios de la organización con un rol Administrador global o Administrador de seguridad pueden usar Azure AD Identity Protection para revisar los eventos de riesgo que han contribuido a la puntuación de riesgo calculado. Si identifican algunos eventos marcados como sospechosos aunque confirmados como válidos (por ejemplo, un inicio de sesión desde una ubicación no familiar cuando un empleado está de vacaciones), el administrador puede resolver el evento para que ya no contribuya a la puntuación de riesgo.

## <a name="next-steps"></a>Pasos siguientes

[Más información sobre las recomendaciones de directiva para la protección de sitios y archivos de SharePoint](sharepoint-file-access-policies.md)
