---
title: "Directivas recomendadas para proteger el correo electrónico - Microsoft 365 Enterprise | Microsoft Docs"
description: "Describe las directivas recomendadas por Microsoft para aplicar directivas y configuraciones de correo electrónico."
author: barlanmsft
manager: angrobe
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 08/30/2017
ms.author: barlan
ms.reviewer: jsnow
ms.custom: it-pro
ms.openlocfilehash: 6c8ad1b7a297c28e52cfc5412fe40d3001d2efa3
ms.sourcegitcommit: d8588b191a4f9daea73698426dd632e7997140dc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2017
---
# <a name="policy-recommendations-for-securing-email"></a>Recomendaciones de directivas para proteger el correo electrónico

En este artículo se describen directivas recomendadas para ayudar a proteger el correo electrónico de la organización, así como los clientes de correo electrónico que admiten la autenticación moderna y el acceso condicional. Estas recomendaciones se suman a las [recomendaciones comunes sobre directivas de acceso e identidad](identity-access-policies.md).

Las siguientes recomendaciones se basan en tres niveles diferentes de seguridad y protección para el correo electrónico que se pueden aplicar en función de la granularidad de las necesidades: **base de referencia**, **confidencial** y **extremadamente regulado**. Puede aprender más sobre estos niveles de seguridad y los sistemas operativos de cliente recomendados, a los que hacen referencia estas recomendaciones, en la [introducción a las directivas y configuraciones de seguridad recomendadas](microsoft-365-policies-configurations.md).

>[!NOTE]
>Todos los grupos de seguridad creados como parte de estas recomendaciones deben crearse con las características de Office habilitadas. Esto es especialmente importante para la implementación de AIP al proteger documentos en SharePoint.
>
>![Características de Office habilitadas para grupos de seguridad](./media/security-group.png)
>

## <a name="baseline"></a>Línea base
Para crear una nueva directiva de acceso condicional, inicie sesión en Microsoft Azure Portal con las credenciales de administrador. Luego vaya a **Azure Active Directory > Seguridad > Acceso condicional**.

Puede agregar una nueva directiva (+Agregar) como se muestra en la siguiente captura de pantalla:

![Directiva de acceso condicional de base de referencia](./media/secure-email/baseline-ca-policy.png)

En las tablas siguientes se describe la configuración correcta necesaria para expresar las directivas requeridas para cada nivel de protección.

### <a name="medium-and-above-risk-requires-mfa"></a>El riesgo medio y superior exige MFA

En la tabla siguiente se describe la configuración de directiva de acceso condicional que se debe implementar para esta directiva.

|Categorías|Tipo|Propiedades|Valores|Notas|
|:---------|:---|:---------|:-----|:----|
|**Asignaciones**|Usuarios y grupos|Include|Seleccionar usuarios y grupos: selecciona un grupo de seguridad específico que contiene usuarios de destino|Comience con el grupo de seguridad que incluye usuarios de prueba.|
|||Excluir|Grupo de seguridad de excepción; cuentas de servicio (identidades de aplicación)|Pertenencia modificada de forma temporal según necesidad|
||Aplicaciones en la nube|Include|Seleccionar aplicaciones: selecciona Office 365 Exchange Online||
||Conditions|Configured|Sí|Configuración específica del entorno y las necesidades|
||Riesgo de inicio de sesión|Nivel de riesgo|Alto, medio|Comprobar ambos|
|**Controles de acceso**|Conceder|Conceder acceso|True|Seleccionado|
|||Exigir MFA|True|Check|
|||Exigir dispositivos compatibles|False||
|||Exigir dispositivos unidos a dominio|False||
|||Exigir todos los controles seleccionados|True|Seleccionado|
|**Habilitar directiva**|||Encendido|Implementa una directiva de acceso condicional|

### <a name="require-a-compliant-or-domain-joined-device"></a>Exigir un dispositivo compatible o unido a dominio

