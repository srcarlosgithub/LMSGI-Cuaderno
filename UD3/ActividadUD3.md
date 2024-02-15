# ACTIVIDAD UD3 - Lenguaje de Marcas en la Web. 

![Alt text](image.png)

## - **INDICE** ##
+ **HTML y su evolución**

+ **XHTML diferencias, ventajas y desventajas con respecto a HTML**

+ **Estructura de un documento HTML**

+ **Cabecera HTML**
  + **Title**
    + **Meta**
    + **Style**
    + **Link**
    + **Script**

+ **Cuerpo HTML** 
  + **Elementos de Bloque**
    + **Definir los diferentes elementos de bloque existentes**
  + **Elementos de Línea**
    + **Definir los diferentes elementos de línea existentes**
  + **Listas, tablas y Formularios**
  + **Elementos Multimedia para HTML5**
+ **Herramientas de edición y desarrollo web**


## - **HTML y su evolución** 

En esta **UD3**, voy a profundizar en uno de los lenguajes de marcas mas famosos y usados en el mundo **HTML**. Comenzaré hablando a modo de introducción sobre **HTML** para luego mas tarde abarcar su estructura, principales usos, su cuerpo...

**¿Donde se usa HTML?**

HTML es un lenguaje de marcas el cual permite estructurar mediante **etiquetas** una página **web**.

Cuando decimos **web** nos referimos a la **World Wide Web**, el cual es el servido de la **red Internet** más popular. Esta permite **compartir** documentos entre personas con **independencia** de la plataforma o **sistema operativo**.

El **correo electrónico** junto con la **web** son los servicios **más utilizados** y por los que ha tenido tanta **popularidad Internet**.


 
## - **Evolución de HTML**

Fue diseñado inicialmente en el año **1991** como parte del **CERN**, ha tenido varias versiones y diferentes **implantaciones**; veamos algunas de ellas:

| Año | Versión  | Observaciones |
|----------|----------|----------|
| 1991    | Diseñado inicial   | ```Incluye 18 etiquetas se considera dialecto SGML```   |
| 1992   | HTML 1.1  | ```Primer Borrador```  |
| 1995   | HTML 2.0   | ````Recomendación W3C````   |
| 1997    | HTML 3.2   | ```Recomendación W3C```  |
| 1997    | HTML 4.0   | ```Recomendación W3C```|
| 1999    | HTML 4.1   | ```Recomendación W3C```|
| 2000    | XHTML   | ```Publicado como recomendación del W3C. Tiene como objetivo sustituir a HTML pero se desarrolló el estándar HTML 5 por otro lado```  |
| 2014    | HTML 5.0   | ```Recomendación W3C```|
| 2016    | HTML 5.1 | ```Recomendación W3C```|
| 2017    | HTML 5.2   | ```Recomendación W3C```|

----
###  **¿XHTML?**

**XHTML** es un estándar que extiende HTML con las propias características del **metalenguaje XML**. Por ello, sigue las mismas reglas del mismo (XML) **a diferencia** de HTML.

Su estructura es **similar** al propio HTML pero con **algunas diferencias**:

  + **Las etiquetas deben estar bien animadas.**
  + **Todas las etiquetas deben estar cerradas.**
  + **Todas las etiquetas y atributos van en minúscula.**
  + **No puede haber texto sin estar dentro de una etiqueta.**
  + **Todos los atributos deben tener valor e ir entre comillas.**
  + **No se deben insertar elementos de bloque dentro de elementos inline.**
  + **Los scripts y estilos deben ir dentro de un CDATA**
  
![Alt text](image-1.png)

----
##  **NAVEGADOR**

El **navegador** es el programa diseñado para la **visualización HTML** que permite tener una versión más legible y visual al usuario.

Algunos de los navegadores más **usados**:

  + Mozilla Firefox

  + Google Chrome
  
  + Microsoft Edge

  + Opera

  + Safari

![Alt text](image-2.png)

 ---------------
##  **ESTRUCTURA DE HTML**

A continuación un ejemplo basico de la **estructura** de un documento **HTML**:

