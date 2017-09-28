---
title: "Proteger archivos con etiquetas y prevención de pérdida de datos de Office 365 | Microsoft Docs"
description: "Aplique directivas de etiquetas y prevención de pérdida de datos (DLP) de Office 365 a sitios de grupo de SharePoint Online con distintos niveles de protección de la información."
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
ms.openlocfilehash: e9138c2c563c8081f075ffa3e65ecf917456c23c
ms.sourcegitcommit: 5b34af60e3aac19d618f1c6297da91e2c050a374
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/09/2017
---
# <a name="protect-files-with-office-365-labels-and-data-loss-prevention"></a>Proteger archivos con etiquetas y prevención de pérdida de datos de Office 365

## <a name="introduction"></a>Introducción
Siga los pasos de este artículo para diseñar e implementar directivas de etiquetas y prevención de pérdida de datos (DLP) de Office 365 para sitios de grupo de base de referencia, confidenciales y extremadamente confidenciales de SharePoint Online. Para más información sobre estos tres niveles de protección, vea [Proteger sitios y archivos de SharePoint Online](secure-sharepoint-online-sites-and-files.md).

## <a name="office-365-labels-for-your-sharepoint-online-sites"></a>Etiquetas de Office 365 para los sitios de SharePoint Online
Al crear y asignar etiquetas de Office 365 a sitios de grupo de SharePoint Online, debe completar las tres fases siguientes.

### <a name="phase-1-determine-the-office-365-label-names"></a>Fase 1: Determinar los nombres de etiqueta de Office 365

En esta fase se determinan los nombres de las etiquetas de Office 365 para los cuatro niveles de protección de la información aplicados a los sitios de grupo de SharePoint Online. En la siguiente tabla se indican los nombres recomendados para cada nivel.
 
|**Nivel de protección de sitio de grupo de SharePoint Online**|**Nombre de etiqueta**|
|:-----|:-----|
|Base de referencia-Público|Interno público|
|Base de referencia-Privado|Private|
|Confidencial|Confidencial|
|Extremadamente confidencial|Extremadamente confidencial|

### <a name="phase-2-create-the-office-365-labels"></a>Fase 2: Crear las etiquetas de Office 365
En esta fase se crean y luego se publican las etiquetas determinadas para los diferentes niveles de protección de la información.

Para crear las etiquetas, puede usar el Centro de administración de Office 365 o Microsoft PowerShell.

**Crear etiquetas de Office 365 con el Centro de administración de Office 365**

1. Inicie sesión en el **portal de Office 365** con una cuenta que tenga el rol Administrador de seguridad o Administrador de la compañía. Para obtener ayuda, vea [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4) (Dónde iniciar sesión en Office 365).
2. En la pestaña **Inicio de Microsoft Office**, haga clic en el **icono Administración**.
3. En la nueva pestaña **Centro de administración de Office** del explorador, haga clic en **Centros de administración > Seguridad y cumplimiento**.
4. En la nueva pestaña **Inicio – Seguridad y cumplimiento** del explorador, haga clic en **Clasificaciones > Etiquetas**.
5. En el panel **Inicio > Etiquetas**, haga clic en **Crear una etiqueta**.
6. En el panel de **nombre de la etiqueta**, escriba el nombre de la etiqueta y haga clic en **Siguiente**.
7. En el panel **Configuración de etiquetas**, haga clic en **Siguiente**.
8. En el panel **Revise su configuración**, haga clic en **Crear esta etiqueta** y luego en **Cerrar**.
9. Repita los pasos del 5 al 8 para las etiquetas adicionales.

**Crear etiquetas de Office 365 con PowerShell**

