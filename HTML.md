## ¿Que es HTML?

**HTML** es uno por no decir el **lenguaje de marcas** mas conocido. Es el estandar evolucionado de **SGML** la cual en **Octubre de 2014** fue obsoleta por la **version 5** de HTML.

Es desarrollado y mantenido por **W3C**.

Se podría decir que la principal función de **HTML** es ser reconocido e **interpretado** por los navegadores web.

También destacar que junto a **CSS** hacen una combinación perfecta ya que CSS permite que HTML pueda tener muchos **estilos** personalizados.

Gracias a **HTML** y el uso de **javascript** hoy en dia podemos dar uso a las **aplicaciones web** 

Podemos reconocer un **fichero** html por su extensión _.html_ .


## ¿Usos y Características?

+ Es **facil** de entender y **usar**.

+ Es utilizado para **crear** paginas web.

+ Permite describir **hipertextos**

+ Permite que el usuario pueda **moverse por cualquier sitio web** haciendo click en un texto específico llamado **hipervinculo**

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
