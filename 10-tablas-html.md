# Tablas en html
Las tablas están incluidas en HTML desde sus primeras versiones y son una forma fantástica de mostrar datos claramente. Además, si las construimos de forma semántica y correctamente, es muy sencillo darle estilos desde CSS y cambiar su diseño con unas cuantas propiedades CSS, puesto que mediante las etiquetas que la componen se puede hacer referencia a cada parte de la misma.

## Tablas básicas 
Una tabla puede ser sencilla o compleja, dependiendo de nuestro objetivo y la cantidad de etiquetas o atributos a utilizar. Así pues, veamos primero las etiquetas básicas para crear una tabla de la forma más sencilla posible:


* ``<table>``	Etiqueta contenedora que tendrá en su interior toda la tabla.
* ``<tr>``	Table Row. Etiqueta contenedora de cada fila de la tabla.
* ``<td``	Table Data. Cada una de las celdas de la tabla.
* ``<th>``	Table Header. Cada una de las celdas de cabecera de la tabla.
  
La etiqueta ``<table>`` sería el elemento que contendría todos los elementos de la tabla, mientras que ``<th>`` y ``<td>`` se utilizarían para cada uno de los campos de la tabla (cabecera y celda respectivamente). Cada vez que se quisiera añadir una nueva fila, habría que incluirlo todo dentro de una etiqueta ``<tr>``.

Estas cuatro etiquetas serían las etiquetas necesarias para crear una tabla. Un ejemplo muy sencillo de una tabla de 3x2 celdas (exceptuando las cabeceras), sería la siguiente:

````
<table>
  <!-- Cabecera -->
  <tr>
    <th>Título columna 1</th>
    <!-- Celda de cabecera de la columna 1 -->
    <th>Título columna 2</th>
    <!-- Celda de cabecera de la columna 2 -->
    <th>Título columna 3</th>
    <!-- Celda de cabecera de la columna 3 -->
  </tr>
  <!-- Primera fila -->
  <tr>
    <td>Celda 1x1</td>
    <!-- Primera celda de la primera fila -->
    <td>Celda 2x1</td>
    <!-- Segunda celda de la primera fila -->
    <td>Celda 3x1</td>
    <!-- Tercera celda de la primera fila -->
  </tr>
  <!-- Segunda fila -->
  <tr>
    <td>Celda 1x2</td>
    <!-- Primera celda de la segunda fila -->
    <td>Celda 2x2</td>
    <!-- Segunda celda de la segunda fila -->
    <td>Celda 3x2</td>
    <!-- Tercera celda de la segunda fila -->
  </tr>
</table>
````
En este caso de ejemplo tendríamos una sencilla tabla de 3x2 celdas. Por defecto, en la tabla se crea de forma que se adapta al número de celdas que tiene la primera fila. Es decir, si en el primer elemento <tr> se indican 3 elementos <th>, la tabla esperará siempre 3 elementos en cada fila. Si indicaramos menos, las celdas correspondientes donde deberían estar aparecerían vacías (sin celda). Si añadieramos una de más, se saldría de la tabla.

Además, si al código HTML anterior le aplicamos unos apropiados estilos CSS de tablas, junto a cambios de colores, fuentes, márgenes, rellenos y otros aspectos visuales, podremos cambiar el diseño de la tabla en poco más que un par de líneas.

El siguiente código CSS puede ser utilizado para mostrar esos cambios sobre la tabla anterior:
````
<style>
  /* Cambios sobre la propia tabla */
  table {
    border-collapse: collapse;
    border: 1px solid #ccc;
  }
  /* Espacio de relleno en celdas y cabeceras */
  td,
  th {
    padding: 10px;
  }
  /* Modificación de estilos en cabeceras */
  th {
    background: #000;
    color: #fff;
    text-transform: uppercase;
  }
  /* Modificación de estilos en celdas */
  td {
    text-align: center;
    border-bottom: 2px solid #111;
    color: #333;
    font-size: 18px;
  }
</style>

<table>
  <!-- Cabecera -->
  <tr>
    <th>Título columna 1</th>
    <!-- Celda de cabecera de la columna 1 -->
    <th>Título columna 2</th>
    <!-- Celda de cabecera de la columna 2 -->
    <th>Título columna 3</th>
    <!-- Celda de cabecera de la columna 3 -->
  </tr>
  <!-- Primera fila -->
  <tr>
    <td>Celda 1x1</td>
    <!-- Primera celda de la primera fila -->
    <td>Celda 2x1</td>
    <!-- Segunda celda de la primera fila -->
    <td>Celda 3x1</td>
    <!-- Tercera celda de la primera fila -->
  </tr>
  <!-- Segunda fila -->
  <tr>
    <td>Celda 1x2</td>
    <!-- Primera celda de la segunda fila -->
    <td>Celda 2x2</td>
    <!-- Segunda celda de la segunda fila -->
    <td>Celda 3x2</td>
    <!-- Tercera celda de la segunda fila -->
  </tr>
</table>
````
## Combinar celdas 
Cada etiqueta ``<td>`` y ``<th>`` puede incluir una serie de atributos para modificar su comportamiento o para establecer relaciones semánticas entre celdas. Probablemente, las más interesantes sean colspan y rowspan:


* colspan	número	Número de columnas que la celda abarcará.
* rowspan	número	Número de filas que la celda abarcará.
headers	ids	Id de los elementos ``<th>`` con los que tiene relación la celda.
scope (solo ``<th>``)	row	La cabecera se aplica a alguna de las filas adyacentes.
col	La cabecera se aplica a alguna de las columnas adyacentes.
rowgroup	La cabecera se aplica a todas las celdas restantes de la fila.
colgroup	La cabecera se aplica a todas las celdas restantes de la columna.
auto	La cabecera se aplica a las celdas de forma automática.
abbr (solo ``<th>``)	nombre	Abreviatura o información alternativa sobre la cabecera.
Con estos atributos podemos indicar que ciertas celdas abarquen más espacio y se combinen con el espacio que ocuparía otra celda adyacente y así crear estructuras de tabla más flexibles.

