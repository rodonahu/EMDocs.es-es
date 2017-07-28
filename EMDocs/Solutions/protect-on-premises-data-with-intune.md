---
title: Proteger datos locales con Microsoft Intune | Microsoft Docs
description: "Con Enterprise Mobility + Security (EMS) podrá mantener la productividad de sus empleados con sus aplicaciones y dispositivos favoritos, al mismo tiempo que protege los datos locales de la empresa."
keywords: 
author: jeffgilb
manager: angrobe
ms.date: 6/7/2017
ms.topic: solution
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ebf7be63-4ac2-4158-9772-58f15416ccb7
ms.reviewer: vlpetros
ms.suite: ems
ms.custom: active-directory
ms.openlocfilehash: 7c835faa3fe56fdc9cf42f0569fefe1acfa22eda
ms.sourcegitcommit: 0541e4aa400a818551469fe9df8929c25c2dd918
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/25/2017
---
# <a name="protect-on-premises-company-data-with-intune"></a>Proteger los datos locales de la empresa con Intune
Los firewalls por sí mismos ya no pueden proporcionar un límite de seguridad corporativa adecuado. Hoy en día, los límites de seguridad deben incluir al usuario final y su forma de acceso, uso y uso compartido los datos de la empresa. Al trabajar, ya sea desde sus smartphones, tabletas o portátiles, los trabajadores de la información esperan un acceso sin dificultades a los recursos desde cualquier lugar, en cualquier dispositivo y siempre que lo necesiten. Habilitar las funcionalidades de acceso y protección para los usuarios puede ser un desafío para los administradores de TI, que también deben asegurarse de que los datos de la empresa estén protegidos. Con Enterprise Mobility + Security (EMS) podrá mantener la productividad de sus empleados con sus aplicaciones y dispositivos favoritos, al mismo tiempo que protege los datos locales de la empresa. Siga leyendo para saber cómo.

## <a name="how-can-enterprise-mobility--security-ems-help-you"></a>¿Cómo puede ayudarle Enterprise Mobility + Security (EMS)?
Enterprise Mobility + Security (EMS) es la única solución en la nube integral que protege de forma nativa los datos corporativos en el propio dispositivo y más allá con cuatro niveles de protección en las identidades, los dispositivos, las aplicaciones y los datos. Con EMS, sus empleados obtendrán acceso seguro y sin problemas al correo electrónico y a los documentos corporativos, mientras que el departamento de TI está seguro de que los datos de la empresa están protegidos.

## <a name="recommended-solution"></a>Solución recomendada
Mediante Microsoft Intune, puede configurar de forma remota directivas de perfil de acceso a recursos para las cuentas de correo electrónico de aprovisionamiento automático, perfiles de acceso (como la configuración de Wi-Fi o VPN) y proporcionar perfiles de certificado que aseguran que los dispositivos aceptan e instalan solo configuraciones de confianza.

Además de proporcionar acceso, el acceso condicional de Intune a servidores locales de Microsoft Exchange 2010 (o versiones posteriores) garantiza que solo los dispositivos administrados y compatibles puedan acceder al correo electrónico de la empresa. Al expandir la administración más allá de los propios dispositivos, también puede usar Cisco Identity Services Engine (ISE) de Intune, y pronto otros asociados, para restringir el acceso a la red de la empresa solo a dispositivos que están inscritos en la administración con Intune y cumplen con las directivas de la empresa. Incluso puede proporcionar acceso seguro a aplicaciones locales sin VPN, redes perimetrales o proxy inversos al aprovechar el proxy de aplicación de Azure Active Directory. Lo mejor de todo es que puede realizar todo esto sin instalar ni mantener ninguna infraestructura local adicional y sin abrir el firewall de la empresa para redirigir el tráfico a través de él.

Este es un breve vídeo con una rápida introducción sobre cómo el acceso condicional con EMS proporciona una experiencia satisfactoria para que los empleados tengan acceso seguro a los datos de la empresa desde dispositivos iOS, Android y Windows:

<iframe width="675" height="480" src="https://youtube.com/embed/fvCT7Y3nlAY" frameborder="0" allowfullscreen></iframe>

