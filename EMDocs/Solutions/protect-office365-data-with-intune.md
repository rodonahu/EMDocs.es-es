---
title: Proteger datos de empresariales de Office 365 | Microsoft Docs
description: "Juntos, EMS y Office 365 ofrecen una solución completa de productividad móvil administrada que equipa a los usuarios con el estándar de oro de la productividad y al departamento de TI con controles de datos totalmente integrados."
keywords: 
author: jeffgilb
manager: swadhwa
ms.date: 1/23/2017
ms.topic: solution
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cc0d2e1f-9c34-4dcb-ac1f-2f355e9ebb7e
ms.reviewer: vlpetros
ms.suite: ems
ms.translationtype: Human Translation
ms.sourcegitcommit: 5d9a4bd18660a573b2dd76c0263b89ecf5ae4610
ms.openlocfilehash: d7e15962a95135dbb16cb41e2643c602b87039cf
ms.contentlocale: es-es
ms.lasthandoff: 05/29/2017


---

# <a name="protect-office-365-company-data-with-intune"></a>Proteger los datos de la empresa de Office 365 con Intune
Lo primero que la mayoría de los empleados quiere tener en su dispositivo móvil es acceso a los documentos y el correo electrónico de la empresa. Además, esperan poder configurarlo sin tener que realizar pasos complejos ni llamar al departamento de soporte técnico. Por otro lado, al departamento de TI le interesa proteger los datos corporativos independientemente de donde estén, pero ahorrándose el quebradero de cabeza de mantener una infraestructura local de gran tamaño. Con Enterprise Mobility + Security (EMS) podrá mantener la productividad de sus empleados con sus aplicaciones favoritas y dispositivos, al mismo tiempo que protege los datos de la empresa. Siga leyendo para saber cómo.

## <a name="how-can-enterprise-mobility--security-ems-help-you"></a>¿Cómo puede ayudarle Enterprise Mobility + Security (EMS)?
EMS es la única solución que está diseñada para proteger de forma nativa las aplicaciones, los archivos y el correo electrónico de Microsoft Office en todos los dispositivos que los usuarios llevan al trabajo. En segundo plano, EMS permite proporcionar fácilmente a los empleados con movilidad un correo electrónico seguro, para lo que proporciona cuatro niveles de protección en las identidades, los dispositivos, las aplicaciones y los datos. Con EMS, sus empleados tendrán un acceso seguro y sin problemas al correo electrónico y los documentos de la empresa, así como a experiencias de productividad y correo electrónico familiar con aplicaciones de Office Mobile, como Outlook, Word, Excel, PowerPoint y OneDrive.

Office 365 está diseñado para los empleados que buscan flexibilidad para llevarse el trabajo adondequiera que vayan, sin sacrificar la experiencia de usuario. Juntos, EMS y Office 365 ofrecen una solución completa de productividad móvil administrada que equipa a los usuarios con el estándar de oro de la productividad y al departamento de TI con controles de datos totalmente integrados.

### <a name="recommended-solution"></a>Solución recomendada
Con Intune, puede proporcionar fácilmente a los empleados acceso a las aplicaciones, los datos y los recursos de la empresa desde prácticamente cualquier lugar en cualquier dispositivo, al mismo tiempo que ayuda a proteger la información corporativa. Intune también es una manera de proteger los datos de la empresa más moderna y más rentable que las soluciones locales más tradicionales, además de ser más fácil. Con el uso de Intune para proteger los datos de Office 365, no hay necesidad de instalar y mantener infraestructuras locales ni de abrir el firewall de la empresa para enrutar el tráfico a través de él.

Este es un breve vídeo con una rápida introducción a la manera en que Intune y Office 365 funcionan juntos para proporcionar una experiencia satisfactoria a fin de que los empleados tengan acceso seguro a los datos de la empresa desde dispositivos iOS, Android y Windows:

<iframe width="675" height="480" src="https://www.youtube.com/embed/To9zfl6-Z6Y" frameborder="0" allowfullscreen></iframe>

