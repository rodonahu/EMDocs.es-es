<properties pageTitle="Pasos que seguir a la hora de retirar o cambiar el nombre de un artículo técnico sobre EMS" description="Pasos que seguir a la hora de retirar o cambiar el nombre de un artículo técnico sobre EMS." metaKeywords="" services="" solutions="" documentationCenter="" authors="v-jocgar" videoId="" scriptId="" manager="robmazz" />

<tags ms.service="contributor-guide" ms.devlang="" ms.topic="article" ms.tgt_pltfrm="" ms.workload="" ms.date="02/26/2016" ms.author="v-jocgar" />

# Pasos que seguir a la hora de cambiar el nombre de un artículo técnico de EMS o retirarlo

To do:
- [ ] #57 Confirm this is how retiring content will work for EMS. This seems more like an internal-only set of procedures. 
- [ ] #58 Confirm that external writers would be able to run a web analytics tool against Microsoft content. 
- [ ] #59 Test the procedure for finding cross-links in the repo.
- [ ] #60 Confirm the URL for the EMS Docs.  
- [ ] #61 Confirm that removing cross-links is possible for external writers. 
- [ ] #62 Confirm that an external writer could create a redirect.
- [ ] #63 Confirm that an external writer could delete an article from the repo.
- [ ] #64 Confirm that an external writer could request removal of Microsoft content from search engines.


<span style="color:red;">Confirm this is how retiring content will work for EMS. This seems more like an internal-only set of procedures. </span>
Esta guía está dirigida a expertos en la materia que figuran como los autores de un artículo que debe retirarse de la sección de documentación técnica de http://docs.microsoft.com/ems. Los pasos también se aplican si se le cambia el nombre a un archivo.

Los autores expertos en la materia deben seguir varios pasos para retirar de manera correcta el contenido de forma que la experiencia de los usuarios del sitio web no se vea afectada negativamente cuando se elimine el artículo del sitio. La eliminación del artículo o el cambio de nombre deben ser los últimos pasos.

Si es miembro de nuestra comunidad de EMS y cree que un artículo debería retirarse por cualquiera que sea el motivo, deje un comentario en él para informar al autor de los fallos.

## Paso 1: Administración de vínculos de entrada

Compruebe si existen vínculos de entrada al contenido que no sean de Microsoft. Con bastante frecuencia, algunos blogs, foros y otros tipos de contenidos de la Web incluyen vínculos a artículos. A menudo, puede trabajar con los propietarios del blog para modificar estos vínculos, así como eliminar o actualizar los que aparezcan en publicaciones de foros. <span style="color:red;">Confirm that external writers would be able to run a web analytics against Microsoft content. </span>Las herramientas para recopilar datos web de análisis pueden avisarle de la existencia de vínculos de entrada con un alto nivel de tráfico que debería administrar de este modo.

## Paso 2: Eliminación de todos los vínculos cruzados al artículo en el repositorio de contenido técnico
<span style="color:red;">Test the procedure for finding cross-links in the repo.</span>
1. Asegúrese de trabajar en una rama local actualizada: ejecute `git pull origin master` (o la variación correspondiente de este comando).

2.  <span style="color:red;">Confirm the paths in the repo.</span> Examine las carpetas \EMDocs\Solutions y \EMDocs\Token para buscar artículos y tokens que establezcan un vínculo al artículo que desea retirar. Asimismo, elimine los vínculos cruzados o reemplácelos por unos nuevos y adecuados. Puede servirse de una utilidad de búsqueda y reemplazo para encontrar los vínculos cruzados si la tiene instalada. En caso contrario, puede usar Windows PowerShell de forma gratuita. A continuación, se muestra cómo utilizar PowerShell para localizar los vínculos cruzados:

 a. Inicie Windows PowerShell.

 b. En el símbolo del sistema de PowerShell, cambie a la carpeta \EMDocs\Solutions:

 `cd \EMDocs\Solutions`

 c. Escriba este comando, que creará una lista con todos los archivos que contengan referencias al artículo que va a eliminar:

 `Get-ChildItem -Recurse -Include *.md* | Select-String "<the name of the topic you are deleting>" | group path | select name`

  Si prefiere enviar la lista con los nombres de los archivos a un archivo de texto (en este case, denominado "psoutput.txt"), puede realizar lo siguiente:

  `Get-ChildItem -Recurse -Include *.md* | Select-String "<the name of the topic you are deleting>" | group path | select name | Out-File C:\Users\<your account>\psoutput.txt`

3. Agregue y confirme todos los cambios, insértelos en su rama de origen y cree una solicitud de incorporación de cambios para mover los cambios de la rama de origen a la rama maestra del repositorio principal.

## Paso 3: Eliminación de todos los vínculos cruzados 
<span style="color:red;">Confirm that removing cross-links is possible for external writers. </span>
Si existen vínculos al artículo que provengan de otras páginas de <span style="color:red;">Confirm the URL for the EMS Docs. </span> http://docs.microsoft.com/ems, debe eliminarlos y crear un redireccionamiento para la página retirada, si procede. Tendrá que trabajar con la persona que mantiene y actualiza la página de aterrizaje de la documentación para la supervisión de este elemento. Si no sabe quién es, póngase en contacto con su partner del equipo de contenido. El usuario que mantiene y actualiza la página de aterrizaje de la documentación deberá llevar a cabo estas dos acciones:

1. En Visual Studio, debe analizar la solución web **completa** de EMS para localizar referencias cruzadas al archivo que se va a retirar. Tendrá que quitar estas referencias o reemplazarlas por la versión actualizada. Debe quitar los vínculos HTML, así como las cadenas de recursos relacionadas de los vínculos HTML. 

2. <span style="color:red;">Confirm that an external writer could create a redirect.</span>En caso de que exista un artículo de sustitución, redirija el contenido a este. 

3. Compruebe los cambios en el repositorio.

## Paso 4: Retirada del artículo
<span style="color:red;">Confirm that an external writer could delete an article from the repo.</span>
Una vez que haya completado los tres pasos anteriores y que los cambios se hayan hecho efectivos, puede eliminar el artículo del repositorio.

## Paso 5: Eliminación de páginas en caché de los motores de búsqueda
<span style="color:red;">Confirm that an external writer could request removal of Microsoft content from search engines.</span>
Siga este paso SOLO si el contenido debe eliminarse rápidamente por cuestiones legales o problemas graves con los clientes. Los procesos naturales de los motores de búsqueda son los encargados de la retirada de páginas de prioridad normal. Diríjase a las siguientes páginas web para quitar las páginas en caché de los motores de búsqueda:

[Bing](https://www.bing.com/webmaster/tools/content-removal?rflid=1)
[Google](https://www.google.com/webmasters/tools/removals?pli=1)


### Volver a la página principal

- [Artículo de información general](./../README.md)
- [Índice de artículos de la guía](./contributor-guide-index.md)


<!--HONumber=Mar16_HO1-->


