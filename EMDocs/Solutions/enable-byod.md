---
title: "Habilitación de BYOD con Intune | Microsoft Docs"
description: 
keywords: 
author: jeffgilb
manager: angrobe
ms.date: 2/10/2017
ms.topic: solution
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6d31eebe-81d2-4c6b-bfec-fbd536096dda
ms.reviewer: vlpetros
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b4edb16e4ef00b7376af800ab542f42c0e530197
ms.openlocfilehash: 9defe28a74bc3e53f6ae5dc33b33396e47247265


---
# <a name="enable-byod-with-intune"></a>Habilitación de BYOD con Intune
Admitir la transformación digital ofrece nuevos desafíos para TI, ya que se esfuerzan por proteger los datos de la empresa al permitir que los empleados sean productivos en el panorama móvil cada vez más complejo de hoy en día. A medida que las organizaciones se desplazan a la nube, los empleados esperan ser productivos en cualquier lugar con una experiencia que coincida con las experiencias de sus clientes en varios dispositivos.

![Opciones en un entorno complejo de dispositivos](..\Solutions\media\enable-byod\management-choices-with-intune.png)

> <sup>Puede descargar esta infografía en https://gallery.technet.microsoft.com/Infographic-Management-3644ae41.</sup>

Algunos de estos dispositivos son administrados por la empresa y pueden estar reservados a un usuario específico o pueden compartirse entre varios empleados. También tendrá dispositivos que son administrados por los propios empleados. Estos dispositivos personales puede ser el iPhone o PC personales que utilizan para trabajar todos los días o un dispositivo auxiliar que utilizan para conectarse de vez en cuando, como el iPad de su hija o un equipo familiar.

Además de los dispositivos, también está cambiando el lugar donde los usuarios realizan su trabajo. Las personas ya no trabajan exclusivamente en un área de trabajo o una oficina tradicional. La fuerza de trabajo moderna ahora trabaja desde casa, en cafés, en los emplazamientos de los clientes, en la carretera e incluso en el aire. Por este motivo, los programas Bring Your Own Device (BYOD) se han convertido en algo muy habitual en el área de trabajo moderna. Depende de TI sacar de alguna forma provecho de los beneficios y las oportunidades de aumentar la satisfacción de los empleados y de reducir los costes, al tiempo que se conserva el control de datos de la empresa.

Los programas BYOD satisfactorios logran un mayor control y una mayor seguridad sin tener que imponer procesos complejos ni cambiar la manera de trabajar de las personas. Una gran experiencia para los usuarios finales significa que tienen una mayor probabilidad de utilizar las soluciones protegidas que se les proporcionan y menos posibilidades de crear soluciones alternativas que están completamente fuera de control para realizar el trabajo.

## <a name="how-can-enterprise-mobility--security-ems-help-you"></a>¿Cómo puede ayudarle Enterprise Mobility + Security (EMS)?

Con EMS puede proporcionar funcionalidades y experiencias para crear un área de trabajo productiva que abarque diversos estilos de trabajo y en cualquier lugar. Si los empleados usan dispositivos iOS, MacOS, Android o Windows, Microsoft Intune, parte de EMS, puede ayudarle a ofrecer productividad a su personal en todos los dispositivos al tiempo que se protegen los datos de la empresa. Intune ofrece funcionalidades MAM y MDM, que permiten proteger los datos corporativos con o sin administración de dispositivos. Además de la administración total del ciclo de vida de las aplicaciones y de los dispositivos móviles, Intune se integra directamente con Office 365 y con las aplicaciones móviles de Office.

### <a name="recommended-solution"></a>Solución recomendada

