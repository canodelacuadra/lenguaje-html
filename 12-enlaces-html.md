# Enlaces de hipertexto
Una de las etiquetas más importantes de HTML (sino la que más) es la etiqueta ``<a>``. Esta etiqueta se utiliza para crear los llamados enlaces, vínculos o hipervínculos. La idea es establecer una referencia a una dirección o URL donde está alojado ese otro documento de destino, que puede ser una página web, un archivo PDF, una imagen o cualquier otro tipo de documento.


``<a>``	Etiqueta para hacer referencia a otras páginas web o recursos como documentos o archivos.

Esta etiqueta debe tener, como mínimo, el atributo ``href``, ya que es el atributo con el que se especifica la dirección URL al documento que se quiere enlazar. Aún así, la etiqueta ``<a>`` también tiene varios atributos opcionales, veamos un resumen de todos ellos:

## Atributos
* href	URL	Enlace al documento que se quiere cargar. Atributo obligatorio.
* download	nombre.ext	Descarga el enlace (href) en lugar de abrirlo. Si se indica valor, se renombra.
* target Valores:
  * ``_blank``	Abre el enlace en una nueva pestaña.
  * ``_self``	Abre el enlace en la pestaña o ``<iframe>`` actual.
  * ``_parent``	Abre el enlace en el documento padre.
  * ``_top``	Abre el enlace en el documento raíz (padre global).
  * ``name``	Abre el enlace en el ``<iframe>`` con el **name** especificado.
* rel	(con los siguientes valores):
  * alternate	Indica que el enlace es una versión alternativa (idioma o formato diferente).
  * author	Indica que el enlace es la web del autor de la página actual.
  * bookmark	El enlace es un permalink a la sección de la página actual.
  * help	Indica que el enlace ofrece ayuda para la página actual.
  * license	Indica que la página actual está cubierta por la licencia referenciada.
  * prev	Indica que el enlace es la parte previa del documento actual.
  * next	Indica que el enlace es la parte siguiente del documento actual.
  * nofollow	Indica que el enlace no está supervisado por el autor del sitio web.
  * noreferrer	El navegador no envía la página de procedencia al visitar el enlace.
  * prefetch	El navegador precarga el enlace (es probable que se haga clic)
  * search	Indica que el enlace es una página para realizar búsquedas.
  * tag	Asocia una etiqueta al enlace especificado, en relación al documento actual.
* hreflang	Idioma	Código ISO 639-1 del idioma del documento.
* type	Tipo	Tipo de contenido MIME al que se enlaza. Atributo no obligatorio.

El soporte del atributo download podría no funcionar en navegadores no actuales, como versiones antiguas de Chrome o Firefox, o desde Internet Explorer:



Veamos a continuación algunos ejemplos de enlaces utilizando algunos atributos indicados en la tabla superior para comprender así su funcionamiento:
````html
<ul>
  <li><a rel="author" href="http://www.emezeta.com/">Emezeta</a></li>
  <li><a href="http://lenguajecss.com/" target="_blank">LenguajeCSS</a></li>
  <li><a href="http://pagina.com/documento.pdf" download="A-38.pdf">PDF</a></li>
  <li><a href="http://pagina.com/documento-en.pdf" hreflang="en">PDF</a></li>
</ul>

````

## Estados de un enlace 
Por defecto, los enlaces tienen 3 estados diferentes:

* Enlaces sin visitas: Un enlace que no ha sido visitado aún (pseudoclase :link en CSS) es representado por los navegadores como un enlace de color azul y subrayado. Se suele aconsejar no realizas cambios bruscos en los estilos de los enlaces, ya que los usuarios que no estén acostumbrados al sitio web no reconocerán instantáneamente un enlace si no es de color azul y/o está subrayado.

* Enlaces visitados: Un enlace que ha sido visitado previamente (pseudoclase :visited en CSS) es representado por los navegadores como un enlace de color lila y subrayado.

* Enlaces activos: Un enlace está en estado activo (pseudoclase :active en CSS) cuando el usuario está pulsando sobre el enlace con el ratón y a la misma vez no ha dejado de pulsar en él. Se suele utilizar para destacar el clic visualmente.

