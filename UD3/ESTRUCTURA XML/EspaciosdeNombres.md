#  **ESTRUCTURA XML**

## - **Espacios de nombres:** 

El **espacio de nombres** o **namespace**, es un identificador que se utiliza para
resolver las ambigüedades que podrían surgir cuando hay dos o más elementos
**iguales**.

La declaración de un espacio de nombres se realiza **con el atributo** xmlns seguido
por el **nombre y una URL**.

**EJEMPLO**:
```XML
<restaurantes xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:noNamespaceSchemaLocation="restaurantes.xsd">
```