<properties pageTitle="Comandos de Git para crear un nuevo artículo o actualizar uno existente" description="Pasos para usar los repositorios de GitHub con contenido técnico sobre Azure." metaKeywords="" services="" solutions="" documentationCenter="" authors="v-jocgar" videoId="" scriptId="" manager="robmazz" />

<tags ms.service="contributor-guide" ms.devlang="" ms.topic="article" ms.tgt_pltfrm="" ms.workload="" ms.date="02/24/2016" ms.author="v-jocgar" />

# Uso de Git

To do:
- [ ] #22 Replace EMS URL for completed articles (see end of instructions)

## Proceso estándar (uso a partir de una rama)
Siga los pasos que se describen aquí para crear una rama local de trabajo en el equipo de forma que pueda diseñar un nuevo artículo destinado a la sección de documentación técnica de Microsoft.com/ems o actualizar uno existente.

1. Inicie Git Bash. 

2. Cambie al repositorio `emdocs`:

        cd emdocs
        
3. Cree una nueva rama de trabajo:

        git checkout <branchname>

4. Cree una rama local de trabajo nueva:

        git pull origin master:<branchname>

5. Cree el nuevo artículo o modifique uno que ya exista. Use Atom (http://atom.io) como editor de Markdown (o el editor que prefiera) para crear y abrir archivos de Markdown nuevos. Una vez que haya creado o modificado el artículo y las imágenes, avance al siguiente paso.

6. Agregue y confirme los archivos nuevos que haya creado:

        git add <path-to-file>
        git commit –m "<comment>"
        
   O bien confirme únicamente los archivos concretos que haya modificado:

        git commit -a –m "<comment>"

7. Notifique a su origen la creación de la rama local de trabajo:

        git push origin <branchname>

8. Inserte los cambios en su rama de GitHub:

        git push origin <branchname>

9. Cuando haya finalizado, si desea enviar el contenido a la rama principal para su almacenamiento provisional, validación o publicación, en la interfaz de usuario de GitHub, cree una solicitud de incorporación de cambios de su rama a la principal.

10. El destinatario de la solicitud de incorporación de cambios revisará la propuesta, la comentará o la aceptará. 

11. De forma opcional, puede comprobar el artículo publicado o los cambios en
<span style="color:red;">Need correct URL for viewing published articles.</span>
 http://docs.microsoft.com/ems/articles/name-of-your-article-without-the-MD-extension


<!--HONumber=Mar16_HO1-->


