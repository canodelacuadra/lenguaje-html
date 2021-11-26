# Elementos estructurales o de sección
En versiones anteriores a HTML5, al crear la estructura de una página, normalmente utilizabamos etiquetas ````<div>```` para ir agrupando secciones de la página. Unido a esto, ibamos añadiendo id o clases (atributos) dependiendo de nuestro interés, para que quedase más claro. Una estructura como la que menciono podría ser la siguiente:
````html
<div class="articulo">
  <h1>Título del artículo</h1>
  <p class="intro">Pequeña introducción.</p>
  <p class="contenido">Aquí va el texto del artículo en cuestión con sus detalles.</p>
  <p class="pie">Escrito por Manz</p>
</div>
````
Vemos que en esta estructura tenemos una agrupación que contiene todos los elementos de un artículo, donde el primer elemento es un encabezado ````<h1>```` (titular), luego un párrafo de introducción, seguido de un párrafo de contenido y un último párrafo a pie de artículo. La estructura podría ser más sencilla o más complicada, pero nos viene bien como ejemplo de introducción a este tema.

Nótese que los elementos utilizados ``<div>`` y ``<p>`` no tienen una semántica específica, salvo que son etiquetas de agrupación y que la segunda contiene un párrafo. En HTML5 se introducen una serie de etiquetas de agrupación que funcionan exactamente como un``<div>``, pero que además tienen un significado semántico porque indican la naturaleza del contenido que agruparán.

Veamos el ejemplo anterior, utilizando etiquetas semánticas:
````html
<article>
  <header>
    <h1>Título del artículo</h1>
    <p class="intro">Pequeña introducción.</p>
  </header>
  <p class="contenido">Aquí va el texto del artículo en cuestión con sus detalles.</p>
  <footer>
    <p>Escrito por ....</p>
  </footer>
</article>
````
De esta forma, preparamos nuestro documento HTML para que cualquier navegador, robot de buscador o aplicación o sistema informático sea capaz de leer el documento HTML y conocer perfectamente la naturaleza del contenido de dicha sección.

## Etiquetas semánticas y encabezados 
Veamos un listado de las etiquetas semánticas que se introducen en HTML5 (los encabezados ya existían en versiones anteriores):

* ``<article>``	Artículo. Parte principal de un escrito (posts, mensaje en foros, comentario...)
* ``<nav>``	Apartado de navegación (enlaces de secciones, categorías, etc...)
* ``<header>``	Cabecera visual de la página (logotipo, título, etc...). No confundir con ``<head>``.
* ``<h1>``	Encabezado de nivel 1. Equivalente al título del documento.
* ``<h2>``	Encabezado de nivel 2. Equivalente al tema del documento.
* ``<h3>``	Encabezado de nivel 3. Equivalente a la sección de un tema.
* ``<h4>``	Encabezado de nivel 4. Equivalente a un apartado de la sección.
* ``<h5>``	Encabezado de nivel 5. Equivalente a un ejemplo del apartado.
* ``<h6>``	Encabezado de nivel 6. Equivalente a un subapartado del ejemplo.
* ``<footer>``	Pie de página de una sección (o del documento completo).
* ``<section>``	Sección o grupo temático de contenido. No usar sólo para dar estilo.
* ``<aside>``	Agrupación de contenido no relacionado con el tema principal del documento.
* ``<address>``	Agrupación con la información de contacto del autor del artículo o documento.

> Nótese que las etiquetas ``<article>`` pueden contener otras etiquetas ``<article>``, como por ejemplo comentarios dentro de artículos:
````html
<article class="post">
  <p>Este sería el texto del artículo.</p>
  <article class="comentario">
    <p>Aquí iría el texto del comentario.</p>
  </article>
</article>
````
