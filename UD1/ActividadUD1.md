# ACTIVIDAD UD1 - Introducción a los Lenguajes de Marcas.
## - **Indice** ##
+ **Qué es un Lenguaje de marcas**
+ **Evolución de los Lenguajes de marcas**
  + **GML**
  + **SGML**
+ **Características de los lenguajes de marcas**
+ **Características y ejemplos de los siguientes lenguajes de marcas:**
  + **XML**
  + **HTML**
  + **JSON**
  + **YAML** 
+ **XML: definición y características del metalenguaje**
  + **Prologo**
  + **Etiquetas**
  + **Atributos**
  + **Ejemplos en XML**

-------------------------------------------------------------------------------

## - **Que es un lenguaje de marcas?** ##

Un **Markup Language** (Lenguaje de marcas) es un lenguaje informatico el cuál tiene como **función principal** codificar un texto junto con etiquetas o **marcas** las cuales definen su **estructura** y **presentación**.

Es el lenguaje que permiten y entienden los **navegadores web**. 

Lo que los diferencia de los lenguajes de programación es que el lenguaje de marcas **no tien   e** funciones **aritmeticas** o **variables**

*Ejemplos:*

| **_HTML_** | **_XML_** | **_Markdown_** |

![](https://www.institutoserlog.com/wp-content/uploads/2019/08/web.jpg)


## - **Evolución de los Lenguajes de Marcas** 
* **[GML](%20GML.md)**
* **[SGML](SGML.md)**

## - **Características de los lenguajes de marcas** 

Las principales características de los lenguajes de marcas son:

+ **Independientes**: Su uso no depende de ninguna plataforma de software ni hardware.

+ **Almacenados en Texto Plano**: Solo están compuestos por caracteres de texto.

+ **Flexibles**: Son lo suficientemente flexibles como para poder usarse en cualquier contexto.

+ **Compatibles**: Las marcas y su contenido se encuentran en el mismo documento.

+ **Autodescriptibles**: Las marcas y etiquetas descríben asi mismo su función.

+ **Organizados**: Su estructura y sintaxis por lo general suele ser organizada.

+ **Facil procesamiento**: El formato debe de estar estructurado dde forma que el procesamiento automático sea sencillo.

## - **Características y ejemplos de los siguientes lenguajes de marcas?** 
* [**XML**](XML.md)
* [**HTML**](HTML.md)
* [**JSON**](JSON.md)
* [**YAML**](YAML.md)


## - **XML: definición y características del metalenguaje** 
**Prologo**: El prologo de un documento XML se ve de la siguiente manera:

![Alt text](Captura de Pantalla 2023-10-29 a las 21.01.45.png)

Este apartado es **opcional** y tiene como **función principal** dar información
relativa al documento, tiene los siguientes elementos:     

+ **version**: indica la versión XML que se esta usando "1.1".

+ **encoding**: indica la codificación usada en el documento "UTF-8".

+ **standalone**: indica la existencia de un esquema XML en el propio documento externo.

**Etiquetas**: Las etiquetas contienen información del documento, las cuales funcionan de la siguiente manera:

+ Las etiquetas deben de tener un **incio** y **final** entre los simbolos **<>**.

+ A continuación esta debe de cerrarse con la misma palabra entre **/<>**.

+ Llamamos **elemento** al par de etiquetas que tienen una **apertura** y **final**.

+ Dentro de un elemento encontramos **información relacionada** a este.

+ Las estiquetas pueden estar compuestas por **atributos** que se hablarán de 
ellos en el siguiente apartado.

+ En un documento XML solo puede haber un elemento **raíz**.

+ Pueden añadirse **comentarios** a tráves de **<!--** y 
**-->**

+ Si un elemento se encuentra **vacio** puede acortarse definiendo la etiqueta
de esta manera **< elemento/>**

**Atributos**:

Los **atributos** de las **etiquetas** añaden información adicional de esta:

+ Un **atributo** es información **adicional** que se le da a una etiqueta en
**concreto**

+ Seguida del **simbolo =** y entre **"comillas dobles"**.

+ Una **etiqueta** puede estar compuesta por **0 o más** atributos.

+ Cada **atributo** contiene información, no puede estar **compuesto** por otro atributo más.

**Ejemplos en XML**:

```
<videojuegos>
  <videojuego id="01">
   <name>DarkSouls III</name>
   <company>Fromsoftware</company>
   <price>59.99€</price>
  </videojuego>

  <videojuego id="02">
   <name>Sekiro: Shadows Die Twice</name>
   <company>Fromsoftware</company>
   <price>59.99€</price>
  </videojuego>   

  <videojuego id="03">
   <name>Bloodborne</name>
   <company>Fromsoftware</company>
   <price>59.99€</price>
  </videojuego>
</videojuegos>
```

![Alt text](<Captura de Pantalla 2023-10-29 a las 21.35.42.png>)