```HTML
<!DOCTYPE html>                 <!-- Doctype para validar el documento --> 
<html>
<head>                          <!-- Cabecera --> 
 <meta charset='utf-8'>
 <meta http-equiv='X-UA-Compatible'
content='IE=edge'>
 <title>Titulo Página</title>
 <meta name='viewport'
content='width=device-width,
initial-scale=1' >
 <link rel='stylesheet' type='text/css'
media='screen' href='main.css'>
 <script src='main.js'></script>
</head>
<body>                          <!-- Cuerpo --> 

</body>
</html>                         <!-- Etiquetas de apertura y cierre --> 


<!-- Ejemplo HTML --> 
``````
----

Como se puede observar la etiqueta **raíz** del documento es **< html >**. Esta etiqueta será la **raíz del documento**; permite tener una serie de **atributos** comunes a todas las etiquetas HTML.

| ETIQUETA | DESCRIPCIÓN  |
|----------|----------|
| class    | Identifica la clase para agrupar estilos.   |
| contentEditable   | El contenido es editable  | 
| hidden   | No se representa en el navegador |
| id    | Identificador del elemento   |
| lang    | Lenguaje que esta escrito   |
| spellcheck    | El elemento debe ser analizado para la ortografía   |
| style    | asigna un estilo   |
| tabindex    | Orden de selección de elementos   |
| title    | Información Extra |
| translate    | Determina si un elemento debe ser traducido  |



-----
  + **Atributos**: Para definir un atributo con DTD, podemos usar la siguiente **sintaxis**:

     ```DTD
    <!ATTLIST nombreElemento nombreAtributo tipoAtributo “valorAtributo”>
    ```

    Dónde **tipoAtributo** puede ser:

    + **CDATA:** cadena de caracteres
    + **(valor1|valor2):** Lista de valores
    + **ID:** ID *entificador único
    + **IDREF:** Referencia a un identificador de otro elemento.
 
    TipoAtributo (II):

  + **IDREFS:** Lista de referencias de otros identificadores.
  + **NMTOKEN:** Nombre XML válido.
  + **NMTOKENS:** Lista de nombres XML válidos.
  + **ENTITY:** Referencia a una entidad.
  + **ENTITIES:** Referencia de un conjunto de entidades.
  + **NOTATION:** Nombre de una anotación.
  + **xml:lang:** Idioma del documento.
  + **xml:space:** Indica si se han de respetar espacios tabulaciones y retornos de
carro múltiples.

    Para el **valor** atributo, podemos utilizar:

+ **valor:** valor o lista de valores (separados por | )que puede tomar el atributo.
+ **#REQUIRED:** Indica que el valor es requerido.
+ **#IMPLIED:** Indica que el valor es opcional.
+ **#FIXED valor:** Indica un valor fijo.

*EJEMPLO DTD*

```XML DTD
<?xml version="1.0" encoding="UTF-8"?>

