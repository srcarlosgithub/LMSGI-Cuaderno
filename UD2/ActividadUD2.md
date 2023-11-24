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

## - **Documentos XML, estructura:** 

En esta **UD2**, voy a profundizar en el uso y validación de documentos XML. Para tener claro los puntos mas importantes de **XML** que redacte en la **UD1** hay que tener en cuenta los siguientes puntos:

● **XML(Extensible Markup Languaje)** es un **metalenguaje** para crear otros
lenguajes **más específicos**.

● Es mantenido por la **W3C** y actualmente está en la versión **1.1**.

● Su **extensión** suele ser .xml y su tipo MIME es application/text o text/xml.
* **W3C recomienda usar la versión 1.0 a no ser que se quieran usar las nuevas
funcionalidades específicamente.**

###  **Su estructura:**

+ La estructura de un documento XML se define por:

  + **[Declaración](Declaracion.md)**

  + **[Elementos](Elementos.md)**

  + **[Atributos](Atributos.md)**

  + **[Comentarios](Comentarios.md)**

  + **[Espacios de Nombres](EspaciosdeNombres.md)**

  + **[Entidades](Entidades.md)**

  + **[CDATA](CDATA.md)**


![](https://blog.webnersolutions.com/wp-content/uploads/2019/11/Demo-XMl.png)

------------------------------------------------------------------


## - **Validación de documentos** 

## - **XML Schema** 

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

