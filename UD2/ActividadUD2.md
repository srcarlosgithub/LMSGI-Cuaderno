# ACTIVIDAD UD2 - Vocabularios y esquemas en XML. 

![](https://www.institutoserlog.com/wp-content/uploads/2019/08/web.jpg)


## - **Indice** ##
+ **Documentos XML, estructura:**
  + **Declaración o prólogo**   
  + **Elementos**
  + **Atributos**
  + **Comentarios**
  + **Espacios de Nombres**
  + **Entidades**
  + **CDATA**

+ **Validación de documentos**
  + **DTD**
    + **Entidades**
    + **Anotaciones**
    + **Elementos**
    + **Atributos** 
  + **XMLSchema**
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

-----------------------------------------

## - **Validación de documentos** 

En esta **UD2**, voy a profundizar en el uso y validación de documentos XML. En el siguiente apartado veremos el principal uso de la validación de documentos XML mediante dos principales estandares; **DTD** y **XML Schema**. 
Ambos cumplen el mismo objetivo, **validar la estructura y el contenido** de un documento XML, aunque cada uno se forma de **diferente** manera.

Un documento XML esta formado de manera **correcta** cuando se cumplen los siguientes puntos.

+ **Tiene un único elemento raíz.**

+ **Todos los elementos deben estar cerrados.**

+ **Los elementos tienen que estar anidados correctamente; no se pueden
intercalar aperturas y cierres.**

+ **Todos los valores de los atributos están entrecomillados.**

+ **Los nombres de elementos y atributos, deben cumplir sus respectivas reglas.**
 

A continuación veremos en concreto a los dos **validadores de XML** mencionados anteriormente y sus principales **caracteriticas**:


###  **DTD:**

**DTD (Document Type Definition**), es una serie de reglas que van a permitir validar que la estructura de un documento es válida.

Las reglas contenidas en un DTD tienen que ver con la **estructura del documento** (elementos, atributos,entidades...); aunque tiene algunas limitaciones que se pueden suplir usando **XML Schema**.
 

 DTD esta compuesto por:

----
  + **Entidades**: Como hemos comentado en XML, se pueden definir entidades dentro de un DTD; que permiten usar esa entidad para establecer un valor.
Las entidades pueden ser:
    + Internas: Definidas en el propio DTD

      ```<!ENTITY nombreEntidad “valor”>```

    + Externas: Definidas en un fichero externo. Pueden ser públicas o privadas. 
    
      + Públicas: 
      
      ```<!ENTITY nombreEntidad PUBLIC “id_publico” “URI/URL”>```
        
      + Privadas: 
      
      ```<!ENTITY nombreEntidad SYSTEM “URI/URL”>```


*Para usar una entidad:
**&nombreEntidad**;*

 ---------------
  + **Anotaciones**: Una **anotación**, nos permite identificar el formato de entidades que no son XML y que no se van a procesar; como puede ser el valor de un atributo.


    Pueden ser: 
    
    + Públicas

    + Privadas

      ```<!NOTATION nombre SYSTEM “URI”>```

      ```<!NOTATION nombre PUBLIC “id_publico”>```

      ```<!NOTATION nombre PUBLIC “Id_publico” “URI”>```
 
-------  
  + **Elementos**: Un elemento en DTD, define la estructura de uno o varios elementos que contienen el documento.
  
    Para definirlo se usa la siguiente sintaxis: ```<!ELEMENT nombreElemento (contenido)>```


    Dónde contenido puede ser:

      + **EMPTY:** Vacío.
      + **ANY:** Cualquier valor.
      + **(#PCDATA):** Elementos de tipo carácter.
      + **(nombreElemento):** Elemento hijo.
      + **(nombreElemento1,NombreElemento2,...):** Lista de elementos hijos.
 
    Dentro de cada **elemento** podemos definir diferentes **cardinalidades**:

| Notación | Descripción  | carácter |
|----------|----------|----------|
| (Elemento)    | Una única ocurrencia    | ```<!ELEMENT aviso (mensaje)>```   |
| (Elemento+)    | Una o más repeticiones   | ```<!ELEMENT aviso (mensaje+)>```  |
| (Elemento*)   | 0 o más ocurrencias   | ````<!ELEMENT aviso (mensaje*)>````   |
| (Elemento1,E2,E3)    | Deben aparecer todos los elementos en la lista    | ```<!ELEMENT mensaje( de,para,mensaje)>```  |
| (Elemento1/E2/)    | Deben de contener uno u otro elemento   | ```<!ELEMENT mensaje( de,para,mensaje)>``|

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
 