<!DOCTYPE airticket[
<!ELEMENT airticket (name,originairport,destinationairport,date,flighttime)>
<!ELEMENT name (#PCDATA)>
<!ELEMENT originairport (#PCDATA)>
<!ELEMENT destinationairport (#PCDATA)>
<!ELEMENT date (#PCDATA)>
<!ELEMENT flighttime (#PCDATA)>
]>

    <airticket>
        <name>Carlos</name>
        <originairport>Malaga</originairport>
        <destinationairport>Oporto</destinationairport>
        <date>19/02/2024</date>
        <flighttime>18:00</flighttime>
    </airticket>

<!-- Ejemplo DTD --> 
``````
 

------------------------------------------------------------------

## - **XML Schema** 

+ **INDICE**:

  + **Definición**
  + **Estructura Básica**
  + **Elementos Locales y Globales**
  + **Elementos Simples**
  + **Elementos Complejos**
  + **Subelementos**
  + **Atributos**
  + **Restricciones**
  + **Tipos de Datos**
  + **Comentarios en XMLSchema**


Anteriormente he estado citando la **función principal** y los **puntos de interes** de validar con **DTD** aunque como mencione, DTD tiene una serie de desventajas frente a lo que a continuación voy a redactar **XML Schema** las cuales son las siguientes:

+ No permite validar el tipo de **dato contenido**; se guardan como cadenas.
+ No permite establecer valores **por defecto**.
+ No permite establecer **el orden** en el que deben aparecer elementos hijos,etc.
 
De estas principales debilidades de DTD **W3C**, estableció en **2001** la primera versión de **XMLSchema** (o esquema XML); a través de ficheros llamados **XSD**(XML Schema Definition); las funcionalidades que aporta XMLSChema son:

  + Permite determinar **qué elementos y atributos admite** un XML.
  + Permite determinar los **tipos de datos** que contienen tanto elementos como
atributos **(numérico, cadena,fecha...)**.
  + Permite asignar valores **por defecto**.
  + Permite determinar **cardinalidades más precisas**, orden de los elementos y
opcionalidad.
  + XMLSchema está escrito en **XML** a diferencia de DTD.
 
 XMLSchema se basa en la creación de elementos y atributos; teniendo en cuenta sus restricciones. Es decir, que se permite establecer **restricciones de tipos o de las relaciones** entre los distintos elementos.

*Ejemplo de XMLSchema:*
 
````XML Schema
<peliculas xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:noNamespaceSchemaLocation="pelicula.xsd">
    <pelicula id="11111">
        <titulo>Matrix</titulo>
        <director>Lana Wachowski</director>
        <sinopsis>El programador informático Thomas Anderson...</sinopsis>
        <actores>Keanu Reeves</actores>
        <añodeestreno>1999</añodeestreno>
    </pelicula>
</peliculas>

<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema">
    <xs:element name="peliculas">
       <xs:complexType>
            <xs:sequence>
                <xs:element name="pelicula" minOccurs="1" maxOccurs="unbounded">
                    <xs:complexType>
                        <xs:sequence>
                            <xs:element name="1" maxOccurs="unbounded">
                                
                            </xs:element>
                        </xs:sequence>
                    </xs:complexType>
                </xs:element>
            </xs:sequence>
       </xs:complexType> 
    </xs:element>
</xs:schema>
````````

El primer paso a realizar para validar nuestro XML mediante **XMLSchema** es **enlazarlo**. 

Para enlazarlo se debe de enlazar **el espacio de nombres** “xs”; y establecer un esquema por defecto”**NoNamespaceSchemaLocation”;** en caso de haber más, se pueden utilizar distintos espacios de nombres.

El esquema puede estar **en local**, o utilizando una URL:

````XML Schema
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema">
    <xs:element name="peliculas">
```````

Ahora habría que crear el anterior documento citado **.xsd** de la siguiente manera:

En el fichero .xsd, se establece el espacio de nombres para utilizar los elementos de XMLSchema (usando la url de W3C).


Dentro de dicho fichero, **ya se declararán** los distintos elementos y atributos necesarios. Los elementos pueden ser:

+ **Locales:** hijos de elementos que no son el elemento raíz y solo se usan una vez.
+ **Globales:** son hijos del elemento raíz y pueden ser reutilizados.
 

 ### ELEMENTOS

Para declarar un elemento en XML SChema se usa la siguiente sintaxis
```<xs:element name=”” type”” default=”” fixed=”” minOccurs=”0” maxOccurs=”0”/>´```


**Donde:**

+ **name:** Nombre del elemento.
+ **type:** tipo de dato. Se establece si el elemento es de tipo Simple.
+ **defaul:** Valor por defecto.
+ **Fixed:** Valor del atributo en caso de que exista.
+ **minOccurs:** Número de veces mínima que puede aparecer. Por defecto 1.
+ **maxOccurs:** Número de veces máxima que puede aparecer. Por defecto 1.

*NOTA: Si un elemento puede aparecer un número indeterminado se establecer el valor “unbounded”.*

Un elemento puede ser dependiendo de su tipo; de **dos formas**:


+ **Simple:** Guarda un texto, número,fecha,etc... Se debe de establecer el atributo type o utilizar una restricción.

+ **Complejo:** Guarda dentro elementos hijos y se pueden establecer restricciones a las relaciones.
 
 
 ### ELEMENTOS SIMPLES

**SimpleType**

*Ejemplo Elemento Simple*

````XML Schema
<xs:element name=”fecha” type=”xs:date”/>
``````



*Ejemplo Elemento Simple con restricción (Veremos más adelante)*

``````XML SChema
<xs:element name=”diaSemana”>
  <xs:simpleType>
     <xs:restriction base=”xs:integer”>
          <xs:minInclusive value=”1”/>
          <xs:maxInclusive value=”7”/>
     </xs:restriction>
  </xs:simpleType>
</xs:element>
 ``````


 ### ELEMENTOS COMPLEJOS

Para declarar un elemento complejo se realiza de la **siguiente forma**:

``````XML SChema
<xs:element name=”mensaje”>
   <xs:complexType>
       <xs:sequence>
          <xs:element name=”para” type=”xs:string”/>
       </xs:sequence>
   </xs:complexType>
</xs:element>
 ``````


Dentro de un tipo complejo se establece: 

+ **subElementos**
+ **atributos.**
Un subelemento, establece la relación de los elementos contenidos con respecto al padre. 

Pueden ser:

+ **xs:sequence:** indica una secuencia de elementos obligatorios, y en el mismo orden.

+ **xs:choise:** señala una secuencia de elementos alternativos. Solo debe aparecer uno de
ellos.

+ **xs:all:** indica una secuencia de elementos opcionales; no es obligatorio que aparezcan
todos en el mismo orden.
 


 ### ATRIBUTOS

Tanto en un elemento complejo o simple, se pueden guardar atributos; **siendo su sintaxis**:

```XML SChema
<xs:attribute name=”” type””/>
``````


El atributo tiene los siguientes valores:

+ **name:** nombre del atributo.
+ **type:** tipo de dato.
+ **use:** indica su obligatoriedad; tiene los siguientes valores:

  + **required:** es obligatorio.
  + **optional:** es opcional.
  + **prohibited:** no se puede utilizar en dicho elemento.


+ **default:** Permite asignar un valor por defecto.

+ **fixed:** determina el valor del atributo en caso de que exista.
Hay que tener en cuenta que los atributos no tienen orden, ni cardinalidad ni pueden tener hijos. Además se pueden establecer restricciones para sus valores.
 

 ### RESTRICCIONES

 Como hemos comentado, se pueden establecer restricciones a elementos y atributos. **Su sintaxis es:**
 ``````
<xs:restriction base=”xs:integer”>
   ....
</xs:restriction>
````````

Dentro de un **elemento restriction**, se establecen facetas.

| Facetas | Descripción  | 
|----------|----------|
| xs:length    | Longitud Fija    |
| xs:minLength    | Longitud mínima   | 
| xs:maxLength   |  Longitud Máxima  |
| xs:totalDigits    | total de dígitos de un número.    |
| xs:fractionDigits   | total dígitos decimales de un número.   |
| xs:minExclusive    | Indica el valor mínimo que puede tomar.   |
| xs:maxExclusive    | Indica el valor máximo que puede tomar.   |
| xs:minInclusive    | Indica el valor debe ser mayor o igual   |
| xs:maxInclusive    | Indica el valor debe ser menor o igual   |
| xs:enumeration    | Lista de valores posibles (string)   |
| xs:whiteSpace    | Determina cómo tratar los espacios en blanco.   |
| xs:pattern    | Fija un patrón de caracteres permitidos.   |

 

 ### TIPOS DE DATOS BASICOS

| Tipo | Descripción  | 
|----------|----------|
| xs:string    | cadena de caracteres    |
| xs:integer    | Números enteros.   | 
| xs:decimal   |  Números decimales; usando “.” como separador.  |
| xs:boolean    | Booleano. “true” para verdadero y “false” para lo contrario.    |
| xs:date    | fecha con formato AAAA-MM-DD   |
| xs:time    | hora con formato hh:mm:ss   |
| xs:duration    | duración de tiempo en formato “PnYnMnDTnHnMnS”.   |


 ### COMENTARIOS

 Se pueden establecer **comentarios** dentro del XMLSchema para ayudar a su comprensión; veamos un *ejemplo*

 ````XML Schema
<xs:element name=”mensaje”>
<xs:annotation>
     <xs:appInfo>Información de mensaje</xs:appInfo>
     <xs:documentation xml:lang=”es”>
        Mensaje a enviar
     </xs:documentation>
</xs:annotation>
``````

Donde:
+ **appInfo:** información del elemento o atributo.

+ **documentation:** documentación en detalle del elemento o atributo.
 