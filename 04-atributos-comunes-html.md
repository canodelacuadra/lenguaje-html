# Atributos comunes html
Como hemos visto,  HTML está formado por elementos etiquetados. Muchas etiquetas. Cada etiqueta tiene una misión y tarea y contendrá cierto contenido relacionado con su misión. Y además tenemos los atributos, que son palabras clave de texto que **modifican**  ligeramente el comportamiento de la etiqueta que lo contiene.

En este apartado vamos a ver una lista de atributos comunes que pueden ser utilizados en cualquier etiqueta de elementos HTML:

* id |:	nombre. 	Establece un identificador a la etiqueta HTML (sólo una por página con ese nombre).
* class:	nombre1, nombre2.	Establece una clase (género) a una elemento HTML. Puede repetirse por página. Además puede haber varias clases por elemento
* lang:	idioma.	Indica el idioma del contenido de la etiqueta HTML.
* translate	yes | no.	Indica si el contenido de la etiqueta es traducible o no.
* title:	título.	Mensaje mostrado en un tooltip (aviso amarillo emergente) al mover el ratón encima.
* data-*|	nombre.	Metadatos en la propia etiqueta. Se puede usar cualquier nombre con prefijo data-.
accesskey| 	atajo.	Combinación de teclas que puede pulsar el usuario para activar el elemento.
* dir:	ltr | rtl.	Establece la direccionalidad del texto (left to right o right to left).
* style:	estilos css.	Aplica propiedades CSS directamente al elemento en cuestión.
> Esta sección no es absolutamente necesaria para usuarios iniciados, y quizás requiera adquirir más práctica con HTML antes de comenzar a leer esta parte.

## Identificador de etiqueta (id) 
En HTML, podemos darle un identificador a una etiqueta HTML y de esta forma darle un nombre. Simplemente, añadimos el atributo id y colocamos el nombre como valor de ese atributo. Ese nombre de identificador no debe empezar nunca por un número y puede contener letras mayúsculas, minúsculas, signos especiales (guión, guión bajo...) o números:
````html
<div id="pagina">
  <div>Aquí irá un anuncio</div>
  <div id="articulo">Aquí irá el contenido de texto del artículo</div>
  <div>Aquí irá un anuncio</div>
</div>
````
Los id se suelen indicar cuando queremos localizar zonas específicas que sabemos que no se van a repetir en esa misma página.

Uno de los detalles importantes de los id, es que no pueden haber dos con el mismo nombre en una página. Ejemplos correctos de id serían «pagina» (para contener toda la página completa), «comentarios» (para contener toda la zona de comentarios de la página) o «header» (para contener la parte con el logo y la cabecera de la página). Lo que debe quedar claro de los ids, es que no se puede tener el mismo id en varias etiquetas HTML en una misma página.

Más adelante, en el apartado de enlaces o hipervínculos, veremos que también podemos utilizarlos para acceder rápidamente, desde un enlace, a esa sección concreta de la página.

## Clases de etiquetas (class) 
Las clases funcionan de una forma muy similar a los id, pero son mucho más flexibles. En primer lugar, no tienen la limitación de los ids, por lo que su nombre se puede repetir y no es necesario que aparezca sólo una vez por página.

De hecho, la idea de las clases es establecer géneros o tipos de etiquetas, a los que les asociemos características comunes. Sigamos con el ejemplo anterior:
````html
<div id="pagina">
  <div class="anuncio">Aquí irá un anuncio</div>
  <div id="articulo">Aquí irá el contenido de texto del artículo</div>
  <div class="anuncio">Aquí irá un anuncio</div>
</div>
````
Obsérvese que, al tener la misma clase «anuncio», podemos realizar acciones para todas las etiquetas de ese tipo y no tener que hacerlo para cada una de ellas por separado. Un ejemplo clásico donde se ve bien su utilidad, es respecto a utilizar ids y clases para dar estilo CSS, donde aplicaremos unos estilos concretos a todas las etiquetas HTML con clase «anuncio».

Además, una etiqueta puede tener múltiples clases diferentes, no una sola. Esto nos da más flexibilidad a la hora de crear clases específicas:
````html
<div id="pagina">
  <div class="anuncio primero">Aquí irá un anuncio</div>
  <div id="articulo">Aquí irá el contenido de texto del artículo</div>
  <div class="anuncio ultimo">Aquí irá un anuncio</div>
</div>
````
Nótese que en la primera etiqueta del anuncio hemos aplicado las clases anuncio y primero, mientras que en el último anuncio hemos aplicado las clases anuncio y último. Esto nos permitiría asignar atributos comunes al anuncio en la clase anuncio, y atributos que sólo dependan de la posición donde esta colocado en primero y/o ultimo.

Recordar siempre que para indicar múltiples clases se debe separar las clases por espacio dentro de un mismoa atributo class. No se debe nunca indicar varios atributos class en una misma etiqueta, ya que el navegador lo que haría es sobreescribir el valor del último class con los de los primeros.

## Idioma del contenido 
Mediante el atributo lang podemos indicar el idioma del contenido de la etiqueta. El valor de dicho atributo tendrá que ser el ````código ISO 639-1```` del idioma al que queremos hacer referencia. También podemos utilizar el atributo translate para indicar si el contenido de un texto es o no traducible:
````html
<p>
  Hace algunos días fuí a ver la nueva película de <span translate="no">StarWars</span>.
