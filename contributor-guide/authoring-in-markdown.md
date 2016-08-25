<properties pageTitle="Creación de contenido relativo a EMS en Markdown" description="Se explica cómo crear imágenes en Markdown de acuerdo con las instrucciones definidas para los repositorios de Enterprise Mobility Suite." services=""     solutions="" documentationCenter="" authors="v-jocgar" manager="robmazz" />

<tags ms.service="contributor-guide" ms.devlang="" ms.topic="article" ms.tgt_pltfrm=""  ms.workload="" ms.date="02/25/2016" ms.author="v-jocgar" />

# Creación de contenido relativo a EMS en Markdown

To Do: 
- [ ] #23 Confirm EMS article layout for images /articles/<service-directory>/media
- [ ] #24 Provide an example for /articles/<service-directory>/media
- [ ] #25 Confirm the max width for images in EMS doc page center column (580 or 600px?) in 3 paragraphs
- [ ] #26 Confirm whether EMS has a different set of symbols for conceptual art other than those offered at http://aka.ms/CnESymbols. 
- [ ] #27 Confirm URL for our Contributor's Guide
- [ ] #28 Confirm the entire linking scheme
- [ ] #29 Are articles organized by service subdirectories?
- [ ] #30 Anchor linking methodology needs to be confirmed
- [ ] #31 Confirm the linking methodology and use of selectors.
- [ ] #32 Test the linking scheme to ensure that it works correctly

Este artículo contiene indicaciones sobre cómo redactar artículos técnicos relacionados con los servicios y las tecnologías de EMS. Estas instrucciones se aplican tanto si desea crear documentación nueva como si pretende actualizar la ya existente.

## ¿Por qué escribir sobre EMS?

Microsoft Enterprise Mobility Suite (EMS) se ha concebido específicamente para ayudar con la migración actual a servicios integrados, móviles y basados en la nube. Sus tres componentes principales (Microsoft Azure Active Directory Premium, Microsoft Intune y Microsoft Azure Rights Management) se crearon desde el principio como servicios en la nube. Se diseñaron para trabajar de forma conjunta, lo que ofrece una integración de varias tecnologías sin parangón en el mercado. Para detectar ataques locales, EMS también incluye Microsoft Advanced Threat Analytics. Con EMS, los usuarios corporativos pueden trabajar en los dispositivos que prefieran sin perjuicio de la protección de los activos de la empresa.

Crear documentación para productos concretos es siempre una de nuestras prioridades. No obstante, debido a que EMS consiste en un conjunto de productos, también se necesitan artículos y documentos de instrucciones que ayuden a nuestros clientes a usar los servicios de manera conjunta. Creamos documentación para escenarios en los que se utilizan varios productos, pero también nos agrada recibir los comentarios de los empleados y usuarios que trabajan con ellos en sus propias empresas.

Como resultado, hemos añadido nuestra documentación a GitHub, donde puede contribuir de numerosas formas, entre las que se encuentran las siguientes:
- **Corrección de errores de texto.** Para nosotros, también constituyen uno de los aspectos que más nos irrita, pero no siempre nos percatamos de ellos, de modo que puede conectarse a GitHub y ayudarnos.
- **Sugerencia de nuevos temas.** Si encuentra un procedimiento o asunto que aparezca con la frecuencia suficiente como para merecer un tema de documentación, pero este aún no existe, no dude en redactarlo y sopesaremos la posibilidad de incluirlo.
- **Adición de dudas a nuestra sección de preguntas frecuentes.** Si tiene alguna duda acerca de aspectos que no tratamos, pero no resulta necesario un tema completo, sino que basta con la respuesta a una pregunta, envíe esta última a la sección de preguntas frecuentes para que podamos analizarla. 

En conclusión, sabemos que puede aportar sugerencias e ideas interesantes, y queremos que le resulte sencillo participar para mejorar EMS en su totalidad. 

## Sugerencias para crear mejores artículos

Cuando redacte para EMS, tenga en cuenta lo siguiente:

**Prácticas recomendadas específicas de EMS**
- El nombre oficial del producto es "Microsoft Enterprise Mobility Suite", pero casi siempre puede abreviarse con la expresión "EMS", como en "Administración de identidad y acceso en la nube con EMS".
- Incluya "EMS" con el nombre de un servicio o función la primera vez que los mencione y, después, omita las siglas (p. ej., "Administración de identidad y acceso en la nube con EMS" se convertiría en "Administración de identidad y acceso en la nube" tras el primer uso). 
- EMS utiliza las mayúsculas en todos los títulos. 
- Por lo general, trate de evitar el uso de acrónimos: confunden a los usuarios.

