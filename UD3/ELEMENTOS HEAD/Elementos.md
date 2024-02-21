#  **ESTRUCTURA XML**

## - **Elementos:** 

Un documento xml se compone por una serie de **elementos**:

+ **Un elemento tiene un nombre que se diferencia entre mayusculas y minusculas.**
+ **Comienza por <nombre> y termina por </nombre>. Deben ser iguales en su apertura
y cierre.**
+ **Los nombres de los elementos deben ser caracteres alfanuméricos, guiones, guiones
bajos o puntos(no puede contener espacios).**
+ **Debe haber un único elemento inicial llamado raíz (aunque puede llamarse de la
forma que queramos).**
+ **Dentro de un elemento, puede haber más elementos o texto.**
+ **Si un elemento está vacío puede escribirse como < nombre/>**

### En un documento XML existen las siguientes relaciones:

+ **Un único elemento raíz (root).**
+ **Cada uno de los elementos descendientes de un elemento, se llaman hijos
(children).**
+ **El elemento ascendente de un elemento, se llama padre (parent).**
+ **Los elementos que tienen un padre común se denominan hermanos (slibling).**

**EJEMPLO**:
```XML
<receta raciones="6" dificultad="media">
    <nombre>Tortilla de Patatas</nombre>
    <ingredientes>
        <ingrediente cantidad="1" unidad="Kilogramo">Patata</ingrediente>
        <ingrediente cantidad="8" unidad="Unidades">Huevo</ingrediente>
        <!--receta como root | nombre como padre | e ingredientes y eleaboracion como hijos-->
        <ingrediente cantidad="1" unidad="Unidades">Cebolla</ingrediente>
        <ingrediente>Acceite de Oliva</ingrediente>
        <ingrediente>Sal</ingrediente>
    </ingredientes>
    <elaboracion>
        Se pelan las patatas...    
    </elaboracion>
</receta>
```