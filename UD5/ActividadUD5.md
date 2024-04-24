# ACTIVIDAD UD5 - Sindicación de contenidos web. 

![alt text](image.png)


## - **Indice** ##
+ **Sindicación de contenidos en la web**
+ **Sindicación de contenidos**
+ **RSS (Sintaxis y ejemplos)**
+ **Atom (sintaxis y ejemplos)**
+ **Herramientasde validación de canales de sindicación**
+ **Añadir canales de sindicación a una web** 
+ **Agregores de canales**
+ **Canales de sindicación**
-----------------------------------------

## - **Sindicación de contenidos en la web** 

En esta **UD5**, hablaré sobre el uso de la sindicación de contenidos en la web, viendo su importancia para poder **difundir** en **internet** el contenido de nuestra web con **HTML** y **CSS**, ya que para esto necesitaremos del uso de esta.

No siempre es fácil dar con el contenido o dar a conocer nuestro contenido. Para ello las **herramientas de sindicación de contenidos** para poder difundir esta información.

También como **puntos de aprendizaje** principales que quiero llevar acabo en esta unidad son:

+ **Conocer los fundamentos y la utilidad de los sitemas de difusión**
+ **Analizar los formatos  más utilizados en redifusión**
+ **Presentar diversas herramientas para la creación y el consumo de canales de información**
+ **Enumerar algunos canales de información interesantes de diversos ámbitos**

![alt text](image-1.png)

Es mantenido por **W3C** al igual que **HTML, XML y CSS**. 

----

 ## **Sindicación de contenidos:**

 Los **sistemas de redifusión web** o **sindicación web** permiten liberar de trabajo a los usuarios a la hora de **proporcionar** un mecanismo de suscripción gracias al cual la información de la web llega a los usuarios **en vez de buscarla**.

Algunos de estos sistemas se basan en canales de redifusión llamados **fuente web, canal web, o web feed**.

Una **fuente web** es un documento el cual contiene **información básica** sobre elementos de información incluyendo referencias para **acceder a estos elementos**.

Existen varios formatos basados en **XML**: como puede ser **Atom** o **RSS**.

 ## **RSS:**

El formato **RSS** *(Really Simple Syndication)* es un **dialecto** XML, que permite distribuir contenidos a través de la **web**.

Al igual que **XML** es mantenido por la **W3C** y fue publicada su primera versión en **1997**; actualmente es **utilizada la v2.0** publicada en 2003.

Su extensión puede ser **.xml** o **.rss**

- ### **Sintaxis**:

  + El elemento raíz siempre sera < rss > que tendrá el **atributo: version**  con el valor **2.0**.

  + Este **elemento** tendra un **subelemento** llamado < channel > por cada canal de **suscripción** que tenga la web.

En el elemento **channel**; tendremos los siguientes elementos obligatorios:

| Elemento | Descripción  | 
|----------|----------|
| < tittle >    | Titulo del canal    | 
| < link >    | Enlace al sitio web   | 
| < description >   | Descripción del contenido | 
| < language >    | Idioma en el que está escrito el canal |
| < copyright >    | Aviso relativo a los derechos de autor |
| < category >    | Una o más categorias a la que pertenece el canal |
| < generator >    | Nombre del programa que ha generado el canal | 

Además de estos elementos, podemos encontrar una o más entradas definidas con el elemento **< item >**. Cada elemento contiene:

| Elemento | Descripción  | 
|----------|----------|
| < tittle >    | Titulo de la entrada    | 
| < link >    | Enlace a la entrada   | 
| < description >   | Descripción de la entrada | 
| < pubDate >    | Fecha de publicación en formato RFC-822 |
| < comments >    | Contiene la URL con los comentarios de la entrada |
| < author >    | Dirección electrónica (email) del autor |

- ### **Ejemplo RSS:**