Imaginemos que al código HTML de la tabla anterior, le añadimos antes de la primera fila de <td>, una nueva fila con una sola celda <td> con un atributo colspan a 3. Con esto estaríamos indicando que esa nueva fila (originalmente, de 3 celdas) va a abarcar las 3 celdas de espacio con una sola celda:

````html
<style>
td {
  border: 1px solid black;
}
</style>

<table>
  <!-- ... -->
  <tr>
    <td colspan="3">Datos adicionales</td>
    <!-- Abarca 3 celdas -->
  </tr>
  <!-- Primera fila -->
  <tr>
    <td>Celda 1x1</td>
    <!-- Primera celda de la primera fila -->
    <td>Celda 2x1</td>
    <!-- Segunda celda de la primera fila -->
    <td>Celda 3x1</td>
    <!-- Tercera celda de la primera fila -->
  </tr>
  <!-- ... -->
</table>
````
El atributo rowspan actuaría exactamente igual, pero abarcando filas en vertical, en lugar de columnas en horizontal. También se podrían combinar. Los atributos colspan y rowspan podrán tener como máximo el número de columnas o filas de la tabla, si tuviera un número mayor, simplemente se utilizará el máximo de la tabla.

## Organización de tablas 
Por defecto, al crear una tabla, el navegador se encarga de crearla a medida que va leyendo las etiquetas, por lo que la tabla se crea en el orden que se han especificado sus elementos, de arriba a abajo. Sin embargo, podemos utilizar una serie de etiquetas contenedoras que establecerán la zona de la tabla donde deben aparecer su contenido:

Etiqueta	Descripción
``<thead>``	Etiqueta contenedora de la cabecera de la tabla. Parte superior de la tabla.
``<tbody>``	Etiqueta contenedora del cuerpo de la tabla. Parte central de la tabla.
``<tfoot>``	Etiqueta contenedora del pie de la tabla. Parte inferior de la tabla.
``<caption>``	Establece un título de la tabla, independientemente de su posición.
A las etiquetas de tabla ya vistas, podemos añadir estas etiquetas, pudiendo definir la zona donde aparecerán sin que, necesariamente tengan el orden correcto. Veamos un ejemplo:

````
<table>
  <!-- Table footer: pie de la tabla (tfoot) -->
  <tfoot>
    <tr>
      <td>Pie de tabla 1</td>
      <td>Pie de tabla 2</td>
    </tr>
  </tfoot>
  <!-- Table header: cabecera de la tabla (thead) -->
  <thead>
    <tr>
      <th>Columna 1</th>
      <th>Columna 2</th>
    </tr>
  </thead>
  <!-- Table body: cuerpo de la tabla (tbody) -->
  <tbody>
    <tr>
      <td>Celda 1</td>
      <td>Celda 2</td>
    </tr>
  </tbody>
  <!-- Leyenda o título de la tabla -->
  <caption>
    Título de la tabla
  </caption>
</table>
````
En este ejemplo, a pesar de seguir el orden tfoot, thead, tbody, caption definido en el HTML, el navegador lee la tabla y la redistribuye según su significado semántico, de modo que lo organiza dejándolo con el orden caption, thead, tbody, tfoot. De esta forma, estas etiquetas nos pueden servir para indicar secciones concretas de la tabla, independientemente del lugar donde estemos escribiendo, algo que puede ser muy útil si estamos creando la tabla de forma dinámica mediante algún lenguaje de programación.

## Agrupación de columnas 
Las tablas, al definirse en el código siguiendo una estructura horizontal, hacen complejo el aplicar o realizar una serie de cambios a una columna. Existe una serie de etiquetas para agrupar o seleccionar columnas y así poder realizar tareas sobre ellas, como por ejemplo, asociarle una clase específica o darle estilos CSS a una columna concreta de la tabla, sin necesidad de ir celda por celda.

Para ello, utilizaremos las dos siguientes etiquetas:

Etiqueta	Descripción
``<colgroup>``	Etiqueta contenedora de columnas. Crea una agrupación de columnas.
``<col>``	Etiqueta que representa a una columna de la tabla.
Estas etiquetas pueden tener especificado un atributo llamado span para así aplicar los atributos de la etiqueta ``<col>`` al número de columnas adyacentes que se indiquen en dicho atributo. Veamos un ejemplo:

````
<table>
  <tr>
    <th>Columna 1</th>
    <th>Columna 2</th>
    <th>Columna 3</th>
  </tr>
  <tr>
    <td>Data 1</td>
    <td>Data 2</td>
    <td>Data 3</td>
  </tr>
  <tr>
    <td>Data 4</td>
    <td>Data 5</td>
    <td>Data 6</td>
  </tr>
  <colgroup>
    <col style="background:red">
    <col span="2" style="background:yellow">
  </colgroup>
</table>
````
Vemos que en el ejemplo se está aplicando un color de fondo rojo a la primera columna, mientras que a las dos siguientes un color de fondo amarillo, ya que tiene indicado el atributo span a 2 y se aplica a las dos siguientes columnas: la segunda y la tercera.

Existen una serie de atributos de etiquetas relacionadas con las tablas que están obsoletos y ya no se deben utilizar, como por ejemplo align, bgcolor o valign. Tienes más información en etiquetas HTML obsoletas.