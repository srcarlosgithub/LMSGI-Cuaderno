#  **Propiedades CSS**

## **Diseño adaptativo (Media Queries)**

Hay que tener en cuenta que nuestro documento web puede ser representado en una **multitud de dispositivos** diferentes entre si, donde la escala de **resolución** de cada uno de ellos **varía** completamente. *Tablets, smartphones, laptops, gafas de realidad aumentada*.

Es **necesario** adaptar el **CSS** para cada **pantalla**. Es por ello que se da el **uso de media queries**. Esta **permite** seleccionar una serie de **reglas** dependiendo del **tamaño de la pantalla**. 

Por ejemplo:

```CSS
@media screen and (min-width: 480px) {
 body {
 background-color: lightgreen;
 }
}
```

![Alt text](image-9.png)