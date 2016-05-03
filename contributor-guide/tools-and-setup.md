<properties pageTitle="Instalación y configuración de herramientas de creación en GitHub" description="Herramientas y pasos para realizar las configuraciones necesarias con el fin de crear contenido de EMS en GitHub." services="contributor-guide" documentationCenter="" authors="v-jocgar" manager="robmazz" />

<tags ms.service="contributor-guide" ms.devlang="" ms.topic="article" ms.tgt_pltfrm="" ms.workload="" ms.date="02/25/2016" ms.author="v-jocgar" />

# Instalación y configuración de herramientas de creación en GitHub
To Do:
- [ ] #21 Entire procedure needs to be tested with a non-Microsoft account and computer. 

Siga los pasos de este artículo para configurar las herramientas con el fin de realizar contribuciones a la documentación técnica de EMS. 

- Si no está familiarizado con Git, le recomendamos consultar algunos términos de Git: [https://help.github.com/articles/github-glossary](https://help.github.com/articles/github-glossary).
- También le sugerimos que vea este conjunto de vídeos sobre [Git y GitHub Foundations](https://www.youtube.com/playlist?list=PLg7s6cbtAD15G8lNyoaYDuKZSKyJrgwB-). Son breves y fáciles de entender.  

## Instrucciones paso a paso

- [Creación de una cuenta de GitHub y configuración del perfil](#create-a-github-account-and-set-up-your-profile)
- [Permisos de GitHub](#permissions-in-github)
- [Instalación de Git para Windows](#install-git-for-windows)
- [Habilitación de la autenticación en dos fases](#enable-two-factor-authentication)
- [Creación de un token de acceso personal](#create-a-personal-access-token)
- [Instalación de un editor de marcado](#install-a-markdown-editor)
- [Configuración de Atom](#configure-atom)
- [Creación de una rama desde el repositorio](#create-a-branch-from-the-repository)
- [Establecimiento de una conexión remota de repositorio y configuración de las credenciales](#set-remote-repository-connection-and-configure-credentials)
- [Configuración local del nombre de usuario y correo electrónico](#configure-your-user-name-and-email-locally)
- [Pasos siguientes](#next-steps)

## Creación de una cuenta de GitHub y configuración del perfil

Para realizar contribuciones al contenido técnico de EMS, necesitará una cuenta de [GitHub](http://www.github.com).

- **Imagen de perfil**: una imagen suya (obligatorio).
- **Nombre**: el nombre y los apellidos (obligatorio).
- **Correo electrónico**: la dirección de correo electrónico (obligatorio).
- **Compañía**: su empresa (obligatorio).
- **Ubicación**: muestra su ubicación (obligatorio).

El perfil debe ser similar a este:

 ![Ejemplo de perfil de GitHub](./media/githubprofile.png)

## Permisos de GitHub

Cualquier persona que tenga una cuenta de GitHub puede realizar contribuciones al contenido técnico de EMS a través de nuestro repositorio público, que se encuentra en [http://www.github.com/microsoft/emdocs](http://www.github.com/microsoft/emdocs). Se requieren permisos especiales.

## Instalación de Git para Windows

Instale **Git para Windows** desde [http://git-scm.com/download/win](http://git-scm.com/download/win). Esta descarga instala el sistema de control de versiones de Git y Git Bash, la aplicación de línea de comandos que empleará para interactuar con el repositorio local de Git.

**Nota**
Este programa es distinto a "Github para Windows". "Github para Windows" es una herramienta basada en GUI diferente que también sirve, pero tendrá que investigar usted mismo cómo funciona. [https://windows.github.com/](https://windows.github.com/)) 

Durante la instalación, tendrá la oportunidad de seleccionar cómo interactuará con el repositorio de Github. Se recomienda que solo utilice Git desde Git Bash. 
 ![Ejemplo de perfil de GitHub](./media/gitbashinstall.png)

## Habilitación de la autenticación en dos fases

Tiene que habilitar la autenticación en dos fases (2FA) en su cuenta de GitHub si está trabajando en el repositorio de contenido privado. Para ello, siga las instrucciones del tema presentado a continuación de la Ayuda de GitHub:

- [Acerca de la autenticación en dos fases](https://help.github.com/articles/about-two-factor-authentication/)

## Creación de un token de acceso personal
El token de acceso personal autentica el usuario y el equipo en el que está usando GitHub.
1. En GitHub, haga clic en su imagen y, luego, en Configuración.
2. En la pestaña Token de acceso personal, haga clic en Generar nuevo token.
3. Proporcione al token una descripción. 
4. Establezca el ámbito. Le recomendamos tener acceso completo al repositorio y usuario; para ello, active las casillas de permiso.
5. Haga clic en Generar token.
6. Copie el token que se muestra y péguelo en un lugar seguro, como un correo electrónico o un documento de Word. Necesita este token para extraerlo e insertarlo en GitHub.

## Instalación de un editor de marcado

Creamos contenido usando una notación de "marcado" sencillo en los archivos, en lugar de complejo (HTML, XML, etc.). Por lo tanto, tendrá que instalar un editor de marcado. Nosotros usamos el marcado característico de GitHub. 

- **Atom**: la mayoría de los colaboradores usan el editor de marcado Atom de GitHub: [http://atom.io](http://atom.io). No se requiere una licencia para uso empresarial e incluye un corrector ortográfico. 
- **Bloc de notas**: puede utilizar el Bloc de notas si desea trabajar con una herramienta que consuma muy pocos recursos.
- **Prose**: se trata de un editor de marcado que consume pocos recursos, elegante, en línea y de código abierto que ofrece una vista previa. Visite [http://prose.io](http://prose.io) y autorice a Prose en el repositorio.
- **[Visual Studio Code](https://www.visualstudio.com/products/code-vs.aspx)**: la entrada de Microsoft en este mercado.
- **MarkdownPad 2**: puede usar [MarkdownPad 2](http://markdownpad.com/) gratis, pero si adquiere una licencia, puede ver el marcado característico de GitHub en la vista previa dinámica.  

## Configuración del editor de marcado Atom

Si utiliza Atom, debe configurar algunas opciones.

- Atom utiliza de forma predeterminada 2 espacios para pestañas, pero se recomienda 4 para que se visualice correctamente. Si deja el valor predeterminado en 2, el artículo tendrá un aspecto excelente en la vista previa local, pero no cuando se importe a docs.microsoft.com. Por lo tanto, configure Atom para utilizar 4 espacios: puede encontrar esta configuración en File (Archivo) -> Settings (Configuración) -> Editor Settings (Editor de configuración) -> Tab Length (Número de pestañas). 
- También le recomendamos activar la característica Soft Wrap (Ajuste flexible) en esta sección, que tiene la misma función que el ajuste automático de línea del Bloc de notas. 
- Para activar la vista previa de marcado, haga clic en Packages (Paquetes)->Markdown Preview (Vista previa de marcado)->Toggle Preview (Alternar vista previa). Puede usar Ctrl + Mayús + M para cambiar a la vista previa de HTML. 

## Creación de una rama desde el repositorio

Creación de una rama desde el repositorio en GitHub 

1. Abra Git Bash. 
2. En el símbolo del sistema, escriba el siguiente comando. 

        git clone https://[your GitHub user name]:[token]@github.com/microsoft/emdocs.git

Este comando crea un directorio `emdocs` en el equipo.  Si utiliza la ubicación predeterminada, estará en `c:\users\<your Windows user name>\emdocs`. Por ejemplo, este comando de clonación tendría un aspecto similar a esto:

        git clone https://smithj:b428654321d613773d423ef2f173ddf4a312345@github.com/microsoft/emdocs.git  

## Establecimiento de una conexión remota de repositorio y configuración de las credenciales

Configure Git para utilizar el id. de GitHub y el token de acceso personal de forma predeterminada para que no tenga que escribir o pegar manualmente ese token de acceso para cada acción de `push` o `pull`. 

Ejecute el siguiente comando en Git Bash:

        cd emdocs
        git remote –v 
        git remote remove origin
        git remote add origin http://<githubID>:<token>@github.com/microsoft/emdocs
        git remote -v

Esta operación tarda algún tiempo. Después de hacer esto, no tendrá que escribirlas de nuevo. Solo tendría que repetir el proceso de nuevo si configura las herramientas en otro equipo.

## Configuración local del nombre de usuario y correo electrónico

Para asegurarse de que aparece correctamente como colaborador, debe configurar el correo electrónico y el nombre de usuario localmente en Git.

1. Inicie Git Bash y cambiar a emdocs.
   ````
   cd emdocs
   ````
2. Configure el nombre de usuario para que coincida con su nombre tal y como se ha configurado en el perfil de GitHub:

    ````
    git config --global user.name "John Doe"
    ````
3. Configure el correo electrónico para que coincida con el correo electrónico principal designado en su perfil de GitHub:

    ````
    git config --global user.email "alias@example.com"
    ````
4. Escriba `git config -l` y revise la configuración local para asegurarse de que el nombre de usuario y correo electrónico de la configuración son correctos.

## Pasos siguientes

- Lea y siga las instrucciones de [Uso de Git](./work-with-git.md) para poder comenzar a crear contenido.


## Volver a la página principal

- [Artículo de información general](./../README.md)
- [Índice de artículos de la guía](./contributor-guide-index.md)


<!--Anchors-->
[Create a GitHub account and set up your profile]: #create-a-github-account-and-set-up-your-profile
[Permissions in GitHub]: #permissions-in-github
[Install Git for Windows]: #install-git-for-windows
[Enable two-factor authentication]: #enable-two-factor-authentication
[Create a personal access token]: #create-a-personal-access-token
[Install a markdown editor]: #install-a-markdown-editor
[Configure Atom]:#configure-atom
[Create a branch from the repository]: #create-a-branch-from-the-repository
[Set remote repository connection and configure credentials]: #set-remote-repository-connection-and-configure-credentials
[Configure your user name and email locally]: #configure-your-user-name-and-email-locally
[Next steps]: #next-steps

<!--HONumber=Mar16_HO1-->


