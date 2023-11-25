# ACTIVIDAD UD2 - Vocabularios y esquemas en XML. 

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
 


**Ejemplos en XML**:

```XML
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

