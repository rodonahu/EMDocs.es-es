---
title: "Protección de archivos y sitios de SharePoint Online | Microsoft Docs"
description: "Recomendaciones de configuración para proteger archivos en los sitios de grupo de SharePoint Online en Office 365"
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
ms.openlocfilehash: 1bfa989d3929092c254972d3066246e1548ce198
ms.sourcegitcommit: 684c942047754e93378e271f5b1a659a9752f0ba
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2017
---
# <a name="secure-sharepoint-online-sites-and-files"></a>Protección de archivos y sitios de SharePoint Online

En este artículo se ofrecen recomendaciones para configurar la protección de archivos y sitios de grupo de SharePoint Online de manera que se equilibre la seguridad con la facilidad de colaboración. Aquí se definen cuatro configuraciones distintas, empezando por un sitio público dentro de la organización con las directivas de uso compartido más abiertas. Cada configuración adicional representa un paso significativo para la protección, pero a costa de que el conjunto de usuarios pertinente pierda capacidad de acceder a los recursos y colaborar en ellos. 

Use estas recomendaciones como punto de partida y ajuste las configuraciones para satisfacer las necesidades de su organización. 

Las configuraciones que se explican en este artículo concuerdan con las recomendaciones de Microsoft para los tres niveles de protección de datos, identidades y dispositivos:

* Protección de base de referencia
* Protección confidencial
* Protección extremadamente confidencial

Para más información sobre estos niveles y capacidades recomendadas para cada nivel, vea los siguientes recursos. 