### <a name="how-to-implement-this-solution"></a>Cómo implementar esta solución
El resto de esta solución se divide en las secciones siguientes que muestran cómo proteger los datos de la empresa de Office 365 con Intune:
- **Inscribir dispositivos móviles y PC Windows en la administración**. En esta sección, se describe cómo inscribir dispositivos (iOS, Android, Android for Work y PC Windows) en la administración con Intune, de modo que pueda implementar directivas en ellos que protejan los datos de la empresa de Office 365.
- **Proteger el acceso a servicios de Office 365**. En esta sección, puede obtener información sobre las directivas de cumplimiento de Intune y cómo administrar el acceso condicional a los servicios Exchange Online y SharePoint Online de Office 365.
- **Proteger los datos de la empresa**. En esta sección, se muestra cómo usar las directivas de protección de aplicaciones para dispositivos Android e iOS, y también cómo aprovechar las directivas de Windows Information Protection (WIP) para proteger los datos de aplicaciones de la empresa en equipos con Windows 10 administrados como dispositivos mediante Intune.
- **Borrar datos de la empresa de forma selectiva**. En esta sección, puede obtener información sobre cómo quitar datos y aplicaciones de la empresa de dispositivos que ya no se necesitan para trabajar, que se han perdido o que han robado.


## <a name="enroll-mobile-devices-and-windows-pcs-into-management"></a>Inscribir dispositivos móviles y PC Windows en la administración
La inscripción de dispositivos y equipos en la administración con Intune garantiza que se apliquen todas las directivas y perfiles de acceso que se han configurado para los dispositivos administrados. Para poder inscribir dispositivos, primero tendrá que [preparar el servicio de Intune](https://docs.microsoft.com/intune/deploy-use/get-ready-to-enroll-devices-in-microsoft-intune) mediante la asignación de licencias a usuarios, la configuración de la entidad de administración de dispositivos móviles y el cumplimiento de los diversos requisitos de inscripción de los distintos tipos de dispositivos que quiera administrar. Mientras lo esté haciendo, probablemente también deberá [personalizar el portal de empresa](https://docs.microsoft.com/intune/deploy-use/get-ready-to-enroll-devices-in-microsoft-intune#configure-the-intune-company-portal) con información de soporte técnico y personalización de marca específica de la empresa para proporcionar una inscripción de confianza y una experiencia de soporte técnico a los usuarios.

Después de preparar el servicio de Intune, el proceso de inscripción de dispositivos en la administración es bastante sencillo, pero es ligeramente diferente para cada tipo de dispositivo:
- **Dispositivos iOS y Mac**. Debe obtener un certificado de Apple Push Notification Service (APNs) para inscribir iPad, iPhone o dispositivos Mac OS X. Después de [cargar el certificado de APNs en Intune](https://docs.microsoft.com/en-us/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune), puede [inscribir dispositivos iOS](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-ios) mediante la aplicación de portal de empresa y usar el sitio web de portal de empresa para [inscribir dispositivos Mac OS X](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-mac-os-x).
- **Dispositivos Android**. No es necesario que haga nada para preparar el servicio de Intune para la inscripción de dispositivos Android. Los usuarios pueden [inscribir sus dispositivos Android](https://docs.microsoft.com/intune/deploy-use/set-up-android-management-with-microsoft-intune) en la administración mediante la aplicación de portal de empresa que está disponible en Google Play.
-   **Android for Work**. Para [configurar Android for Work](https://docs.microsoft.com/intune/deploy-use/set-up-android-for-work) para Android 5.0 Lollipop y dispositivos con versiones posteriores que permiten que Intune administre los perfiles de trabajo, su organización debe registrarse en Android for Work con Google y después configurar Android for Work en el nodo ADMIN de la consola de administración de Intune.
- **Equipos y dispositivos Windows Phone**. Debe [establecer un alias DNS para el servidor de inscripción](https://docs.microsoft.com/en-us/intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune) para facilitar la inscripción de dispositivos de Windows. Si no quiere hacerlo, puede [inscribir dispositivos Windows](https://docs.microsoft.com/intune/enduser/enroll-your-w10-phone-or-w10-pc-windows) mediante la adición de una cuenta profesional o educativa.

> [!TIP]
> Puede facilitar aún más la inscripción de dispositivos Windows a los usuarios al [habilitar la característica de inscripción automática](https://docs.microsoft.com/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment) de Azure AD (Premium). Al hacerlo, los dispositivos se inscribirán de forma automática en la administración con Intune cuando un usuario agregue una cuenta profesional o educativa para registrar su dispositivo personal o un dispositivo propiedad de la empresa se una al Azure AD de su organización.

## <a name="secure-access-to-office-365-services"></a>Proteger el acceso a servicios de Office 365
Los usuarios esperan tener acceso a todos los archivos y el correo electrónico de la empresa al usar aplicaciones móviles de Office 365, pero debe asegurarse de que solo los dispositivos de confianza se conecten a los recursos de empresa. Para ello, puede usar directivas de acceso condicional de Intune a fin de asegurarse de que los empleados accedan a los servicios en la nube de Office 365 únicamente desde dispositivos administrados que cumplan las directivas.

Para que las directivas de acceso condicional funcionen, debe definir primero una [directiva de cumplimiento de dispositivos de Intune](https://docs.microsoft.com/intune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune). Estos tipos de directivas de Intune comprueban los dispositivos, no solo cuando se inscriben por primera vez sino de manera periódica a partir de ese momento, para asegurarse de que los valores de configuración de los dispositivos son correctos. De este modo, se asegura fácilmente de que solo pueden acceder a los recursos de empresa los dispositivos que cumplen los requisitos de seguridad. Basta con que defina los requisitos que hacen que un dispositivo sea compatible (por ejemplo, que solicite una contraseña para desbloquear, que permita o deniegue las contraseñas sencillas, que la contraseña tenga una longitud mínima, que no tenga jailbreak, etc.). Para ello, cree una directiva de cumplimiento de dispositivos de Intune y, después, impleméntela en los usuarios.

> [!IMPORTANT]
> Las directivas de acceso condicional no funcionarán si no se ha aplicado ninguna directiva de cumplimiento para validar el cumplimiento.

Las [directivas de acceso condicional](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune) se pueden usar para proteger el acceso a servicios de Office 365, como Dynamics CRM Online<sup>1</sup>, Exchange Online<sup>2</sup>, SharePoint Online<sup>2</sup> y Skype Empresarial Online<sup>1</sup>. En los ejemplos siguientes, se configurarán directivas de acceso condicional para Exchange Online y SharePoint Online.  

> <sup>1</sup> Solo iOS y Android.

> <sup>2</sup> Dispositivos iOS, Android y Windows.

### <a name="secure-access-to-exchange-online"></a>Proteger el acceso a Exchange Online
Con Intune, el correo electrónico de Exchange Online de la empresa está protegido en función de las directivas de cumplimiento y de acceso condicional que establezca. Por ejemplo, puede [restringir el acceso al correo electrónico de Exchange Online](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune) a los dispositivos que no usen una contraseña segura, que no tengan jailbreak y que no estén cifrados.

Una vez que haya configurado directivas de acceso condicional para acceder a Exchange Online, esto es lo que sucederá cuando un usuario intente consultar el correo electrónico en un dispositivo que no esté administrado mediante Intune:
1. El usuario intenta leer el correo electrónico de la empresa de Exchange Online mediante la aplicación de correo electrónico nativo en un dispositivo Android no administrado. Se deniega el acceso al correo electrónico porque el dispositivo no se administra mediante Intune y, por lo tanto, no es compatible con la directiva de cumplimiento.
2. El único correo electrónico que el usuario puede ver es el procedente del servicio de Intune, que le indica que el dispositivo no es compatible con las directivas de empresa y que debe inscribirlo para poder acceder al correo electrónico.
3. Una vez que se haya inscrito el dispositivo y se haya evaluado como compatible con las directivas de empresa, se restaurará el acceso total al correo electrónico de la empresa.

![Imágenes en las que se muestra el funcionamiento del acceso condicional con Exchange Online.](..\Solutions\media\protect-office365-data-with-intune\protect-office365-data-with-intune-fig1.png)

### <a name="secure-access-to-sharepoint-online"></a>Proteger el acceso a SharePoint Online
Intune también puede [proteger fácilmente el acceso a archivos de SharePoint Online](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune) con el acceso condicional. Al igual que al proteger el acceso al correo electrónico, debe configurar dos directivas que es necesario cumplir para permitir el acceso: una directiva de cumplimiento de dispositivos para asegurarse de que las directivas de empresa se siguen en el dispositivo y una directiva de acceso condicional que defina las condiciones que deben cumplirse para acceder al servicio.

Cuando un usuario intenta usar un dispositivo no administrado para conectarse al servicio de SharePoint Online protegido mediante directivas de acceso condicional de Intune, sucede lo siguiente:
1.    Se le deniega el acceso al usuario a los recursos de SharePoint Online y se le muestra un mensaje en el que se le indica que debe reforzar la seguridad y se le proporcionan vínculos para inscribir sus dispositivos en la administración de Intune.
2.    Mediante los vínculos proporcionados en el mensaje de acceso denegado, el usuario inscribe el dispositivo.
3.    Una vez que se haya inscrito el dispositivo y se haya evaluado como compatible con las directivas de empresa, se restaurará el acceso total a los datos de SharePoint Online de la empresa.

![Imágenes en las que se muestra el funcionamiento del acceso condicional con SharePoint Online.](..\Solutions\media\protect-office365-data-with-intune\protect-office365-data-with-intune-fig2.png)

## <a name="protect-company-data"></a>Proteger los datos de la empresa
Probablemente ya sabe que la mayoría de los empleados usan sus dispositivos móviles para cuestiones personales y laborales. Especialmente ahora que ha aumentado el número de dispositivos propiedad de los empleados que se usan para el trabajo, existe un riesgo mayor de pérdidas accidentales de datos a través de aplicaciones y servicios que están fuera de su control, como el correo electrónico, las redes sociales y la nube pública. Por ejemplo, cuando un empleado envía las imágenes de ingeniería más recientes desde su cuenta de correo electrónico personal, copia y pega la información del producto en un tweet o guarda un informe de ventas en curso en su almacenamiento en la nube pública. Por eso, el reto es mantener la productividad de empleados, al mismo tiempo que se hace todo lo posible por evitar las pérdidas de datos de la empresa deliberadas e involuntarias.

Aunque las directivas de acceso condicional le permiten asegurarse de que solo los usuarios y los dispositivos compatibles pueden acceder al correo electrónico, siempre queda la cuestión de proteger los correos electrónicos en sí mismos junto con los archivos adjuntos. ¿Cómo puede impedir que ese contenido se copie, se mueva, se guarde en una ubicación diferente o se comparta con otros usuarios? Intune resuelve este problema mediante el uso de directivas de administración de aplicaciones móviles (MAM) para dispositivos iOS y Android y directivas de Windows Information Protection (WIP) para dispositivos móviles y equipos con Windows 10.  

### <a name="mam-for-managed-ios-and-android-mobile-devices"></a>MAM para dispositivos móviles iOS y Android administrados
Puede usar directivas de administración de aplicaciones móviles (MAM) de Intune para ayudar a proteger los datos de la empresa a los que accedan los dispositivos iOS y Android de los usuarios. Al implementar estas directivas de nivel de aplicación, puede controlar la manera en que los empleados usan y comparten los datos de la empresa.

> [!TIP]
> Las directivas de MAM de Intune se pueden usar independientemente de cualquier solución de administración de dispositivos móviles (MDM), siempre y cuando al usuario se le haya asignado una licencia de Intune. Esto significa que puede proteger los datos de la empresa tanto si inscribe los dispositivos en la administración de Intune como si no lo hace, o incluso si el dispositivo está administrado mediante un servicio de MDM que no sea de Microsoft.

Como administrador, debe [configurar las opciones de la directiva de aplicación de MAM de Intune desde el portal de administración de Azure](https://docs.microsoft.com/intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune). Los dos tipos de opciones de configuración incluidas en las directivas de MAM son la *reubicación de datos* y el *acceso*. Las directivas de reubicación de datos definen la manera en que se pueden usar los datos desde una aplicación protegida. Por ejemplo, puede impedir el uso de “Guardar como” o funciones como cortar, copiar y pegar. La configuración de la directiva de acceso determina el nivel de seguridad del dispositivo que considera necesario para que los empleados usen la aplicación. Con esta configuración, puede requerir un PIN de aplicación adicional o incluso impedir que la aplicación se ejecute en dispositivos con jailbreak o rooting.

En la captura de pantalla siguiente se muestran algunas maneras de proteger una aplicación mediante directivas de MAM de Intune. En este ejemplo, se requiere un PIN para acceder a la aplicación (configuración de acceso) y, para proteger los datos de la empresa, se deniega la función de pegar la información de la empresa en aplicaciones no administradas (configuración de reubicación de datos):

1.    La primera vez que se inicia la aplicación administrada (en este ejemplo, Yammer para iOS), se le pide al usuario que cree un PIN para acceder a la aplicación. Después, tendrá que especificar el PIN cada vez que inicie la aplicación.
2.    El usuario puede copiar datos de la empresa, como conversaciones de Yammer, y pegarlos en otras aplicaciones administradas.
3.    Pero cuando el usuario intenta pegar ese contenido en un mensaje de texto (o en otra aplicación no administrada), la función de pegar no estará disponible.  

![Imágenes en las que se muestra el funcionamiento de las directivas de MAM.](..\Solutions\media\protect-office365-data-with-intune\protect-office365-data-with-intune-fig3.png)

### <a name="windows-information-protection-wip-for-managed-windows-10-pcs-and-mobile-devices"></a>Windows Information Protection (WIP) para dispositivos móviles y equipos con Windows 10 administrados
Las directivas de WIP de Intune ayudan a protegerse frente a posibles pérdidas de datos en los dispositivos con Windows 10 administrados. Lo mejor de todo es que estas directivas funcionan sin interferir con la experiencia del empleado y no requieren cambios en el entorno de red u otras aplicaciones.

Así es como funciona: los datos de la empresa se cifran automáticamente después de que se carguen en un dispositivo de Windows administrado desde un origen de la empresa o después de que un empleado los marque como profesionales (en vez de personales). Cuando los datos empresariales se escriben en un disco, WIP usa el Sistema de cifrado de archivos (EFS) proporcionado por Windows para protegerlos y asociarlos con la identidad de la empresa. Cuando cree una directiva de WIP de Intune, debe definir una lista de aplicaciones de confianza que pueden acceder a los datos de la empresa y modificarlos. Después, la funcionalidad de AppLocker funciona en segundo plano con el sistema operativo para controlar qué aplicaciones se pueden ejecutar, cómo se accede a los datos de la empresa y cómo se comparten. No es necesario modificar las aplicaciones permitidas para que puedan abrir los datos de la empresa, ya que están incluidas en la lista que permite que Windows les conceda acceso a los datos de la empresa.

> [!TIP]
> Cuando las aplicaciones y los datos de la empresa están protegidos mediante directivas de WIP, los usuarios finales verán “Administrado” junto a los nombres de las aplicaciones permitidas en el menú Inicio de sus dispositivos. Los accesos directos de las aplicaciones y los archivos guardados también incluirán el icono de maletín de WIP, además del icono de aplicación estándar.
<img src="..\Solutions\media\protect-office365-data-with-intune\protect-office365-data-with-intune-fig4.png" alt="Image showing how WIP policies affect the Start Menu and files" style="width:376px;height:112x;">

Las [opciones de las directivas de configuración de WIP](https://docs.microsoft.com/intune/deploy-use/microsoft-intune-policy-reference#windows-configuration-policies) permiten establecer distintos niveles de control y auditoría desde la consola de administrador de Intune. Los niveles de protección de datos van desde **Silencio** (solo se registra la actividad de WIP) hasta **Bloquear** (se impide que los usuarios compartan contenido de aplicaciones protegidas). **Reemplazar** es un valor intermedio que permite que los usuarios compartan datos de la empresa con aplicaciones no protegidas con una advertencia, pero también registra estas acciones para su posterior revisión.

A continuación se indica la manera en que las directivas de WIP de Intune pueden ayudar a proteger los datos de la empresa en dispositivos con Windows 10 administrados:
1.    Se crea una directiva de WIP y se implementa en los usuarios desde la consola de administrador de Intune.
2.    En este ejemplo, se usa la información de AppLocker para Microsoft Word para agregar Word 2016 a la lista de aplicaciones permitidas, se establece el nivel de restricción de directiva en Reemplazar y se implementa la directiva en los usuarios.
3.    Un usuario intenta pegar datos de la compañía, copiados de un documento de Word 2016 protegido, en una instancia nueva y sin proteger del Bloc de notas. Se le pide de inmediato que confirme si este cambio en la clasificación (de profesional a personal) es planeado y se le informa de que se realizará un seguimiento de la acción.

![Imágenes en las que se muestra el funcionamiento de las directivas de WIP.](..\Solutions\media\protect-office365-data-with-intune\protect-office365-data-with-intune-fig5.png)

## <a name="selectively-wipe-company-data"></a>Borrar datos de la empresa de forma selectiva
Cuando un dispositivo ya no es necesario para el trabajo, se va a reasignar o simplemente se ha perdido, debe poder eliminar los datos y las aplicaciones de la empresa que contenga. Para ello, puede aprovechar las funcionalidades de borrado completo y de borrado selectivo de Intune. Los usuarios también pueden borrar remotamente los dispositivos de propiedad personal que hayan inscrito en la administración desde el Portal de empresa de Intune.

En lugar de realizar un [borrado completo](https://docs.microsoft.com/intune/deploy-use/use-remote-wipe-to-help-protect-data-using-microsoft-intune#full-wipe) que restaure un dispositivo a su configuración predeterminada de fábrica y quite los datos y la configuración del usuario, puede usar la funcionalidad de [borrado selectivo](https://docs.microsoft.com/intune/deploy-use/use-remote-wipe-to-help-protect-data-using-microsoft-intune#selective-wipe) para quitar solo los datos de la empresa que contenga el dispositivo y conservar intactos los datos personales del usuario.

La realización del borrado selectivo de un dispositivo es tan fácil como hacer clic con el botón derecho en el nombre de un dispositivo, seleccionar **Retirar/Eliminar datos** y, después, **Borrar el dispositivo de forma selectiva**:

![Imagen de las opciones de borrado selectivo en la consola de Intune.](..\Solutions\media\protect-office365-data-with-intune\protect-office365-data-with-intune-fig6.png)

Cuando se inicie, el dispositivo empezará de inmediato el proceso de borrado selectivo para quitarlo de la administración. Una vez que se haya completado el proceso, se habrán eliminado todos los datos de la empresa y el nombre del dispositivo ya no aparecerá en la consola de administrador de Intune, con lo que se completa el ciclo de vida de administración del dispositivo.

### <a name="learn-more"></a>Obtener más información
[Introducción al uso de Enterprise Mobility + Security](https://docs.microsoft.com/enterprise-mobility/solutions/ems-get-started)

[Microsoft Enterprise Mobility](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility)

