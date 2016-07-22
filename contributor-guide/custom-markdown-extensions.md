<properties pageTitle="Extensiones Markdown personalizadas que se usan en nuestros artículos técnicos"  description="Enumera las extensiones Markdown personalizadas que habilitan vídeos insertados, notas y sugerencias, contenido reutilizable, además de otros elementos, en los artículos técnicos de docs.microsoft.com/ems." services="" solutions="" documentationCenter="" authors="v-jocgar" manager="robmazz" editor=""/>

<tags ms.service="contributor-guide" ms.devlang="" ms.topic="article" ms.tgt_pltfrm=""  ms.workload="" ms.date="02/26/2016" ms.author="v-jocgar"/>

## Extensiones Markdown personalizadas para EMS
To Do:
- [ ] #34 Confirm that we're using Markdown extensions for Note, Important, etc. 
- [ ] #35 Confirm that EMS is using tokens, and the correct directory location.
- [ ] #36 Confirm that the custom icon files are available and installed in the correct location.
- [ ] #37 Confirm the directory name for tokens that use media files
- [ ] #38 Confirm the correct procedures for using tokens.
- [ ] #39 Provide an example of the syntax for using tokens. 
- [ ] #40 Confirm EMS Documentation URL.
- [ ] #41 Confirm that videos from Channel 9 can be used by external writers. 
- [ ] #42 Confirm location of EMS videos on Channel 9.
- [ ] #43 Confirm usage of EMS videos on Channel 9.
- [ ] #44 Confirm video embed syntax.
- [ ] #45 Need a rendered example from Github.
- [ ] #46 Need a rendered example of video from Github.
- [ ] #47 Need a rendered example from the EMS docs website. 
- [ ] #48 Confirm that Selectors are available to EMS articles
- [ ] #49 Need a simple selectors replacement example
- [ ] #50 Confirm simple selectors syntax
- [ ] #51 Need replacement simple selectors syntax
- [ ] #52 Need a replacement simple selectors example
- [ ] #53 Confirm that two-way selectors function as described.
- [ ] #54 Need a replacement two-way selectors example
- [ ] #55 Confirm two-way selectors syntax
- [ ] #56 Need a replacement two-way selectors example


## Ayuda general de Markdown

Se recomienda leer el tema [Authoring for EMS in Markdown](./authoring-in-markdown.md) (Creación para EMS en Markdown) antes de continuar con este. 

## Extensiones Markdown personalizadas que se usan en nuestros artículos técnicos

Nuestros artículos usan el marcado característico de GitHub para dar formato a la mayoría de los artículos; por ejemplo, párrafos, vínculos, listas, títulos, etc. Sin embargo, usamos extensiones Markdown personalizadas en las secciones de las páginas representadas de Microsoft.com/ems donde tenemos que aplicar un formato más enriquecido. Estas son las extensiones que usamos actualmente:

+ [Notas y sugerencias]
+ [Tokens]
+ [Vídeos insertados]
+ [Selectores de tecnología y plataforma]

## Notas y sugerencias
<span style="color:red;">Confirm that we're using Markdown extensions for Note, Important, etc.</span>
Puede elegir entre 4 tipos de notas y sugerencias:

- EMS.NOTE
- EMS.WARNING
- EMS.TIP
- EMS.IMPORTANT

### Uso
En general, utilice con moderación las notas y sugerencias en los artículos. Cuando lo haga, elija el tipo adecuado de nota o sugerencia:

- Utilice EMS.NOTE para resaltar información neutral o positiva que acentúe o complemente puntos clave del texto principal. Una nota proporciona información que se aplica solo en casos especiales.

  ![](./media/notes-note.png)

- Utilice EMS.WARNING para alertar al usuario de que una condición podría provocar un problema en el futuro. Por ejemplo, al seleccionar una opción determinada o tomar una decisión específica, es posible que ya no pueda dar marcha atrás.

  ![](./media/notes-warning.png)

- Utilice EMS.TIP para ayudar a los usuarios a aplicar las técnicas y los procedimientos descritos en el texto según sus necesidades específicas. Una sugerencia también podría recomendar métodos alternativos que puede que no sean evidentes. Sin embargo, las sugerencias no son esenciales para comprender el texto en líneas generales.

  ![](./media/notes-tip.png)

- Utilice EMS.IMPORTANT con el fin de proporcionar información esencial para la realización de una tarea.

  ![](./media/notes-important.png)

