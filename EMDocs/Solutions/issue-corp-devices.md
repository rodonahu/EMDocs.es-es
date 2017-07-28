---
title: Administrar los dispositivos propiedad de la empresa con Intune | Microsoft Docs
description: 
keywords: 
author: jeffgilb
manager: angrobe
ms.date: 6/7/2017
ms.topic: solution
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e9e695ec-5608-43bb-bbfb-808b869b1567
ms.reviewer: vlpetros
ms.suite: ems
ms.openlocfilehash: 51e8edb18d68618c147ba5011dc1f047cdb43cac
ms.sourcegitcommit: 0541e4aa400a818551469fe9df8929c25c2dd918
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/25/2017
---
# <a name="manage-company-owned-devices-with-intune"></a>Administrar los dispositivos propiedad de la empresa con Intune

Hay numerosas opciones disponibles para cumplir las expectativas de movilidad de los empleados en las empresas modernas, incluidos programas Bring Your Own Device (BYOD). Aun así, muchas organizaciones quieren tener un control todavía mayor para saber qué dispositivos se usan a la hora de tener acceso a los datos de la empresa. En estos casos, las empresas pueden implementar estrategias Choose Your Own Device (CYOD), según las cuales el departamento de TI proporciona dispositivos móviles administrados a los empleados.

Para que las estrategias CYOD tengan éxito, las empresas deben poder ofrecer diversos dispositivos a fin de que los usuarios puedan elegir. Esto resulta especialmente cierto si la organización implementa CYOD como alternativa a BYOD, porque si a los usuarios no les gusta el dispositivo que se les emita, encontrarán una manera de usar sus dispositivos personales no administrados. Con CYOD, el departamento de TI puede inscribir en la administración solo tipos de dispositivos específicos, reducir los costos de soporte técnico y ayudar a proteger los datos de la empresa desde el mismo instante en que se emite un dispositivo a un empleado.  Los empleados disponen de las opciones de dispositivos móviles que están acostumbrados a usar en la vida privada y no necesitan realizar ningún paso adicional ni llamar al soporte técnico para administrar el dispositivo o para configurar el acceso a los datos de la empresa.  

## <a name="how-can-enterprise-mobility--security-help-you"></a>¿Cómo puede ayudarle Enterprise Mobility + Security?