1. [Conéctese al Centro de seguridad y cumplimiento de Office 365 mediante PowerShell remoto](http://go.microsoft.com/fwlink/?LinkID=799771&clcid=0x409) y especifique las credenciales de una cuenta que tenga el rol Administrador de seguridad o Administrador de la compañía.
2. Rellene la lista de nombres de etiqueta y luego ejecute estos comandos en el símbolo del sistema de PowerShell:

```
$labelNames=@([list of label names, each enclosed in quotes and separated by commas])
ForEach ($element in $labelNames){ New-ComplianceTag -Name $element }
```

Luego siga estos pasos para publicar las nuevas etiquetas de Office 365.

1. En el panel **Inicio > Etiquetas** del Centro de seguridad y cumplimiento, haga clic en **Publicar etiquetas**.
2. En el panel para **elegir las etiquetas que se van a publicar**, haga clic para **elegir las etiquetas que se van a publicar**.
3. En el panel de **elección de etiquetas**, haga clic en **Agregar** y seleccione las cuatro etiquetas.
4. Haga clic en **Listo**.
5. En el panel para **elegir las etiquetas que se van a publicar**, haga clic en **Siguiente**.
6. En el panel **Elegir ubicaciones**, haga clic en **Siguiente**.
7. En el panel **Escriba un nombre para la directiva**, escriba un nombre para el conjunto de etiquetas en **Nombre** y haga clic en **Siguiente**.
8. En el panel **Revise su configuración**, haga clic para **publicar las etiquetas** y luego haga clic en **Cerrar**.

### <a name="phase-3-apply-the-office-365-labels-to-your-sharepoint-online-sites"></a>Fase 3: Aplicar las etiquetas de Office 365 a los sitios de SharePoint Online
Siga estos pasos para aplicar las etiquetas de Office 365 a las carpetas de documentos de los sitios de grupo de SharePoint Online.

1. En la pestaña **Inicio de Microsoft Office** del explorador, haga clic en el icono **SharePoint**.
2. En la nueva pestaña **SharePoint** del explorador, haga clic en un sitio al que haya que asignarle una etiqueta de Office 365.
3. En la nueva pestaña del sitio de SharePoint del explorador, haga clic en **Documentos**.
4. Haga clic en el icono de configuración y luego en **Configuración de biblioteca**.
5. En **Permisos y administración**, haga clic para **aplicar la etiqueta a los elementos de esta biblioteca**.
6. En **Configuración-Aplicar etiqueta**, seleccione la etiqueta adecuada y haga clic en **Guardar**.
7. Cierre la pestaña del sitio de SharePoint Online.
8. Repita los pasos anteriores para asignar etiquetas de Office 365 a otros sitios de SharePoint Online.

A continuación se muestra la configuración resultante.

 ![Protección de base de referencia](./media/protect-files-with-o365-labels-dlp/site_labels.png)

### <a name="dlp-policies-for-your-sharepoint-online-sites"></a>Directivas de DLP para los sitios de SharePoint Online
Siga estos pasos para configurar una directiva de DLP que notifique a los usuarios cada vez que compartan un documento en un sitio de grupo confidencial de SharePoint Online de fuera de la organización.

1. En la pestaña **Inicio de Microsoft Office** del explorador, haga clic en el icono **Seguridad y cumplimiento**.
2. En la nueva pestaña **Seguridad y cumplimiento** del explorador, haga clic en **Prevención de pérdida de datos > Directiva**.
3. En el panel **Prevención de pérdida de datos**, haga clic en **+ Crear una directiva**.
4. En el panel **Start with a template or create a custom policy** (Empezar con una plantilla o crear una directiva personalizada), haga clic en **Personalizada** y luego en **Siguiente**.
5. En el panel **Escriba un nombre para la directiva**, escriba el nombre de la directiva de DLP de nivel confidencial en Nombre y haga clic en **Siguiente**.
6. En el panel **Elegir ubicaciones**, haga clic para que se le **permita elegir ubicaciones concretas** y luego haga clic en **Siguiente**.
7. En la lista de ubicaciones, deshabilite las ubicaciones **Correo electrónico de Exchange** y **Cuentas de OneDrive** y haga clic en **Siguiente**.
8. En el panel **Customize the types of sensitive info you want to protect** (Personalizar los tipos de información confidencial que quiere proteger), haga clic en **Editar**.
9. En el panel **Choose the types of content to protect** (Elegir los tipos de contenido que se va a proteger), haga clic en **Agregar** en el cuadro desplegable y luego en **Etiquetas**.
10. En el panel **Etiquetas**, haga clic en **+ Agregar**, seleccione la etiqueta **Confidencial**, haga clic en **Agregar** y luego en **Listo**.
11. En el panel **Choose the types of content to protect** (Elegir los tipos de contenido que se va a proteger), haga clic en **Guardar**.
12. En el panel **Customize the types of sensitive info you want to protect** (Personalizar los tipos de información confidencial que quiere proteger), haga clic en **Siguiente**.
13. En el panel **What do you want to do if we detect sensitive info?** (Qué quiere hacer si se detecta información confidencial), haga clic para **personalizar la sugerencia y el correo electrónico**.
14. En el panel **Customize policy tips and email notifications** (Personalizar sugerencias de directiva y notificaciones de correo electrónico), haga clic en **Customize the policy tip text** (Personalizar el texto de la sugerencia de directiva).
15. En el cuadro de texto, escriba o pegue lo siguiente y haga clic en **Aceptar**.
 * Para compartir con un usuario de fuera de la organización, descargue el archivo y luego ábralo. Haga clic en **Archivo**, en **Proteger documento**, en **Cifrar con contraseña** y luego especifique una contraseña segura. Envíe la contraseña en un correo electrónico diferente u otro medio de comunicación.
 * O bien escriba o pegue la sugerencia de directiva propia que indique a los usuarios cómo compartir un archivo fuera de la organización.
16. En el panel sobre **qué quiere hacer si se detecta información confidencial**, desactive la casilla de verificación para **evitar que los usuarios puedan compartir y restringir el acceso al contenido compartido** y haga clic en **Siguiente**.
17. En el panel sobre si **quiere activar la directiva o probarla primero**, haga clic en **Sí** para activarla inmediatamente y luego haga clic en **Siguiente**.
18. En el panel **Revise su configuración**, haga clic en **Crear** y luego en **Cerrar**.

A continuación se muestra la configuración resultante para sitios de grupo confidenciales de SharePoint Online.

 ![Protección confidencial](./media/protect-files-with-o365-labels-dlp/sensitive_w_dlp.png)

Ahora siga estos pasos para configurar una directiva de DLP que impida a los usuarios compartir un documento en un sitio de grupo extremadamente confidencial de SharePoint Online de fuera de la organización.

1. En la pestaña **Inicio de Microsoft Office** del explorador, haga clic en el icono **Seguridad y cumplimiento**.
2. En la nueva pestaña **Seguridad y cumplimiento** del explorador, haga clic en **Prevención de pérdida de datos > Directiva**.
3. En el panel **Prevención de pérdida de datos**, haga clic en **+ Crear una directiva**.
4. En el panel para **empezar con una plantilla o crear una directiva personalizada**, haga clic en **Personalizada** y luego en **Siguiente**.
5. En el panel **Escriba un nombre para la directiva**, escriba el nombre de la directiva de DLP de nivel extremadamente confidencial en **Nombre** y haga clic en **Siguiente**.
6. En el panel **Elegir ubicaciones**, haga clic para que se le **permita elegir ubicaciones concretas** y luego haga clic en **Siguiente**.
7. En la lista de ubicaciones, deshabilite las ubicaciones **Correo electrónico de Exchange** y **Cuentas de OneDrive** y haga clic en **Siguiente**.
8. En el panel para **personalizar los tipos de información confidencial que quiere proteger**, haga clic en **Editar**, luego, en el panel para **elegir los tipos de contenido que se va a proteger**, haga clic en **Agregar ** en el cuadro desplegable y luego en **Etiquetas**.
9.  En el panel **Etiquetas**, haga clic en **+ Agregar**, seleccione la etiqueta **Extremadamente confidencial**, haga clic en **Agregar** y luego en **Listo**.
10. En el panel para **elegir los tipos de contenido que se va a proteger**, haga clic en **Guardar** y, luego, en el panel para **personalizar los tipos de información confidencial que quiere proteger**, haga clic en **Siguiente**.
11. En el panel sobre **qué quiere hacer si se detecta información confidencial**, haga clic para **personalizar la sugerencia y el correo electrónico**.
12. En el panel **Customize policy tips and email notifications** (Personalizar sugerencias de directiva y notificaciones de correo electrónico), haga clic en **Customize the policy tip text** (Personalizar el texto de la sugerencia de directiva).
13. En el cuadro de texto, escriba o pegue lo siguiente y haga clic en Aceptar:
 * Para compartir con un usuario de fuera de la organización, descargue el archivo y luego ábralo. Haga clic en **Archivo**, en **Proteger documento**, en **Cifrar con contraseña** y luego especifique una contraseña segura. Envíe la contraseña en un correo electrónico diferente u otro medio de comunicación.
 * O bien escriba o pegue la sugerencia de directiva propia que indique a los usuarios cómo compartir un archivo fuera de la organización.
14. En el panel sobre **qué quiere hacer si se detecta información confidencial**, seleccione para **exigir una justificación de empresa para invalidar** y haga clic en **Siguiente**.
15. En el panel sobre si **quiere activar la directiva o probarla primero**, haga clic en **Sí** para activarla inmediatamente y luego haga clic en **Siguiente**.
16. En el panel **Revise su configuración**, haga clic en **Crear** y luego en **Cerrar**.

A continuación se muestra la configuración resultante para sitios de grupo extremadamente confidenciales de SharePoint Online.

 ![Protección extremadamente confidencial](./media/protect-files-with-o365-labels-dlp/hc_w_dlp.png)

Para más información, vea [Protección de archivos con AIP](protect-files-with-aip.md).

## <a name="next-steps"></a>Pasos siguientes
[Instrucciones de seguridad de Microsoft para campañas políticas, organizaciones sin ánimo de lucro y otras organizaciones ágiles](https://technet.microsoft.com/library/mt493213.aspx)

[Proteger sitios y archivos de SharePoint Online](secure-sharepoint-online-sites-and-files.md)

[Protección de sitios de SharePoint Online en un entorno de prueba y desarrollo](secure-sharepoint-online-sites-dev-test.md)

[Adopción de la nube y soluciones híbridas](https://technet.microsoft.com/library/dn262744.aspx)






