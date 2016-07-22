<properties pageTitle="Metadatos de artículos técnicos de Enterprise Mobility Suite" description="Describe los metadatos necesarios para los artículos." metaKeywords="" services="" solutions="" documentationCenter="" authors="v-jocgar" videoId="" scriptId="" manager="required" />

<tags ms.service="contributor-guide" ms.devlang="" ms.topic="article" ms.tgt_pltfrm="" ms.workload="" ms.date="02/24/2016" ms.author="v-jocgar" />

# Metadatos de artículos técnicos de Enterprise Mobility Suite

To Do: 
- [ ] #11 Confirm that the instructions for each property are correct.
- [ ] #12 Confirm the URL in the Properties:Description section.
- [ ] #13 Update list of services and ms-service list of values (see RobMazz email #3 2016-02-18).
- [ ] #14 Confirm the URL in the Properties:Tags section (location of EMS articles).
- [ ] #15 Confirm the short list (3) of optional tags in the Properties:Tags. ¿Debe haber más etiquetas? 
- [ ] #16 Confirm the list of services in the Tags:ms-services section.
- [ ] #17 Update the list of article types (resource types) in the Tags:mstopic section (RobMazz email #1 2016-02-18).
- [ ] #18 Update and approve list of programming languages in the Tags:ms.devlang section (RobMazz email #4 2016-02-18).
- [ ] #19 Confirm the list of target platforms in the Tags:ms.tgt_pltfrm section (RobMazz email #2 2016-02-18).
- [ ] #20 Confirm that all links (especially anchors) work properly. 

Todos los artículos técnicos de EMS contienen dos secciones de metadatos: una sección de propiedades (properties) y otra de etiquetas (tags). La sección de propiedades habilita algunos elementos relacionados con la automatización del sitio web y la SEO, mientras que la de etiquetas permite la creación de una gran cantidad de informes de contenido interno. Ambas secciones resultan necesarias.

- [Sintaxis]
- [Uso]
- [Atributos y valores de la sección properties]
- [Atributos y valores de la sección tags]

## Sintaxis

La sección properties utiliza la sintaxis siguiente:

    <properties
       pageTitle="Page title that displays in search results and the browser tab | Microsoft EMS"
       description="Article description that will be displayed on landing pages and in most search results"
       services="service-name"
       documentationCenter="dev-center-name"
       authors="GitHub-alias-of-only-one-author"
       manager="manager-alias"
       editor=""
       tags="optional"
       keywords="Separate terms with commas. Check with your SEO champ before you change content in this article containing these terms."/>

La sección tags utiliza la sintaxis siguiente:

    <tags
       ms.service="required"
       ms.devlang="may be required"
       ms.topic="article"
       ms.tgt_pltfrm="may be required"
       ms.workload="na"
       ms.date="mm/dd/yyyy"
       ms.author="Your MSFT alias or your full email address;semicolon separates two or more"/>

## Uso

- Se distingue entre mayúsculas y minúsculas en los nombres del elemento y de los atributos.
- La sección properties debe constituir la primera línea del archivo.
- Deje una línea en blanco después de cada sección de metadatos y antes del título de la página para asegurarse de que este último se convierta correctamente a HTML durante el proceso de publicación.

## Atributos y valores de la sección properties

![](./media/checkmark-small.png)**pageTitle**: necesario; importante para SEO. El texto de este atributo aparece en la pestaña del navegador y como el título en los resultados de búsqueda. Utilice entre 55 y 60 caracteres, incluidos espacios y el identificador del sitio web *| Microsoft EMS* (escrito de la siguiente manera: espacio, barra vertical, espacio y "Microsoft EMS").  El atributo pageTitle debe ser diferente del H1.

![](./media/checkmark-small.png)**description**: necesario; importante para la SEO (relevancia) y la funcionalidad de los sitios. La descripción debe contener entre 125 y 155 caracteres, incluidos espacios. Describa el propósito del contenido para que los clientes puedan saber si deben elegirlo entre los resultados de búsqueda. El valor es:

