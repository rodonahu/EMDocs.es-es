---
title: "Implementar sitios con tres niveles de protección | Microsoft Docs"
description: "Cree y configure sitios de grupo de SharePoint Online en Office 365 con distintos niveles de protección de la información."
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
ms.date: 09/11/2017
ms.author: josephd
ms.openlocfilehash: 0c4e7eaf6449b551a0a6222d475b2c42f49550f9
ms.sourcegitcommit: 684c942047754e93378e271f5b1a659a9752f0ba
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2017
---
# <a name="deploy-sites-for-three-tiers-of-protection"></a>Implementar sitios con tres niveles de protección

## <a name="introduction"></a>Introducción

Siga los pasos de este artículo para diseñar e implementar sitios de grupo de base de referencia, confidenciales y extremadamente confidenciales de SharePoint Online. Para más información sobre estos tres niveles de protección, vea [Proteger sitios y archivos de SharePoint Online](secure-sharepoint-online-sites-and-files.md).

## <a name="baseline-sharepoint-online-team-sites"></a>Sitios de grupo de base de referencia de SharePoint Online
La protección de base de referencia incluye sitios de grupo públicos y privados. Todo el personal de la organización puede acceder a los sitios de grupo públicos. Solo los miembros del grupo de Office 365 asociado al sitio de grupo pueden detectar sitios privados y acceder a ellos. Ambos tipos de sitios de grupo permiten a los miembros compartir el sitio con otros usuarios.

### <a name="public"></a>Público
Para crear un sitio de grupo de SharePoint Online de base de referencia con acceso y permisos públicos, haga lo siguiente:

1. Inicie sesión en el **portal de Office 365** con una cuenta que también se vaya a usar para administrar el sitio de grupo de SharePoint Online (un administrador de SharePoint Online). Para obtener ayuda, vea [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4) (Dónde iniciar sesión en Office 365).
2. En la lista de iconos, haga clic en **SharePoint**.
3. En la nueva pestaña **SharePoint** del explorador, haga clic en + **Crear sitio**.
4. En la página **Crear un sitio**, haga clic en **Sitio de grupo**.
5. En **Nombre del sitio**, escriba un nombre para el sitio de grupo público. 
6. En la **descripción del sitio de grupo**, escriba una descripción de la finalidad del sitio.
7. En **Configuración de privacidad**, seleccione **Público: cualquier usuario de la organización puede acceder a este sitio** y luego haga clic en **Siguiente**.
8. En el panel **Who do you want to add?** (Usuarios que quiere agregar), haga clic en **Finalizar**.

A continuación se muestra la configuración resultante.

 ![SharePoint de base de referencia público](./media/deploy-sites-for-three-tiers-of-protection/pub_site.png)

### <a name="private"></a>Private
Para crear un sitio de grupo de SharePoint Online de base de referencia con acceso y permisos privados, haga lo siguiente:

1. Si lo necesita, inicie sesión en el **portal de Office 365** con una cuenta que también se vaya a usar para administrar el sitio de grupo de SharePoint Online (un administrador de SharePoint Online). Para obtener ayuda, vea [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4) (Dónde iniciar sesión en Office 365).
2. En la lista de iconos, haga clic en **SharePoint**.
3. En la nueva pestaña **SharePoint** del explorador, haga clic en + **Crear sitio**.
4. En la página **Crear un sitio**, haga clic en **Sitio de grupo**.
5. En **Nombre del sitio**, escriba un nombre para el sitio de grupo privado. 
6. En la **descripción del sitio de grupo**, escriba una descripción de la finalidad del sitio.
7. En **Configuración de privacidad**, seleccione **Privado: solo los miembros pueden acceder a este sitio** y haga clic en **Siguiente**.
8. En el panel de **Who do you want to add?** (Usuarios que quiere agregar), en **Agregar miembros**, escriba los nombres de cuentas de usuario que tengan acceso a este sitio de grupo privado.
9. Cuando haya terminado de agregar el conjunto inicial de miembros del sitio, haga clic en **Finalizar**.

A continuación se muestra la configuración resultante.

 ![SharePoint de base de referencia privado](./media/deploy-sites-for-three-tiers-of-protection/priv_site.png)

## <a name="sensitive-sharepoint-online-team-sites"></a>Sitios de grupo confidenciales de SharePoint Online
Un sitio de grupo de SharePoint Online confidencial es un sitio de grupo aislado, lo que significa que los permisos se controlan mediante la pertenencia a grupos de SharePoint en lugar de la pertenencia al grupo de Office 365 asociado al sitio de grupo.

Para crear un sitio de grupo aislado, siga estos dos pasos principales.

### <a name="step-1-design-your-isolated-site"></a>Paso 1: Diseñar el sitio aislado
Para diseñar el sitio de grupo aislado, debe determinar:

