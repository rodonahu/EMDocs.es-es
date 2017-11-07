---
title: "Introducción a las directivas de identidad y acceso a dispositivos - Microsoft 365 Enterprise | Microsoft Docs"
description: Explica las directivas recomendadas por Microsoft para aplicar directivas y configuraciones de identidad y acceso a dispositivos.
author: barlanmsft
manager: angrobe
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 10/27/2017
ms.author: barlan
ms.reviewer: jsnow
ms.custom: it-pro
ms.openlocfilehash: 46a63151471a10b578ffaf3bddb27ddfcd5500a5
ms.sourcegitcommit: feb1e385af0bc2a2eba56e5c2d1e8b4ba8866126
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2017
---
# <a name="general-identity-and-device-access-policy-recommendations"></a>Recomendaciones generales de directivas de identidad y acceso a dispositivos
En este artículo se explican las directivas comunes recomendadas para ayudar a proteger Microsoft 365 Enterprise. También se tratan las configuraciones de plataforma cliente predeterminadas que se recomiendan para proporcionar la mejor experiencia de sistema operativo a los usuarios, además de los requisitos técnicos previos del acceso condicional.

En estas instrucciones se explica cómo implementar las directivas recomendadas en un entorno recién aprovisionado. La configuración de estas directivas en un entorno de laboratorio independiente permite entender y evaluar las directivas recomendadas antes de su implementación en los entornos de preproducción y producción. El entorno recién aprovisionado puede ser solo en la nube o híbrido.  

Para implementar correctamente las directivas recomendadas, debe tomar medidas en Azure Portal para cumplir los requisitos previos indicados anteriormente. En concreto, tiene que:
* Configurar redes con nombre a fin de garantizar que Azure Identity Protection pueda generar correctamente una puntuación del riesgo
* Exigir a todos los usuarios que se registren para Multi-Factor Authentication (MFA)
* Configurar la sincronización de contraseña y el restablecimiento de contraseña autoservicio para permitir que los usuarios puedan restablecer las contraseñas por sí mismos

Puede destinar directivas de Azure AD e Intune a grupos de usuarios específicos. Se sugiere implementar las directivas definidas anteriormente por fases. De este modo puede validar el rendimiento de las directivas y los equipos de soporte técnico con respecto a la directiva de forma incremental.


## <a name="prerequisites"></a>Requisitos previos