Con Intune, puede proporcionar fácilmente a los empleados acceso a las aplicaciones, los datos y los recursos de la empresa desde prácticamente cualquier lugar en cualquier dispositivo, al mismo tiempo que ayuda a proteger la información corporativa. La integración directa con Office 365 permite increíbles experiencias de usuario final y proporciona las funcionalidades de prevención de pérdida de datos más completas para aplicaciones móviles de Office y control de acceso a Office 365. Cuando un dispositivo se pierde, lo roban o ya no es necesario para el trabajo, Intune permite borrar de forma selectiva solo los datos de la empresa en los dispositivos BYOD.

Este es un breve vídeo donde usuarios reales y de profesionales de TI comentan sus necesidades y desafíos al equilibrar la productividad y la protección en un mundo principalmente móvil y en la nube:
<iframe width="675" height="480" src="https://www.youtube.com/embed/pgAmKnluwVw" frameborder="0" allowfullscreen></iframe>

### <a name="how-to-implement-this-solution"></a>Cómo implementar esta solución

El resto de esta solución se divide en las secciones siguientes, que muestran cómo:

-   **Inscribir dispositivos y comprobar su conformidad**. En esta sección se describe cómo permitir a los usuarios inscribir los dispositivos (iOS, MacOS, Android, Android for Work y Windows) en la administración con Intune e implementar sus directivas y asegurarse de que son compatibles con los requisitos básicos de seguridad.

-   **Proporcionar acceso a los recursos de empresa**. Esta sección se muestra cómo TI puede permitir a los usuarios el acceso fácil y seguro a los recursos de la empresa mediante la implementación de perfiles de acceso en los dispositivos administrados, y cómo administrar implementaciones de aplicaciones adquiridas por volumen con Intune.  

-   **Proteger los datos de la empresa**. En esta sección, puede obtener información sobre cómo proporcionar acceso condicional a los recursos de la empresa, evitar la pérdida de datos y quitar datos y aplicaciones de la empresa en dispositivos que ya no se necesitan para trabajar, que se han perdido o que los han robado.

## <a name="enroll-devices-and-check-for-compliance"></a>**Inscribir dispositivos y comprobar su conformidad**

En esta sección se describe cómo permitir a los usuarios inscribir dispositivos en la administración con Intune y asegurar de que sus dispositivos son compatibles con los requisitos básicos de seguridad.

### <a name="enable-users-to-enroll-their-personal-devices-into-management"></a>Permitir a los usuarios inscribir sus dispositivos personales en la administración

