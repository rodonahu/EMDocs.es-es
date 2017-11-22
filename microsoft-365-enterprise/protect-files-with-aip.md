---
title: Proteger archivos de SharePoint Online con Azure Information Protection | Microsoft Docs
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
ms.date: 11/15/2017
ms.author: josephd
ms.openlocfilehash: ec88a40392e8bc530a40c35a1d8dadd1be8eb4f3
ms.sourcegitcommit: 684c942047754e93378e271f5b1a659a9752f0ba
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2017
---
# <a name="protect-files-with--azure-information-protection"></a>Proteger archivos con Azure Information Protection

## <a name="introduction"></a>Introducción

Siga los pasos de este artículo para configurar Azure Information Protection (AIP) para proporcionar cifrado y permisos a los archivos de un sitio de grupo de SharePoint Online extremadamente confidencial. 

La protección de cifrado y permisos viaja con un archivo aunque este se descargue del sitio. Para más información sobre sitios de grupo de SharePoint Online extremadamente confidenciales, vea [Proteger sitios y archivos de SharePoint Online](secure-sharepoint-online-sites-and-files.md).

> [!NOTE]
> Cuando se aplica el cifrado de Azure Information Protection a los archivos almacenados en Office 365, el servicio no puede procesar el contenido de estos archivos. No funcionan algunas características de colaboración, como la coautoría, eDiscovery, la búsqueda y Delve. Las directivas de prevención de pérdida de datos (DLP) solo pueden trabajar con los metadatos (incluidas las etiquetas de Office 365), pero no con el contenido de estos archivos (por ejemplo, números de tarjeta de crédito incluidos en los archivos).

## <a name="configure-azure-information-protection"></a>Configurar Azure Information Protection

En primer lugar siga las instrucciones de [Activación de Azure Rights Management desde el Centro de administración de Office 365](https://docs.microsoft.com/information-protection/deploy-use/activate-office365).

Luego, siga estos pasos para configurar Azure Information Protection con una nueva directiva con ámbito y una subetiqueta para la protección y los permisos relacionados con el sitio de grupo de SharePoint Online extremadamente confidencial:

1. Inicie sesión en el **portal de Office 365** con una cuenta que tenga el rol Administrador de seguridad o Administrador de la compañía. Para obtener ayuda, vea [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4) (Dónde iniciar sesión en Office 365).
2. En una pestaña independiente del explorador, vaya a Azure Portal ([https://portal.azure.com](https://portal.azure.com/)).
3. Si es la primera vez que configura Azure Information Protection, consulte [estas instrucciones](https://docs.microsoft.com/information-protection/deploy-use/configure-policy#to-access-the-azure-information-protection-blade-for-the-first-time).
4. En el panel de lista, haga clic en **Más servicios**, escriba **information** y haga clic en **Azure Information Protection**.
5. En la hoja **Azure Information Protection**, haga clic en **Directivas con ámbito > + Agregar una directiva**.
6. Escriba un nombre de la nueva directiva en **Nombre de la directiva** y una descripción en **Descripción**.
7. Haga clic en **Seleccionar a qué usuarios o grupos se aplica esta directiva > Usuarios o grupos** y, luego, seleccione el grupo de acceso de los miembros del sitio para su sitio de grupo de SharePoint Online extremadamente confidencial.
8. Haga clic en **Seleccionar > Aceptar**.
9. Para la etiqueta **Extremadamente confidencial**, haga clic en el botón de puntos suspensivos (...) y, luego, en **Agregar una subetiqueta**.
10. Escriba un nombre para la subetiqueta en **Nombre** y una descripción en **Descripción**.
11. En **Establecer permisos para documentos y correos electrónicos que contengan esta etiqueta**, haga clic en **Proteger**.
12. En la sección **Protección**, haga clic en **Azure (clave de nube)**.
13. En la hoja **Protección**, en **Configuración de protección**, haga clic en **+ Agregar permisos**.
14. En la hoja **Agregar permisos**, en **Especificar usuarios y grupos**, haga clic en **+ Examinar directorio**.
15. En el panel **Usuarios y grupos de AAD**, seleccione el grupo de acceso de miembros del sitio para el sitio de grupo de SharePoint Online extremadamente confidencial y haga clic en **Seleccionar**.
16. En **Choose permissions from the preset** (Elegir permisos entre los preestablecidos), desactive las casillas **Print, Copy and extract content** (Imprimir, copiar y extraer contenido) y **Reenviar**.
17. Haga clic en **Aceptar** dos veces.
18. En la hoja **Subetiqueta**, configure los distintivos visuales según sea necesario y haga clic en **Guardar**.
19. Cierre la hoja de directiva en la que acaba de agregar el ámbito.
20. En la hoja **Azure Information Protection: directivas con ámbito**, haga clic en **Publicar** y, luego, en **Sí**.

Esta es la configuración resultante del sitio de grupo de SharePoint Online extremadamente confidencial.

 ![Extremadamente confidencial](./media/protect-files-with-aip/hc_w_aip.png)

Ya está listo para empezar a crear documentos y protegerlos con Azure Information Protection y su nueva etiqueta.

Debe [instalar el cliente de Azure Information Protection](https://docs.microsoft.com/information-protection/rms-client/install-client-app) en el dispositivo o equipo basado en Windows. Puede generar scripts y automatizar la instalación, o bien pueden hacerlo los usuarios manualmente. 

Para obtener más información, vea los recursos siguientes:

* [El lado cliente de Azure Information Protection](https://docs.microsoft.com/information-protection/rms-client/use-client)
* [Instalación del cliente de Azure Information Protection](https://docs.microsoft.com/information-protection/rms-client/client-admin-guide)
* [Página de descarga para la instalación manual](https://www.microsoft.com/download/details.aspx?id=53018)

Una vez instalado, los usuarios ejecutan y luego inician sesión desde una aplicación de Office (como Microsoft Word) con su cuenta de Office 365. La nueva barra de **Information Protection** le permitirá seleccionar la etiqueta. 

Asegúrese de que los usuarios conozcan qué sitio de grupo de SharePoint Online y qué etiqueta deben usar para proteger sus archivos extremadamente confidenciales.

>[!Note]
>Si tiene varios sitios de grupo de SharePoint Online extremadamente confidenciales, deberá crear varias directivas con ámbito de Azure Information Protection que contengan subetiquetas con la configuración anterior, con los permisos de cada subetiqueta establecidos en el grupo de acceso de miembros de sitio de un equipo de grupo concreto de SharePoint Online.
>

## <a name="next-steps"></a>Pasos siguientes

[Adopción de la nube y soluciones híbridas](https://technet.microsoft.com/library/dn262744.aspx)