Puede inscribir dispositivos corporativos o propiedad de la organización para administrarlos con Microsoft Intune de muchas maneras, en función del tipo de dispositivo, cómo se haya adquirido y las necesidades de la organización. También puede instalar la aplicación de Portal de empresa para inscribir y administrar dispositivos corporativos, como [en un escenario BYOD](https://docs.microsoft.com/enterprise-mobility-security/solutions/enable-byod). Intune pueden inscribir los dispositivos iOS de propiedad corporativa directamente en la administración mediante las herramientas de configuración proporcionadas por Apple. Un administrador puede inscribir cualquier tipo de dispositivo mediante el administrador de inscripción de dispositivos. Los dispositivos con un número IMEI también se pueden identificar y etiquetar como de propiedad corporativa para, así, posibilitar escenarios de dispositivos propiedad de la empresa.

Con EMS puede proporcionar funcionalidades y experiencias para crear un área de trabajo productiva que abarque diversos estilos de trabajo y en cualquier lugar. Si los empleados usan dispositivos iOS, MacOS, Android o Windows, Intune puede ayudarle a ofrecer productividad a su personal en todos los dispositivos al tiempo que se protegen los datos de la empresa. Además de la administración total del ciclo de vida de las aplicaciones y de los dispositivos móviles, Intune se integra directamente con Office 365 y con las aplicaciones móviles de Office para proteger fácilmente los datos de la empresa.

### <a name="recommended-solution"></a>Solución recomendada

Con Intune, puede proporcionar fácilmente a los empleados acceso a las aplicaciones, los datos y los recursos de la empresa desde prácticamente cualquier lugar en cualquier dispositivo, al mismo tiempo que ayuda a proteger la información corporativa. La integración directa con Office 365 permite increíbles experiencias de usuario final y proporciona las funcionalidades de prevención de pérdida de datos más completas para aplicaciones móviles de Office y control de acceso a Office 365. Cuando un dispositivo se pierde, lo roban o simplemente ya no se necesita para el trabajo, Intune permite borrar de forma selectiva solo los datos de la empresa en los dispositivos administrados.

>[!Note]
>Intune reconoce los dispositivos como de propiedad *corporativa* cuando se usa uno de los métodos descritos en esta solución para inscribir un dispositivo. Cuando el servicio de Intune reconoce un dispositivo como corporativo, verá **Corporativo** en la columna Propiedad para ese registro del dispositivo en la consola de administrador.

![Opciones en un entorno complejo de dispositivos](..\Solutions\media\enable-byod\management-choices-with-intune.png)

> <sup>Puede descargar esta infografía en https://gallery.technet.microsoft.com/Infographic-Management-3644ae41.</sup>

### <a name="how-to-implement-this-solution"></a>Cómo implementar esta solución
El resto de esta solución se divide en las secciones siguientes, que muestran cómo:
- **Inscribir dispositivos iOS corporativos**. En esta sección se describe cómo usar la integración de Apple Configurator (en un dispositivo Mac) y DEP de Apple para inscribir dispositivos corporativos.
- **Inscribir dispositivos Windows 10 corporativos**. En esta sección se describe cómo inscribir automáticamente en la administración dispositivos Windows 10 cuando están unidos al Azure Active Directory de la empresa.
- **Inscribir dispositivos mediante una cuenta de administrador de inscripción de dispositivos (DEM)**. Obtenga información sobre la manera en que las cuentas de DEM permiten que una sola persona del departamento de TI inscriba en la administración un número de dispositivos superior al predeterminado.
- **Etiquetar dispositivos corporativos con números de identidad de equipo móvil internacional (IMEI)**. En esta sección se describe otra opción para empezar a administrar dispositivos corporativos en el momento de la inscripción mediante la importación de números IMEI que identifican dispositivos corporativos.
- **Asegurarse de que los dispositivos administrados cumplen los requisitos básicos de seguridad**. En esta sección se describe cómo garantizar que los dispositivos usados para tener acceso a los datos y las aplicaciones de la empresa cumplen los requisitos básicos de seguridad.
- **Proporcionar acceso a los recursos de empresa**. Esta sección se muestra cómo TI puede permitir a los usuarios el acceso fácil y seguro a los recursos de la empresa mediante la implementación de perfiles de acceso en los dispositivos administrados, y cómo administrar implementaciones de aplicaciones adquiridas por volumen con Intune.
- **Proteger los datos de la empresa**. En esta sección, puede obtener información sobre cómo proporcionar acceso condicional a los recursos de la empresa, evitar la pérdida de datos y quitar datos y aplicaciones de la empresa en dispositivos que ya no se necesitan para trabajar, que se han perdido o que los han robado.

## <a name="enroll-corporate-owned-ios-devices"></a>Inscribir dispositivos iOS de empresa
Si, como parte de su estrategia de CYOD, ofrece a los usuarios dispositivos iOS para que elijan, puede preconfigurar la inscripción para que el dispositivo se administre con Intune desde el mismo momento en que el usuario lo enciende por primera vez. Intune permite la inscripción mediante el [Programa de inscripción de dispositivos (DEP) de Apple](https://docs.microsoft.com/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) o con la herramienta Apple Configurator en un equipo Mac para la inscripción [directa](https://docs.microsoft.com/intune/deploy-use/ios-direct-enrollment-in-microsoft-intune) o con el [Asistente para la configuración](https://docs.microsoft.com/intune/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune). También puede implementar un perfil de inscripción *de forma inalámbrica* en los dispositivos iOS que se adquieren a través de DEP.

### <a name="setup-assistant-enrollment"></a>Inscripción con el asistente para la configuración
Cuando se usa la [opción de inscripción con el asistente para la configuración de dispositivos iOS](https://docs.microsoft.com/intune/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune), el dispositivo se restablece a sus valores predeterminados de fábrica y se prepara para la configuración final por parte del nuevo usuario del dispositivo. En este método, el administrador debe conectar el dispositivo iOS mediante USB a un equipo Mac que ejecute [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) para preconfigurar la inscripción. Después, los dispositivos se entregan a los usuarios, que ejecutan el proceso del Asistente de configuración. Mediante este proceso se configura el dispositivo con sus credenciales profesionales o educativas y se completa el proceso de inscripción.

### <a name="direct-enrollment"></a>Inscripción directa
La [inscripción directa para dispositivos iOS](https://docs.microsoft.com/intune/deploy-use/ios-direct-enrollment-in-microsoft-intune) crea un archivo compatible con Apple Configurator para su uso durante la preparación del dispositivo. No se restablece la configuración de fábrica del dispositivo inscrito, pero no tiene ninguna afiliación de usuario. En este método, el administrador debe conectar el dispositivo iOS mediante USB a un equipo Mac que ejecute [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) para inscribir el dispositivo.

### <a name="dep-enrollment"></a>Inscripción de DEP
Microsoft Intune puede implementar un perfil de inscripción que inscriba dispositivos iOS adquiridos a través del [Programa de inscripción de dispositivos (DEP)](https://docs.microsoft.com/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) *de forma inalámbrica*. El paquete de inscripción puede incluir opciones del Asistente para la configuración del dispositivo, de modo que cuando un usuario ejecute el Asistente en el dispositivo, el dispositivo se inscriba en Intune para permitir la administración desde el *día 0*.

>[!Important]

>Los usuarios no pueden anular la inscripción de [dispositivos inscritos a través de DEP](https://docs.microsoft.com/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune).

## <a name="enroll-corporate-owned-windows-10-devices"></a>Inscribir dispositivos Windows 10 corporativos
Puede hacer que la inscripción de dispositivos Windows en la administración sea todavía más fácil para los usuarios al habilitar la característica de inscripción automática de Azure AD (Premium). Al hacerlo, los dispositivos se inscribirán de forma automática en la administración con Intune cuando un usuario agregue una cuenta profesional o educativa para registrar su dispositivo propiedad de la empresa cuando se una al Azure AD de su organización.

[Azure Active Directory Join (Azure AD Join) de Windows 10](https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-overview) facilita a los usuarios el proceso de conectarse a la nube de la empresa a través de Azure AD. Desde allí, podrán tener acceso a las aplicaciones y los recursos de la organización desde sus dispositivos Windows. Con la integración de la inscripción automática de dispositivos, estos se administran automáticamente mediante Microsoft Intune.

>[!Tip]

>Para habilitar la inscripción de MDM automática en el directorio de Azure AD Premium desde [Microsoft Azure Portal](https://portal.azure.com), vaya a **Azure Active Directory** > **Movilidad (MDM y MAM)** > **Microsoft Intune**.

Azure AD Join está diseñado para las empresas que usan exclusivamente la nube o que le dan prioridad. Estas organizaciones suelen ser pequeñas y medianas empresas que no tienen una infraestructura local de Active Directory Domain Services (AD DS) de Windows Server. Dicho esto, también las grandes organizaciones pueden usar Azure AD Join para los dispositivos que no se pueden unir de forma tradicional a un dominio (por ejemplo, dispositivos móviles) o para los usuarios que necesiten principalmente tener acceso a Office 365 u otras aplicaciones SaaS de Azure AD. Cuando se realiza la administración de dispositivos con Intune, los administradores de TI pueden administrar dispositivos unidos a Azure AD junto con dispositivos unidos a un dominio de AD DS en la consola de administración de Configuration Manager a través de [MDM híbrida](https://docs.microsoft.com/sccm/mdm/understand/choose-between-standalone-intune-and-hybrid-mobile-device-management#what-is-hybrid-mdm-with-configuration-manager).
Cuando un usuario agrega una cuenta profesional o educativa a un dispositivo Windows 10, el dispositivo se marca automáticamente como "corporativo".

## <a name="enroll-devices-with-a-device-enrollment-manager-dem-account"></a>Inscribir dispositivos con una cuenta de administrador de inscripción de dispositivos (DEM)
Puede usar una sola [cuenta de administrador de inscripción de dispositivos (DEM)](https://docs.microsoft.com/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) de Intune para inscribir un gran número de dispositivos móviles para su organización. Una vez que haya creado una cuenta de DEM, puede usarla para inscribir un máximo de 1000 dispositivos.

Puede usar una cuenta DEM para inscribir solo dispositivos que no use un usuario específico. Estos tipos de dispositivos son buenos para aplicaciones de punto de venta o de utilidad, por ejemplo, pero inadecuados para usuarios que necesitan acceso al correo electrónico o a los recursos de empresa.
- Los usuarios no pueden usar aplicaciones del Programa de Compras por Volumen de Apple (PCV) debido a los requisitos de identificador de Apple por usuario para la administración de aplicaciones.
- Si usa DEM para inscribir dispositivos iOS, no puede usar Apple Configurator o el Programa de inscripción de dispositivos (DEP) de Apple para inscribir dispositivos.

## <a name="tag-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers"></a>Etiquetar dispositivos corporativos con números de identidad de equipo móvil internacional (IMEI)
Microsoft Intune permite que los administradores [importen números de identidad de equipo móvil internacional (IMEI)](https://docs.microsoft.com/intune/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers) de plataformas de dispositivos móviles para ayudar a identificar dispositivos móviles corporativos.

Puede importar hasta 5000 números IMEI mediante un archivo .CSV con un formato especial o bien mediante la entrada manual de hasta 15 números IMEI de dispositivo de cada vez desde la consola de administración de Intune. Cuando se inscribe en Intune un dispositivo con número IMEI, normalmente cuando un usuario instala la aplicación de portal de empresa y completa el proceso de inscripción, el dispositivo se etiqueta como corporativo y aparece como inscrito en el grupo Dispositivos IMEI.

## <a name="make-sure-that-managed-devices-comply-with-basic-security-requirements"></a>Asegurarse de que los dispositivos administrados cumplen con los requisitos básicos de seguridad
Independientemente de si se inscribe un dispositivo iOS, Android o Windows 10, el departamento de TI debe garantizar que los dispositivos usados para tener acceso a los datos y las aplicaciones de la empresa cumplen con los requisitos básicos de seguridad. Estas reglas pueden incluir el uso de un PIN para acceder a los dispositivos y el cifrado de los datos almacenados en ellos. A un conjunto de tales reglas se le denomina una [directiva de cumplimiento](https://docs.microsoft.com/intune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune).

Cuando [se crea y se implementa una directiva de cumplimiento](https://docs.microsoft.com/intune/deploy-use/create-a-device-compliance-policy-in-microsoft-intune) en un usuario, se comprobarán todos los dispositivos administrados por Intune para ver si cumplen los requisitos básicos de seguridad definidos como parte de la directiva CYOD o BYOD. Después de evaluado el cumplimiento con la directiva de este dispositivo, se notificará de su estado al servicio Intune. En algunos casos, es posible que los usuarios deban corregir la configuración no compatible, como el uso de un PIN o cifrado del dispositivo, pero otras veces la aplicación de portal de empresa solo notificará al usuario acerca de los problemas de cumplimiento encontrados.

## <a name="provide-access-to-company-resources"></a>Proporcionar acceso a los recursos de empresa

En esta sección se muestra cómo TI puede permitir a los usuarios el acceso fácil y seguro a los recursos de la empresa mediante la implementación de perfiles de acceso en los dispositivos administrados y cómo administrar aplicaciones adquiridas por volumen.

### <a name="provide-access-to-company-data"></a>Proporcionar acceso a los datos de la empresa
Lo primero que la mayoría de los empleados quiere tener en su dispositivo móvil es acceso a los documentos y el correo electrónico de la empresa. Además, esperan poder configurarlo sin tener que realizar pasos complejos ni llamar al departamento de soporte técnico. Microsoft Intune facilita la [creación e implementación de la configuración del correo electrónico](https://docs.microsoft.com/intune/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune) para las aplicaciones de correo electrónico nativas que están instaladas previamente en dispositivos móviles que usa la organización.

> [!NOTE]
> Intune admite la configuración de perfil de correo electrónico de Android for Work para las aplicaciones de correo electrónico Gmail y Nine Work que se encuentran en Google Play Store.

Además del correo electrónico, EMS también le ayuda a controlar el acceso y proteger datos locales de la empresa a los que se accede desde fuera de los límites de seguridad tradicionales de la empresa. Los perfiles de correo electrónico, [Wi-Fi](https://docs.microsoft.com/intune/deploy-use/wi-fi-connections-in-microsoft-intune) y [VPN](https://docs.microsoft.com/intune/deploy-use/vpn-connections-in-microsoft-intune#create-a-vpn-profile) de Microsoft Intune funcionan de manera conjunta para ayudar a los usuarios a obtener acceso a los archivos y recursos que necesitan para trabajar, estén donde estén. También se puede acceder a los servicios y aplicaciones web de la empresa hospedados de forma local y protegerlos de forma segura mediante el proxy de aplicación de Azure Active Directory y el acceso condicional.

### <a name="add-apps-for-enrolled-devices"></a>Agregar aplicaciones a los dispositivos inscritos
Es fácil agregar aplicaciones para dispositivos inscritos con Intune, pero antes de implementar o administrar una aplicación, debe [agregarla a Intune](https://docs.microsoft.com/intune/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune) mediante el Editor de software de Intune. Use el Editor de software de Intune para configurar las propiedades de la aplicación y, si procede, cargarla en su espacio de almacenamiento en la nube.

Con Intune, puede [implementar o administrar los siguientes tipos de aplicaciones](https://docs.microsoft.com/intune/deploy-use/add-apps) en dispositivos inscritos:
- **Instalador de software**. Entre estos tipos de aplicaciones se incluyen el instalador de software de Windows (.exe o .msi), el paquete de aplicación de Android (.apk), el paquete de aplicación de iOS (.ipa), el paquete de aplicación de Windows Phone (.xap, .appx y .appxbundle), el paquete de aplicación de Windows (.appx, .appxbundle) y Windows Installer mediante archivos MDM (.msi). Todos los tipos de aplicación del instalador de software se cargan en el [espacio de almacenamiento en nube](https://docs.microsoft.com/intune/deploy-use/add-apps#cloud-storage-space).
- **Vínculo externo**. Este tipo de implementación de aplicaciones proporciona un vínculo externo (dirección URL) que permite a los usuarios descargar una aplicación desde una tienda de aplicaciones o un vínculo a una aplicación basada en Web que se ejecuta desde el explorador web. Las aplicaciones basadas en vínculos externos no se almacenan en el espacio de almacenamiento en nube de Intune.
- **Aplicación iOS administrada desde la tienda de aplicaciones**. Puede usar aplicaciones iOS administradas para administrar e implementar aplicaciones iOS gratuitas desde la tienda de aplicaciones. También puede usar aplicaciones iOS administradas para asociar directivas de administración de aplicaciones móviles a aplicaciones compatibles y revisar su estado en la consola del administrador. Las aplicaciones iOS administradas no se almacenan en el espacio de almacenamiento en nube de Intune.

### <a name="manage-volume-purchased-apps"></a>Administrar aplicaciones adquiridas por volumen
Puede [ofrecer fácilmente aplicaciones de la tienda a los dispositivos administrados](https://docs.microsoft.com/intune/deploy-use/deploy-apps-in-microsoft-intune) e incluso aplicaciones específicas a dispositivos no administrados mediante el sitio web del portal de empresa, pero Intune también le permite administrar e implementar aplicaciones que haya adquirido por volumen en la tienda de aplicaciones de iOS y en la Tienda Windows para empresas. Esto ayuda a reducir la carga administrativa relacionada con el seguimiento de las aplicaciones adquiridas por volumen.

> [!TIP]
> Puede [configurar fácilmente el inicio de sesión único (SSO) con Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) para permitir a los usuarios iniciar sesión en aplicaciones con el nombre de usuario de dominio y la contraseña que utilizan en local. Además, puede [proporcionar acceso basado en Internet a aplicaciones web hospedadas en local](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started) mediante el Proxy de aplicación de Azure Active Directory.

Con Intune es fácil importar la información de las licencias por volumen del almacén de aplicaciones, realizar el seguimiento del número de licencias que se han utilizado y evitar que los usuarios instalen más copias de la aplicación de las propias.

-   [Administrar aplicaciones adquiridas por volumen para dispositivos iOS](https://docs.microsoft.com/intune/deploy-use/manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune). Puede comprar varias licencias para aplicaciones de iOS a través del [Programa de Compras por Volumen de Apple para empresas](http://www.apple.com/business/vpp/). Esto implica configurar una cuenta de PCV de Apple en el sitio web de Apple y cargar el token de PCV de Apple en Intune. De este modo, puede sincronizar la información de compras por volumen con Intune y hacer el seguimiento del uso de aplicaciones compradas por volumen.

-   [Tienda Windows para empresas](https://docs.microsoft.com/intune/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune). En la [Tienda Windows para empresas](https://www.microsoft.com/business-store) puede buscar y comprar aplicaciones para su organización, tanto sueltas como en lote. Si conecta la tienda a Microsoft Intune, puede administrar las aplicaciones adquiridas por volumen desde el portal de Intune.

## <a name="protect-company-data"></a>Proteger los datos de la empresa

Intune protege los datos empresariales mediante varias capas de tecnología. En la capa de identidad, el acceso condicional protege el acceso a los servicios, puesto que solo permite el acceso desde dispositivos administrados que cumplan los requisitos. En la capa de aplicaciones cliente, las directivas de protección de aplicaciones protegen frente a la pérdida de datos, ya que evitan que estos se muevan a aplicaciones no protegidas o a ubicaciones de almacenamiento y los borran cuando se pierde o se roba un dispositivo.

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
