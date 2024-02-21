#  **ESTRUCTURA XML**

## - **CDATA:** 

En XML, una **sección CDATA** es un conjunto de caracteres que no debe ser tratado por el analizador, pero si formará parte de la información **(a diferencia de un comentario).**

+ **Comienza por <![CDATA[.**
+ **Acaba con ]]>**

**EJEMPLO**:
```XML
<evaluacion id="1"> 
                <LMGSI>10.00</LMGSI><![CDATA[ <---
                <html>
                    <head>hola</head>
                    <body>ejemplo de cdata</body>
                </html>
                ]]>
                <ISO>10.00</ISO>
                <F.HARDWARE>10.00</F.HARDWARE>
                <PAR>10.00</PAR>
                <BD>10.00</BD>
```