</p>
````
De esta forma, le indicamos al navegador o a herramientas como Google Translator, que esa frase específica no se debe traducir porque es el título que queremos que aparezca siempre. Por defecto, si no se indica el atributo translate en una etiqueta, es como si tuviera el valor yes por defecto.

### Títulos o tooltips 
En la mayoría de las etiquetas HTML podemos indicar el atributo title para especificar un mensaje de texto que aparezca cuando el usuario detenga el ratón sobre el elemento un instante. Al usuario le aparece un pequeño aviso emergente, generalmente con fondo amarillo y letras negras, que muestra el texto en cuestión:
````
<div>
  <img src="Gandalf.jpg"
    alt="Gandalf el gris, utilizando un portátil para consultar su correo."
    title="¡Este es Gandalf el gris!" />
</div>
````
Es importante no confundir el atributo title con el atributo alt de las imágenes, que generalmente se confunden porque pueden tener objetivos idénticos, pero no siempre es así. El atributo alt debe ser un texto alternativo que describa la imagen en el caso de que no se pueda ver visualmente, mientras que el atributo title puede describir la imagen, pero no tiene porque ser una descripción alternativa.

De la misma forma, podemos utilizar el atributo title para otros elementos, como por ejemplo, etiquetas ````<a>```` (enlaces) u otras.

### Metadatos (datasets) 
En HTML, veremos que la mayoría de los metadatos (información adicional) se incluyen en la etiqueta ````<head>```` del documento HTML. Sin embargo, también se puede incluir metadatos en la propia etiqueta HTML a través de un atributo con prefijo data-.

De esta forma, podemos inventarnos cualquier atributo que contenga información, habitualmente orientada a utilizarse desde Javascript:
````
<div id="compartir">
  <a href="https://twitter.com/share/?url=https://lenguajehtml.com/"
     data-share="43">Twitter</a>
  <a href="https://www.facebook.com/sharer/sharer.php?u=https://lenguajehtml.com/"
     data-share="66">Facebook</a>
  <a href="https://plus.google.com/share?url=https://lenguajehtml.com/"
     data-share="38">Google+</a>
</div>
````
En este ejemplo guardamos, a través de Javascript, el número de veces que ha sido compartido un enlace de la página, pudiendo reutilizarlo posteriormente en nuestro código. Si queremos hacer referencia a estos elementos desde Javascript, debemos hacerlo mediante la propiedad .dataset:
````js
var links = document.querySelectorAll("#compartir a");

links[0].dataset.share; // 43
links[1].dataset.share; // 66
links[2].dataset.share; // 38

````
### Atajo de teclado (accesskey) 
En HTML es posible añadir el atributo accesskey para indicar un atajo de teclado que puede pulsar el usuario para activar ese elemento. En el siguiente ejemplo, tenemos 4 elementos: dos campos de texto, un enlace y un botón. Cada uno de ellos tiene su atributo accesskey para que cuando el usuario pulse ALT+tecla, se active ese elemento:

````html
<form>
  <input accesskey="N" placeholder="Nombre (ALT+N)" /> <!-- Campo de datos -->
  <input accesskey="A" placeholder="Apellidos (ALT+A)" /> <!-- Campo de datos -->
  <a accesskey="L" href="#">Enlace (ALT+L)</a> <!-- Enlace HTML -->
  <button accesskey="B">Botón (ALT+B)</button> <!-- Botón HTML -->
</form>

````
De esta forma, si pulsamos ALT+N, se colocará el foco en el primer campo de texto, si pulsamos ALT+L será como si hubieramos pulsado el enlace con el ratón y si pulsamos ALT+B se pulsará el botón.



### Direccionalidad del contenido 
Existe un atributo dir que permite al desarrollador indicar la direccionalidad del texto en el documento, ideal para idiomas en los que se escribe de derecha a izquierda. El valor por defecto de este atributo es ltr (left to right, de izquierda a derecha), pero podemos modificarlo y establecer el valor rtl (right to left, de derecha a izquierda):


````
<p>Esto es un ejemplo de texto con direccionalidad de izquierda a derecha.</p>
<p dir="rtl">Esto es un ejemplo de texto con direccionalidad de derecha a izquierda.</p>

````

También es posible conseguir este efecto utilizando la propiedad CSS direction, que puede establecer su valor a ltr (por defecto) o a rtl.

## Estilos en línea 
El atributo style es un atributo que se utiliza en las etiquetas HTML para incrustar código CSS directamente en la propia etiqueta. También se suele denominar CSS embebido o CSS incrustado.

Aunque generalmente, la mejor forma de aplicar estilos CSS es colocarlos en un documento CSS al margen de la página (lo que garantiza que todo esté bien separado y modularizado), hay situaciones en las que es conveniente o incluso necesario, añadir el código CSS en la propia etiqueta. En ese caso, se haría de la siguiente forma:
````
<p style="background: red; color: white;">Esto es un mensaje con estilos CSS</p>
````
Nótese que estamos indicando dos reglas CSS dentro de una misma etiqueta. En ¿Cómo usar CSS? tienes otros métodos para indicar CSS en una página web.