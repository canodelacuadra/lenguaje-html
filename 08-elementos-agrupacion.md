# Elementos de agrupación. Texto en  bloque
Habíamos comentado que existían dos tipos de etiquetas HTML: las etiquetas que contienen fragmentos de texto (se utilizan para dar significado a esas palabras o fragmentos) y las etiquetas que agrupan conjunto de información (fragmentos de texto y/u otras etiquetas).
Vamos a verlas en este capítulo y en el siguiente

En esta ocasión, vamos a ver el segundo grupo, que son las etiquetas que se utilizan para agrupar y organizar información (y otras etiquetas). Veamos un ejemplo:
````html
<div>
  <p>Hola, esto es un primer párrafo de ejemplo.</p>
  <p>Y esto, es un segundo párrafo de ejemplo.</p>
</div>
````
## Agrupaciones 
Las siguientes etiquetas se utilizan para agrupar información, como es el caso de las etiquetas ``<div>`` o ``<p>`` que vimos en el ejemplo mostrado anteriormente:


* ``<div>``		Capa o división utilizado para agrupar varias etiquetas HTML.
* ``<p>``		Define un párrafo de texto (con sus etiquetas HTML para texto).
* ``<pre>``		Establece un texto preformateado (respetando espacios y saltos de línea).
* ``<blockquote>``	cite	Agrupa información y características de una cita (autor, fuente, etc...).
* ``<main>``		Contenedor para englobar la parte principal de la página.
* ``<hr>``		Indica una separación temática del texto.
  
La etiqueta ``<pre>`` se utiliza para mostrar texto respetando el formato con el que está escrito (espacios en blanco, saltos de línea, etc...). También es muy habitual utilizarlo junto a la etiqueta ``<code>`` anidada en su interior, de forma que tenemos un bloque de código preformateado:
````html
<pre>
  <code class="language-javascript">
    function mensaje(s) {
      console.log(s);
    }
  </code>
</pre>
````
Como se puede ver, en el caso de crear bloques de código, suele ser una buena práctica incluir un atributo class con el lenguaje que estamos utilizando. Esto no es una funcionalidad nativa de HTML5, pero muchas librerías de Javascript nos permiten resaltar la sintaxis dependiendo del lenguaje de programación indicado (ya que varía de uno a otro).

Por otro lado, la etiqueta ``<blockquote>`` suele utilizarse para agrupar información referida a una cita o frase:
````html
<blockquote cite="http://es.wikiquote.org/wiki/Fight_Club">
  <p>La primera regla del Club de la Lucha es: Nadie habla sobre el Club de la Lucha.</p>
  <footer>
    <cite class="author">Tyler Durden</cite> en
    <cite class="title">El Club de la Lucha</cite>
  </footer>
</blockquote>
````
Obsérvese que utilizamos el atributo opcional cite para indicar una referencia externa de la fuente de la cita. Luego, en su interior, tenemos un párrafo que contiene la frase en cuestión, seguida de una sección semántica (pie de cita) que a su vez contiene referencias al autor de la cita y el título de la película.

## Listas 
En HTML podemos crear listas de información de una forma muy sencilla. Empecemos por las etiquetas disponibles:


* ``<ul>``		Define una lista sin orden. Se trata de la etiqueta contenedora.
* ``<ol>``	start, reversed, type	Define una lista numerada (con orden). Etiqueta contenedora.
* ``<li>``	value	Define un ítem de la lista.
  
En primer lugar debemos elegir la etiqueta ``<ul>`` o la etiqueta ``<ol>`` dependiendo de si queremos una lista donde no importa el orden (lista de objetos que tengo en el bolsillo) o una lista en la que si importa el orden (lista de canciones preferidas de mayor a menor). Una vez elegido, comenzamos a añadir ítems, uno por etiqueta ``<li>``. La forma más básica de crear una lista sería la siguiente:
````html
<ul>
  <li>Primer ítem.</li>
  <li>Segundo ítem.</li>
  <li>Tercer ítem.</li>
</ul>
````
Esto crearía una lista, donde cada uno de los ítems aparecería con un circulo negro cada uno. Una particularidad poco conocida es que HTML nos permite omitir las etiquetas de cierre ``</li>`` si van seguidas de otra etiqueta de apertura ``<li>``.

Si reemplazamos la etiqueta ``<ul>`` por ``<ol>`` los ítems pasan a ser ítems numerados (por defecto, números enteros a partir de 1). Las etiquetas <ol> permiten indicar varios atributos opcionales para modificar la forma en que se numera cada ítem:


* start	[número]	Indica el número del primer ítem de la lista y del que empezará a contar.
reversed	-	Si se indica este atributo, la lista se numera en orden inverso.
* type	1 | a | A | i | I	Lista con números enteros, letras o números romanos (en minúsculas o mayúsculas).
El siguiente ejemplo muestra una lista numerada con letras minúsculas, que empiezan en c, pero irán en orden inverso, por lo que terminarán en c:
````html
<ol start="c" type="a" reversed>
  <li value="1">Primer ítem.</li>
  <li value="2">Segundo ítem.</li>
  <li value="3">Tercer ítem.</li>
</ol>
````
Obsérvese que también se puede establecer el atributo value a cada ítem de la lista para asignarle, por ejemplo, un valor numérico o ponderarlos.

### Listas de descripciones 
De la misma forma que podemos crear listas genéricas, podemos crear listas de descripciones. La diferencia es que este tipo de listas se suele utilizar cuando queremos asociar pares de nombre-valor. Primero veamos las etiquetas:

Etiqueta	Descripción
``<dl>``	Define una lista de descripciones. Es la etiqueta contenedora.
``<dt>``	Término de la descripción. Contiene el nombre o término a describir.
``<dd>``	Descripción o valor asociado al término. Pueden existir varios por término.
Veamos un ejemplo práctico de este tipo de listas:
````html
<dl>
  <dt>Gallina</dt>
  <dd>Ave doméstica del orden de las galliformes.</dd>
  <dd>Cobarde, pusilánime.</dd>
</dl>
````
## Ilustraciones (figuras) 
Por último, dentro del apartado de etiquetas de agrupación tenemos las nuevas etiquetas ``<figure>`` y ``<figcaption>``. Estas etiquetas se utilizan para agrupar conceptos formados por una ilustración (figura) y una leyenda. Con estos elementos de agrupación se puede agrupar una imagen y su correspondiente pie de foto, pudiendo ampliar a otro tipo de contenidos multimedia como video o audio.


* ``<figure>``	Establece una figura, que puede contener una serie de elementos diversos.
* ``<figcaption>``	Asocia una leyenda, generalmente texto, a la figura anterior. Opcional.
Veamos un ejemplo:
````html
<figure>
  <img src="http://lenguajehtml.com/img/html5-logo.png" alt="Logotipo de HTML5" />
  <figcaption>Logotipo oficial del lenguaje de marcas HTML5.</figcaption>
</figure>
````
> Nótese que en la ilustración o figura, se puede contener todo tipo de elementos, no solo imágenes. Ejemplos válidos podrían ser videos, párrafos de texto o incluso contenido multimedia.