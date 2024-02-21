#  **ESTRUCTURA XML**

## - **Entidades:** 

Las entidades en XML, permiten incluir información predefinida en un documento:

+ Pueden ser definidas en el **propio DTD** o que **sean externas**.
+ Empiezan por **&** y finalizan por **;**
+ Se pueden clasificar por:
    + **Generales** (forma parte del documento)
        + **Internas** (Son predefinidas y mantienen su valor)
        + **Externas** (Mantienen los valores en un fichero externo).
    + **Entidades de parámetros** (Se transforma en DTD)

## Existen 5 entidades generales predefinidas internas:

| Entidad | Descripción  | carácter |
|----------|----------|----------|
| &lt;    | Menor que    | <   |
| &gt;    | Mayor que   | >   |
| &amp;   | Ampersand   | &   |
| &apos;    | Comilla simple    | ´   |
| &quot;    | Comilla doble   | ""   |

**EJEMPLO**:
```XML
    <nombre>Tortilla de Patatas</nombre>
    <ingredientes>
        <ingrediente cantidad="1" unidad="Kilogramo">Patata</ingrediente>
        <ingrediente cantidad="8" unidad="Unidades">Huevo</ingrediente>
        <!--ejemplos de las entidades y como se componen-->
        <ingrediente cantidad="1" unidad="Unidades">Cebolla</ingrediente>
        <ingrediente>Acceite de Oliva</ingrediente>
        <ingrediente>Sal</ingrediente>
    </ingredientes>
```