### <a name="how-to-implement-this-solution"></a>Cómo implementar esta solución
El resto de esta solución se divide en las secciones siguientes que muestran cómo proteger los datos de la empresa de Office 365 con Intune:
- **Inscribir dispositivos móviles y PC Windows en la administración**. En esta sección se describe cómo inscribir dispositivos (iOS, Android, Android for Work y PC Windows) en la administración para que pueda configurar el acceso seguro a recursos locales con Intune.
- **Acceder al correo de la empresa y protegerlo**. En esta sección, se muestra cómo Intune puede configurar de forma automática el correo electrónico de la aplicación nativa para los usuarios y cómo proporcionar acceso condicional a Exchange Server local.
- **Proporcionar acceso a otros recursos locales de la empresa**. En esta sección, se describe cómo proporcionar a los empleados acceso seguro a recursos de red locales mediante Wi-Fi, VPN o el proxy de aplicación de Azure Active Directory.
- **Usar certificados para proteger el acceso a los recursos de la empresa**. En esta sección, obtendrá ayuda para crear e implementar un certificado PKCS #12 (.PFX) o de protocolo de inscripción de certificados simple (SCEP) para proteger el acceso de usuarios a los recursos de la empresa.

## <a name="enroll-mobile-devices-and-windows-pcs-into-management"></a>Inscribir dispositivos móviles y PC Windows en la administración
La inscripción de dispositivos y equipos en la administración con Intune garantiza que se puedan aplicar todas las directivas y perfiles de acceso que ha configurado para los dispositivos administrados. Para poder inscribir dispositivos, primero tendrá que [preparar el servicio de Intune](https://docs.microsoft.com/intune/deploy-use/get-ready-to-enroll-devices-in-microsoft-intune) mediante la asignación de licencias a usuarios, la configuración de la entidad de administración de dispositivos móviles y el cumplimiento de los diversos requisitos de inscripción de los distintos tipos de dispositivos que quiera administrar. Mientras lo esté haciendo, probablemente también deberá [personalizar el portal de empresa](https://docs.microsoft.com/intune/deploy-use/get-ready-to-enroll-devices-in-microsoft-intune#configure-the-intune-company-portal) con información de soporte técnico y personalización de marca específica de la empresa para proporcionar una inscripción de confianza y una experiencia de soporte técnico a los usuarios.

Después de preparar el servicio de Intune, el proceso de inscripción de dispositivos en la administración es sencillo, pero es ligeramente diferente para cada tipo de dispositivo:

-   **Dispositivos iOS y Mac**. Debe obtener un certificado de Apple Push Notification Service (APNs) para inscribir iPad, iPhone o dispositivos Mac OS X. Después de [cargar el certificado de APNs en Intune](https://docs.microsoft.com/en-us/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune), los usuarios pueden [inscribir dispositivos iOS](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-ios) mediante la aplicación de portal de empresa y usar el sitio web de portal de empresa para [inscribir dispositivos Mac OS X](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-mac-os-x).
-   **Dispositivos Android**. No es necesario que haga nada para preparar el servicio de Intune para la inscripción de dispositivos Android. Los usuarios pueden [inscribir sus dispositivos Android](https://docs.microsoft.com/intune/deploy-use/set-up-android-management-with-microsoft-intune) en la administración mediante la aplicación de portal de empresa que está disponible en Google Play.
-   **Android for Work**. Para [configurar Android for Work](https://docs.microsoft.com/intune/deploy-use/set-up-android-for-work) para Android 5.0 Lollipop y dispositivos con versiones posteriores que permiten que Intune administre los perfiles de trabajo, su organización debe registrarse en Android for Work con Google y después configurar Android for Work en el nodo ADMIN de la consola de administración de Intune.
-   **Equipos y dispositivos Windows Phone**. Debe [establecer un alias DNS para el servidor de inscripción](https://docs.microsoft.com/intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune) para facilitar la inscripción de dispositivos de Windows. Si no quiere hacerlo, puede [inscribir dispositivos Windows](https://docs.microsoft.com/intune/enduser/enroll-your-w10-phone-or-w10-pc-windows) mediante la adición de una cuenta profesional o educativa.

> [!TIP]
> Puede facilitar aún más la inscripción de dispositivos Windows a los usuarios al [habilitar la característica de inscripción automática](https://docs.microsoft.com/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment) de Azure AD (Premium). Al hacerlo, los dispositivos se inscribirán de forma automática en la administración con Intune cuando un usuario agregue una cuenta profesional o educativa para registrar su dispositivo personal o un dispositivo propiedad de la empresa se una al Azure AD de su organización.

## <a name="access-and-protect-company-email"></a>Acceder al correo de la empresa y protegerlo
Lo primero que la mayoría de los empleados quiere tener en su dispositivo móvil es acceso a los documentos y el correo electrónico de la empresa. Además, esperan poder configurarlo sin tener que realizar pasos complejos ni llamar al departamento de soporte técnico. Microsoft Intune facilita la creación e implementación de la configuración del correo electrónico para las aplicaciones de correo electrónico nativas que están instaladas previamente en dispositivos móviles que usa la organización.

Mediante directivas de acceso condicional de Intune para Exchange local, puede estar seguro de que solo los dispositivos administrados (y que cumplan las directivas) registrados en Azure Active Directory pueden acceder a la información de Exchange Server local de la empresa.

### <a name="configure-exchange-email-settings-for-native-email-apps-on-managed-devices"></a>Configurar el correo electrónico de Exchange para las aplicaciones de correo electrónico nativas en dispositivos administrados
Puede [configurar fácilmente la aplicación de correo electrónico nativa](https://docs.microsoft.com/intune/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune) en los siguientes dispositivos al crear directivas de configuración de perfil de correo electrónico e implementarlas a los usuarios:

-   Windows Phone 8 (y versiones posteriores).
-   Windows 10 para escritorios y Windows 10 Mobile
-   iOS 8.0 (y versiones posteriores)
-   Android (Samsung Knox Standard 4.0 y versiones posteriores o Android for Work)

> [!NOTE]
> Intune admite la configuración de perfil de correo electrónico de Android for Work para las aplicaciones de correo electrónico Gmail y Nine Work que se encuentran en Google Play Store.

### <a name="protect-access-to-your-on-premises-exchange-server"></a>Proteger el acceso a Exchange Server local
Además de usar Intune para proporcionar opciones de configuración de correo electrónico para conectarse a servidores de Exchange locales, también puede usar Intune para [controlar el acceso de correo electrónico a un Exchange Server local](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-exchange-onpremises-with-microsoft-intune) (2010 o versiones posteriores) a través de Intune [Exchange Connector local](https://docs.microsoft.com/intune/deploy-use/intune-on-premises-exchange-connector).

Si no se inscribe un dispositivo o no es compatible con las directivas de la empresa, al usuario se le presenta información sobre cómo inscribir su dispositivo en la administración o cómo solucionar problemas de cumplimiento que bloquean el acceso al correo electrónico.

> [!TIP]
> Eche un vistazo a estos [escenarios de ejemplo](https://docs.microsoft.com/intune/deploy-use/restrict-email-access-example-scenarios#all-ios-devices-that-access-exchange-on-premises-must-be-managed-by-intune) para obtener más ideas sobre cómo usar el acceso condicional de Intune para proteger el correo electrónico de Exchange de su empresa.

También puede [configurar una directiva de acceso condicional para Exchange local](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-exchange-onpremises-with-microsoft-intune#configure-a-conditional-access-policy) para los siguientes tipos de dispositivo que use su organización:

-   Windows Phone (8.1 y versiones posteriores)
-   iOS 8.0 (y versiones posteriores)
-   Android (4.0 o versiones posteriores y Samsung Knox Standard 4.0)
-   Android for Work (actualmente, solo se admite para los perfiles de correo electrónico de las aplicaciones Gmail y Nine Work)
-   La aplicación Correo en PC Windows administrados

> [!NOTE]
> Las directivas de acceso condicional de Intune solo funcionan con las aplicaciones de correo electrónico nativas de los dispositivos, excepto las aplicaciones de correo electrónico Gmail y Nine Work en el perfil de trabajo de Android for Work. Actualmente, la aplicación Microsoft Outlook para Android e iOS no es compatible, pero se planea que sea compatible en el futuro.

## <a name="provide-access-to-other-on-premises-company-resources"></a>Proporcionar acceso a otros recursos locales de la empresa
Además del correo electrónico, EMS también le ayuda a controlar el acceso y proteger datos locales de la empresa a los que se accede desde fuera de los límites de seguridad tradicionales de la empresa. Los perfiles de correo electrónico, Wi-Fi y VPN de Microsoft Intune funcionan de manera conjunta para ayudar a los usuarios a obtener acceso a los archivos y recursos que necesitan para trabajar, estén donde estén. También se puede acceder a los servicios y aplicaciones web de la empresa hospedados de forma local y protegerlos de forma segura mediante el proxy de aplicación de Azure Active Directory y el acceso condicional.

### <a name="deploy-wi-fi-settings-to-managed-devices"></a>Implementar configuración de Wi-Fi para dispositivos administrados
Las directivas de configuración de Wi-Fi de Intune le facilitan la [implementación de la configuración de red inalámbrica a los usuarios](https://docs.microsoft.com/intune/deploy-use/wi-fi-connections-in-microsoft-intune). Estas opciones facilitan a los usuarios conectarse a la red corporativa sin configurar de forma manual las opciones de Wi-Fi en cualquiera de los dispositivos admitidos siguientes:

-   Android 4.0 (y versiones posteriores, Samsung KNOX Standard y Android for Work)<sup>1</sup>
-   iOS 8.0 (y versiones posteriores)<sup>1</sup>
-   Mac OS X 10.9 (y versiones posteriores)<sup>1</sup>
-   Dispositivos Windows (Windows 8.1 y PC posteriores, Windows Phone 8.1 o Windows 10 Mobile y versiones posteriores)<sup>2</sup>

> <sup>1</sup>Puede usar una directiva de configuración de Wi-Fi de Intune integrada.

> <sup>2</sup>Puede [importar un perfil de configuración .xml de Wi-Fi exportado previamente](https://docs.microsoft.com/intune/deploy-use/wi-fi-connections-in-microsoft-intune#export-or-import-a-wi-fi-configuration-profile-for-windows-devices).

### <a name="deploy-vpn-settings-to-managed-devices"></a>Implementar configuración de VPN para dispositivos administrados
Las conexiones VPN se usan cuando los usuarios necesitan conectarse de forma remota a los recursos de la empresa desde sus dispositivos móviles. Con Intune, puede [crear e implementar perfiles de configuración de VPN](https://docs.microsoft.com/intune/deploy-use/vpn-connections-in-microsoft-intune#create-a-vpn-profile) que permitan a los usuarios tener acceso de forma fácil y segura a los recursos de la red corporativa sin configurar de forma manual la información del método de autenticación o del servidor VPN.

Puede configurar VPN para los diferentes [tipos de conexión VPN compatibles con Intune](https://docs.microsoft.com/intune/deploy-use/vpn-connections-in-microsoft-intune#vpn-connection-types) en los siguientes tipos de dispositivos:

-   Android 4.0 (y versiones posteriores, Samsung KNOX Standard y Android for Work)
-   iOS 8.0 (y versiones posteriores)
-   Mac OS X 10.9 (y versiones posteriores)
-   Dispositivos Windows (Windows 8.1 y PC posteriores, Windows Phone 8.1 y Windows 10 Mobile y versiones posteriores)

### <a name="protect-network-access"></a>Proteger el acceso a redes
De la misma forma que permite el acceso a información de Exchange de la empresa solo a dispositivos administrados y compatibles, puede usar las directivas de red de [Cisco Identity Services Engine (ISE)](http://www.cisco.com/c/en/us/td/docs/security/ise/2-1/admin_guide/b_ise_admin_guide_21/b_ise_admin_guide_20_chapter_00.html) para proteger el acceso a su entorno de red. Cisco ISE es un sistema de control de acceso a redes basado en directivas que puede implementarse en infraestructuras empresariales compatibles con 802.1X cableado, inalámbrico y VPN.

En lugar de configurar en la consola de administración de Intune, el acceso del dispositivo a redes administradas de Cisco ISE se configura en el servidor de Cisco ISE. Solo tiene que [conceder permisos al servidor de Cisco ISE para tener acceso a su inquilino de Intune](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-networks) y después usar directivas de Cisco ISE para permitir el acceso a su entorno de red solo a los dispositivos administrados y compatibles.

> [!IMPORTANT]
> Se necesitan [licencias de Cisco ISE](http://www.cisco.com/c/en/us/td/docs/security/ise/2-1/admin_guide/b_ise_admin_guide_21/b_ise_admin_guide_20_chapter_0110.html), que no se incluyen con EMS, para aprovechar esta protección.

También puede habilitar el inicio de sesión único (SSO) y el acceso condicional al acceso remoto seguro para aplicaciones web hospedadas de forma local mediante el proxy de aplicación de Azure AD. El proxy de aplicación de Azure AD facilita a los usuarios tener acceso a aplicaciones web hospedadas de forma local, como sitios de SharePoint, Outlook Web Access u otras aplicaciones web de LOB, sin necesidad de una VPN. También se pueden proteger las conexiones a API web para admitir diferentes dispositivos y aplicaciones hospedados tras una puerta de enlace de Escritorio remoto.

[Configurar el proxy de aplicación de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-enable) es fácil. Solo tiene que habilitar la característica de Azure AD (Basic o Premium), instalar un pequeño servicio de Windows Server denominado conector dentro de la red y luego publicar aplicaciones en él. No hay que abrir ningún puerto de firewall de entrada ni poner nada en una red perimetral. Una vez configurado, el acceso a las aplicaciones web locales se proporciona mediante el inicio de sesión único en Azure AD. [Las reglas de acceso condicional](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-conditional-access), como requerir la autenticación multifactor o bloquear el acceso cuando los empleados no están en el trabajo, proporcionan medidas de seguridad adicionales

## <a name="use-certificates-to-secure-company-resource-access"></a>Usar certificados para proteger el acceso a los recursos de la empresa
Si proporciona a los usuarios acceso a los recursos de la empresa a través de VPN, Wi-Fi o perfiles de correo electrónico, tiene la opción de [protegerlo con un certificado](https://docs.microsoft.com/intune/deploy-use/configure-intune-certificate-profiles) instalado en el dispositivo de cada usuario en vez de depender de un nombre de usuario y contraseña simple para la autenticación.

Puede crear e implementar un perfil de certificado **PKCS #12 (.PFX)** o de **protocolo de inscripción de certificados simple (SCEP)** para que lo usen los dispositivos que solicitan certificados de autenticación en estas plataformas de dispositivo:

-   iOS 8.0 (y versiones posteriores)
-   Mac OS X 10.9 (y versiones posteriores)
-   Android 4.0 (y versiones posteriores y Android for Work)
-   Windows 8.1 (y versiones posteriores)
-   Windows Phone 8.1 (y versiones posteriores)
-   Windows 10 para escritorios y Windows 10 Mobile y versiones posteriores

Aunque necesita una entidad de certificación empresarial (CA) para realizar cualquier autenticación basada en certificados para su empresa, hay otros requisitos previos que se deben cumplir antes de usar cualquier certificado SCEP o .PFX para proteger el acceso a los recursos de la empresa.

-   Para poder usar Intune para crear e implementar perfiles de certificado SCEP, primero debe [configurar la infraestructura de certificado para SCEP](https://docs.microsoft.com/intune/deploy-use/configure-certificate-infrastructure-for-scep). Este paso requiere que configure varios servidores locales, incluida una entidad de certificación empresarial (CA), un servidor de inscripción de dispositivos de red (NDES) y los servidores de Microsoft Intune Certificate Connector.
-   Para [usar perfiles de certificado .PFX](https://docs.microsoft.com/intune/deploy-use/configure-certificate-infrastructure-for-pfx) (certificados de dispositivo móvil de confianza) además de la entidad de certificación empresarial, necesita Intune Certificate Connector (puede instalarse en la entidad de certificación). NDES no es necesario.

> [!NOTE]
> Es opcional usar un servidor de proxy de aplicación web (WAP) con los dos certificados SCEP y .PFX para permitir que los dispositivos reciban y renueven certificados mediante una conexión a Internet.

Al [implementar perfiles de certificado](https://docs.microsoft.com/intune/deploy-use/configure-intune-certificate-profiles) en usuarios, el certificado de la entidad de certificación de confianza se instala en su dispositivo. Después, el dispositivo usa el perfil de certificado SCEP o .PFX para crear una solicitud de certificado por sí mismo. Cuando se complete la solicitud de certificado, puede usar certificados para autenticar directivas de configuración de Wi-Fi, VPN y del perfil de correo electrónico; para ello, seleccione la opción de método de autenticación de directiva de certificados (en lugar del nombre de usuario y la contraseña).

### <a name="learn-more"></a>Obtener más información

[Introducción al uso de Enterprise Mobility + Security](https://docs.microsoft.com/enterprise-mobility/solutions/ems-get-started)

[Microsoft Enterprise Mobility](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility)
