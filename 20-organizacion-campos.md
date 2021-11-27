# Organización de formularios y accesibilidad y usabilidad
Vamos a ver unos elementos que nos ayudan a organizar el formulario y a orientar al ususario en el manejo del mismo.

Las etiquetas que veremos son las siguientes:

* Relación de campo y texto	``<label>``	
* Agrupación visual o temática de campos de entrada	``<fieldset>``	
* Leyenda para la etiqueta ``<fieldset>``	``<legend>``	Leyenda

### Agrupación visual 
La primera etiqueta es ``<fieldset>``, un elemento utilizado como etiqueta contenedora para agrupar visualmente, mediante un trazo simple, todos los campos de un formulario que estén relacionados (misma temática o apartado, por ejemplo). La etiqueta ``<legend>``, suele incluirse en el interior de ``<fieldset>`` para mostrar un título en el trazo de esa agrupación.
````
<form name="formulario" method="post" action="/send.php">
  <!-- Agrupación de campos -->
  <fieldset>
    <legend>Datos personales</legend>

    <!-- Campo de texto -->
    Nombre de usuario:
    <input type="text" name="nombre" placeholder="Por ej: John Smith" />

    <!-- Campo numérico -->
    Edad:
    <input type="number" name="edad" min="18" max="100" placeholder="18" />

    <!-- Botón radio de opción -->
    Sexo:
    <!-- Primera opción -->
    <input type="radio" name="sexo" value="H" /> Hombre
    <!-- Segunda opción -->
    <input type="radio" name="sexo" value="M" /> Mujer
  </fieldset>
</form>
````
## Orden de campos (tabindex)
Cuando nos encontramos en un campo de un formulario, al pulsar la tecla TAB podemos avanzar al siguiente campo sin necesidad de recurrir al ratón. También podemos conseguir la operación inversa pulsando SHIFT+TAB, es decir, retroceder al campo anterior del formulario.

Por defecto, el navegador sigue el orden de los campos según el HTML. Sin embargo, si queremos personalizar dicho orden, podemos utilizar el atributo tabindex, indicando un número con el orden en cuestión:
````
<form name="formulario" method="post" action="/send.php">
  Nombre de usuario:
  <input type="text" name="nombre" placeholder="Por ej: John Smith" tabindex="1" />
  Edad:
  <input type="number" name="edad" min="18" max="100" placeholder="18" tabindex="3" />
  Apellidos:
  <input type="text" name="apellidos" placeholder="Apellidos" tabindex="2" />
</form>
````
En este caso, si nos colocamos en el primer campo del formulario y pulsamos TAB, saltaremos directamente al tercer campo, ya que tiene indicado tabindex a 2, y con un nuevo TAB saltaremos al segundo campo, ya que es el que tiene tabindex a 3.

Se recomienda utilizar este atributo sólo cuando esté justificado y las circunstancias lo requieran, ya que cambiar el orden de los campos puede confundir al usuario o facilitar equivocaciones al rellenar el formulario.

## Relación texto-campo 
Sin embargo, el ejemplo superior podría modificar un aspecto minúsculo que podría mejorar su usabilidad. Por ejemplo, si un usuario quiere pulsar sobre uno de los botones de radio para elegir el sexo y pulsa sobre el texto (Hombre o Mujer), no ocurrirá nada. El usuario debe pulsar exactamente sobre el botón de radio a elegir.

Sin embargo, si utilizamos la etiqueta contenedora ``<label>``, podemos establecer una relación semántica de un texto con un campo de entrada de datos. Al incluir texto y campo de texto dentro de la etiqueta ``<label>``, tiene el mismo efecto pulsar en el campo de texto que en el propio texto (muy útil también en casillas de verificación).

Veamos el ejemplo anterior, mejorado con las etiquetas ``<label>``:
````
<form name="formulario" method="post" action="/send.php">
  <fieldset>
    <legend>Datos personales</legend>
    <!-- Relación del texto con el campo -->
    <label>
      Nombre de usuario:
      <input type="text" name="nombre" placeholder="Por ej: John Smith" />
    </label>
    <!-- Relación del texto con el campo -->
    <label>
      Edad:
      <input type="number" name="edad" min="18" max="100" placeholder="18" />
    </label>
    Sexo:
    <!-- Relación del texto con el primer botón -->
    <label> <input type="radio" name="sexo" value="H" /> Hombre </label>
    <!-- Relación del texto con el segundo botón -->
    <label> <input type="radio" name="sexo" value="M" /> Mujer </label>
  </fieldset>
</form>
````
A las etiquetas ``<label>`` se le puede indicar opcionalmente un atributo for con un nombre específico, y así poder establecer la relación con una etiqueta HTML con id con el mismo nombre, sin necesidad de que estén contiguos o adyacentes.