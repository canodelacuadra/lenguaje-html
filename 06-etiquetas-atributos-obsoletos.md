## Elementos y atributos obsoletos
Con el paso y transición de versiones anteriores (HTML1 ...HTML4 o XHTML) a HTML5, hay muchas etiquetas HTML que han sido marcadas como obsoletas y se recomienda dejar de utilizarlas cuanto antes. Es posible que algunas de ellas aún funcionen en navegadores actuales, pero llegará un momento que dejarán de ser soportadas por el navegador.

Las siguientes etiquetas ya no se utilizan en HTML5 y han sido marcadas como obsoletas. Se recomienda no utilizarlas o utilizar una de las alternativas propuestas:

|Etiqueta obsoleta|	Descripción|	Alternativa|
|--|--|--|
|````<applet>````|	Etiqueta para applets Java.|	````<embed>````, ````<object>````|
|````<acronym>````|	Indica un acrónimo.	|````<acronym>````|
|````<bgsound>````|	Especifica un sonido de fondo.	|````<audio>````|
|``<dir>``|	Indica una lista de archivos o carpetas.|	``<ul>``|
|``<frame>``|	Define un marco específico.	|``<iframe>``|
|``<frameset>``|	Define un conjunto de marcos.|	-|
|``<noframes>``|	Indica una alternativa si el navegador no soporta marcos.|````<acronym>````|	Indica un acrónimo.	|````<acronym>````|	-|````<acronym>````|	Indica un acrónimo.	|````<acronym>````|
|``<hgroup>``|	Agrupa encabezados.	|``<header>``, ``<div>``|
|``<isindex>``|	Campo para búscar en el documento.	|``<input>``|
|``<listing>``, ``<xmp>``|	Fragmentos de código fuente.	|``<pre><code>``|
|``<noembed>``|	Alternativa (fallback) para contenidos.	|``<object>``|
|``<strike>``|	Muestra un texto tachado.	|``<del>``, ``<s>``|
|``<basefont>``|	Define una tipografía por defecto.	|CSS: font-family|
|``<big>``|	Aumenta el tamaño del texto.	|CSS: font-size|
|``<blink>``|	Muestra el texto de forma parpadeante.|	-|
|``<center>``|	Centra el texto.	|CSS: text-align|
|``<font>``|	Cambia la tipografía o sus características.|	CSS: font-family|
|``<marquee>``|	Muestra el texto moviéndose de un lado a otro.|	-|
|``<multicol>``|	Columnas múltiples.|	CSS: columnas|
|``<nobr>``|	Evita que un texto haga un salto de línea.|	CSS: white-space|
|``<spacer>``|	Inserta un espacio horizontal.|	&nbsp;|
|``<tt>``	|Muestra el texto con una fuente monoespaciada.|	CSS: font-family|
|``<menu>``	|Crea menús de listados.|	``<ul> <nav>``|
## Atributos obsoletos 
De la misma forma que ocurre con las etiquetas, existen una serie de atributos de ciertas etiquetas que han pasado a dejar de utilizarse. A continuación tienes una lista con algunos de dichos atributos:

|Atributo obsoleto|	Pertenece a...|	Descripción|	Alternativa|
|--|--|--|--|
|charset|	``<a>``, ``<link>``	|Codificación del enlace.||	
|name|	``<a>``, ``<embed>``,``<img>``, ``<option>``|	Establece un ancla.|	id|
|language|	``<script>``|	Indica el lenguaje utilizado.|	type|
|link|	``<body>``|	Indica el color de los enlaces.	|CSS: :link|
|alink|``<body>``|	Indica el color de los enlaces.	|CSS: :active|
|vlink	|``<body>``	|Indica el color de los enlaces.	|CSS: :visited|
|bgcolor	|``<body>``|	Indica el color de fondo de página.	|CSS: background-color|
|align, valign|	``<table>``	|Indica la alineación vertical/horizontal.|	CSS: alineaciones|
|hspace, vspace|	``<table>``, ``<iframe>``|	Indica espacios en tablas/marcos.|	CSS: modelo de cajas|
|allowtransparency|	``<iframe>``	|Permite transparencia.	||
|frameborder|	``<iframe>``|	Indica el borde de los marcos flotantes.|	|
|scrolling|	``<iframe>``|	Permite o no hacer scroll en un marco.|	|
|align, border|	``<img>``, ``<table>``|	Indica que alineación o borde utilizar.	
|cellpadding|	``<table>``|	Indica espacios entre celdas de tabla.|	CSS: tablas|
|cellspacing|	``<table>``|	Indica espacios entre celdas de tabla.|	CSS: tablas|
|nowrap|	``<td>``, ``<th>``|	Establece fijo el tamaño de una celda.|	CSS: tamaños|