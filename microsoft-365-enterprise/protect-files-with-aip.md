---
title: Proteger archivos con Azure Information Protection | Microsoft Docs
description: Aplique Azure Information Protection para proteger los archivos en un sitio de grupo de SharePoint Online extremadamente confidencial.
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
ms.openlocfilehash: 34758e152a483a2bada03aeb4c4b5ee3327fb469
ms.sourcegitcommit: 5b34af60e3aac19d618f1c6297da91e2c050a374
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/09/2017
---
# <a name="protect-files-with--azure-information-protection"></a>Proteger archivos con Azure Information Protection

## <a name="introduction"></a>Introducción

Siga los pasos de este artículo para configurar Azure Information Protection (AIP) para proporcionar cifrado y permisos a los archivos de un sitio de grupo de SharePoint Online extremadamente confidencial. 

La protección de cifrado y permisos viaja con un archivo aunque este se descargue del sitio. Para más información sobre sitios de grupo de SharePoint Online extremadamente confidenciales, vea [Proteger sitios y archivos de SharePoint Online](secure-sharepoint-online-sites-and-files.md).

## <a name="configure-azure-information-protection"></a>Configurar Azure Information Protection

En primer lugar siga las instrucciones de [Activación de Azure Rights Management desde el Centro de administración de Office 365](https://docs.microsoft.com/information-protection/deploy-use/activate-office365).

Luego configure la etiqueta **Extremadamente confidencial de AIP** con protección y permisos para el sitio de grupo de SharePoint Online extremadamente confidencial con estos pasos:

1. Inicie sesión en el **portal de Office 365** con una cuenta que tenga el rol Administrador de seguridad o Administrador de la compañía. Para obtener ayuda, vea [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4) (Dónde iniciar sesión en Office 365).
2. En una pestaña independiente del explorador, vaya a Azure Portal ([https://portal.azure.com](https://portal.azure.com/)).
3. En el panel de lista, haga clic en **Más servicios**, escriba **information** y haga clic en **Azure Information Protection**.
4. En la hoja **Azure Information Protection-Directiva global**, en la lista de etiquetas, haga clic en **Extremadamente confidencial**.
5. En la hoja **Etiqueta: Extremadamente confidencial**, en **Establecer permisos para documentos y correos electrónicos que contengan esta etiqueta**, haga clic en **Proteger**.
6. En la sección **Protección**, haga clic en **Azure RMS**.
7. En la hoja **Protección**, en **Configuración de protección**, haga clic en **+ Agregar permisos**.
8. En la hoja **Agregar permisos**, en **Especificar usuarios y grupos**, haga clic en **+ Examinar directorio**.
9. En el panel **Usuarios y grupos de AAD**, seleccione el grupo de acceso de miembros del sitio para el sitio de grupo de SharePoint Online extremadamente confidencial y haga clic en **Seleccionar**.
10. En **Choose permissions from the preset** (Elegir permisos entre los preestablecidos), desactive las casillas **Print, Copy and extract content** (Imprimir, copiar y extraer contenido) y **Reenviar**.
11. Haga clic en **Aceptar** dos veces.
12. En la hoja **Etiqueta: Extremadamente confidencial**, haga clic en **Guardar**.
13. En la hoja **Azure Information Protection-Directiva global**, haga clic en **Publicar**.

A continuación se muestra la configuración resultante del sitio de grupo extremadamente confidencial de SharePoint Online.

 ![Extremadamente confidencial](./media/protect-files-with-aip/hc_w_aip.png)

Ya está listo para empezar a crear documentos y protegerlos con Azure Information Protection y la etiqueta Extremadamente confidencial.

Debe [instalar el cliente de Azure Information Protection](https://docs.microsoft.com/information-protection/rms-client/install-client-app) en el dispositivo o equipo basado en Windows. Puede generar scripts y automatizar la instalación, o bien pueden hacerlo los usuarios manualmente. 

Para obtener más información, vea los recursos siguientes:

* [El lado cliente de Azure Information Protection](https://docs.microsoft.com/information-protection/rms-client/use-client)
* [Instalación del cliente de Azure Information Protection](https://docs.microsoft.com/information-protection/rms-client/client-admin-guide)
* [Página de descarga para la instalación manual](https://www.microsoft.com/download/details.aspx?id=53018)

Una vez instalado, los usuarios ejecutan y luego inician sesión desde una aplicación de Office (como Microsoft Word) con su cuenta de Office 365. Una nueva barra de herramientas **Confidencialidad** permite seleccionar la etiqueta **Extremadamente confidencial**. 

Asegúrese de que los usuarios conozcan en qué sitio de grupo de SharePoint Online deben almacenar sus archivos extremadamente confidenciales.

>[!Note]
>Si tiene varios sitios de grupo de SharePoint Online extremadamente confidenciales, debe crear varias etiquetas de Azure Information Protection con la configuración anterior, con los permisos de cada etiqueta establecidos en el grupo de acceso de miembros de sitio de un equipo de grupo concreto de SharePoint Online.
>

## <a name="next-steps"></a>Pasos siguientes
[Instrucciones de seguridad de Microsoft para campañas políticas, organizaciones sin ánimo de lucro y otras organizaciones ágiles](https://technet.microsoft.com/library/mt493213.aspx)

[Proteger sitios y archivos de SharePoint Online](secure-sharepoint-online-sites-and-files.md)

[Crear sitios de grupo en un entorno de desarrollo o prueba de campaña política](secure-sharepoint-online-sites-dev-test.md)

[Adopción de la nube y soluciones híbridas](https://technet.microsoft.com/library/dn262744.aspx)