Aunque estas notas y sugerencias son compatibles con vínculos, imágenes, listas y bloques de código, trate de lograr siempre que las notas y sugerencias sean simples y directas. Si está creando notas complejas con gran cantidad de formato, podría ser un indicio de que necesita otra sección en el texto principal del artículo. Asimismo, el uso de demasiadas notas en un artículo puede ser molesto y dificultar la lectura.

### Marcado de muestra

Todas las muestras se visualizan como EMS.NOTE. Para usar TIP, WARNING o IMPORTANT, reemplace "NOTE" en el marcado:

    > [EMS.TIP]

    > [EMS.WARNING]

    > [EMS.IMPORTANT]

Un solo párrafo:

    > [EMS.NOTE] To complete this tutorial, you must have an active Microsoft account. If you don't have an account, you can create a free account in just a couple of minutes.

Varios párrafos:

    > [EMS.NOTE] To complete this tutorial, you must have an active Microsoft account.
    >
    > If you don't have an account, you can [create a free account](https://signup.live.com/signup) in just a couple of minutes.

## Tokens
<span style="color:red;">Confirm that EMS is using tokens, and the correct directory location.</span>
Los fragmentos de texto reutilizable de nuestro repositorio de GitHub se denominan "tokens". Si tiene texto que debe usarse en varios artículos, incluya una referencia a los fragmentos de texto en los archivos Markdown. El fragmento de texto (el token) es un archivo Markdown simple (.md). Puede contener cualquier marcado válido, como texto, vínculos e imágenes. 

Todos los archivos Markdown de token deben estar en <span style="color:red;">Confirm that the custom icon files are available and installed in the correct location.</span> [el directorio /tokens] (need correct location) de la raíz del repositorio. Cuando se publica el artículo, el texto de token se integra perfectamente con el tema publicado.

- Para hacer referencia a un token, empleamos una sintaxis específica.

- Los archivos multimedia que coloque en un token deben crearse en la carpeta `/media` específica del token. Las carpetas de elementos multimedia de los tokens pertenecen a <span style="color:red;">Confirm the directory name for tokens that use media files</span> [la carpeta ems-content/tokens/media](need correct location). 

## Uso
<span style="color:red;">Confirm the correct procedures for using tokens.</span>
- Use tokens siempre que necesite que el mismo texto aparezca en varios artículos.
- Los tokens están diseñados para usarse en cantidades significativas de contenido; por ejemplo, un párrafo o dos, un procedimiento compartido o una sección compartida. No los utilice en unidades más pequeñas que una frase; no se pueden emplear en nombres de producto o frases incompletas.
- No inserte tokens dentro de otros tokens, ya que se producirán problemas en el sistema de publicación.
- No comparta elementos multimedia entre archivos. Utilice un archivo independiente con un nombre único para cada token y artículo. Almacene el archivo multimedia en la carpeta de elementos multimedia asociada al token.
- No use un token como el único contenido de un artículo. Los tokens están diseñados para complementar al contenido del resto del artículo.
- Dado que todos los tokens deben estar en el directorio `/token`, la ruta de acceso a un token de un artículo siempre será

    ../token

- NO repita una referencia de vínculo o de nombre de archivo de imagen en el artículo y el token. Agregue "-token" al nombre de archivo multimedia o la referencia de vínculo para evitar repetir la referencia.

 **Referencia de vínculo**

 Change: odata.org
 To: odata.org-token

 **Referencia de imagen**

 Change: table.png
 To: table-token.png

### Marcado de ejemplo para tokens
<span style="color:red;">Provide an example of the syntax for using tokens. </span>
La sintaxis para agregar un token a un artículo de documentación es la siguiente:

    [EMS.TOKEN [token-short-name](../tokens/token-file-name.md)]

Ejemplo

    [EMS.INCLUDE [howto-blob-storage](../tokens/howto-blob-storage.md)]

La primera parte del token es el nombre del token sin la ruta de acceso ni la extensión .md. La segunda parte es la ruta de acceso relativa al token del directorio /token con la extensión .md.

### Representación

En la página de GitHub representada, el token se representará de la siguiente forma:

 [EMS.TOKEN howto-blob-storage]

En el HTML representado de <span style="color:red;">Confirm EMS Documentation URL</span> http://docs.microsoft.com/ems, el código HTML de los tokens se combina con el resto del documento HTML. Sin embargo, el código HTML incluirá un comentario HTML con el nombre de archivo Markdown original y el hash de confirmación de GitHub. Este comentario se incluye para poder solucionar problemas, de modo que el contenido de origen pueda identificarse y encontrarse con facilidad en GitHub:

  ![](./media/token.png)