* [Protección de identidades y dispositivos para Office 365](https://technet.microsoft.com/library/28986107-e2fb-4116-bfdd-f66d751a7c16#BKMK_O365IDP)
* [Soluciones de protección de archivos en Office 365](https://technet.microsoft.com/library/28986107-e2fb-4116-bfdd-f66d751a7c16#BKMK_O365fileprotect)

## <a name="capability-overview"></a>Introducción a las capacidades
Las recomendaciones para sitios de grupo de SharePoint Online abarcan toda una variedad de capacidades de Office 365. Para sitios extremadamente confidenciales, se recomienda Azure Information Protection. Está incluido en Enterprise Mobility + Security (EMS). 

En este diagrama se muestran las configuraciones recomendadas para cuatro sitios de grupo de SharePoint Online.

 ![Configuraciones de SharePoint recomendadas](./media/secure-sharepoint-online-sites-and-files/capabilityoverview.png)

Como se muestra:

* La protección de base de referencia incluye dos opciones para los sitios de grupo de SharePoint Online: un sitio público y un sitio privado. Los sitios públicos son aquellos visibles y accesibles por cualquier persona de la organización. Los sitios privados solo pueden detectarlos y acceder a ellos los miembros del sitio. Estas dos configuraciones de sitio permiten compartir fuera del grupo. 
* Los sitios para protección confidencial y extremadamente confidencial son sitios privados con acceso limitado solamente a los miembros de grupos específicos.
* Con las etiquetas de Office 365, se pueden clasificar los datos con un nivel de protección necesario. Cada sitio de grupo de SharePoint Online está configurado para etiquetar automáticamente los archivos de bibliotecas de documentos con una etiqueta predeterminada para el sitio. Las etiquetas de este ejemplo son Interno público, Privado, Confidencial y Extremadamente confidencial, que se corresponden con las cuatro configuraciones de sitio. Los usuarios pueden cambiar las etiquetas, pero esta configuración garantiza que todos los archivos reciben una etiqueta predeterminada.
* Las directivas de prevención de pérdida de datos (DLP) se configuran para que las etiquetas Confidencial y Extremadamente confidencial de Office 365 puedan advertir o prevenir a los usuarios cuando intentan enviar estos tipos de archivo fuera de la organización.
* Para los sitios configurados con protección extremadamente confidencial, Azure Information Protection cifra y concede permisos para los archivos.

## <a name="tenant-wide-settings-for-sharepoint-online-and-onedrive-for-business"></a>Configuración de todos los inquilinos para SharePoint Online y OneDrive para la Empresa
SharePoint Online y OneDrive para la Empresa incluyen opciones de configuración de todos los inquilinos que afectan a todos los sitios y usuarios. Algunas de estas opciones también se pueden ajustar en el nivel de sitio para que sea más restrictivo (pero no para que lo sea menos). En esta sección se describe la configuración de todos los inquilinos que afecta a la seguridad y la colaboración. 

### <a name="sharing"></a>Uso compartido
Para esta solución, se recomienda la siguiente configuración de todos los inquilinos:

* Mantenga la directiva de uso compartido predeterminada, que permite compartir con todos los tipos de cuenta, incluso de forma anónima.
* Establezca la expiración de los vínculos anónimos, si así lo quiere.
* Establezca en Interno el tipo de vínculo predeterminado para el uso compartido. De esta manera se previene la pérdida accidental de datos fuera de la organización.

Aunque pueda parecer contradictorio permitir el uso compartido externo, este enfoque proporciona más control sobre el uso compartido de archivos en comparación con el envío de archivos por correo electrónico. SharePoint Online y Outlook funcionan conjuntamente para proporcionar una colaboración segura en los archivos. 

* De manera predeterminada, Outlook comparte un vínculo a un archivo en lugar de enviar el archivo por correo electrónico. 
* Con SharePoint Online y OneDrive para la Empresa, es muy fácil compartir vínculos a archivos con colaboradores que se encuentran tanto dentro como fuera de la organización.

También tiene controles que ayudan a regir el uso compartido externo. Por ejemplo, puede:

* Deshabilitar un vínculo de invitado anónimo.
* Revocar el acceso de usuario a un sitio.
* Ver quién tiene acceso a un sitio o documento específico.
* Establecer la expiración de vínculos anónimos de uso compartido (configuración de inquilino).
* Limitar quién puede compartir fuera de la organización (configuración de inquilino).

### <a name="use-external-sharing-together-with-data-loss-prevention-dlp"></a>Combinar el uso compartido externo con la prevención de pérdida de datos (DLP)
Si no permite el uso compartido externo, los usuarios con necesidades de negocio encontrarán métodos y herramientas alternativas. Microsoft recomienda combinar el uso compartido externo con directivas DLP para proteger archivos confidenciales y extremadamente confidenciales.

### <a name="device-access-settings"></a>Configuración de acceso a dispositivos
La configuración de acceso a dispositivos para SharePoint Online y OneDrive para la Empresa permite determinar si el acceso está limitado solo al explorador (no se pueden descargar archivos) o el acceso está bloqueado. Esta configuración se encuentra actualmente en First Release y se aplica en todo el inquilino. Próximamente se ofrecerá la capacidad de configurar directivas de acceso a dispositivos en el nivel de sitio. Para esta solución, se recomienda no usar la configuración de acceso de dispositivo que se aplica en todo el inquilino.

Para usar la configuración de acceso a dispositivos mientras se encuentra en First Release: [Configurar las opciones de los programas Estándar o First Release de Office 365](https://support.office.com/article/Set-up-the-Standard-or-First-Release-options-in-Office-365-3B3ADFA4-1777-4FF0-B606-FB8732101F47).

### <a name="onedrive-for-business"></a>OneDrive para la Empresa
Revise esta configuración para decidir si quiere cambiar la configuración predeterminada para los sitios de OneDrive para la Empresa. Actualmente, las configuraciones de acceso a dispositivos y de uso compartido están duplicadas desde el centro de administración de SharePoint Online y se aplican a ambos entornos.

## <a name="sharepoint-team-site-configuration"></a>Configuración del sitio de grupo de SharePoint
En la tabla siguiente se resume la configuración para cada uno de los sitios de grupo que se han descrito en este artículo. Use estas configuraciones como punto de partida y ajuste los tipos de sitio y las configuraciones para satisfacer las necesidades de la organización. No todas las organizaciones necesitan todos los tipos de sitio. El número de organizaciones que necesita una protección extremadamente confidencial es muy reducido.

| |**Protección de base de referencia n.º 1**|**Protección de base de referencia n.º 2**|**Protección confidencial**|**Extremadamente confidencial**|
|:-----|:-----|:-----|:-----|:-----|
|Descripción|Colaboración y detección abierta dentro de la organización.|Grupo y sitio privado con uso compartido permitido fuera del grupo.|Sitio aislado, en el que se definen niveles de acceso según la pertenencia a grupos específicos. Solo se permite el uso compartido a los miembros del sitio. DLP avisa a los usuarios cuando intentan enviar archivos fuera de la organización.|Sitio aislado + cifrado de archivos y permisos con Azure Information Protection. DLP impide a los usuarios enviar archivos fuera de la organización.|
|Sitio de grupo público o privado|Público|Private|Private|Private|
|¿Quién tiene acceso?|Todos los usuarios de la organización, incluidos los usuarios B2B y usuarios invitados.|Solo los miembros del sitio. Otros usuarios pueden pedir acceso.|Solo los miembros del sitio. Otros usuarios pueden pedir acceso.|Solo los miembros. Otros usuarios no pueden pedir acceso.|
|Controles de uso compartido en el nivel de sitio|Uso compartido permitido con cualquier usuario. Configuración predeterminada.    |Uso compartido permitido con cualquier usuario. Configuración predeterminada.|Los miembros no pueden compartir el acceso al sitio. <br>Los usuarios que no son miembros pueden pedir acceso al sitio, pero estas solicitudes deben ser supervisadas por un administrador del sitio.|Los miembros no pueden compartir el acceso al sitio. <br>Los usuarios que no son miembros no pueden pedir acceso al sitio o al contenido.|
|Controles de acceso a dispositivos en el nivel de sitio|Sin controles adicionales.|Sin controles adicionales.|Pronto se incorporarán controles de nivel de sitio, que impiden a los usuarios descargar archivos en dispositivos no compatibles o que no están unidos a ningún dispositivo. Esto permite solamente el acceso de explorador desde los demás dispositivos.|Pronto se incorporarán controles de nivel de sitio, que bloquean la descarga de archivos en dispositivos no compatibles o que no están unidos a ningún dominio.|
|Etiquetas de Office 365|Interno público|Private|Confidencial|Extremadamente confidencial|
|Directivas DLP|||Advierten a los usuarios cuando se envían archivos etiquetados como Confidenciales fuera de la organización. <br>Para bloquear el uso compartido externo de tipos de datos confidenciales, como números de tarjeta de crédito u otros datos personales, puede configurar directivas DLP adicionales para estos tipos de datos (incluidos los tipos de datos personalizados que configure).|Impiden a los usuarios enviar archivos etiquetados como Extremadamente confidencial fuera de la organización. Permiten a los usuarios anular esto si proporcionan una justificación que incluya el nombre del usuario con el que van a compartir el archivo.|
|Azure Information Protection||||Con Azure Information Protection se puede cifrar y conceder permisos a los archivos automáticamente. Esta protección viaja con los archivos en caso de que estos se pierdan. Office 365 no puede leer archivos cifrados con Azure Information Protection. Además, las directivas DLP solo pueden trabajar con los metadatos (incluidas las etiquetas), pero no con el contenido de estos archivos (por ejemplo, números de tarjeta de crédito incluidos en los archivos).|

Para consultar los pasos necesarios para la implementación de los cuatro tipos diferentes de sitios de grupo de SharePoint Online en esta solución, consulte [Implementar sitios con tres niveles de protección](deploy-sites-for-three-tiers-of-protection.md).

Para obtener instrucciones detalladas para una configuración de demostración, prueba de concepto o prueba y desarrollo, consulte [Protección de sitios de SharePoint Online en un entorno de prueba y desarrollo](secure-sharepoint-online-sites-dev-test.md).

## <a name="office-365-classification-and-labels"></a>Clasificación y etiquetas de Office 365
Se recomienda usar etiquetas de Office 365 para entornos con datos confidenciales. Después de configurar y publicar las etiquetas de Office 365, puede hacer esto:

* Aplicar una etiqueta predeterminada a una biblioteca de documentos en un sitio de grupo de SharePoint Online, para que todos los documentos en esa biblioteca obtengan la etiqueta predeterminada. 
* Aplicar etiquetas a contenido automáticamente si coincide con determinadas condiciones.
* Crear directivas DLP basadas en etiquetas de Office 365.
* Permitir que las personas de la organización apliquen manualmente una etiqueta al contenido de grupos de Outlook en la Web, Outlook 2010 y versiones posteriores, OneDrive para la Empresa, SharePoint Online y Office 365. A menudo, los usuarios son los que mejor saben con qué tipo de contenido están trabajando, de modo que pueden clasificarlo y aplicar la directiva de DLP adecuada.

 ![Etiquetas de Office 365](./media/secure-sharepoint-online-sites-and-files/labels.png)
 
Como se muestra, esta solución incluye la creación de las siguientes etiquetas:

* Extremadamente confidencial
* Confidencial
* Private
* Interno público

Estas etiquetas se asignan a los sitios recomendados en las ilustraciones y los gráficos antes citados en este artículo. Esta solución recomienda configurar las directivas DLP para evitar la filtración de archivos etiquetados como Confidenciales y Extremadamente confidenciales a miembros ajenos a la organización.

Para consultar los pasos necesarios para configurar etiquetas de Office 365 y directivas DLP en esta solución, consulte [Protect SharePoint Online files with Office 365 labels and DLP](protect-files-with-o365-labels-dlp.md) (Protección de archivos de SharePoint Online con etiquetas y directivas DLP de Office 365).

Para obtener instrucciones detalladas para una configuración de demostración, prueba de concepto o prueba y desarrollo, consulte [Protección de sitios de SharePoint Online en un entorno de prueba y desarrollo](secure-sharepoint-online-sites-dev-test.md).

## <a name="azure-information-protection"></a>Azure Information Protection
Con Azure Information Protection, puede aplicar etiquetas y protecciones a los archivos para que acompañen a los archivos allá donde vayan. Para esta solución, se recomienda usar una directiva con ámbito de Azure Information Protection y una subetiqueta de la etiqueta Extremadamente confidencial para conceder permisos y cifrar los archivos que deben protegerse con el máximo nivel de seguridad. 

Tenga en cuenta que, cuando se aplica el cifrado de Azure Information Protection a los archivos almacenados en Office 365, el servicio no puede procesar el contenido de estos archivos. No funcionan algunas características de colaboración, como la coautoría, eDiscovery, la búsqueda y Delve. Las directivas DLP solo pueden trabajar con los metadatos (incluidas las etiquetas de Office 365), pero no con el contenido de estos archivos (por ejemplo, números de tarjeta de crédito incluidos en los archivos).

 ![Etiquetas de Office 365](./media/secure-sharepoint-online-sites-and-files/azureinfoprotect.png)

Como se muestra:

* La configuración de las directivas y etiquetas de Azure Information Protection se realiza desde el portal de Microsoft Azure. Se recomienda configurar una subetiqueta de una directiva con ámbito.
* Las etiquetas de Azure Information Protection se muestran como una barra de herramientas de **Information Protection** en las aplicaciones de Office. 

### <a name="adding-permissions-for-external-users"></a>Agregar permisos a usuarios externos
Hay dos maneras de conceder a los usuarios externos el acceso a archivos protegidos con Azure Information Protection. En ambos casos, los usuarios externos deben tener una cuenta de Azure AD. Si los usuarios externos no son miembros de una organización que usa Azure AD, pueden obtener una cuenta de Azure AD como usuario individual a través de esta página de suscripción: [https://aka.ms/aip-signup](https://aka.ms/aip-signup).

* **Agregar usuarios externos a un grupo de Azure AD que se usa para configurar la protección de una etiqueta**.
 Primero debe agregar la cuenta como un usuario B2B en el directorio. Puede que el [almacenamiento en caché de pertenencia al grupo de Azure Rights Management](https://docs.microsoft.com/information-protection/plan-design/prepare#group-membership-caching-by-azure-rights-management) tarde un par de horas. Con este método, los permisos se conceden a todos los archivos protegidos que tengan la etiqueta (incluso los archivos protegidos antes de que se agregara un usuario al grupo de Azure AD).

* **Agregar usuarios externos directamente a la protección de etiqueta**.
 Puede agregar todos los usuarios de una organización (por ejemplo, Fabrikam.com), un grupo de Azure AD (por ejemplo, un grupo de finanzas dentro de una organización) o un usuario individual. Por ejemplo, puede agregar un equipo externo de reguladores para la protección de una etiqueta. Con este método, se conceden permisos solo a los archivos protegidos con la etiqueta después de que se haya agregado la entidad externa a la protección.

### <a name="deploying-and-using-azure-information-protection"></a>Implementación y uso de Azure Information Protection
Para consultar los pasos necesarios para configurar Azure Information Protection en esta solución, consulte [Protección de archivos de SharePoint Online con Azure Information Protection](protect-files-with-aip.md).

Para obtener instrucciones detalladas para una configuración de demostración, prueba de concepto o prueba y desarrollo, consulte [Protección de sitios de SharePoint Online en un entorno de prueba y desarrollo](secure-sharepoint-online-sites-dev-test.md).

## <a name="next-steps"></a>Pasos siguientes 

[Implementación de sitios para obtener tres niveles de protección](deploy-sites-for-three-tiers-of-protection.md)
