# Formularios HTML
 Los formularios son una forma sencilla de establecer mecanismos para que el usuario pueda introducir información en una página web de forma sencilla e intuitiva, 
 * y el sitio web sea capaz de procesarla correctamente 
 * y añadirla en una base de datos,
 * Consultar una base de dtos
 * enviarla por email o
 * procesarla para mostrar información final al usuario.

Nuestros objetivos al crear un formulario HTML5 deben ser los siguientes:

* Hacer lo más sencillo posible el proceso de inserción de datos por parte del usuario.
* Intentar que la experiencia de usuario sea lo más agradable posible.
* Intentar que los datos introducidos estén en un formato predecible y esperado.
* Reducir los errores al introducir datos en la medida de lo posible.
* Comunicar claramente si ocurren errores al introducir datos.
## Contenedor de formulario 
Para comenzar con la creación de un formulario, el primer paso es indicar una etiqueta contenedora ``<form>``, que incluirá toda la información que se quiere recoger en ese formulario:
````
<form></form>
````
De esta forma, se puede incluso crear varias etiquetas ``<form>`` por página, pudiendo así crear varios formularios diferentes, como por ejemplo, uno para realizar una búsqueda en la página, otro para dejar un comentario y otro para enviar un email al autor.

También es posible colocar campos de formulario fuera de una etiqueta ``<form>``, sin embargo, no tendrán el funcionamiento específico de enviar al servidor aunque sí podrían manejarse desde javascript.

La etiqueta ``<form>`` dispone de varios atributos para utilizar:

* action	URL	Dirección URL del back-end donde se enviará la información del formulario.
* method	get | post	Método HTTP de envío. GET a través de URL, POST para envío extenso.
* name	nombre	Nombre del formulario. Útil para procesar posteriormente.
* target	destino	Nombre del lugar donde se abrirá el formulario. \_blank para nueva pestaña.
* enctype	tipo	Codificación para el envío del formulario. Importante para envío de archivos.
* accept-charset	codificación	Fuerza a utilizar una codificación en los parámetros de texto del formulario.
* autocomplete	on | off	Activa o desactiva el autocompletado para todos los campos del formulario.
* novalidate		Con este atributo presente, el formulario obvia la validación HTML5.

Así pues, un primer formulario base de ejemplo (aún vacío, sin campos de entrada de datos, sólo con la etiqueta contenedora) podría ser el que vemos en el siguiente ejemplo:
````
<form name="formulario" method="post" action="/send.php"></form>
````
Nótese que se definen 3 atributos base en ``<form>``:

En action se indica la dirección donde se enviarán los datos cuando el usuario pulse el botón de enviar. En caso de omitirse esta información, se enviarían los datos a la propia página actual, volviéndola a cargar.

En method se define el tipo de método HTTP a utilizar. Utilizaremos el método GET cuando nos interese que los datos se envíen en la propia URL. En caso contrario, POST.

En name el nombre del formulario para cuando necesitemos hacer referencia a él (generalmente desde Javascript o desde backend).

## Tipos de datos 
Para que un usuario pueda introducir información en un formulario, requiere que se le indiquen una serie de campos que le permitan introducir la información de la forma más cómoda y rápida posible. Para ello, debemos saber a priori que tipo de dato le vamos a pedir al usuario (texto, numérico, fecha, etc...), y así saber que tipo de campo de entrada de datos es más conveniente colocar.


* Información de texto	Nombres, apellidos, direcciones físicas...	``<input>``
``<textarea>``
* Números o cantidades	Edades, precios, cuantías...	``<input>`` para números
* Fechas u horas	Fecha de nacimiento, inicio de evento...	``<input>`` para fechas
* Verdadero/falso	Si/No, Opción A/B, ON/OFF...	``<input type="checkbox">``
* Opción única	(Elegir una opción de 2 ó más posibles)	````<input type="radio">````
````<select>````
* Varias opciones	(Elegir varias opciones de 2 ó más posibles)	``<select multiple>``
``<input type="checkbox">``
* Opción única abierta	(Elegir una opción o indicar una propia)	``<datalist>``
* Selección de color	(Escoger un color o tonalidad)	``<input type="color">``
* Selección de archivo	(Escoger un archivo para enviar)	``<input type="file">``

En HTML5, de forma nativa, el navegador proporciona estos campos de entrada en los que el usuario puede introducir información específica. Cada uno de ellos tiene sus propias particularidades y características, además de que hay que tener cuidado con algunos, ya que pueden no estar soportados por completo en todos los navegadores.

Campos de entrada 
Una de las etiquetas que más utilizaremos para obtener información a modo de campo de entrada de datos en un formulario es la etiqueta ``<input>``. Su funcionalidad más utilizada es la de servir como campo de texto:
````
<form name="formulario" method="post" action="/send.php">
  <!-- Primer campo de entrada de datos -->
  Nombre de usuario:
  <input type="text" name="nombre" value="" />
  <!-- Botón de envío del formulario -->
  <input type="submit" value="Enviar" />
</form>
````
En este ejemplo tenemos un pequeño formulario donde se le pide al usuario su nombre con la etiqueta ``<input type="text">`` y, posteriormente, se coloca un botón para enviar el formulario con la etiqueta ``<input type="submit">``. Aunque vemos que se trata de la misma etiqueta ``<input>``, dependiendo del valor indicado en el atributo type realizará una tarea u otra.

# La etiqueta "input" 
La etiqueta ``<input>`` tiene una gran cantidad de atributos (algunos dependiendo del valor de type, que mostraremos más adelante). Estos son los atributos que podemos utilizar de forma general para prácticamente cualquier campo de entrada de datos con la etiqueta ``<input>``:


* type	tipo de campo	Indica el tipo de campo del que se trata.
* name	nombre del campo	Indica el nombre del campo para hacer referencia más tarde.
* value	valor por defecto	Indica el valor inicial que tendrá ese campo de datos.
* form	nombre del formulario	Asocia este campo de datos con un formulario específico.
* placeholder	sugerencia	Indica una sugerencia al usuario antes de escribir.
* size	número	Tamaño visual (número de carácteres) del campo de datos.
* autocomplete	on | off	Activa o desactiva el autocompletado para este campo.
* autofocus	-	Establece el foco (coloca el cursor) en este campo al cargar la página.

El atributo type nos permitirá indicar que tipo de campo de dato mostrará en el navegador (text, number, date... ). Mediante el atributo name le daremos un nombre al campo de texto, así cuando enviemos la información del formulario, podremos manejarla desde javascript o desde el back-end haciendo referencia a dicho nombre.