## Vídeos insertados
<span style="color:red;">Confirm that videos from Channel 9 can be used by external writers.</span>
Nuestros artículos técnicos admiten vídeos insertados siempre y cuando procedan del sitio [Channel 9](http://channel9.msdn.com/) de Microsoft. Los vídeos de Channel 9 deben estar integrados con <span style="color:red;">Confirm location of EMS videos on Channel 9.</span> [el centro de vídeos de docs.microsoft.com] (need actual location). En estos momentos no se admiten vídeos de YouTube insertados; como colaborador de la comunidad, si lo desea, puede incluir un vínculo** a YouTube si el vídeo que quiere mostrar está publicado en esa plataforma.

### Uso
<span style="color:red;">Confirm usage of EMS videos on Channel 9.</span>
- Asegúrese de que el vídeo se encuentre en el centro de vídeos de Channel 9.

- Copie el id. del vídeo desde la dirección URL descriptiva del vídeo de Channel 9. Por ejemplo, el id. del vídeo de [https://channel9.msdn.com/Shows/This+Week+On+Channel+9/TWC9-Stacking-Microsoft-Windows-10-Pi-Bobble-Head-your-Nodejs-and-more](https://channel9.msdn.com/Shows/This+Week+On+Channel+9/TWC9-Stacking-Microsoft-Windows-10-Pi-Bobble-Head-your-Nodejs-and-more) es ** ??? **.

### Sintaxis
<span style="color:red;">Confirm video embed syntax. </span>
    > [EMS.VIDEO video-id-string]

### Representación
<span style="color:red;">Need a rendered example of video from Github. </span>
En GitHub: [need example of how an article looks when added on Github](something.md)

<span style="color:red;">Need a rendered example from the EMS docs website. </span>
Artículo publicado: [need an example of how an article looks on the doc site when incorporated](need actual location)

## Selectores de tecnología y plataforma
<span style="color:red;">Confirm that Selectors are available to EMS articles</span>
Utilice modificadores de tecnología y plataforma en artículos técnicos al crear varias versiones del mismo artículo con el objetivo de corregir las diferencias de implementación entre plataformas o tecnologías. En la mayoría de los casos, tendrá que emplearlos en nuestro contenido de plataforma móvil para desarrolladores. Actualmente, hay dos tipos diferentes de selectores: [simples](#simple-selectors) y [bidireccionales](#two-way-selectors).

Como en cada tema de la selección se emplea el mismo selector Markdown, se recomienda colocarlo en el tema de un token y, luego, hacer referencia a ese token en todos los temas que usen el mismo selector.

### Selectores simples

Los selectores simples (unidireccionales) se representan como un conjunto de botones de opción justo debajo del título. Use estos botones cuando los clientes tengan que elegir entre temas de un único conjunto de plataformas o tecnologías, como. NET, Node.js y Java.  Use la extensión Markdown personalizada en cualquiera de los selectores; no utilice en ellos HTML.  

<span style="color:red;">Need a simple selectors replacement example; leaving this Azure version here for reference.</span>
Consulte [Get started with Notification Hubs](http://azure.microsoft.com/documentation/articles/notification-hubs-windows-phone-get-started/) (Introducción a Centros de notificaciones) para ver cómo el autor creó 8 versiones del mismo artículo y usó los selectores para permitir la navegación en todos ellos.

![Ejemplo de selector simple](./media/selectors.png)

#### Sintaxis
<span style="color:red;">Confirm simple selectors syntax</span>
    > [EMS.SELECTOR]
    - [Link #1 Label](link #1 url)
    - [Link #2 Label](link #2 url)

#### Ejemplo
<span style="color:red;">Need replacement simple selectors syntax</span>
    > [EMS.SELECTOR]
    - [Windows Runtime 8.1 Universal](../articles/notification-hubs-windows-store-dotnet-get-started/)
    - [Windows Phone Silverlight 8.x](../articles/notification-hubs-windows-phone-get-started/)
    - [iOS](../articles/notification-hubs-ios-get-started/)
    - [Android](../articles/notification-hubs-android-get-started/)
    - [Kindle](../articles/notification-hubs-kindle-get-started/)
    - [Baidu](../articles/notification-hubs-baidu-get-started/)
    - [Xamarin.iOS](../articles/partner-xamarin-notification-hubs-ios-get-started/)
    - [Xamarin.Android](../articles/partner-xamarin-notification-hubs-android-get-started/)
    - [Chrome](../articles/notification-hubs-chrome-get-started/)

#### Representación

<span style="color:red;">Need a replacement simple selectors example; leaving this here for reference.</span>
La imagen anterior muestra la representación en docs.microsoft.com/ems. En las páginas de GitHub representadas, los selectores se representan como una lista con viñetas de vínculos.

### Selectores bidireccionales
<span style="color:red;">Confirm that two-way selectors function as described.</span>
Los selectores bidireccionales permiten a los usuarios seleccionar un tema de una matriz bidireccional. Esto resulta necesario cuando una tecnología EMS, como Servicios móviles, es compatible con varias plataformas de back-end y diversos clientes. Tenga en cuenta lo siguiente:

- Aunque se diseñó como `(Platform | Backend)`, ahora se puede personalizar el texto de la lista desplegable.
- No necesita un elemento de lista en todos los puntos de la matriz, solamente uno en el que haya una dirección URL de un tema y que no esté duplicada.
- El vínculo puede ser cualquier dirección URL, aunque, normalmente, es otro tema de GitHub.

<span style="color:red;">Need a replacement two-way selectors example; leaving this Azure version here for reference.</span>
Consulte [Introducción a Servicios móviles](http://azure.microsoft.com/en-us/documentation/articles/mobile-services-ios-get-started/) para ver cómo el autor creó 15 versiones del mismo artículo (9 plataformas cliente móviles y 2 plataformas de back-end) y usó los selectores para permitir la navegación en todos ellos. Tenga en cuenta que 3 artículos no tienen las dos versiones de back-end.

![Ejemplo de selectores bidireccionales](./media/selector-list.png)

#### Sintaxis
<span style="color:red;">Confirm two-way selectors syntax</span>
    > [AZURE.SELECTOR-LIST (Dropdown1 | Dropdown2 )]
    - [(Dropdown1Text1 | Dropdown2Text1 )](../articles/dropdown1-text1-dropdown2-text1.md)
    - [(Dropdown1Text1 | Dropdown2Text2 )](../articles/dropdown1-text1-dropdown2-text1.md)
    - [(Dropdown1Text2 | Dropdown2Text3 )](../articles/dropdown1-text1-dropdown2-text1.md)
    - [(Dropdown1Text3 | Dropdown2Text4 )](../articles/dropdown1-text1-dropdown2-text1.md)

#### Ejemplo
<span style="color:red;">Need a replacement two-way selectors example</span>
    > [AZURE.SELECTOR-LIST (Platform | Backend )]
    - [(iOS | .NET)](./mobile-services-dotnet-backend-ios-get-started-push.md)
    - [(iOS | JavaScript)](./mobile-services-javascript-backend-ios-get-started-push.md)
    - [(Windows Runtime 8.1 universal | C#)](./mobile-services-dotnet-backend-windows-universal-dotnet-get-started-push.md)
    - [(Windows Runtime 8.1 universal C# | Javascript)](./mobile-services-javascript-backend-windows-universal-dotnet-get-started-push.md)
    - [(Windows Phone | .NET)](./mobile-services-dotnet-backend-windows-phone-get-started-push.md)
    - [(Windows Phone | Javascript)](./mobile-services-javascript-backend-windows-phone-get-started-push.md)
    - [(Android | .NET)](./mobile-services-dotnet-backend-android-get-started-push.md)
    - [(Android | Javascript)](./mobile-services-javascript-backend-android-get-started-push.md)
    - [(Xamarin iOS | Javascript)](./partner-xamarin-mobile-services-ios-get-started-push.md)
    - [(Xamarin Android | Javascript)](./partner-xamarin-mobile-services-android-get-started-push.md)
    - [HTML](../articles/mobile-services-html-get-started/)
    - [PhoneGap](../articles/mobile-services-javascript-backend-phonegap-get-started/)
    - [Sencha](../articles/partner-sencha-mobile-services-get-started/)

#### Representación
<span style="color:red;">Need a replacement two-way selectors example; leaving this here for reference.</span>
La imagen anterior muestra la representación en azure.microsoft.com. En las páginas de GitHub representadas, los selectores se representan como una lista con viñetas de vínculos.

<!--Anchors-->
[Notes and tips]: #notes-and-tips
[Tokens]: #tokens
[Embedded videos]: #embedded-videos
[Technology and platform selectors]: #technology-and-platform-selectors

## Volver a la página principal

- [Overview article](./../README.md)
- [Index of guidance articles](./contributor-guide-index.md)


<!--HONumber=Mar16_HO1-->


