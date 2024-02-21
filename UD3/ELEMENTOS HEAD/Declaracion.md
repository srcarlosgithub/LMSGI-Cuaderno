#  **ESTRUCTURA XML**

## - **Declaración (prologo):** 

Es un elemento opcional que se incluye al inicio del documento; debe empezar por **< ?xml y acabar por ?>** . 

Puede contener los siguientes **[Atributos](Atributos.md)**:

+ **Version: Versión de XML.**
+ **encoding: Codificación del documento.**
+ **standalone: Indica si el documento es independiente o si existe un DTD externo. Admite valores “yes” o “no” para indicar si existe dicho vocabulario.**

*DTD: Document Type Definition: contiene las reglas que determinan que un
documento XML es válido. Lo veremos en esta unidad.*

**EJEMPLO**:
```XML
<?xml version="1.0" encoding="UTF-8" standalone="yes" ?>
```