* Los grupos y niveles de permisos de SharePoint.
* El conjunto de grupos de acceso que van a ser miembros de los grupos de SharePoint.
 El conjunto recomendado de grupos de acceso es uno para miembros del sitio, otro para lectores del sitio y el último para administradores del sitio.
* Si va a usar grupos anidados dentro de los grupos de acceso.

Por ejemplo, la estructura del grupo y los niveles de permisos recomendados de SharePoint son similares a los siguientes:

|**Grupo de SharePoint**|**Nivel de permisos**|**Grupo de acceso (ejemplos)**|
|:-----|:-----|:-----|
|Miembros de [nombre del sitio]|Editar|Miembros de [nombre del sitio]|
|Visitantes de [nombre del sitio]|Lectura|Lectores de [nombre del sitio]|
|Propietarios de [nombre del sitio]|Control total|Administradores de [nombre del sitio]|

Los niveles de permisos y los grupos de SharePoint se crean de forma predeterminada para un sitio de grupo. Debe determinar los nombres de los grupos de acceso.

Para obtener los detalles del proceso de diseño, vea [Diseñar un sitio de grupo SharePoint Online aislado](https://technet.microsoft.com/library/mt784687.aspx).

### <a name="step-2-deploy-your-isolated-site"></a>Paso 2: Implementar el sitio aislado
Para implementar el sitio aislado, primero debe:

* Determinar las cuentas de usuario y los grupos que va a agregar a cada uno de los grupos de acceso.
* Crear los grupos de acceso y agregar a miembros de grupos y usuarios.

Para obtener los pasos detallados, vea la **fase 1** de [Implementar un sitio de grupo SharePoint Online aislado](https://technet.microsoft.com/library/mt784693.aspx).

Luego cree el sitio de grupo de SharePoint Online con estos pasos.

1. Si lo necesita, inicie sesión en el **portal de Office 365** con una cuenta que también se vaya a usar para administrar el sitio de grupo de SharePoint Online (un administrador de SharePoint Online). Para obtener ayuda, vea [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4) (Dónde iniciar sesión en Office 365).
2. En la lista de iconos, haga clic en **SharePoint**.
3. En la nueva pestaña **SharePoint** del explorador, haga clic en + **Crear sitio**.
4. En la página **Crear un sitio**, haga clic en **Sitio de grupo**.
5. En **Nombre del sitio**, escriba un nombre para el sitio de grupo privado.
6. En la descripción del **sitio de grupo**, escriba una descripción opcional.
7. En **Configuración de privacidad**, seleccione **Privado: solo los miembros pueden acceder a este sitio** y haga clic en **Siguiente**.
8. En el panel **Who do you want to add?** (Usuarios que quiere agregar), haga clic en **Finalizar**.

Luego, desde el nuevo sitio de grupo de SharePoint Online, configure los permisos con estos pasos.

1. Determine el nombre principal de usuario (UPN) del administrador de TI o de otra persona que vaya a ser responsable de responder a las solicitudes de acceso al sitio y de dirigirlas (belindan@contoso.com es un ejemplo de UPN). Anote ese UPN.
2. En la barra de herramientas, haga clic en el icono de configuración y luego en **Permisos del sitio**.
3. En el panel **Permisos del sitio**, haga clic en **Advanced permissions settings** (Configuración de permisos avanzada).
4. En la nueva pestaña **Permisos** del explorador, haga clic en **Configuración de solicitud de acceso**.
5. En el cuadro de diálogo **Configuración de solicitud de acceso**:
  1. Desactive las casillas de verificación **Permitir que los miembros compartan el sitio y archivos y carpetas individuales** y **Permitir a los miembros invitar a otros al grupo de miembros del sitio**.
  2. Escriba el UPN del administrador de TI del paso 1 en **Enviar todas las solicitudes de acceso**.
  3. Haga clic en **Aceptar**.
6. En la pestaña **Permisos** del explorador, haga clic en **Miembros de [nombre del sitio]** en la lista.
7. En **Personas y grupos**, haga clic en **Nuevo**. En el cuadro de diálogo **Compartir**, escriba el nombre del grupo de acceso de miembros de sitio para este sitio, selecciónelo y luego haga clic en **Compartir**.
8. Haga clic en el botón Atrás del explorador y luego en **Propietarios de [nombre del sitio]** en la lista.
9. En **Personas y grupos**, haga clic en **Nuevo**. En el cuadro de diálogo **Compartir**, escriba el nombre del grupo de acceso de administradores de sitio para este sitio, selecciónelo y luego haga clic en **Compartir**.
10. Haga clic en el botón Atrás del explorador y luego en **Visitantes de [nombre del sitio]** en la lista.
11. En **Personas y grupos**, haga clic en **Nuevo**. En el cuadro de diálogo **Compartir**, escriba el nombre del grupo de acceso de lectores de sitio para este sitio, selecciónelo y luego haga clic en **Compartir**.
12. Cierre la pestaña **Permisos** del explorador.

A continuación se muestran los resultados de esta configuración de permisos:

* El grupo de SharePoint **Propietarios de [nombre del sitio]** contiene el grupo de acceso de administradores de sitio, en el que todos los miembros tienen el nivel de permisos **Control total**.
* El grupo de SharePoint **Miembros de [nombre del sitio]** contiene el grupo de acceso de miembros de sitio, en el que todos los miembros tienen el nivel de permisos **Editar**.
* El grupo de SharePoint **Visitantes de [nombre del sitio]** contiene el grupo de acceso de lectores de sitio, en el que todos los miembros tienen el nivel de permisos **Leer**.
* La capacidad de los miembros de invitar a otros miembros está deshabilitada. 
* La capacidad de los miembros de solicitar acceso está habilitada. 

A continuación se muestra la configuración resultante.

 ![Protección confidencial](./media/deploy-sites-for-three-tiers-of-protection/sens_site.png)

Los miembros del sitio, a través de la pertenencia a grupos en uno de los grupos de acceso, ahora pueden colaborar de forma segura en los recursos del sitio.

## <a name="highly-confidential-sharepoint-online-team-sites"></a>Sitios de grupo de SharePoint Online extremadamente confidenciales
Un sitio de grupo de SharePoint Online extremadamente confidencial es un sitio de grupo aislado, lo que significa que los permisos se controlan mediante la pertenencia a grupos de SharePoint en lugar de la pertenencia al grupo de Office 365 asociado al sitio de grupo.

Para crear un sitio de grupo aislado para información y colaboración extremadamente confidenciales, hay dos pasos principales.

### <a name="step-1-design-your-isolated-site"></a>Paso 1: Diseñar el sitio aislado
Para diseñar el sitio de grupo aislado, debe determinar:

* Los grupos y niveles de permisos de SharePoint.
* El conjunto de grupos de acceso que van a ser miembros de los grupos de SharePoint.
 El conjunto recomendado de grupos de acceso es uno para miembros del sitio, otro para lectores del sitio y el último para administradores del sitio.
* Si va a usar grupos anidados dentro de los grupos de acceso.

Por ejemplo, la estructura del grupo y los niveles de permisos recomendados tienen este aspecto:
 
|**Grupo de SharePoint**|**Nivel de permisos**|**Grupo de acceso (ejemplos)**|
|:-----|:-----|:-----|
|Miembros de [nombre del sitio]|Editar|Miembros de [nombre del sitio]|
|Visitantes de [nombre del sitio]|Lectura|Lectores de [nombre del sitio]|
|Propietarios de [nombre del sitio]|Control total|Administradores de [nombre del sitio]|

Los niveles de permisos y los grupos de SharePoint se crean de forma predeterminada para un sitio de grupo. Debe determinar los nombres de los grupos de acceso.

Para obtener los detalles del proceso de diseño, vea [Diseñar un sitio de grupo SharePoint Online aislado](https://technet.microsoft.com/library/mt784687.aspx).

### <a name="step-2-deploy-your-isolated-site"></a>Paso 2: Implementar el sitio aislado
Para implementar el sitio aislado, primero debe:

* Determinar los miembros de grupos y usuarios de cada uno de los grupos de acceso.
* Crear los grupos de acceso y agregar a miembros de grupos y usuarios.
* Crear un sitio de grupo aislado que use los grupos de acceso.

Para obtener los pasos detallados, vea [Implementar un sitio de grupo SharePoint Online aislado](https://technet.microsoft.com/library/mt784693.aspx).

A continuación se muestran los resultados de esta configuración de permisos:

* El grupo de SharePoint **Propietarios de [nombre del sitio]** contiene el grupo de acceso de administradores de sitio, en el que todos los miembros tienen el nivel de permisos **Control total**.
* El grupo de SharePoint **Miembros de [nombre del sitio]** contiene el grupo de acceso de miembros de sitio, en el que todos los miembros tienen el nivel de permisos **Editar**.
* El grupo de SharePoint **Visitantes de [nombre del sitio]** contiene el grupo de acceso de lectores de sitio, en el que todos los miembros tienen el nivel de permisos **Leer**.
* La capacidad de los miembros de invitar a otros miembros está deshabilitada. 
* La capacidad de los no miembros de solicitar acceso está deshabilitada. 

Esta es la configuración resultante.

 ![Protección extremadamente confidencial](./media/deploy-sites-for-three-tiers-of-protection/hc_site.png)

Los miembros del sitio, a través de la pertenencia a grupos en uno de los grupos de acceso, ahora pueden colaborar de forma segura en los recursos del sitio. 

## <a name="next-steps"></a>Pasos siguientes

[Protección de archivos con etiquetas de Office 365 y DLP](protect-files-with-o365-labels-dlp.md)







