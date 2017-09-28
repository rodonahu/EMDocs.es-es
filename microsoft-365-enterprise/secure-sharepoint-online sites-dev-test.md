---
title: "Protección de sitios de SharePoint Online en un entorno de prueba y desarrollo | Microsoft Docs"
description: "Cree sitios de grupo de SharePoint Online en un entorno de prueba y desarrollo, que pueden ser públicos, privados, confidenciales o extremadamente confidenciales."
services: active-directory
keywords: Office 365, Windows 10, Enterprise Mobility + Security, Microsoft 365 Enterprise
documentationcenter: 
author: JoeDavies-MSFT
manager: laurawi
ms.assetid: 
ms.prod: microsoft-365-enterprise
ms.service: 
ms.workload: 
ms.tgt_pltfrm: na
ms.devlang: na
ms.topic: article
ms.date: 08/28/2017
ms.author: josephd
ms.openlocfilehash: b8f7f7db99ec04139cdf811f73ecb124bdd7ac2a
ms.sourcegitcommit: 0e0a15476e3bbd2d4ac6101c2cedd02e082ee25d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2017
---
# <a name="secure-sharepoint-online-sites-in-a-devtest-environment"></a>Protección de sitios de SharePoint Online en un entorno de prueba y desarrollo

## <a name="introduction"></a>Introducción

En este artículo se ofrecen instrucciones detalladas para crear un entorno de prueba y desarrollo que incluya los cuatro tipos diferentes de sitios de grupo de SharePoint Online para la solución de [protección de archivos y sitios de SharePoint Online](secure-sharepoint-online-sites-and-files.md). 

Con este entorno de prueba y desarrollo podrá experimentar con los comportamientos de protección de la información y ajustar la configuración a sus necesidades concretas antes de implementar sitios de grupo de SharePoint Online en producción.

## <a name="phase-1-create-your-devtest-environment"></a>Fase 1: Crear el entorno de prueba y desarrollo
En esta fase se obtienen suscripciones de evaluación para Office 365 y Enterprise Mobility + Security para una organización ficticia.