- Este texto puede aparecer como la descripción o el párrafo de resumen en los resultados de búsqueda de Google.
- Este texto se muestra en <span style="color:red;">Confirm URL</span> [los resultados del índice de artículos](http://docs.microsoft.com/ems/articles/).

![](./media/checkmark-small.png)**services**: necesario en los artículos que traten sobre algún servicio. Se suele hacer referencia a este valor como el "campo de datos dinámico de servicios". Enumere todos los servicios aplicables separados por comas. El primer servicio que indique determinará las rutas de navegación de la página y el panel de navegación izquierdo que aparece en ella.

En aquellos artículos en los que se especifique un valor services y otro documentationCenter, será el primero el que determine la ruta de navegación. Los valores adicionales que incluya aparecerán como etiquetas en el artículo publicado. Values:

- active-directory
- active-directory-b2c
- active-directory-ds
- app-service-api
- api-management
- app-service
- app-service-mobile
- app-service-web
- application-gateway
- application-insights
- automatización
- copia de seguridad
- batch
- best-practice
- facturación
- biztalk-services
- caché
- cdn
- cloud-services
- data-catalog
- data-factory
- data-lake-analytics
- data-lake-store
- devtest-lab
- dns
- documentdb
- expressroute
- event-hubs
- hdinsight
- iot-hub
- key-vault
- load-balancer
- machine-learning
- marketplace
- media-services
- mobile-engagement
- mobile-services
- multi-factor-authentication
- notification-hubs
- operational-insights
- operations-management-suite
- powerapps
- recovery-manager
- redis-cache
- remoteapp
- rights-management
- programador
- buscar
- security-center
- service-bus
- service-fabric
- site-recovery
- sql-database
- sql-data-warehouse
- sql-reporting
- a largo plazo
- almacenar
- storsimple
- stream-analytics
- traffic-manager
- virtual-machines
- virtual-network
- visual-studio-online
- vpn-gateway
- web-sites

![](./media/checkmark-small.png)**documentationCenter**: necesario para los artículos centrados en el desarrollo que convenga asociar con un centro de desarrollo. Especifique el centro de desarrollo o lenguaje concretos que se aplican al artículo. El valor que indique determinará las rutas de navegación de la página. En aquellos artículos en los que se especifique un valor services y otro documentationCenter, será el primero el que determine la ruta de navegación. Values:

- **.net**
- **nodejs**
- **java**
- **php**
- **python**
- **ruby**
- **mobile**: en desuso. Reemplácelo por una plataforma móvil específica.
- **ios**: nuevo valor en comprobación.
- **android**: nuevo valor en comprobación.
- **windows**: nuevo valor en comprobación.
- **xamarin**: nuevo valor en comprobación.

![](./media/checkmark-small.png)**authors**: necesario; solo un valor. Indique la cuenta de GitHub del autor principal o del SME del artículo. Este atributo activa la línea de autor en el artículo publicado. Especifique tan solo un valor, a pesar de la forma plural del nombre del atributo.

![](./media/checkmark-small.png)**manager**: necesario si se es un colaborador de Microsoft. Indique el alias de correo electrónico del administrador de publicación de contenidos del ámbito tecnológico. Si es un colaborador de la comunidad, incluya el atributo, pero déjelo vacío para que podamos rellenarlo.

![](./media/checkmark-small.png)**editor**: no se usa. No lo utilice para otros fines.

![](./media/checkmark-small.png)**tags**: opcional. Inclúyalo solo si desea habilitar un vínculo bajo la ruta de navegación del artículo a una lista prefiltrada de artículos que coincidan con uno de los valores aprobados y que aparezcan en la página de índice de artículos <span style="color:red;">Confirm URL</span> (http://docs.microsoft.com/ems/articles/). Estos valores están destinados a ofrecer una forma de agrupar contenido cuando el criterio de dicha agrupación no responda a un servicio concreto. Tales valores de tags también pueden proporcionar un etiquetado que indique el componente tecnológico al que se aplica el artículo. Este valor **no** es compatible con los hashtags o las etiquetas de forma libre; las etiquetas deben habilitarse en el sitio web. Puede añadir varios valores de tags a un artículo separándolos por comas. Los valores aprobados son los siguientes:

<span style="color:red;">Confirm these tag values</span>
  - existente
  - facturación
  - mysql

![](./media/checkmark-small.png)**keywords**: opcional. Su utilización se restringe a los expertos en SEO. Separe los términos por comas. **Consulte al experto en SEO antes de cambiar o eliminar contenido del artículo que incluya estos términos.** Este atributo registra las palabras clave a las que el experto en SEO ha dirigido el contenido y que está sometiendo a seguimiento para mejorar la clasificación en las búsquedas. Las palabras clave no se representan en el HTML publicado. Este atributo no resulta necesario para la validación.

## Atributos y valores de la sección tags

![](./media/checkmark-small.png)**ms.service**: necesario. Indica el servicio, herramienta o función a los que se aplica el artículo. Un valor por página.

 Si una página se aplica a varios servicios, elija aquel al que lo haga de forma más directa; por ejemplo, un artículo que recurra a una aplicación hospedada en sitios web para demostrar la funcionalidad de bus de servicio deberá presentar el valor **service-bus**, en lugar de **web-sites**. Si una página se aplica a varios servicios por igual, elija el valor **multiple**. En caso de que una página no se aplique a ningún servicio, lo que sucede con poca frecuencia, opte por el valor **na**.

<span style="color:red;">Confirm these values.</span>
 - **active-directory**
 - **api-management**
 - **app-service**: solo se aplica a material conceptual de tipo general del Servicio de aplicaciones.
 - **app-service-api**
 - **app-service-logic**
 - **app-service-mobile**
 - **app-service-web**
 - **application-insights**
 - **automatización**
 - **copia de seguridad**
 - **batch**
 - **biztalk-services**
 - **facturación**
 - **caché**
 - **cdn**
 - **cloud-services**
 - **expressroute**
 - **hdinsight**
 - **iot-hub**
 - **key-vault**
 - **machine-learning**
 - **media-services**
 - **mobile-engagement**
 - **mobile-services**
 - **multi-factor-authentication**
 - **multiple**: la página se aplica a varios servicios por igual.
 - **na**: la página no se aplica a ningún servicio (poco frecuente).
 - **notification-hubs**
 - **operational-insights**
 - **powerapps**
 - **recovery-manager**
 - **redis-cache**
 - **remoteapp**
 - **rights-management**
 - **programador**
 - **service-bus**
 - **service-fabric**
 - **site-recovery**: anteriormente, recovery-services.
 - **sql-database**
 - **sql-data-warehouse**
 - **sql-reporting**
 - **a largo plazo**
 - **storsimple**
 - **traffic-manager**
 - **virtual-machines**
 - **virtual-network**
 - **visual-studio-online**
 - **vpn-gateway**
 - **web-sites**

![](./media/checkmark-small.png)**ms.devlang**: necesario. Indica el lenguaje de programación al que se aplica el artículo. Un único valor por página.

 Si una página se aplica a dos lenguajes de programación por igual, elija el valor **multiple**. En caso de que el artículo sea principalmente conceptual y su contenido, aplicable de forma general a varios lenguajes de programación, opte por el valor **multiple**. Si una página no está destinada a desarrolladores y su aplicabilidad a lenguajes de programación no resulta pertinente, utilice el valor **na**. Use el valor **rest-api** para identificar temas de referencia de la API de REST.

<span style="color:red;">Confirm these values</span>
 - **cpp**
 - **dotnet**
 - **java**
 - **javascript**
 - **multiple**: la página se aplica a varios lenguajes de programación por igual.
 - **na**: la página no está dirigida a desarrolladores y no es específica de ningún lenguaje de programación.
 - **nodejs**
 - **objective-c**
 - **php**
 - **python**
 - **rest-api**
 - **ruby**


![](./media/checkmark-small.png)**ms.topic**: necesario. Indica el tipo de tema. La mayoría de las páginas nuevas que crean los colaboradores serán artículos o material de referencia.

<span style="color:red;">Confirm these values</span>
 - **article**: un tema conceptual, un tutorial, una guía de funciones u otro artículo que no sea de referencia.

 - **get-started-article**: asígnelo a los artículos que se destaquen en la sección Introducción del panel de navegación izquierdo de un servicio.

 - **hero-article**: un tutorial de carácter esencial, diseñado como introducción a un servicio o función. Gracias a él, los visitantes pueden empezar a usar el servicio rápidamente. Además, fomenta los registros de pruebas gratuitas y las activaciones de MSDN. Asigne este valor SOLO a los artículos que se destaquen en la parte superior de la página de destino de la documentación del servicio.

 - **reference**: una página de referencia de API (incluida la API de REST) o página de referencia de cmdlets de PowerShell.

![](./media/checkmark-small.png)**ms.tgt_pltfrm**: necesario. Indica la plataforma objetivo; por ejemplo, Windows, Linux, Windows Phone, iOS, Android o plataformas de memoria caché especiales. Un valor por página. Este valor será **na** en la mayoría de los temas, excepto móviles y máquinas virtuales.

<span style="color:red;">Confirm these values</span>
 - **cache-in-role**
 - **cache-multiple**
 - **cache-redis**
 - **cache-service**
 - **cache-shared**
 - **command-line-interface**
 - **ibiza**: contenido que se sirve del portal de Ibiza. Utilícelo solo en los casos en los que la función que se analice se encuentre disponible tanto en este portal como en el actual.
 - **mobile-android** 
 - **mobile-html**
 - **mobile-ios**
 - **mobile-kindle**
 - **mobile-multiple**
 - **mobile-nokia-x**
 - **mobile-phonegap**
 - **mobile-sencha**
 - **mobile-windows**
 - **mobile-windows-phone**
 - **mobile-windows-store**
 - **mobile-xamarin**
 - **mobile-xamarin-android**
 - **mobile-xamarin-ios**
 - **multiple**: la página se aplica a varias plataformas por igual.
 - **na**: no hay ningún especificador de plataforma aplicable a esta página.
 - **powershell**
 - **vm-linux**
 - **vm-multiple**
 - **vm-windows**
 - **vm-windows-sharepoint**
 - **vm-windows-sql-server**
 - **vs-getting-started**: identifica el grupo de páginas Introducción de VS. Etiqueta añadida el 1/12/14.
 - **vs-what-happened**: identifica la página ¿Qué ha pasado? en Introducción de VS. Etiqueta añadida el 1/12/14.

![](./media/checkmark-small.png)**ms.workload**: necesario. Indica la carga de trabajo a la que se aplica la página. Un único valor por artículo. 

![](./media/checkmark-small.png) **ms.date**: necesario. Especifica la fecha en la que se revisaron por última vez la relevancia, la precisión, la corrección de las capturas de pantalla y el funcionamiento de los vínculos. Especifique la fecha en el formato mm/dd/aaaa. Esta fecha también aparece en el artículo publicado como la fecha de la última actualización.

![](./media/checkmark-small.png) **ms.author**: necesario. Indica los autores asociados con el tema. Para especificar varios valores, debe separarlos por punto y coma. Se aceptan alias de Microsoft o direcciones de correo completas. La longitud no puede superar los 200 caracteres.

## Volver a la página principal

- [Artículo de información general](./../README.md)
- [Índice de artículos de la guía](./contributor-guide-index.md)


<!--Anchors-->
[Syntax]: #syntax
[Usage]: #usage
[Attributes and values for the properties section]: #attributes-and-values-for-the-properties-section
[Attributes and values for the tags section]: #attributes-and-values-for-the-tags-section


<!--HONumber=Mar16_HO1-->


