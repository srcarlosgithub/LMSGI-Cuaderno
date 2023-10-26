## ¿Que es XML?

**XML** no es un lenguaje de marcas como tal, sino que define una **seríe de reglas** para crear lenguajes de marcas específicos.

Este permite **crear** documentos con datos estructurados por el usuario **usando** dichas **reglas**.

Dichos documentos contienen información que es legible tanto para los **humanos** como para las *maquinas* de **forma sencilla**.

Se guarda en forma de **texto** y al igual que **HTML** proviene de **SGML**.

![Alt text](2656443.png)

## ¿Usos y Características?

+ Permite crear **etiquetas** (a través de dichas reglas creando en sí un **lengua de marcas**)

+ Permite el uso de **esquemas** (usando espacios de nombres), validando la estructura del mismo documento.

+ En un documento **XML** tanto la **estructura** como el **diseño** estan definidos de forma separada.

+ Es almacenado en formato **texto** (no binario).

+ Permite guardar información en distintas **codificaciones**.

## ¿Estructura, Ejemplo práctico y sintaxis?

La **estructura** de **XML** esta compuesta por:

+ **Prólogo**: Es opcional, indica información relativa al propio **documento** puede contener los siguientes elementos;
    + **Version:** Indica la versión del documento XML (la ultima es 1.1).

    + **Encoding:** Indica la codificación aplicada al documento (UTF-8).

    + **Standalone:** Indica la existencia de un esquema XML en el propio o externo documento.
```
<?xml version="1.0" encoding="UTF-8 standalone="yes"?>
```

+ **Etiquetas**: Las etiquetas son lo que hace característico a los Lenguajes de Marcas.

Estas siempre van **< abiertas >** entre llaves (<>) y terminan cuando se cierran **</ abiertas>** con la misma palabra.

Cuando sucede esto se le llama **elemento** en los cuales se pueden encontrar **información**, u otros **elementos**.

Pueden añadirse **comentarios** en las etiquetas de esta manera < !-- comentario --> y las etiquetas pueden contener **atributos**.

+ **Atributos**: Es una información **adicional** sobre la **etiqueta** en concreto.

Este comienza por una **palabra** seguido por un **=** y su información adicional entre **""** .

Una etiqueta **no tiene** porque **contener** un atributo pero si fuera el caso podría tener **mas de uno**.

```
<videojuego identificador="008">
```
En este caso la etiqueta sería **videojuego** y el atributo **identificador**


### EJEMPLO XML: ###
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