Para crear una nueva directiva de acceso condicional de Intune para Exchange Online, inicie sesión en el [portal de administración de Microsoft (http://manage.microsoft.com)](http://manage.microsoft.com/) con las credenciales de administrador y luego vaya a **Directiva > Acceso condicional > Directiva de Exchange Online**.

![Directiva de Exchange Online](./media/secure-email/exchange-online-policy.png)

Debe establecer una directiva de acceso condicional específicamente para Exchange Online en el portal de administración de Intune para exigir un dispositivo compatible o unido a dominio.

|Categorías|Tipo|Propiedades|Valores|Notas|
|:---------|:---|:---------|:-----|:----|
|**Acceso a la aplicación**|Outlook y otras aplicaciones que usan autenticación moderna|Todas las plataformas|True|Seleccionado|
|||Windows debe cumplir el siguiente requisito|El dispositivo debe estar unido a dominio o ser compatible|Seleccionado (lista)|
|||Plataforma seleccionada|False||
||Outlook Web Access (OWA)|Bloquear dispositivos no compatibles de la misma plataforma que Outlook|True|Check|
||Aplicaciones de Exchange ActiveSync que usan la autenticación básica|Bloquear los dispositivos no compatibles de las plataformas que admite Microsoft Intune|True|Check|
|||Bloquear todos los otros dispositivos de las plataformas que no admite Microsoft Intune|True|Check|
|**Implementación de directiva**|Grupos de destino|Seleccionar los grupos de seguridad de Active Directory a los que se dirige esta directiva|||
|||Todos los usuarios|False||
|||Grupos de seguridad seleccionados|True|Seleccionado|
|||Modificar|Seleccionar un grupo de seguridad específico que contiene usuarios de destino||
||Excluir grupos|Seleccionar los grupos de Active Directory para excluirlos de la directiva (reemplaza a los miembros de la lista de grupos de destino)|||
|||No hay usuarios exentos|True|Seleccionado|
|||Grupos de seguridad seleccionados|False|||

### <a name="mobile-application-management-conditional-access-for-exchange-online"></a>Acceso condicional para la administración de aplicaciones móviles para Exchange Online

Debe establecer una directiva de acceso condicional específicamente para Exchange Online en el portal de administración de Intune para administrar aplicaciones móviles.

Para administrar aplicaciones móviles, inicie sesión en Microsoft Azure Portal con las credenciales de administrador y luego vaya a **Intune App Protection > Configuración > Acceso condicional > Exchange Online**.

|Categorías|Tipo|Propiedades|Valores|Notas|
|:---------|:---|:---------|:-----|:----|
|**Acceso de la aplicación**|Aplicaciones permitidas|Permitir el acceso de las aplicaciones|Permitir aplicaciones que admiten las directivas de aplicación de Intune|Seleccionado (lista): da como resultado una lista de combinaciones de aplicaciones o plataformas compatibles con las directivas de aplicación de Intune|
|**Acceso de usuario**|Aplicaciones permitidas|Grupos de usuarios restringidos|Agregar usuarios o grupos: selección de un grupo de seguridad específico que contiene usuarios de destino|Comenzar con el grupo de seguridad que incluye usuarios de prueba|
|||Grupos de usuarios exentos|Grupos de seguridad de excepción|||

#### <a name="apply-to"></a>Aplicar a

Una vez que se ha completado el proyecto de prueba, se deben aplicar estas directivas a todos los usuarios de la organización.

## <a name="sensitive"></a>Confidencial

### <a name="low-and-above-risk-requires-mfa"></a>El riesgo bajo y superior exige MFA
En la tabla siguiente se describe la configuración de directiva de acceso condicional que se debe implementar para las directivas de riesgo bajo y superior.

|Categorías|Tipo|Propiedades|Valores|Notas|
|:---------|:---|:---------|:-----|:----|
|**Asignaciones**|Usuarios y grupos|Include|Seleccionar usuarios y grupos: selecciona un grupo de seguridad específico que contiene usuarios de destino|Comenzar con el grupo de seguridad que incluye usuarios de prueba|
|||Excluir|Grupo de seguridad de excepción; cuentas de servicio (identidades de aplicación)|Pertenencia modificada de forma temporal según necesidad|
||Aplicaciones en la nube|Include|Seleccionar aplicaciones: selecciona Office 365 Exchange Online||
||Conditions|Configured|Sí|Configuración específica del entorno y las necesidades|
||Riesgo de inicio de sesión|Configured|Sí|Configuración específica del entorno y las necesidades|
|||Nivel de riesgo|Bajo, medio, alto|Marcar los tres|
|**Controles de acceso**|Conceder|Conceder acceso|True|Seleccionado|
|||Exigir MFA|True|Check|
|||Exigir dispositivos compatibles|False||
|||Exigir dispositivo unido a dominio|False||
|||Exigir todos los controles seleccionados|True|Seleccionado|
|**Habilitar directiva**|||Encendido|Implementa una directiva de acceso condicional|

### <a name="require-a-compliant-or-domain-joined-device"></a>Exigir un dispositivo compatible o unido a dominio
(Vea las instrucciones de base de referencia)

### <a name="mobile-application-management-conditional-access-for-exchange-online"></a>Acceso condicional para la administración de aplicaciones móviles para Exchange Online

(Vea las instrucciones de base de referencia)

#### <a name="apply-to"></a>Aplicar a

Una vez que se ha completado el proyecto de prueba, se deben aplicar estas directivas a los usuarios de la organización que necesitan acceso al correo electrónico considerado confidencial.

## <a name="highly-regulated"></a>Extremadamente regulado
### <a name="mfa-required"></a>MFA obligatorio

En la tabla siguiente se describe la configuración de directiva de acceso condicional que se debe implementar para la directiva extremadamente regulada.

|Categorías|Tipo|Propiedades|Valores|Notas|
|:---------|:---|:---------|:-----|:----|
|**Asignaciones**|Usuarios y grupos|Include|Seleccionar usuarios y grupos: selecciona un grupo de seguridad específico que contiene usuarios de destino|Comenzar con el grupo de seguridad que incluye usuarios de prueba|
|||Excluir|Grupo de seguridad de excepción; cuentas de servicio (identidades de aplicación)|Pertenencia modificada de forma temporal según necesidad|
||Aplicaciones en la nube|Include|Seleccionar aplicaciones: selecciona Office 365 Exchange Online||
|**Controles de acceso**|Conceder|Conceder acceso|True|Seleccionado|
|||Exigir MFA|True|Check|
|||Exigir dispositivos compatibles|False|Check|
|||Exigir dispositivo unido a dominio|False||
|||Exigir todos los controles seleccionados|True|Seleccionado|
|**Habilitar directiva**|||Encendido|Implementa una directiva de acceso condicional|

### <a name="require-a-compliant-or-domain-joined-device"></a>Exigir un dispositivo compatible o unido a dominio
(Vea las instrucciones de base de referencia)
### <a name="mobile-application-management-conditional-access-for-exchange-online"></a>Acceso condicional para la administración de aplicaciones móviles para Exchange Online
(Vea las instrucciones de base de referencia)
#### <a name="apply-to"></a>Aplicar a
Una vez que se ha completado el proyecto de prueba, se deben aplicar estas directivas a los usuarios de la organización que necesitan acceso al correo electrónico considerado extremadamente regulado.

### <a name="high-risk-users-policy"></a>Directiva de usuarios de alto riesgo
Para asegurarse de que se obligue a todas las cuentas comprometidas de usuarios de alto riesgo a realizar un cambio de contraseña al iniciar sesión, se debe aplicar la directiva siguiente.

Inicie sesión en [Microsoft Azure Portal (http://portal.azure.com)](http://portal.azure.com/) con las credenciales de administrador y luego vaya a **Azure AD Identity Protection > Directiva de riesgo de usuario**.

|Categorías|Tipo|Propiedades|Valores|Notas|
|:---------|:---|:---------|:-----|:----|
|**Asignaciones**|Users|Include|Todos los usuarios|Seleccionado|
|||Excluir|ninguna.||
||Conditions|Riesgo de usuario|Alto|Seleccionado|
|**Controles**|Acceso|Permitir acceso|True|Seleccionado|
||Acceso|Exigir cambio de contraseña|True|Check|
|**Revisar**|N/D|No aplicable|No aplicable|N/D|
|**Aplicar directiva**|||Encendido|Comienza a aplicar la directiva|


## <a name="additional-configurations"></a>Configuraciones adicionales
Además de las directivas anteriores, debe configurar las siguientes opciones de administración de dispositivos y aplicaciones móviles de esta sección.

### <a name="intune-mobile-application-management"></a>Administración de aplicaciones móviles de Intune

Para asegurarse de que el correo electrónico se protege mediante las recomendaciones de directivas indicadas anteriormente para cada nivel de seguridad y protección de datos, debe crear directivas de protección de aplicaciones de Intune desde Azure Portal.

Para crear una nueva directiva de protección de aplicaciones, inicie sesión en Microsoft Azure Portal con las credenciales de administrador y luego vaya a **Intune App Protection > Configuración > Directiva de aplicaciones**.

Agregue una nueva directiva (+Agregar) como se muestra en la siguiente captura de pantalla:

![Administración de aplicaciones móviles de Intune](./media/secure-email/intune-mobile-app-mgmt.png)

>[!NOTE]
>Hay ligeras diferencias en las opciones de directiva de protección de aplicaciones entre iOS y Android. La siguiente directiva es específicamente para Android.
>

En las tablas siguientes se describe la configuración de la directiva de protección de aplicaciones de Intune recomendada:

|Categorías|Tipo|Propiedades|Valores|Notas|
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

### <a name="intune-mobile-device-management"></a>Administración de dispositivos móviles de Intune
Cree las siguientes directivas de cumplimiento y configuración al iniciar sesión en el [portal de administración de Microsoft (http://manage.microsoft.com)](https://manage.microsoft.com/) con las credenciales de administrador.

#### <a name="ios-email-profile"></a>Perfil de correo electrónico iOS
En el [portal de administración de Intune (https://manage.microsoft.com)](https://manage.microsoft.com/), cree las siguientes directivas de configuración en **Directiva > Directivas de configuración > Agregar > iOS > Perfil de correo electrónico (iOS 8 y posterior)**.

|Categorías|Tipo|Propiedades|Valores|Notas|
|:---------|:---|:---------|:-----|:----|
|**Perfil de correo electrónico**|Exchange Active Sync|Host (#)|Outlook.office365.com||
|||Nombre de cuenta (#)|SecureEmailAccount|Elección de administrador|
|||Username|Nombre principal de usuario|Seleccionado: desplegable|
|||dirección de correo electrónico|Dirección SMTP principal|Seleccionado: desplegable|
|||Método de autenticación|Nombre de usuario y contraseña|Seleccionado: desplegable|
|||Utilizar S/MIME|False||
||Configuración de sincronización|Número de días de correo electrónico para sincronizar|Dos semanas|Seleccionado: desplegable|
|||Usar SSL|True|Check|
|||Permitir que los mensajes se muevan a otras cuentas de correo electrónico|False||
|||Permitir el envío de correo electrónico desde aplicaciones de terceros|True||
|||Sincronizar las direcciones de correo electrónico usadas recientemente|True|Check|

#### <a name="ios-app-sharing-profile"></a>Perfil de uso compartido de aplicaciones iOS
En el [portal de administración de Intune (https://manage.microsoft.com)](https://manage.microsoft.com/), cree las siguientes directivas de configuración en **Directiva > Directivas de configuración > Agregar > iOS > Configuración general (iOS 8.0 y posterior)**.

|Categorías|Tipo|Propiedades|Valores|Notas|
|:---------|:---|:---------|:-----|:----|
|**Seguridad**|Todos|Todos|No configurado||
|**Nube**|Todos|Todos|No configurado||
|**Aplicaciones**|Explorador|Todos|No configurado||
||Aplicaciones|Permitir la instalación de aplicaciones|No configurado||
|||Requerir una contraseña para tener acceso al almacén de aplicaciones|No configurado||
|||Permitir compras dentro de la aplicación|No configurado||
|||Permitir documentos administrados en otras aplicaciones administradas (iOS 8.0 y posterior)|No|Seleccionado: desplegable|
|||Permitir documentos no administrados en otras aplicaciones administradas|No configurado||
|||Permitir videoconferencias|No configurado||
|||Permitir que el usuario confíe en nuevos autores de aplicaciones empresariales|No configurado||
||Juegos|Todos|No configurado||
||Contenido multimedia|Todos|No configurado|||

#### <a name="android-email-profile"></a>Perfil de correo electrónico de Android
En el [portal de administración de Intune (https://manage.microsoft.com)](https://manage.microsoft.com/), cree las siguientes directivas de configuración en **Directiva > Directivas de configuración > Agregar > iOS > Perfil de correo electrónico (Samsung KNOX Standard 4.0 y posterior)**.

|Categorías|Tipo|Propiedades|Valores|Notas|
|:---------|:---|:---------|:-----|:----|
|**Perfil de correo electrónico**|Exchange Active Sync|Host (#)| Outlook.office365.com|
|||Nombre de cuenta (#)|SecureEmailAccount|Elección de administrador|
|||Username|Nombre principal de usuario|Seleccionado: desplegable|
|||dirección de correo electrónico|Dirección SMTP principal|Seleccionado: desplegable|
|||Método de autenticación|Nombre de usuario y contraseña|Seleccionado: desplegable|
|||Utilizar S/MIME|False||
||Configuración de sincronización|Número de días de correo electrónico para sincronizar|Dos semanas|Seleccionado: desplegable|
|||Programación de sincronización|No configurado|Seleccionado: desplegable|
|||Usar SSL|True|Check|
|||Tipo de contenido para sincronizar|||
|||Correo electrónico|True|Check (bloqueado)|
|||Contacts|True|Check|
|||Calendario|True|Check|
|||Tareas|True|Check|
|||Notas|True|Check|

#### <a name="android-for-work-email-profile"></a>Perfil de correo electrónico de Android for Work
En el [portal de administración de Intune (https://manage.microsoft.com)](https://manage.microsoft.com/), cree las siguientes directivas de configuración en **Directiva > Directivas de configuración > Agregar > iOS > Perfil de correo electrónico (Android for Work - Gmail)**.

|Categorías|Tipo|Propiedades|Valores|Notas|
|:---------|:---|:---------|:-----|:----|
|**Perfil de correo electrónico**|Exchange Active Sync|Host(#)| Outlook.office365.com|
|||Nombre de cuenta(#)|SecureEmailAccount|Elección de administrador|
|||Username|Nombre principal de usuario|Seleccionado: desplegable|
|||dirección de correo electrónico|Dirección SMTP principal|Seleccionado: desplegable|
|||Método de autenticación|Nombre de usuario y contraseña|Seleccionado: desplegable|
||Configuración de sincronización|Número de días de correo electrónico para sincronizar|Dos semanas|Seleccionado: desplegable|
|||Usar SSL|True|Check|

#### <a name="android-for-work-app-sharing-profile"></a>Perfil de uso compartido de aplicaciones de Android for Work
En el [portal de administración de Intune (https://manage.microsoft.com)](https://manage.microsoft.com/), cree las siguientes directivas de configuración en **Directiva > Directivas de configuración > Agregar > iOS > Configuración general (Android for Work)**.

|Categorías|Tipo|Propiedades|Valores|Notas|
|:---------|:---|:---------|:-----|:----|
|**Seguridad**|Contraseña|Longitud mínima de contraseña|No configurado||
|||Número de errores de inicio de sesión repetidos antes de que se quite el perfil de trabajo|No configurado||
|||Minutos de inactividad antes de que se bloquee el dispositivo|No configurado||
|||Expiración de contraseña (días)|No configurado||
|||Recordar el historial de contraseñas|No configurado||
|||Exigir una contraseña para desbloquear el dispositivo móvil|No configurado||
|||Permitir desbloqueo mediante huellas digitales (Android 6.0+)|No configurado||
|||Permitir Smart Lock y otros agentes de confianza (Android 6.0+)|No configurado||
||Configuración de perfil de trabajo|Permitir uso compartido de datos entre perfiles de trabajo y personales|Las aplicaciones de un perfil de trabajo pueden controlar la solicitud de uso compartido desde un perfil personal|Seleccionado: desplegable|
|||Ocultar notificaciones del perfil de trabajo cuando el dispositivo está bloqueado (Android 6.0+)|No configurado||
|||Establecer directiva de permisos de aplicación predeterminada (Android 6.0+)|No configurado|||

#### <a name="device-compliance-policy"></a>Directiva de cumplimiento de dispositivos
En el [portal de administración de Intune (https://manage.microsoft.com)](https://manage.microsoft.com/), cree las siguientes directivas de configuración en **Directiva > Directiva de cumplimiento > Agregar**.

|Categorías|Tipo|Propiedades|Valores|Notas|
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