**Buenas prácticas de redacción**
- Recurra a un tono cercano e informal, como si le hablara a otra persona frente a frente. Consulte el [tema relativo al estilo y al tono](./style-and-voice.md) para obtener más detalles.
- Pase el corrector para detectar errores de ortografía y gramática en sus artículos, incluso aunque tenga que copiar el texto en Word para ello.
- Use frases simples. Resultan más fáciles de entender y de traducir, ya sea por traductores humanos o automáticos.
- No interrumpa los pasos con comentarios o acotaciones.
- Incluya las palabras "siguiente" o "como sigue" en las frases que precedan a una lista o fragmento de código.
- En el caso de los pasos que incluyan fragmentos de código, agregue la información adicional acerca del paso como un comentario en el código. 
    - De este modo, disminuye la cantidad de texto que se tiene que leer. 
    - La información clave debe copiarse en el proyecto de código para recordar a los usuarios la función del código cuando lo consulten más tarde.

## Ayuda general de Markdown
- Para obtener sugerencias generales sobre Markdown, consulte los [conceptos básicos de Markdown](https://help.github.com/articles/markdown-basics/) en el sitio web de GitHub.
- También puede descargar nuestra [hoja de referencia de Markdown para EMS](./media/ems-markdown-cheat-sheet.pdf?raw=true). 
- Si necesita vincular artículos en Markdown, consulte las [instrucciones de vinculación](#guidelines-for-linking-technical-articles) que se presentan a continuación.
- El sitio web <span style="color:red;">Confirm URL</span> http://docs.microsoft.com/ems admite [bloques de código delimitados](https://help.github.com/articles/creating-and-highlighting-code-blocks/#fenced-code-blocks). Para delimitar bloques de código, se debe insertar una fila de tres caracteres de acentos graves (```) en las líneas que se encuentren antes y después de tales bloques. Constituyen una forma cómoda de destacar el código del resto del texto.   
- EMS también admite el empleo de [sintaxis resaltada](https://help.github.com/articles/creating-and-highlighting-code-blocks/#syntax-highlighting) dentro de los bloques de código. No obstante, a diferencia del formato Markdown característico de GitHub, donde el hecho de [especificar un lenguaje concreto](https://help.github.com/articles/creating-and-highlighting-code-blocks/#syntax-highlighting) en la primera línea de código modifica la combinación de colores de la sintaxis, EMS solo admite **una** combinación de colores en la sintaxis resaltada, con independencia del lenguaje de programación que se especifique.

## Creación de imágenes en Markdown
Puede incluir imágenes en sus artículos siguiendo la sintaxis simple de Markdown. 

### Creación de carpetas de imágenes y sintaxis de vínculos

Para los artículos nuevos, deberá crear una carpeta en la ubicación siguiente:
<span style="color:red;">Confirm article repo layout for images</span>

    /articles/<service-directory>/media/

Por ejemplo:
<span style="color:red;">Provide an example</span>

    /articles/identity-access/media/

Después de crear la carpeta y añadirle imágenes, emplee la sintaxis siguiente para crear imágenes en el artículo:

```
![Alt image text](./media/your-image-filename.png)
```

## Instrucciones específicas para Enterprise Mobility Suite relativas a las imágenes

Se recomienda la inclusión de capturas de pantalla en caso de que no resulte posible agregar los pasos que se deben seguir. Redacte el contenido de forma que pueda comprenderse sin las capturas de pantalla en caso de que fuera necesario.

Siga estas instrucciones a la hora de crear e incluir archivos de imágenes:
- Comparta archivos de imágenes entre los distintos documentos si resultara posible. Copie la dirección URL del archivo que desee y agréguela al artículo. 
- Se recomienda encarecidamente el uso de archivos en formato PNG (Portable Network Graphics) frente al de otros tipos.
- Utilice cuadrados rojos con la anchura predeterminada que se ofrece en Paint (5 píxeles) para centrar la atención en elementos concretos de las capturas de pantalla.  

    Ejemplo:

    ![En este ejemplo, se muestra la utilización de un cuadrado rojo como llamada.](./media/gs13noauth.png)

- Evite los espacios en blanco en los bordes de las capturas de pantalla. Estas deberían presentar un borde gris de un píxel de anchura para que las áreas blancas de las imágenes no se confundan con la página web.
    - Si recorta una captura de pantalla de forma que le quede un fondo blanco en los márgenes, agregue un borde gris de un solo píxel alrededor de la imagen.  
    - Si utiliza Paint, elija uno de los grises más claros de la paleta de colores predeterminada (#C3C3C3).
![Gris para el borde](./media/grey-border-in-paint.png)     
    - En caso de que use una aplicación de gráficos que requiera el empleo de valores RGB, los números de este color son R195, G195, B195. 
- Puede agregar fácilmente un borde gris alrededor de una imagen en Visio. Para hacerlo: 
  - Seleccione la imagen. 
  - Seleccione Línea y asegúrese de definir el color correcto. 
  - Cambie el grosor de la línea a 1,5 puntos.  

    **Ejemplo:**

    ![En este ejemplo, aparece un borde gris rodeando un espacio en blanco.](./media/agent-700w.png)

- Las imágenes conceptuales con espacio en blanco no requieren la adición de un borde gris.  

    **Ejemplo:**

    ![En este ejemplo, se puede ver una imagen conceptual con espacio en blanco y sin borde gris.](./media/ic727360.png)

- Trate de no crear una imagen demasiado ancha. En caso contrario, su tamaño se ajustará de forma automática. No obstante, en ocasiones, al ajustarse las imágenes, se desenfocan, por lo que se recomienda limitar su anchura a <span style="color:red;">Confirm max image width</span> 580 píxeles y cambiar el tamaño de forma manual antes de enviarlas, si fuera necesario.

- Muestre salidas de comandos en capturas de pantalla.  Si el artículo incluye pasos en los que el usuario debe utilizar un shell, resultará de utilidad mostrar salidas de comandos en tales imágenes. En este caso, al limitar el tamaño del shell a unos 72 caracteres, se suele garantizar que la imagen se adecue a la recomendación de los <span style="color:red;">Confirm max image width</span> 580 píxeles de anchura. Antes de realizar la captura de pantalla de una salida, ajuste la ventana de forma que se muestre únicamente el comando y la salida pertinentes (de manera opcional, puede incluir una línea blanca a cada lado).
- Realice capturas de pantalla completas de las ventanas cuando sea posible. Al efectuar una captura de pantalla de la ventana de un navegador, cambie la anchura de esta a <span style="color:red;">Confirm max image width</span> 580 píxeles o menos y reduzca el alto de la ventana lo máximo posible de forma que la aplicación encaje en ella.

    Ejemplo:

    ![En este ejemplo, se muestra la captura de pantalla de la ventana de un navegador.](./media/helloworldlocal.png)

- Tenga cuidado con la información que revela en las capturas de pantalla. Asegúrese de no mostrar información interna de la empresa o de carácter personal.
- En los diagramas o imágenes conceptuales, recurra a los iconos oficiales del conjunto de símbolos e iconos de Cloud and Enterprise. Tiene a su disposición una recopilación pública en <span style="color:red;">Confirm that we use these icons</span> http://aka.ms/CnESymbols.


## Instrucciones para vincular artículos técnicos

| Escenario de vinculación | Guía para establecer el vínculo de destino  |
|---------------|-----------|
|Vinculación entre artículos técnicos de EMS|Use vínculos relativos.|
|Vinculación a una página de EMS que se encuentre fuera del directorio de documentación, a un tema de MSDN Library, a un tema de la biblioteca de TechNet o a un artículo de Knowledge Base|​Use el vínculo real al artículo o tema. Quite la información regional de idioma ("en-us") incluida en él.|
|Inclusión de un vínculo en un artículo de EMS a cualquier otra página web|Utilice el vínculo directo.|

### Use un texto descriptivo del vínculo.

Las palabras que se incluyan en los vínculos deben ser descriptivas, es decir, palabras comunes o el título de la página de aterrizaje. No emplee la expresión "haga clic aquí". Repercute negativamente en la SEO y no describe de forma adecuada el destino.

**Correcto:**
<span style="color:red;">Confirm URL for our Contributor's Guide</span> 
- `For more information, see the [contributor guide index](https://github.com/Microsoft/EMDocs/contributor-guide/contributor-guide-index.md).`

- `For more details, see the [SET TRANSACTION ISOLATION LEVEL](https://msdn.microsoft.com/library/ms173763.aspx) reference.`

**Incorrecto:**

- `For more details, see [https://msdn.microsoft.com/library/ms173763.aspx](https://msdn.microsoft.com/library/ms173763.aspx).`

<span style="color:red;">Confirm URL for our Contributor's Guide</span> 
- `For more information, click [here](https://github.com/Microsoft/EMDocs/contributor-guide/contributor-guide-index.md).`

### Sintaxis de Markdown para vínculos relativos de EMS
<span style="color:red;">Confirm the entire linking scheme</span> 

Para crear un vínculo insertado entre artículos técnicos de EMS, utilice este formato de vínculo. Si crea vínculos nuevos a artículos o desde ellos en los directorios, debe seguir la nueva sintaxis de vinculación.

Artículo que se vincula de un subdirectorio a un artículo del directorio raíz:

    [link text](../article-name.md)

Artículo del directorio raíz que se vincula a un artículo del subdirectorio de un servicio: 
<span style="color:red;">Are articles organized by service subdirectories?</span>

    [link text](service-directory/article-name.md)

Artículo del subdirectorio de un servicio que se vincula a un artículo que se encuentra en otro subdirectorio de servicio:

    [link text](../service-directory/article-name.md)
 
Artículo de un directorio que se vincula a otro artículo del mismo directorio:

    [link text](article-name.md)


Ya no es necesario que cree delimitadores, puesto que se generan de forma automática en el momento de la publicación para todos los títulos del tipo H2. Basta con establecer vínculos a las secciones del tipo H2:
<span style="color:red;">Anchor linking methodology needs to be confirmed</span>

    [link](#the-text-of-the-H2-section-separated-by-hyphens)
    [Create cache](#create-cache)

Para incluir un vínculo a un delimitador de otro artículo que se encuentre en el mismo subdirectorio:

    [link text](article-name.md#anchor-name)
    [Configure your profile](media-services-create-account.md#configure-your-profile)

Para incluir un vínculo a un delimitador de otro subdirectorio de servicio:

    [link text](service-directory/article-name.md#anchor-name)
    [Configure your profile](service-directory/media-services-create-account.md#configure-your-profile)


## Sintaxis de vinculación personalizada de Markdown
<span style="color:red;">Confirm the linking methodology and use of selectors.</span>

Debido a que los archivos de inclusión se encuentran en otro directorio, deberá usar rutas de acceso relativas tal y como se muestra a continuación. Para establecer un vínculo a un único artículo a partir de un archivo de inclusión, utilice este formato:

    [link text](../articles/service-folder/article-name.md)
    
Obtenga más información sobre cómo usar un archivo de inclusión en las [instrucciones sobre extensiones personalizadas de Markdown](custom-markdown-extensions.md#includes).

Si cuenta con selectores incrustados en un archivo de inclusión, utilice este tipo de vinculación: 

    > [EMS.SELECTOR-LIST (Dropdown1 | Dropdown2)]
    - [(Text1 | Example1 )](../articles/service-folder/article-name1.md)
    - [(Text1 | Example2 )](../articles/service-folder/article-name2.md)
    - [(Text2 | Example3 )](../articles/service-folder/article-name3.md)
    - [(Text2 | Example4 )](../articles/service-folder/article-name4.md)

Para crear un vínculo a una página relacionada con EMS (como una página de precios, de un contrato de nivel de servicio o de cualquier otro tipo que no constituya un artículo de documentación), emplee una URL absoluta, pero omita la información de configuración regional *en-us*. La finalidad es que los vínculos funcionen en GitHub y en el sitio representado:

    [link text](https://www.microsoft.com/server-cloud/enterprise-mobility/pricing.aspx)

Para comprobar los vínculos, inserte la página en la bifurcación, obtenga una vista representada de ella y publíquela en el espacio aislado pertinente. Los vínculos cruzados de la versión de GitHub de la página deben funcionar siempre que los destinos de las direcciones URL aparezcan en la rama.

## Vínculos de estilo de referencia

Puede utilizar vínculos de estilo de referencia para facilitar la lectura de su contenido de origen. Los vínculos de estilo de referencia reemplazan la sintaxis de vinculación insertada por una simplificada que permite mover las direcciones URL largas al final del artículo. Este es un ejemplo de Daring Fireball:

Texto insertado:

    I get 10 times more traffic from [Google][1] than from [Yahoo][2] or [MSN][3].

Vínculos de referencia al final del artículo:

    <!--Reference links in article-->
    [1]: http://google.com/
    [2]: http://search.yahoo.com/  
    [3]: http://search.msn.com/


## Volver a la página principal

- [Artículo de información general](./../README.md)
- [Índice de artículos de la guía](./contributor-guide-index.md)



<!--HONumber=Mar16_HO1-->