Primero siga las instrucciones de la **fase 2** del [entorno de prueba y desarrollo de Office 365](https://technet.microsoft.com/library/mt736406.aspx).

Después, regístrese en la **suscripción de evaluación de EMS**, agréguela a la misma organización que la suscripción de evaluación para Office 365 y siga estos pasos:

1. Si es necesario, inicie sesión en el **portal de Office 365** con las credenciales de la cuenta de administrador global de la suscripción de evaluación. Si necesita ayuda, vea [Dónde iniciar sesión en Office 365 para la Empresa](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).
2. Haga clic en el icono **Administración**.
3. En la pestaña **Centro de administración de Office** del explorador, en el panel de navegación izquierdo, haga clic en **Facturación > Servicios de compra**.
4. En la página **Servicios de compra**, busque el elemento **Enterprise Mobility + Security E5**. Después, mantenga el puntero sobre él y haga clic en **Iniciar evaluación gratuita**.
5. En la página **Confirmar pedido**, haga clic en **Probar ahora**.
6. En la página **Recibo del pedido**, haga clic en **Continuar**.

Después, habilite la licencia de Enterprise Mobility + Security E5 para la cuenta de administrador global.

1. En la pestaña **Centro de administración de Office 365** del explorador, en el panel de navegación izquierdo, haga clic en **Usuarios > Usuarios activos**.
2. Haga clic en la cuenta de administrador global y luego en **Editar para Licencias de productos**.
3. En el panel **Licencias de productos**, **active** la licencia de producto de **Enterprise Mobility + Security E5**, haga clic en **Guardar** y luego haga clic en **Cerrar** dos veces.


## <a name="phase-2-create-and-configure-your-azure-active-directory-ad-groups-and-users"></a>Fase 2: Crear y configurar los usuarios y grupos de Azure Active Directory (AD)
En esta fase se crean y configuran los grupos y usuarios de Azure AD para la organización ficticia.

En primer lugar, debe [conectarse al módulo PowerShell de Azure Active Directory V2](https://go.microsoft.com/fwlink/?linkid=842218).

Después, ejecute estos comandos desde el símbolo del sistema de PowerShell o el entorno de script integrado (ISE):
```
$groupNames=@("C-Suite","IT staff","Research staff","Regular staff","Marketing staff","Sales staff")
ForEach ($element in $groupNames){ New-AzureADGroup -DisplayName $element -MailEnabled $false -SecurityEnabled $true -MailNickName "NotSet" }
```

Luego configure la concesión de licencias automática para que se asignen licencias de forma automática a los miembros de los grupos para las suscripciones de Office 365 y EMS y, después, siga estos pasos:

1. Cree una pestaña independiente en el explorador y luego vaya a **Azure Portal** en [https://portal.azure.com](https://portal.azure.com). Si es necesario, inicie sesión con las credenciales de la cuenta de administrador global de la suscripción de evaluación de Office 365 E5.
2. En Azure Portal, haga clic en **Azure Active Directory > Licencias > Todos los productos**.
3. En la lista, seleccione **Enterprise Mobility + Security E5** y **Office 365 Enterprise E5** y haga clic en **Asignar**.
4. En la hoja **Asignar licencia**, haga clic en **Usuarios y grupos**.
5. En la lista de grupos, seleccione lo siguiente:
 * C-Suite (Directivos)
 * IT staff (Personal de TI)
 * Research staff (Personal de investigación)
 * Regular staff (Personal normal)
 * Marketing staff (Personal de marketing)
 * Sales staff (Personal de ventas)
6. Haga clic en **Seleccionar** y luego en **Asignar**.
7. Cierre la pestaña Azure Portal del explorador.

Luego rellene el nombre de la organización, la ubicación y una contraseña común. Ejecute los siguientes comandos desde el símbolo del sistema de PowerShell o el entorno de script integrado (ISE) para crear cuentas de usuario. Después agréguelas a sus grupos correspondientes.

```
$orgName="[organization name, such as contoso for the contoso.onmicrosoft.com trial subscription domain name]"
$location="[the ISO ALPHA2 country code, such as US for the United States]"
$commonPassword="[common password for all the new accounts]"

$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password=$commonPassword

$groupName="C-Suite"
$userNames=@("CEO","CFO","CIO") 
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){ 
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location 
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
$groupName="IT staff"
$userNames=@("ITAdmin1","ITAdmin2") 
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){ 
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location 
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
$groupName="Research staff"
$userNames=@("Researcher1") 
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){ 
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location 
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
$groupName="Regular staff"
$userNames=@("Regular1", "Regular2") 
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){ 
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location 
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
$groupName="Marketing staff"
$userNames=@("Marketing1", "Marketing2") 
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){ 
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location 
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
$groupName="Sales staff"
$userNames=@("SalesPerson1") 
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){ 
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location 
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
```

>[!Note]
>Se usa una contraseña común para automatizar y facilitar la configuración de un entorno de prueba y desarrollo. No se recomienda para suscripciones de producción.
>

Luego siga los pasos siguientes para comprobar que la concesión de licencias basada en grupos funciona correctamente.

1. En la pestaña de **inicio de Microsoft Office** del explorador, haga clic en el icono **Administración**.
2. En la nueva pestaña **Centro de administración de Office** del explorador, haga clic en **Usuarios**.
3. En la lista de usuarios, haga clic en **CEO** (Consejero delegado).
4. En el panel que muestra las propiedades de la cuenta de usuario **CEO**, compruebe que se le han asignado las licencias **Enterprise Mobility + Security E5** y **Office 365 Enterprise E5** (en **Licencias de productos**).

## <a name="phase-3-create-office-365-labels"></a>Fase 3: Crear etiquetas de Office 365

En esta fase se crean las etiquetas para los diferentes niveles de seguridad de las carpetas de documentos de sitios de grupo de SharePoint Online.

1. Si es necesario, use una instancia privada del explorador de Internet e inicie sesión en el **portal de Office 365** con la cuenta de administrador global de la suscripción de evaluación de Office 365 E5. Si necesita ayuda, vea [Dónde iniciar sesión en Office 365 para la Empresa](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).
2. En la pestaña de **inicio de Microsoft Office**, haga clic en el icono **Administración**.
3. En la nueva pestaña **Centro de administración de Office** del explorador, haga clic en **Centros de administración > Security & Compliance**.
4. En la nueva pestaña **Inicio – Security & Compliance** del explorador, haga clic en **Clasificaciones > Etiquetas**.
5. En el panel **Inicio > Etiquetas**, haga clic en **Crear una etiqueta**.
 1. En el panel **Name your label** (Nombre de la etiqueta), escriba **Interno público** y haga clic en **Siguiente**.
 2. En el panel **Configuración de etiquetas**, haga clic en **Siguiente**.
 3. En el panel **Revise su configuración**, haga clic en **Crear esta etiqueta** y luego en **Cerrar**.
6. Repita los pasos anteriores para estas etiquetas adicionales:
 * Private
 * Confidencial
 * Extremadamente confidencial
7. En el panel **Inicio > Etiquetas**, haga clic para **Publish labels** (Publicar etiquetas).
8. En el panel **Choose labels to publish** (Elegir las etiquetas que se van a publicar), haga clic en **Choose labels to publish** (Elegir las etiquetas que se van a publicar).
9. En el panel **Choose labels** (Elegir etiquetas), haga clic en **Agregar**, seleccione las cuatro etiquetas y haga clic en **Listo**.
10. En el panel **Choose labels to publish** (Elegir las etiquetas que se van a publicar), haga clic en **Siguiente**.
11. En el panel **Elegir ubicaciones**, haga clic en **Siguiente**.
12. En el panel **Escriba un nombre para la directiva**, escriba **Organización de ejemplo** en **Nombre** y haga clic en **Siguiente**.
13. En el panel **Revise su configuración**, haga clic en **Publish labels** (Publicar etiquetas) y luego haga clic en **Cerrar**.

## <a name="phase-4-create-your-sharepoint-online-team-sites"></a>Fase 4: Crear los sitios de grupo de SharePoint Online
En esta fase se crean y configuran los cuatro tipos de sitios de grupo de SharePoint Online de la organización de ejemplo.

### <a name="organization-wide-team-site"></a>Sitio de grupo En toda la organización
Para crear un sitio de grupo público de base de referencia de SharePoint Online, haga lo siguiente:

1. Si es necesario, abra un explorador en el equipo local e inicie sesión en el portal de Office 365 con la cuenta de administrador global. Si necesita ayuda, vea [Dónde iniciar sesión en Office 365 para la Empresa](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).
2. En la lista de iconos, haga clic en **SharePoint**.
3. En la nueva pestaña **SharePoint** del explorador, haga clic en **+ Crear sitio**.
4. En la página **Crear un sitio**, haga clic en **Sitio de grupo**.
5. En **Nombre del sitio**, escriba **En toda la organización**.
6. En **Team site description** (Descripción de sitio de grupo), escriba **Sitio de SharePoint para toda la organización**.
7. En **Configuración de privacidad**, seleccione **Public – anyone in the organization can access this site** (Público: cualquier usuario de la organización puede acceder a este sitio) y luego haga clic en **Siguiente**.
8. En el panel **Who do you want to add?** (¿A quién desea agregar?), haga clic en **Finalizar**.

Después configure la carpeta de documentos del sitio de grupo En toda la organización para la etiqueta Interno público.

1. En la pestaña **En toda la organización-Inicio** del explorador, haga clic en **Documentos**.
2. Haga clic en el icono de configuración y luego en **Configuración de biblioteca**.
3. En **Permisos y administración**, haga clic para **Apply label to items in this library** (Aplicar etiqueta a los elementos de esta biblioteca).
4. En **Settings-Apply Label** (Configuración-Aplicar etiqueta), seleccione **Interno público** y haga clic en **Guardar**.

Abajo se muestra la configuración resultante.

 ![Protección de sitios de grupo pública](./media/secure-sharepoint-online sites-dev-test/pubsite.png)

### <a name="project-1-team-site"></a>Sitio de grupo Proyecto 1
Para crear un sitio de grupo privado de base de referencia de SharePoint Online para un proyecto dentro de la organización, haga lo siguiente:

1. Si es necesario, use un explorador en el equipo local e inicie sesión en el **portal de Office 365** con la cuenta de administrador global. Si necesita ayuda, vea [Dónde iniciar sesión en Office 365 para la Empresa](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).
2. En la lista de iconos, haga clic en **SharePoint**.
3. En la nueva pestaña **SharePoint** del explorador, haga clic en **+ Crear sitio**.
4. En la página **Crear un sitio**, haga clic en **Sitio de grupo**.
5. En **Nombre del sitio**, escriba **Proyecto 1**.
6. En **Team site description** (Descripción del sitio de grupo), escriba **Sitio de SharePoint para Proyecto 1**.
7. En **Configuración de privacidad**, seleccione **Private – only members can access this site** (Privado: solo los miembros pueden acceder a este sitio) y haga clic en **Siguiente**.
8. En el panel **Who do you want to add?** (¿A quién desea agregar?), haga clic en **Finalizar**.

Después, configure la carpeta de documentos del sitio de grupo Proyecto 1 para la etiqueta Privado.

1. En la pestaña **Proyecto 1-Inicio** del explorador, haga clic en **Documentos**.
2. Haga clic en el icono de configuración y luego en **Configuración de biblioteca**.
3. En **Permisos y administración**, haga clic para **Apply label to items in this library** (Aplicar etiqueta a los elementos de esta biblioteca).
4. En **Settings-Apply Label** (Configuración-Aplicar etiqueta), seleccione **Privado** y haga clic en **Guardar**.

Abajo se muestra la configuración resultante.

 ![Protección de sitios de grupo privados](./media/secure-sharepoint-online sites-dev-test/privsite.png)

### <a name="marketing-campaigns-team-site"></a>Sitio de grupo Campañas de marketing

Para crear un sitio de grupo aislado de SharePoint Online que tenga el nivel confidencial para recursos de campañas de marketing, haga lo siguiente:

1. Abra un explorador en el equipo local e inicie sesión en el **portal de Office 365** con la cuenta de administrador global. Si necesita ayuda, vea [Dónde iniciar sesión en Office 365 para la Empresa](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).
2. En la lista de iconos, haga clic en **SharePoint**.
 1. En la nueva pestaña **SharePoint** del explorador, haga clic en **+ Crear sitio**.
 2. En la página **Crear un sitio**, haga clic en **Sitio de grupo**.
3. En **Team site name** (Nombre de sitio de grupo), escriba **Campañas de marketing**.
4. En **Team site description** (Descripción de sitio de grupo), escriba **Sitio de SharePoint para recursos de campaña de marketing (confidencial)**.
5. En **Configuración de privacidad**, seleccione **Private – only members can access this site** (Privado: solo los miembros pueden acceder a este sitio) y haga clic en **Siguiente**.
6. En el panel **Who do you want to add?** (¿A quién desea agregar?), haga clic en **Finalizar**.
7. En la nueva pestaña **Campañas de marketing** del explorador, en la barra de herramientas, haga clic en el icono de configuración y luego en **Permisos del sitio**.
8. En el panel **Permisos del sitio**, haga clic en **Advanced permissions settings** (Configuración de permisos avanzada).
9. En la nueva pestaña **Permisos** del explorador, haga clic en **Configuración de solicitud de acceso**.
10. En el cuadro de diálogo **Configuración de solicitud de acceso**:
  1. Desactive las casillas **Permitir que los miembros compartan el sitio y archivos y carpetas individuales** y **Permitir a los miembros invitar a otros al grupo de miembros del sitio**.
  2. Escriba **ITAdmin1@[nombreDeOrganización].onmicrosoft.com** en **Enviar todas las solicitudes de acceso**.
  3. Haga clic en **Aceptar**.
11. Haga clic en **Campañas de Marketing-Miembros** en la lista.
12. En la página **Personas y grupos**, haga clic en **Nuevo**.
13. En el cuadro de diálogo **Compartir**, escriba **Marketing staff** (Personal de marketing), selecciónelo y haga clic en **Compartir**.
14. Repita los pasos anteriores para la cuenta de usuario **Researcher1**.
15. Haga clic en el botón Atrás del explorador y luego en **Campañas de marketing-Propietarios** en la lista.
16. En la página **Personas y grupos**, haga clic en **Nuevo**.
17. En el cuadro de diálogo **Compartir**, escriba **IT staff** (Personal de TI), selecciónelo y haga clic en **Compartir**.
18. Haga clic en el botón Atrás del explorador y cierre la pestaña **Personas y grupos** del explorador, haga clic en la pestaña **Campañas de marketing-Inicio** del explorador y cierre el panel **Permisos del sitio**.

Estos son los resultados de la configuración de los permisos:

* El grupo de SharePoint **Campañas de marketing-Miembros** solamente contiene el grupo **Campañas de marketing** (que contiene la cuenta de usuario de administrador global), el grupo **Marketing staff** [Personal de marketing] (que contiene las cuentas de usuario Marketing1 y Marketing2) y la cuenta de usuario **Researcher1**.
* El grupo de SharePoint **Campañas de marketing-Propietarios** solo contiene el grupo **IT staff** [Personal de TI] (que contiene únicamente las cuentas de usuario ITAdmin1 e ITAdmin2).
* El grupo de SharePoint **Campañas de marketing-Visitantes** no contiene grupos ni cuentas de usuario.
* Los miembros no pueden modificar los permisos de nivel de sitio (esto solo pueden hacerlo los miembros del grupo **Campañas de marketing-Propietarios**).
* Otras cuentas de usuario no pueden acceder al sitio ni a sus recursos, pero pueden pedir acceso al sitio, que envía un correo electrónico al buzón de la cuenta de usuario _ITAdmin1_.

Después, configure la carpeta de documentos del sitio de grupo Campañas de marketing para la etiqueta Confidencial.

1. En la pestaña **Campañas de marketing-Inicio** del explorador, haga clic en **Documentos**.
2. Haga clic en el icono de configuración y luego en **Configuración de biblioteca**.
3. En **Permisos y administración**, haga clic para **Apply label to items in this library** (Aplicar etiqueta a los elementos de esta biblioteca).
4. En **Configuración-Aplicar etiqueta**, seleccione **Confidencial** y haga clic en **Guardar**.

Luego configure una directiva de prevención de pérdida de datos (DLP) que notifique a los usuarios cada vez que compartan un documento en un sitio de grupo de SharePoint Online con la etiqueta Confidencial, que incluye el sitio Campañas de marketing, fuera de la organización.

1. En la pestaña de **inicio de Microsoft Office** del explorador, haga clic en el icono **Seguridad y cumplimiento**.
2. En la nueva pestaña **Seguridad y cumplimiento** del explorador, haga clic en **Prevención de pérdida de datos > Directiva**.
3. En el panel **Prevención de pérdida de datos**, haga clic en **+ Crear una directiva**.
4. En el panel **Start with a template or create a custom policy** (Empezar con una plantilla o crear una directiva personalizada), haga clic en **Personalizada** y luego en **Siguiente**.
5. En el panel **Escriba un nombre para la directiva**, escriba **Sitios de grupo de SharePoint Online de etiqueta Confidencial** en **Nombre** y haga clic en **Siguiente**.
6. En el panel **Elegir ubicaciones**, haga clic en **Let me choose specific locations** (Permitir elegir ubicaciones concretas) y luego haga clic en **Siguiente**.
7. En la lista de ubicaciones, deshabilite las ubicaciones **Correo electrónico de Exchange** y **Cuentas de OneDrive** y haga clic en **Siguiente**.
8. En el panel **Customize the types of sensitive info you want to protect** (Personalizar los tipos de información confidencial que quiere proteger), haga clic en **Editar**.
9. En el panel **Choose the types of content to protect** (Elegir los tipos de contenido que se va a proteger), haga clic en **Agregar** en el cuadro desplegable y luego en **Etiquetas**.
10. En el panel **Etiquetas**, haga clic en **+ Agregar**, seleccione la etiqueta **Confidencial**, haga clic en **Agregar** y luego en **Listo**.
11. En el panel **Choose the types of content to protect** (Elegir los tipos de contenido que se va a proteger), haga clic en **Guardar**.
12. En el panel **Customize the types of sensitive info you want to protect** (Personalizar los tipos de información confidencial que quiere proteger), haga clic en **Siguiente**.
13. En el panel **What do you want to do if we detect sensitive info?** (¿Qué quiere hacer si se detecta información confidencial?), haga clic en **Customize the tip and email** (Personalizar la sugerencia y el correo electrónico).
14. En el panel **Customize policy tips and email notifications** (Personalizar sugerencias de directiva y notificaciones de correo electrónico), haga clic en **Customize the policy tip text** (Personalizar el texto de la sugerencia de directiva).
15. En el cuadro de texto, escriba o pegue lo siguiente y haga clic en **Aceptar**:
 * Para compartir con un usuario de fuera de la organización, descargue el archivo y luego ábralo. Haga clic en **Archivo**, **Proteger documento**, **Cifrar con contraseña** y especifique una contraseña segura. Envíe la contraseña en un correo electrónico diferente u otro medio de comunicación.
16. En el panel **What do you want to do if we detect sensitive info?** (¿Qué quiere hacer si se detecta información confidencial?), desactive la casilla **Block people from sharing, and restrict access to shared content** (Evitar que los usuarios puedan compartir y restringir el acceso al contenido compartido) y haga clic en **Siguiente**.
17. En el panel **Do you want to turn on the policy or test things out first?** (¿Desea activar la directiva o probarla primero?), haga clic en **Sí** para activarla inmediatamente y luego haga clic en **Siguiente**.
18. En el panel **Revise su configuración**, haga clic en **Crear** y luego en **Cerrar**.

Abajo se muestra la configuración resultante.

 ![Protección confidencial](./media/secure-sharepoint-online sites-dev-test/senssite.png)

### <a name="company-strategy-team-site"></a>Sitio de grupo Estrategia de empresa
Para crear un sitio de grupo aislado de SharePoint Online que tenga el nivel extremadamente confidencial para recursos estratégicos de empresa dirigido a los directores ejecutivos de la organización, haga lo siguiente:

1. Si es necesario, use un explorador en el equipo local e inicie sesión en el **portal de Office 365** con la cuenta de administrador global. Si necesita ayuda, vea [Dónde iniciar sesión en Office 365 para la Empresa](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).
2. En la lista de iconos, haga clic en **SharePoint**.
3. En la nueva pestaña **SharePoint** del explorador, haga clic en **+ Crear sitio**.
  1. En la página **Crear un sitio**, haga clic en **Sitio de grupo**.
  2. En **Team site name** (Nombre de sitio de grupo), escriba **Estrategia de empresa**.
  3. En **Team site description** (Descripción de sitio de grupo), escriba **Sitio de SharePoint para la estrategia de empresa (extremadamente confidencial)**.
4. En **Configuración de privacidad**, seleccione **Private – only members can access this site** (Privado: solo los miembros pueden acceder a este sitio) y haga clic en **Siguiente**.
5. En el panel **Who do you want to add?** (¿A quién desea agregar?), haga clic en **Finalizar**.
6. En la nueva pestaña **Estrategia de empresa** del explorador, en la barra de herramientas, haga clic en el icono de configuración y luego en **Permisos del sitio**.
7. En el panel **Permisos del sitio**, haga clic en **Advanced permissions settings** (Configuración de permisos avanzada).
8. En la nueva pestaña **Permisos** del explorador, haga clic en **Configuración de solicitud de acceso**.
9. En el cuadro de diálogo **Configuración de solicitud de acceso**, desactive **Permitir que los miembros compartan el sitio y archivos y carpetas individuales** y **Permitir a los miembros invitar a otros al grupo de miembros del sitio** (de forma que las tres casillas estén desactivadas) y haga clic en **Aceptar**.
10. Haga clic en **Estrategia de empresa-Miembros** en la lista y, en la página **Personas y grupos**, haga clic en **Nuevo**.
11. En el cuadro de diálogo **Compartir**, escriba **C-Suite** (Directivos), selecciónelo y haga clic en **Compartir**.
12. Haga clic en **Estrategia de empresa-Propietarios** en la lista y, en la página **Personas y grupos**, haga clic en **Nuevo**.
13. En el cuadro de diálogo **Compartir**, escriba **IT staff** (Personal de TI), selecciónelo y haga clic en **Compartir**.
14. Haga clic en el botón Atrás del explorador y cierre la pestaña **Personas y grupos**.
15. Haga clic en la pestaña **Estrategia de empresa-Inicio** del explorador y luego cierre el panel **Permisos del sitio**.

Estos son los resultados de la configuración de los permisos:

* El grupo de SharePoint **Estrategia de empresa-Miembros** solo contiene el grupo **C-Suite** [Directivos] (que contiene únicamente las cuentas de usuario CEO, CFO y CIO) y el grupo **Estrategia de empresa** (que contiene únicamente la cuenta de usuario de administrador global).
* El grupo de SharePoint **Estrategia de empresa-Propietarios** solo contiene el grupo **IT staff** [Personal de TI] (que contiene únicamente las cuentas de usuario _ITAdmin1_ e _ITAdmin2_).
* El grupo de SharePoint **Estrategia de empresa-Visitantes** no contiene grupos ni cuentas de usuario.
* Los miembros no pueden modificar los permisos de nivel de sitio (esto solo pueden hacerlo los miembros del grupo **Estrategia de empresa-Propietarios**).
* Otras cuentas de usuario no pueden acceder al sitio o a sus recursos ni pedir acceso al sitio. Los permisos adicionales para el sitio deben ser asignados por el administrador global o por un miembro del grupo **Estrategia de empresa-Propietarios**.

Después, configure la carpeta de documentos del sitio de grupo Estrategia de empresa para la etiqueta Extremadamente confidencial.

1. En la pestaña **Estrategia de empresa-Inicio** del explorador, haga clic en **Documentos**.
2. Haga clic en el icono de configuración y luego en **Configuración de biblioteca**.
3. En **Permisos y administración**, haga clic para **Apply label to items in this library** (Aplicar etiqueta a los elementos de esta biblioteca).
4. En **Configuración-Aplicar etiqueta**, seleccione **Extremadamente confidencial** y haga clic en **Guardar**.

Después, configure una directiva de DLP que impida a los usuarios compartir un documento en un sitio de grupo de SharePoint Online con la etiqueta Extremadamente confidencial, que incluye el sitio Estrategia de empresa, fuera de la organización.

1. Si fuera necesario, use un explorador en el equipo local e inicie sesión en el **portal de Office 365** con una cuenta que tenga el rol Administrador de seguridad o Administrador de la compañía. Si necesita ayuda, vea [Dónde iniciar sesión en Office 365 para la Empresa](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).
2. En la pestaña de **inicio de Microsoft Office** del explorador, haga clic en el icono **Seguridad y cumplimiento**.
3. En la nueva pestaña **Seguridad y cumplimiento** del explorador, haga clic en **Prevención de pérdida de datos > Directiva**.
4. En el panel **Prevención de pérdida de datos**, haga clic en **+ Crear una directiva**.
5. En el panel **Start with a template or create a custom policy** (Empezar con una plantilla o crear una directiva personalizada), haga clic en **Personalizada** y luego en **Siguiente**.
6. En el panel **Escriba un nombre para la directiva**, escriba **Sitios de grupo de SharePoint Online etiquetados como Extremadamente confidencial** en **Nombre** y haga clic en **Siguiente**.
7. En el panel **Elegir ubicaciones**, haga clic en **Let me choose specific locations** (Permitir elegir ubicaciones concretas) y luego haga clic en **Siguiente**.
8. En la lista de ubicaciones, deshabilite las ubicaciones **Correo electrónico de Exchange** y **Cuentas de OneDrive** y haga clic en **Siguiente**.
9. En el panel **Customize the types of sensitive info you want to protect** (Personalizar los tipos de información confidencial que quiere proteger), haga clic en **Editar**.
10. En el panel **Choose the types of content to protect** (Elegir los tipos de contenido que se va a proteger), haga clic en **Agregar** en el cuadro desplegable y luego en **Etiquetas**.
11. En el panel **Etiquetas**, haga clic en **+ Agregar**, seleccione la etiqueta **Extremadamente confidencial**, haga clic en **Agregar** y luego en **Listo**.
12. En el panel **Choose the types of content to protect** (Elegir los tipos de contenido que se va a proteger), haga clic en **Guardar**.
13. En el panel **Customize the types of sensitive info you want to protect** (Personalizar los tipos de información confidencial que quiere proteger), haga clic en **Siguiente**.
14. En el panel **What do you want to do if we detect sensitive info?** (¿Qué quiere hacer si se detecta información confidencial?), haga clic en **Customize the tip and email** (Personalizar la sugerencia y el correo electrónico).
15. En el panel **Customize policy tips and email notifications** (Personalizar sugerencias de directiva y notificaciones de correo electrónico), haga clic en **Customize the policy tip text** (Personalizar el texto de la sugerencia de directiva).
16. En el cuadro de texto, escriba o pegue lo siguiente y haga clic en **Aceptar**:
 * Para compartir con un usuario de fuera de la organización, descargue el archivo y luego ábralo. Haga clic en **Archivo**, **Proteger documento**, **Cifrar con contraseña** y especifique una contraseña segura. Envíe la contraseña en un correo electrónico diferente u otro medio de comunicación.
17. En el panel **What do you want to do if we detect sensitive info?** (¿Qué desea hacer si se detecta información confidencial?), seleccione **Require a business justification to override** (Exigir una justificación de empresa para invalidar) y haga clic en **Siguiente**.
18. En el panel **Do you want to turn on the policy or test things out first?** (¿Desea activar la directiva o probarla primero?), haga clic en **Sí** para activarla inmediatamente y luego haga clic en **Siguiente**.
19. En el panel **Revise su configuración**, haga clic en **Crear** y luego en **Cerrar**.

Luego siga las instrucciones de [Activación de Azure Rights Management desde el Centro de administración de Office 365](https://docs.microsoft.com/information-protection/deploy-use/activate-office365).

Después, configure la etiqueta Extremadamente confidencial de Azure Information Protection con protección y permisos, y siga estos pasos:

1. En una pestaña independiente del explorador en el que ha iniciado sesión con la cuenta de administrador global, vaya a **Azure Portal** ([http://portal.azure.com](http://portal.azure.com/)).
2. En el panel de lista, haga clic en **Más servicios**, escriba **Información** y haga clic en **Azure Information Protection**.
3. En la hoja **Azure Information Protection-Directiva global**, en la lista de etiquetas, haga clic en **Extremadamente confidencial**.
4. En la hoja **Etiqueta: Extremadamente confidencial**, en **Establecer permisos para documentos y correos electrónicos que contengan esta etiqueta**, haga clic en **Proteger**.
5. En la sección **Protección**, haga clic en **Azure RMS**.
6. En la hoja **Protección**, en **Configuración de protección**, haga clic en **+ Agregar permisos**.
7. En la hoja **Agregar permisos**, en **Seleccionar usuarios y grupos**, haga clic en **+ Seleccionar usuarios y grupos**.
8. En el panel **Usuarios y grupos de AAD**, seleccione **C-Suite** y haga clic en **Seleccionar**.
9. En **Choose permissions from the preset** (Elegir permisos entre los preestablecidos), desactive las casillas **Print, Copy and extract content** (Imprimir, copiar y extraer contenido) y **Reenviar**.
10. Haga clic en **Aceptar** dos veces.
11. En la hoja **Etiqueta: Extremadamente confidencial**, haga clic en **Guardar**.
12. En la hoja **Azure Information Protection-Directiva global**, haga clic en **Publicar**.

Para proteger un documento con Azure Information Protection y la etiqueta Extremadamente confidencial, debe [instalar el cliente de Azure Information Protection](https://docs.microsoft.com/information-protection/rms-client/install-client-app) en un equipo de prueba, instalar Office desde el portal de Office 365 y luego iniciar sesión desde Microsoft Word con una cuenta del grupo C-Suite (Directivos) de la suscripción de evaluación.

Abajo se muestra la configuración resultante.

 ![Protección extremadamente confidencial](./media/secure-sharepoint-online sites-dev-test/hcsite.png)

### <a name="create-documents-and-test-access"></a>Crear documentos y probar el acceso

Ahora está listo para crear documentos en estos cuatro sitios y probar el acceso a ellos con diferentes cuentas de usuario de la suscripción de evaluación.

Abajo se muestra la configuración global de los cuatro sitios de grupo de SharePoint Online.

 ![Configuración final](./media/secure-sharepoint-online sites-dev-test/finalconfig.png)

Cuando esté listo para la implementación en producción de sitios seguros de SharePoint Online, vea [Protección de archivos y sitios de SharePoint Online](https://technet.microsoft.com/en-us/library/mt842190.aspx) para obtener información detallada y vínculos a artículos de implementación paso a paso.


## <a name="next-steps"></a>Pasos siguientes
[Protección de archivos y sitios de SharePoint Online](secure-sharepoint-online-sites-and-files.md)

[Soluciones de seguridad](https://technet.microsoft.com/library/mt784690.aspx)

[Adopción de la nube y soluciones híbridas](https://technet.microsoft.com/library/dn262744.aspx)

[Instrucciones de seguridad de Microsoft para campañas políticas, organizaciones sin ánimo de lucro y otras organizaciones ágiles](https://technet.microsoft.com/library/mt493213.aspx)