Antes de implementar las directivas que se describen en el resto de este documento, hay varios requisitos previos que debe cumplir la organización:
* [Configurar redes con nombre](https://docs.microsoft.com/azure/active-directory/active-directory-known-networks-azure-portal). Azure AD Identity Protection recopila y analiza todos los datos de sesión disponibles para generar una puntuación de riesgo. Se recomienda especificar los intervalos de IP públicos de la organización para la red en la configuración de redes con nombre de Azure AD. Al tráfico procedente de estos intervalos se le asigna una puntuación de riesgo reducida, así que el tráfico de fuera del entorno corporativo se trata como puntuación de riesgo mayor.
* [Registrar a todos los usuarios con Multi-Factor Authentication (MFA)](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-manage-users-and-devices). Azure AD Identity Protection usa Azure MFA para realizar una comprobación de seguridad adicional. Se recomienda exigir a todos los usuarios que se registren en Azure MFA con antelación.
* [Habilitar el registro automático de dispositivos de equipos Windows unidos a dominio](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup). El acceso condicional puede garantizar que el dispositivo que se conecta al servicio sea un dispositivo unido a dominio o compatible. Para permitir esto en equipos Windows, el dispositivo debe estar registrado con Azure AD.  En este artículo se explica cómo configurar el registro automático de dispositivos.  Tenga en cuenta que AD FS es un requisito.
* **Preparar el equipo de soporte técnico**. Tenga preparado un plan para los usuarios que no puedan completar MFA. Puede consistir en agregarlos a un grupo de exclusión de directivas o registrar nueva información MFA para ellos. Antes de llevar a cabo cualquiera de estos importantes cambios de seguridad, debe asegurarse de que sea el usuario real el que realice la solicitud. Un paso eficaz es exigir a los administradores de los usuarios que ayuden con la aprobación.
* [Configurar la escritura diferida de contraseñas en AD local](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started). La escritura diferida de contraseñas permite a Azure AD exigir que los usuarios cambien sus contraseñas locales cuando se ha detectado un alto riesgo de cuenta comprometida. Puede habilitar esta característica mediante Azure AD Connect de dos maneras distintas. Puede habilitar la escritura diferida de contraseñas en la pantalla de características opcionales del asistente para la configuración de Azure AD Connect, o bien puede habilitarla a través de Windows PowerShell.  
* [Habilitar la autenticación moderna](https://support.office.com/article/Enable-or-disable-modern-authentication-in-Exchange-Online-58018196-f918-49cd-8238-56f57f38d662) y [proteger los puntos de conexión heredados](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-supported-apps).  El acceso condicional funciona tanto con aplicaciones de escritorio como móviles que usan autenticación moderna. Si la aplicación usa protocolos de autenticación heredados, puede obtener acceso a pesar de las condiciones que se apliquen. Es importante saber qué aplicaciones pueden usar reglas de acceso condicional y los pasos que debe seguir para proteger otros puntos de entrada a la aplicación.
* [Habilitar Azure Information Protection](https://docs.microsoft.com/information-protection/get-started/infoprotect-tutorial-step1) al activar Rights Management. Use Azure Information Protection con el correo electrónico para empezar con la clasificación de mensajes de correo electrónico. Siga el tutorial de inicio rápido para personalizar y publicar la directiva.  

### <a name="recommended-email-clients"></a>Clientes de correo electrónico recomendados
Los siguientes clientes de correo electrónico admiten la autenticación moderna y el acceso condicional. Azure Information Protection todavía no está disponible para todos los clientes.

|Plataforma|Cliente|Versión/Notas|Azure Information Protection|
|:-------|:-----|:------------|:--------------------|
|**Windows**|Outlook|2016, 2013 [Habilitar autenticación moderna](https://support.office.com/article/Enable-Modern-Authentication-for-Office-2013-on-Windows-devices-7dc1c01a-090f-4971-9677-f1b192d6c910)|Sí|
|**iOS**|Outlook|[Más reciente](https://itunes.apple.com/us/app/microsoft-outlook-email-and-calendar/id951937596?mt=8)|No|
|**Android**|Outlook|[Más reciente](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en)|No|
|**macOS**|Versión preliminar pública||No|
|**Linux**|No compatible||No|

Para acceder a documentos protegidos con Azure Information Protection es posible que se necesite software adicional. Asegúrese de usar [software y formatos de documentos compatibles](https://docs.microsoft.com/information-protection/get-started/requirements-applications) para crear y ver documentos protegidos con Azure Information Protection.


### <a name="recommended-client-platforms-when-securing-documents"></a>Plataformas de cliente recomendadas para proteger documentos
Si se ha aplicado una directiva de documentos seguros, se recomiendan los siguientes clientes.

|Plataforma|Word/Excel/PowerPoint|OneNote|Aplicación OneDrive|Aplicación SharePoint|Cliente de sincronización de OneDrive|
|:-------|:-----|:------------|:-------|:-------------|:-----|
|Windows 7|Compatible.|Compatible.|No aplicable|No aplicable|Versión preliminar<sup>*</sup>|
|Windows 8.1|Compatible.|Compatible.|No aplicable|No aplicable|Versión preliminar<sup>*</sup>|
|Windows 10|Compatible.|Compatible.|No aplicable|No aplicable|Versión preliminar<sup>*</sup>|
|Windows Phone 10|No compatible|No compatible|Compatible.|Compatible.|No aplicable|
|Android|Compatible.|Compatible.|Compatible.|Compatible.|No aplicable|
|iOS|Compatible.|Compatible.|Compatible.|Compatible.|No aplicable|
|macOS|Versión preliminar pública|Versión preliminar pública|No aplicable|No aplicable|No compatible|
|Linux|No compatible|No compatible|No compatible|No compatible|No compatible|

<sup>*</sup> Más información sobre la [versión preliminar del Cliente de sincronización de OneDrive](https://support.office.com/article/Azure-Active-Directory-conditional-access-with-the-OneDrive-sync-client-on-Windows-028d73d7-4b86-4ee0-8fb7-9a209434b04e).

> [!NOTE]
> Las siguientes recomendaciones se basan en tres niveles diferentes de seguridad y protección para el correo electrónico que se pueden aplicar en función de la granularidad de las necesidades: **base de referencia**, **confidencial** y **extremadamente regulado**. Puede aprender más sobre estos niveles de seguridad y los sistemas operativos de cliente recomendados, a los que hacen referencia estas recomendaciones, en la [introducción a las directivas y configuraciones de seguridad recomendadas](microsoft-365-policies-configurations.md).


## <a name="baseline"></a>Línea de base
En esta sección se ofrecen las recomendaciones sobre el nivel de base de referencia de los datos, la identidad y la protección de dispositivos. Estas recomendaciones deben satisfacer las necesidades de protección predeterminadas de muchas organizaciones.

>[!NOTE]
>Las directivas siguientes son complementarias y se basan unas en las otras. En cada sección se describen solo las adiciones aplicadas a cada nivel.
>

### <a name="conditional-access-policy-settings"></a>Configuración de directiva de acceso condicional

#### <a name="identity-protection"></a>Protección de identidad
Puede ofrecer a los usuarios una experiencia de inicio de sesión único (SSO), como se describe en las secciones anteriores. Solo debe intervenir cuando sea necesario en función de los [eventos de riesgo](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-risk-events).  

* Exigir MFA según el riesgo de inicio de sesión **medio o superior**
* Exigir cambio de contraseña seguro para usuarios de riesgo **alto**

>[!IMPORTANT]
>Para esta recomendación de directiva se exigen la [sincronización de contraseña](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization) y el [restablecimiento de contraseña autoservicio](https://docs.microsoft.com/azure/active-directory/active-directory-passwords).
>

#### <a name="data-loss-prevention"></a>Prevención de pérdida de datos
El objetivo de las directivas de administración de dispositivos y aplicaciones es proteger frente a la pérdida de datos en caso de pérdida o robo de un dispositivo. Para ello, asegúrese de que el acceso a los datos está protegido mediante un PIN, de que los datos del dispositivo están cifrados y de que el dispositivo no está comprometido.

|Recomendación de directiva|Descripción|
|:--------------------|:----------|
|**Exigir la administración de equipos de usuario**|Exija a los usuarios que unan los equipos Windows a un dominio de Active Directory o que los inscriban en la administración con Microsoft Intune o System Center Configuration Manager.|
|**Aplicar la configuración de seguridad a través de objetos de directiva de grupo (GPO) o directivas de Configuration Manager para equipos unidos a dominio**|Implemente directivas que configuren los equipos administrados para habilitar BitLocker, habilite un antivirus y habilite el firewall.|
|**Exigir la administración de dispositivos móviles de usuario**|Exija que los dispositivos de usuario usados para acceder al correo electrónico se administren mediante Intune **o** que se acceda al correo electrónico de empresa únicamente a través de aplicaciones de correo electrónico móviles protegidas mediante directivas de Intune App Protection como Outlook Mobile.|
|**Aplicar una directiva de cumplimiento de dispositivo de Intune en dispositivos administrados**|Aplique una directiva de cumplimiento de dispositivo de Intune para dispositivos móviles corporativos administrados y equipos administrados por Intune que exija: un PIN con una longitud mínima de 6, el cifrado del dispositivo, un dispositivo en buen estado (que no esté descodificado, descifrado y que pase la atestación de estado) y, si está disponible, que exija que los dispositivos sean de riesgo **bajo** según lo determinado por un MTP ajeno como Lookout o SkyCure.|
|**Aplicar una directiva de Intune App Protection para aplicaciones administradas que se ejecutan en dispositivos no administrados**|Aplique una directiva de Intune App Protection para aplicaciones administradas que se ejecutan en dispositivos móviles no administrados personales que exija: un PIN con una longitud mínima de 6, el cifrado del dispositivo y que el dispositivo esté en buen estado (que no esté descodificado, descifrado y que pase la atestación de estado).|

### <a name="user-impact"></a>Impacto en el usuario

Para la mayoría de las organizaciones es importante poder establecer las expectativas del usuario con respecto a cuándo y en qué circunstancias se espera que inicien sesión en Office 365 para acceder al correo electrónico.  

Los usuarios normalmente se benefician del inicio de sesión único (SSO), excepto en las situaciones siguientes:
* Cuando solicitan tokens de autenticación para Exchange Online:
  * Es posible que se pida a los usuarios autenticarse mediante MFA siempre que se detecte un riesgo de inicio de sesión **medio o superior** y aún no hayan efectuado MFA en sus sesiones actuales.  
  * Los usuarios tienen que usar aplicaciones de correo electrónico que admitan el SDK de Intune App Protection o acceder a los mensajes desde dispositivos compatibles con Intune o unidos a un dominio de AD.
* Cuando los usuarios con inicio de sesión de riesgo se han autenticado correctamente mediante MFA, se les pide que cambien la contraseña.

## <a name="sensitive"></a>Confidencial
En esta sección se ofrecen las recomendaciones para el nivel confidencial de los datos, la identidad y la protección de dispositivos. Estas recomendaciones van dirigidas a aquellos clientes que tienen un subconjunto de datos que se debe proteger a niveles superiores o que exige que todos los datos se protejan a estos niveles superiores.

Puede aplicar una mayor protección a todos los conjuntos de datos o a conjuntos concretos en el entorno de Office 365. Por ejemplo, puede aplicar directivas para garantizar que los datos confidenciales solo se compartan entre aplicaciones protegidas para evitar la pérdida de datos. Se recomienda proteger las identidades y los dispositivos que acceden a información confidencial con niveles de seguridad comparables.

### <a name="conditional-access-policy-settings"></a>Configuración de directiva de acceso condicional
#### <a name="identity-protection"></a>Protección de identidad

Puede ofrecer a los usuarios una experiencia de inicio de sesión único (SSO), como se describe en las secciones anteriores. Solo debe intervenir cuando sea necesario en función de los [eventos de riesgo](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-risk-events).   

* Exigir MFA en sesiones de riesgo **bajo o superior**
* Exigir cambio de contraseña seguro para usuarios de riesgo alto

>[!IMPORTANT]
>Para esta recomendación de directiva se exigen la [sincronización de contraseña](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization) y el [restablecimiento de contraseña autoservicio](https://docs.microsoft.com/azure/active-directory/active-directory-passwords).
>

#### <a name="data-loss-prevention"></a>Prevención de pérdida de datos

El objetivo de estas directivas de administración de dispositivos y aplicaciones es proteger frente a la pérdida de datos en caso de pérdida o robo de un dispositivo. Para ello, asegúrese de que el acceso a los datos está protegido mediante un PIN, de que los datos del dispositivo están cifrados y de que el dispositivo no está comprometido.

|Recomendación de directiva|Descripción|
|:--------------------|:----------|
|**Exigir la administración de equipos de usuario**|Exija a los usuarios que unan los equipos a un dominio de Active Directory o inscriban los equipos en la administración con Intune o Configuration Manager y asegúrese de que esos dispositivos son compatibles con las directivas antes de permitir el acceso al correo electrónico.|
|**Aplicar la configuración de seguridad a través de objetos de directiva de grupo (GPO) o directivas de Configuration Manager para equipos unidos a dominio**|Implemente directivas que configuren los equipos administrados para habilitar BitLocker, habilite un antivirus y habilite el firewall.|
|**Exigir la administración de dispositivos móviles de usuario**|Exija que los dispositivos de usuario usados para acceder al correo electrónico se administren mediante Intune **o** que se acceda al correo electrónico de empresa únicamente a través de aplicaciones de correo electrónico móviles protegidas mediante directivas de Intune App Protection como Outlook Mobile.|
|**Aplicar una directiva de cumplimiento de dispositivo de Intune en dispositivos administrados**|Aplique una directiva de cumplimiento de dispositivo de Intune para dispositivos móviles corporativos administrados y equipos administrados por Intune que exija: un PIN con una longitud mínima de 6, el cifrado del dispositivo, un dispositivo en buen estado (que no esté descodificado, descifrado y que pase la atestación de estado) y, si está disponible, que exija que los dispositivos sean de riesgo **bajo** según lo determinado por un MTP ajeno como Lookout o SkyCure.|
|**Aplicar una directiva de Intune App Protection para aplicaciones administradas que se ejecutan en dispositivos no administrados**|Aplique una directiva de Intune App Protection para aplicaciones administradas que se ejecutan en dispositivos móviles no administrados personales que exija: un PIN con una longitud mínima de 6, el cifrado del dispositivo y que el dispositivo esté en buen estado (que no esté descodificado, descifrado y que pase la atestación de estado).|

### <a name="user-impact"></a>Impacto en el usuario
Para la mayoría de las organizaciones es importante poder establecer las expectativas de los usuarios con respecto a cuándo y en qué circunstancias se espera que inicien sesión en el correo electrónico de Office 365.

Los usuarios normalmente se benefician del inicio de sesión único (SSO), excepto en las situaciones siguientes:
* Cuando solicitan tokens de autenticación para Exchange Online:
  * Se pide a los usuarios autenticarse mediante MFA siempre que se detecta un riesgo de inicio de sesión **bajo o superior** y aún no han efectuado MFA en sus sesiones actuales.  
  * Los usuarios tienen que usar aplicaciones de correo electrónico que admitan el SDK de Intune App Protection o acceder a los mensajes desde dispositivos compatibles con Intune o unidos a un dominio de AD.
* Cuando los usuarios con inicio de sesión de riesgo se han autenticado correctamente mediante MFA, se les pide que cambien la contraseña.

## <a name="highly-regulated"></a>Extremadamente regulado
En esta sección se ofrecen las recomendaciones para el nivel extremadamente regulado de los datos, la identidad y la protección de dispositivos. Estas recomendaciones van dirigidas a aquellos clientes que pueden tener una cantidad muy pequeña de datos extremadamente clasificados, un secreto comercial o datos regulados. Microsoft proporciona capacidades para ayudar a las organizaciones a cumplir estos requisitos, incluida protección adicional para identidades y dispositivos.

### <a name="conditional-access-policy-settings"></a>Configuración de directiva de acceso condicional
#### <a name="identity-protection"></a>Protección de identidad

Para el nivel extremadamente regulado, Microsoft recomienda aplicar MFA para todas las sesiones nuevas.
* Exigir MFA para todas las sesiones nuevas
* Exigir cambio de contraseña seguro para usuarios de riesgo **alto**

>[!IMPORTANT]
>Para esta recomendación de directiva se exigen la [sincronización de contraseña](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization) y el [restablecimiento de contraseña autoservicio](https://docs.microsoft.com/azure/active-directory/active-directory-passwords).
>

#### <a name="data-loss-prevention"></a>Prevención de pérdida de datos
El objetivo de estas directivas de administración de dispositivos y aplicaciones es evitar la pérdida de datos en caso de pérdida o robo de un dispositivo. Para ello, asegúrese de que el acceso a los datos está protegido mediante un PIN, de que los datos del dispositivo están cifrados y de que el dispositivo no está comprometido.

Para el nivel extremadamente regulado, se recomienda exigir que las aplicaciones que admitan la directiva de Intune App Protection se ejecuten únicamente en dispositivos compatibles con Intune o unidos a dominio.

|Recomendación de directiva|Descripción|
|:--------------------|:----------|
|**Exigir la administración de equipos de usuario**|Exija a los usuarios que unan los equipos Windows a un dominio de Active Directory **o** que inscriban los equipos en la administración con Intune o Configuration Manager y asegúrese de que esos dispositivos son compatibles con las directivas antes de permitir el acceso al correo electrónico.|
|**Aplicar la configuración de seguridad a través de objetos de directiva de grupo (GPO) o directivas de Configuration Manager para equipos unidos a dominio**|Implemente directivas que configuren los equipos administrados para habilitar BitLocker, habilite un antivirus y habilite el firewall.|
|**Exigir la administración de dispositivos móviles de usuario**|Exija que los dispositivos usados para acceder al correo electrónico y los archivos de Office 365 se administren mediante Intune o que se acceda al correo electrónico de empresa únicamente a través de aplicaciones de correo electrónico móviles protegidas mediante directivas de Intune App Protection como Outlook Mobile.|
|**Aplicar una directiva de cumplimiento de dispositivo de Intune en dispositivos administrados**|Aplique una directiva de cumplimiento de dispositivo de Intune para dispositivos móviles corporativos administrados y equipos administrados por Intune que exija: un PIN con una longitud mínima de 6, el cifrado del dispositivo, un dispositivo en buen estado (que no esté descodificado, descifrado y que pase la atestación de estado) y, si está disponible, que exija que los dispositivos sean de riesgo Bajo según lo determinado por un MTP ajeno como Lookout o SkyCure.|

### <a name="user-impact"></a>Impacto en el usuario
Para la mayoría de las organizaciones es importante poder establecer las expectativas de los usuarios con respecto a cuándo y en qué circunstancias se espera que inicien sesión en archivos de Office 365.

* Los usuarios con configuraciones extremadamente reguladas deben volver a autenticarse con MFA cuando su sesión expira.
* A los usuarios con inicio de sesión de riesgo se les pide que cambien la contraseña después de autenticarse mediante MFA.
* Cuando solicitan tokens de autenticación para Exchange Online:
  * A los usuarios se les pide autenticarse mediante MFA cada vez que inician una sesión nueva.  
  * Los usuarios deben usar aplicaciones de correo electrónico compatibles con el SDK de Intune App Protection
  * Los usuarios deben acceder a los mensajes de correo electrónico desde dispositivos compatibles con Intune o unidos a un dominio de AD.

## <a name="next-steps"></a>Pasos siguientes

[Más información sobre recomendaciones de directivas para proteger el correo electrónico](secure-email-recommended-policies.md)
