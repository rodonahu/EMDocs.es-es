<properties title="Create tables in markdown" pageTitle="Create tables in markdown for EMS articles (Creación de tablas en Markdown para artículos de EMS)" description="Explica cómo codificar tablas en Markdown." metaKeywords="" services="" solutions="" documentationCenter="" authors="v-jocgar" videoId="" scriptId="" manager="robmazz" />

<tags ms.service="contributor-guide" ms.devlang="" ms.topic="article" ms.tgt_pltfrm="" ms.workload="" ms.date="02/26/2016" ms.author="v-jocgar" />

# Creación de tablas en Markdown

To Do:
- [ ] #33 Add the custom Markdown Note syntax to the Note below.

Las tablas de los artículos deben usarse con moderación. Utilícelas solo si los datos son realmente tabulares.

**Nota**
Las tablas de Markdown tienen limitaciones a la hora de administrar cadenas largas de texto; en las celdas de las tablas no se usa la característica de ajuste automático de línea. Las celdas simplemente se expandirán a todo el ancho del contenido, con lo que será complicado ver la tabla en pantallas más pequeñas. Reserve las tablas para conjuntos de información más reducidos y busque otras formas significativas de mostrar conjuntos de contenido más amplios.

## Sintaxis de las tablas de Markdown
La manera más sencilla de crear una tabla en Markdown es usar barras laterales y guiones. Necesita, como mínimo, 3 guiones en la segunda fila de cada columna para crear el encabezado de la tabla. El texto del encabezado de la tabla se centra automáticamente y se representa en negrita.  

 ![1]

Markdown representa automáticamente el sombreado de la fila de la tabla alternativa.  
 ![2]

Puede justificar las columnas usando dos puntos:

  	|:-----|   - this is left aligned (default -- can be omitted)
  	|-----:|   - this is right aligned
  	|:-----:|  - this is centered

El uso de barras laterales es opcional; no tiene que alinear perfectamente el texto y las barras laterales de la tabla para que se represente correctamente. Este ejemplo de formato rápido

 ![3]

se lee y representa correctamente en Markdown.  
 ![4]

Si utiliza tablas HTML y el marcado no se está procesando entre las dos tablas, debe agregar una etiqueta BR de cierre después de la etiqueta TABLE de cierre.

![5]

Para ver una forma rápida y fácil de crear tablas en Markdown, pruebe el generador de tablas de Markdown: http://www.tablesgenerator.com/markdown_tables


## Volver a la página principal

- [Artículo de información general](./../README.md)
- [Índice de artículos de la guía](./contributor-guide-index.md)

<!--image references-->
[1]: ./media/table-markdown-1.png
[2]: ./media/table-markdown-2.png
[3]: ./media/table-markdown-3.png
[4]: ./media/table-markdown-4.png
[5]: ./media/break-tables.png


<!--HONumber=Mar16_HO1-->