La inscripción de dispositivos y equipos en la administración con Intune garantiza que se puedan aplicar todas las directivas y perfiles de acceso que ha configurado para los dispositivos administrados. Para poder inscribir dispositivos, primero tendrá que [preparar el servicio de Intune](https://docs.microsoft.com/intune/deploy-use/get-ready-to-enroll-devices-in-microsoft-intune) mediante la asignación de licencias a usuarios, la configuración de la entidad de administración de dispositivos móviles y el cumplimiento de los diversos requisitos de inscripción de los distintos tipos de dispositivos que quiera administrar. Mientras lo esté haciendo, probablemente también deberá [personalizar el portal de empresa](https://docs.microsoft.com/intune/deploy-use/get-ready-to-enroll-devices-in-microsoft-intune#configure-the-intune-company-portal) con información de soporte técnico y personalización de marca específica de la empresa para proporcionar una inscripción de confianza y una experiencia de soporte técnico a los usuarios.

Después de preparar el servicio de Intune, el proceso de inscripción de dispositivos en la administración es sencillo, pero es ligeramente diferente para cada tipo de dispositivo:

-   **Dispositivos iOS y Mac**. Debe obtener un certificado de Apple Push Notification Service (APNs) para inscribir dispositivos iPad, iPhone o de MacOS. Después de [cargar el certificado de APNs en Intune](https://docs.microsoft.com/en-us/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune), los usuarios pueden [inscribir dispositivos iOS](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-ios) mediante la aplicación de portal de empresa y usar el sitio web de portal de empresa para [inscribir dispositivos MacOS](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-mac-os-x).

-   **Dispositivos Android**. No es necesario que haga nada para preparar el servicio de Intune para la inscripción de dispositivos Android. Los usuarios pueden [inscribir sus dispositivos Android](https://docs.microsoft.com/intune/deploy-use/set-up-android-management-with-microsoft-intune) en la administración mediante la aplicación de portal de empresa que está disponible en Google Play.

-   **Android for Work**. Para [configurar Android for Work](https://docs.microsoft.com/intune/deploy-use/set-up-android-for-work) para Android 5.0 Lollipop y dispositivos con versiones posteriores que permiten que Intune administre los perfiles de trabajo, su organización debe registrarse en Android for Work con Google y después configurar Android for Work en el nodo ADMIN de la consola de administración de Intune.

-   **Equipos y dispositivos Windows Phone**. Debe [establecer un alias DNS para el servidor de inscripción](https://docs.microsoft.com/intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune) para facilitar la inscripción de dispositivos de Windows. Si no quiere hacerlo, puede [inscribir dispositivos Windows](https://docs.microsoft.com/intune/enduser/enroll-your-w10-phone-or-w10-pc-windows) mediante la adición de una cuenta profesional o educativa.

> [!TIP]
> Puede facilitar aún más la inscripción de dispositivos Windows a los usuarios al [habilitar la característica de inscripción automática](https://docs.microsoft.com/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment) de Azure AD (Premium). Al hacerlo, los dispositivos se inscribirán de forma automática en la administración con Intune cuando un usuario agregue una cuenta profesional o educativa para registrar su dispositivo personal o un dispositivo propiedad de la empresa se una al Azure AD de su organización.

### <a name="make-sure-that-managed-devices-comply-with-basic-security-requirements"></a>Asegurarse de que los dispositivos administrados cumplen con los requisitos básicos de seguridad

Después de que los usuarios inscriban sus dispositivos en la administración, TI debe garantizar que los dispositivos usados para acceder a los datos y aplicaciones de la empresa cumplen con los requisitos básicos de seguridad. Estas reglas pueden incluir el uso de un PIN para acceder a los dispositivos y el cifrado de los datos almacenados en ellos. A un conjunto de estas reglas se le denomina [directiva de cumplimiento](https://docs.microsoft.com/intune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune).

Cuando se [crea y se implementa una directiva de cumplimiento](https://docs.microsoft.com/intune/deploy-use/create-a-device-compliance-policy-in-microsoft-intune) en un usuario, se comprobarán todos los dispositivos administrados por Intune para ver si cumplen con los requisitos básicos de seguridad definidos como parte de la directiva BYOD. Después de evaluado el cumplimiento con la directiva de este dispositivo, se notificará de su estado al servicio Intune. En algunos casos, es posible que los usuarios deban corregir la configuración no compatible, como el uso de un PIN o cifrado del dispositivo, pero otras veces la aplicación de portal de empresa solo notificará al usuario acerca de los problemas de cumplimiento encontrados.

## <a name="provide-access-to-company-resources"></a>Proporcionar acceso a los recursos de empresa

En esta sección se muestra cómo TI puede permitir a los usuarios el acceso fácil y seguro a los recursos de la empresa mediante la implementación de perfiles de acceso en los dispositivos administrados y cómo administrar aplicaciones adquiridas por volumen.

### <a name="provide-access-to-company-data"></a>Proporcionar acceso a los datos de la empresa
Lo primero que la mayoría de los empleados quiere tener en su dispositivo móvil es acceso a los documentos y el correo electrónico de la empresa. Además, esperan poder configurarlo sin tener que realizar pasos complejos ni llamar al departamento de soporte técnico. Microsoft Intune facilita la [creación e implementación de la configuración del correo electrónico](https://docs.microsoft.com/intune/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune) para las aplicaciones de correo electrónico nativas que están instaladas previamente en dispositivos móviles que usa la organización.

> [!NOTE]
> Intune admite la configuración de perfil de correo electrónico de Android for Work para las aplicaciones de correo electrónico Gmail y Nine Work que se encuentran en Google Play Store.

Además del correo electrónico, EMS también le ayuda a controlar el acceso y proteger datos locales de la empresa a los que se accede desde fuera de los límites de seguridad tradicionales de la empresa. Los perfiles de correo electrónico, [Wi-Fi](https://docs.microsoft.com/intune/deploy-use/wi-fi-connections-in-microsoft-intune) y [VPN](https://docs.microsoft.com/intune/deploy-use/vpn-connections-in-microsoft-intune#create-a-vpn-profile) de Microsoft Intune funcionan de manera conjunta para ayudar a los usuarios a obtener acceso a los archivos y recursos que necesitan para trabajar, estén donde estén. También se puede acceder a los servicios y aplicaciones web de la empresa hospedados de forma local y protegerlos de forma segura mediante el proxy de aplicación de Azure Active Directory y el acceso condicional.

### <a name="manage-volume-purchased-apps"></a>Administrar aplicaciones adquiridas por volumen
Puede [ofrecer fácilmente aplicaciones de la tienda a los dispositivos administrados](https://docs.microsoft.com/intune/deploy-use/deploy-apps-in-microsoft-intune) e incluso aplicaciones específicas a dispositivos no administrados mediante el sitio web del portal de empresa, pero Intune también le permite administrar e implementar aplicaciones que haya adquirido por volumen en la tienda de aplicaciones de iOS y en la Tienda Windows para empresas. Esto ayuda a reducir la carga administrativa relacionada con el seguimiento de las aplicaciones adquiridas por volumen.

> [!TIP]
> Puede [configurar fácilmente el inicio de sesión único (SSO) con Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) para permitir a los usuarios iniciar sesión en aplicaciones con el nombre de usuario de dominio y la contraseña que utilizan en local. Además, puede [proporcionar acceso basado en Internet a aplicaciones web hospedadas en local](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started) mediante el Proxy de aplicación de Azure Active Directory.

Con Intune es fácil importar la información de las licencias por volumen del almacén de aplicaciones, realizar el seguimiento del número de licencias que se han utilizado y evitar que los usuarios instalen más copias de la aplicación de las propias.

-   [Administrar aplicaciones adquiridas por volumen para dispositivos iOS](https://docs.microsoft.com/intune/deploy-use/manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune). Puede comprar varias licencias para aplicaciones de iOS a través del [Programa de Compras por Volumen de Apple para empresas](http://www.apple.com/business/vpp/). Esto implica configurar una cuenta de PCV de Apple en el sitio web de Apple y cargar el token de PCV de Apple en Intune. De este modo, puede sincronizar la información de compras por volumen con Intune y hacer el seguimiento del uso de aplicaciones compradas por volumen.

-   [Tienda Windows para empresas](https://docs.microsoft.com/intune/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune). En la [Tienda Windows para empresas](https://www.microsoft.com/business-store) puede buscar y comprar aplicaciones para su organización, tanto sueltas como en lote. Si conecta la tienda a Microsoft Intune, puede administrar las aplicaciones adquiridas por volumen desde el portal de Intune.

## <a name="protect-company-data"></a>Proteger los datos de la empresa

Intune protege los datos empresariales mediante varias capas de tecnología. En la capa de identidad, el acceso condicional protege el acceso a los servicios, puesto que solo permite el acceso desde dispositivos administrados que cumplan los requisitos. En la capa de aplicaciones cliente, la administración de aplicaciones móviles (MAM) protege frente a la pérdida de datos; para ello, evita que estos se muevan a aplicaciones no protegidas o a ubicaciones de almacenamiento y los borra cuando se pierde o se roba un dispositivo.

### <a name="enforce-conditional-access-to-company-resources"></a>Aplicar el acceso condicional a los recursos de la empresa

Puede utilizar directivas de cumplimiento junto con [directivas de acceso condicional](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune) para comprobar si los dispositivos cumplen con los requisitos básicos de seguridad que requiere la directiva BYOD. Si un dispositivo no cumple con la directiva, se aplican las reglas de acceso condicional y se deniega el acceso hasta que el dispositivo esté configurado para satisfacer los requisitos de la directiva. Esto garantiza que solo los dispositivos administrados y compatibles pueden tener acceso a los datos de la empresa desde servicios como Exchange ([Exchange local](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-exchange-onpremises-with-microsoft-intune) o [Exchange Online](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune)), SharePoint Online, Skype Empresarial Online y otros.

> [!IMPORTANT]
> Las directivas de acceso condicional no funcionarán si no se ha aplicado ninguna directiva de cumplimiento para validar el cumplimiento.

### <a name="prevent-data-loss-of-company-data-with-application-protection-policies"></a>Evitar la pérdida de datos de la empresa con directivas de protección de aplicaciones

Las directivas de protección de aplicaciones de Intune ofrecen la flexibilidad para administrar el modo de acceso a los datos con o sin la inscripción de dispositivos. La capacidad de proteger los datos de la empresa con o sin la inscripción de dispositivos permite habilitar escenarios de protección de datos para que la empresa pueda acceder de manera segura a los datos, incluso cuando un usuario es reacio a inscribir sus dispositivos en administración.

Puede usar [directivas de protección de aplicaciones de Intune](https://docs.microsoft.com/intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune) para ayudar a proteger los datos de la empresa a los que acceden los dispositivos iOS y Android de los usuarios. Al implementar estas directivas de nivel de aplicación, se controla la manera en que los empleados usan y comparten los datos de la empresa si el mismo dispositivo no está administrado por Intune.

Utilice las [directivas de Windows Information Protection (WIP)](https://docs.microsoft.com/intune/deploy-use/microsoft-intune-policy-reference#windows-configuration-policies) para hacer lo mismo en los dispositivos de Windows 10 administrados. Estas directivas funcionan sin interferir con la experiencia del empleado y no requieren cambios en el entorno de red u otras aplicaciones.

### <a name="wipe-company-data-while-leaving-personal-data-intact"></a>Borrar datos de la empresa mientras se dejan intactos los datos personales

Cuando un dispositivo ya no es necesario para el trabajo, se va a reasignar o simplemente se ha perdido, debe poder eliminar los datos y las aplicaciones de la empresa que contenga. Para ello, puede aprovechar las funcionalidades de borrado completo y de borrado selectivo de Intune. Los usuarios también pueden borrar remotamente los dispositivos de propiedad personal que hayan inscrito en la administración desde el Portal de empresa de Intune.

En lugar de realizar un [borrado completo](https://docs.microsoft.com/intune/deploy-use/use-remote-wipe-to-help-protect-data-using-microsoft-intune#full-wipe) que restaure un dispositivo a su configuración predeterminada de fábrica y quite los datos y la configuración del usuario, puede usar la funcionalidad de [borrado selectivo](https://docs.microsoft.com/intune/deploy-use/use-remote-wipe-to-help-protect-data-using-microsoft-intune#selective-wipe) para quitar solo los datos de la empresa que contenga el dispositivo y conservar intactos los datos personales del usuario.

Cuando se inicie, el dispositivo empezará de inmediato el proceso de borrado selectivo para quitarlo de la administración. Una vez que se haya completado el proceso, se habrán eliminado todos los datos de la empresa y el nombre del dispositivo ya no aparecerá en la consola de administrador de Intune, con lo que se completa el ciclo de vida de administración del dispositivo.

### <a name="learn-more"></a>Obtener más información
[Introducción al uso de Enterprise Mobility + Security](https://docs.microsoft.com/enterprise-mobility/solutions/ems-get-started)

[Microsoft Enterprise Mobility](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility)



<!--HONumber=Feb17_HO2-->