```RSS
<?xml version="1.0" encoding="UTF-8" ?>
<rss version="2.0">

<channel>
  <title>Carlos Home Page</title>
  <link>https://www.carlosgithub.com</link>
  <description>Directorio UD5 Ejemplo RSS</description>
  <item>
    <title>RSS Ejemplo primer articulo</title>
    <link>https://www.carlosgithub/RSSejemplo</link>
    <description>Articulo de RSS con ejemplo</description>
  </item>
</channel>

</rss>
```

## **ATOM:**

Atom es otro **formato de sindicación** de contenidos basado en **XML**. Los ficheros **Atom** suelen tener extensión **.xml** o **.atom**.

- ### **Sintaxis:**

La sintaxis de Atom es la siguiente:

  + El elemento raíz < feed > que se le indica el espacio de nombres **xmlns=https://www.w3.org/2005/Atom** ; además de los elementos a continuación:
  
| Elemento | Descripción  | 
|----------|----------|
| < id >    | Identifica el canal utilizando una URL    | 
| < tittle >    | Título del canal   | 
| < updated >   | Fecha de la última actualización | 
| < author >    | Indica el autor; contiene la etiqueta < name > y opcionalmente < email > y < uri > |
| < link >    | Enlace mediante el atributo *href* al canal |
| < author >    | Dirección electrónica (email) del autor |

En el elemento raíz feed podemos encontrar los siguientes elementos opcionales:

| Elemento | Descripción  | 
|----------|----------|
| < category >    | Categoría del canal; puede tener múltiples elementos.    | 
| < contributor >    | Nombre o nombres del colaborador; contiene las etiquetas < name > y opcionalmente < email > o < uri >   | 
| < generator >   | Programa que ha generado este feed. | 
| < rights >    | Contiene información acerca de los derechos de propiedad del canal. |
| < subtitle >    | Contiene la disposición final. |

Dentro del propio Feed pueden aparecer una o varias entradas; estas se identifican por el elemento < entry >; el elemento entry aparecerán los siguientes elementos:

| Elemento | Descripción  | 
|----------|----------|
| < id >    | Identificador de la entrada debe ser una URI    | 
| < tittle >    | Título de la entrada   | 
| < updated >   | Fecha de actualización | 
| < content >    | Descripción del contenido > |
| < author >    | Autor de la entrada; debe contener el elemento < name > y opcionalmente los elementos < email > o < uri > |
| < link >    | Enlace a la entrada con el atributo *href* |
| < summary >    | Resumen de la entrada |
| < category >    | Categoría de la entrada |
| < contributor >    | Colaborador de la entrada; debe contener el elemento < name > y opcionalmente los elementos < email > o < uri > |
| < published >    | Fecha de publicación |
| < link >    | Información acerca de la propiedad o los derechos de la entrada |


- ### **Ejemplo ATOM:**

```ATOM

<?xml version="1.0" encoding="utf-8"?>

<feed xmlns="http://www.w3.org/2005/Atom">

  <title>Example Feed</title>
  <subtitle>A subtitle.</subtitle>
  <link href="http://example.org/feed/" rel="self" />
  <id>urn:uuid:60276c80-d399-11d9-b91C-00939390006</id>
  <updated>2003-12-13T18:30:022</updated>

  <entry>
    <title>Atom-Powered Robots Run Amok</title>
    <link href="http://example.org/2003/12/13/atom03" />
    <link rel="alternate” type="text/html” href="http://example.org/2003/12/13at0m03.html"/>
    <id>urn:uuid:1225c695-cfb8-4ebb-aana-SOda344efada</id>
    <published>2003-11-09117:23:022</published>
    <updated>2003-12-13T18:39:022</updated>
    <summary>Some text.</summary>
    <content type="xhtml">
      <div xmlns="http://w.3.or9/1999/xhtaU">
        <p>This is the entry content.</p>
      </div>
    </content>
    <author>
      <name>John Doe</name>
      <email>johndoe@example.con</email>
    </author>
  </entry>

</feed>

```

## **Validar Canales:**

Podemos utilizar validadores para ver 