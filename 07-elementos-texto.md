# Elementos de texto " texto en línea"
A grandes rasgos, en un documento HTML existen dos tipos de etiquetas HTML: las etiquetas que contienen fragmentos de texto (se utilizan para dar significado a esas palabras o fragmentos) y las etiquetas que agrupan conjunto de información (fragmentos de texto y/u otras etiquetas). 
> También se pueden diferenciar como enlementos en bloque o elementos en línea (pero como eso significa presentación está un poco desaconsejado)

En el siguiente ejemplo, tenemos la etiqueta ``<p>``, que pertenece al segundo grupo (agrupación), mientras que la etiqueta ``<strong>`` forma parte del primer grupo, que es del que vamos a hablar en esta sección:

````html
<p>
Hola, esto es un pequeño <strong>ejemplo</strong>.
</p>
````
# Fragmentos de texto 
En primer lugar, existe una serie de etiquetas HTML simples para seleccionar un fragmento de texto y dotarlo de un significado especial. Por ejemplo:


* ``<strong>``	Fragmento de texto importante o palabras clave.
* ``<em>``	Fragmento de texto enfatizado respecto a la frase que lo contiene.
* ``<mark>``	Fragmento de texto resaltado, simulando estar marcado con rotulador amarillo.
* ``<i>``	Fragmento de texto con voz o tono alternativo al resto.
* ``<b>``	Fragmento de texto sin importancia destacable (fines utilitarios).
* ``<u>``	Fragmento de texto para nombres propios o escritura incorrecta intencionada (sic).
* ``<s>``	Fragmento de texto inexacto o que ya no es relevante. (errores o inexactitudes)
* ``<span>``	Fragmento de texto sin significado (útil para seleccionar).
* ``<cite>``	Fragmento de texto con el título de un trabajo creativo: obras, libros...
> Ojo, algunas de estas etiquetas, en versiones anteriores de HTML tenían un significado diferente, como por ejemplo la etiqueta ``<b>``, que antiguamente simbolizaba un fragmento de texto en negrita o la etiqueta ``<i>``, que representaba un fragmento de texto en cursiva.

Por su parte, la etiqueta ``<span>`` es una versión en línea de la etiqueta ``<div>``, ya que su misión es agrupar contenido de texto, mientras que la misión del ``<div>`` es agrupar otras etiquetas HTML que a su vez pueden agrupar otras y otras etiquetas HTML.

## Modificación de significado 
Con las siguientes etiquetas HTML también podemos modificar el significado de la información que contienen:


* ``<sup>``		Superíndice .
* ``<sub>``		Subíndice .
* ``<small>``		Anotaciones menores pequeñas puntualizaciones.
* ``<q>``	cite	Cita o frase extraída de otro contexto.
* ``<dfn>``	title	Definición (término que posteriormente será definido).
* ``<abbr>``	title	Abreviatura o acrónimo.
Las etiquetas HTML ``<sup>`` y ``<sub>`` se utilizan para indicar superíndices y subíndices. De esta forma tenemos un mecanismo que nos permite diferenciar el número 242 del número 242:

````html
<p>
  El resultado de 24<sup>2</sup> es el valor de X<sub>a</sub>.
</p>
````

Por otra parte, la etiqueta HTML ``<q>`` nos permite hacer referencia a una cita o frase extraída de otro contexto. Obsérvese que en esta etiqueta disponemos de un atributo opcional cite, mediante el cuál podemos hacer referencia a una URL (en este caso a la ficha de la película de Batman) que en este caso es de donde procede la frase:

````html
<p>
 <q cite="http://www.imdb.com/title/tt0468569/">
    Hay hombres que solo quieren ver arder el mundo.
  </q>
</p>
````
Es importante tener en cuenta que no se trata de la creación de un enlace para que el usuario haga clic, ya que estos se crean mediante la etiqueta ``<a>`` que veremos más adelante.

También tenemos las etiquetas ``<dfn>`` y ``<abbr>`` que nos permiten indicar definiciones y abreviaturas, y que ambas permiten el uso del atributo opcional title para indicar el significado de dicho término o abreviatura. Un ejemplo de ambas etiquetas combinadas:

````html
<p>
  El término <dfn><abbr title="Kilómetro">Km</abrr></dfn> es una unidad de longitud.
</p>
````
## Los saltos de línea
 son etiquetas especiales de HTML para comenzar en una línea nueva (emular el efecto al pulsar ENTER). Al contrario que todas las que hemos visto, las etiquetas ``<br>`` son etiquetas que no necesitan etiqueta de cierre, por lo que sólo se escribe la etiqueta de apertura.


* ``<br>``	Salto de línea (nueva línea).
* ``<wbr>``	Oportunidad de salto de línea (división silábica con guión).
También existe la etiqueta ``<wbr>`` que se denomina oportunidad de salto de línea y posee el mismo funcionamiento de la división silábica con guión, es decir, indicamos donde es posible hacer un salto de línea si la situación lo requiere, como por ejemplo, si la palabra no cabe dentro de un elemento y se quiere evitar que desborde el contenido.

## Aspectos informáticos 
Existen una serie de etiquetas HTML ligeramente orientadas a aspectos informáticos como combinaciones de teclado del usuario o para representar variables matemáticas o informáticas:


* ``<kbd>``		Entrada de información del usuario (generalmente, combinación de teclado).
* ``<samp>``		Salida de información de un programa informático.
* ``<var>``		Variable (contexto matemático o informático).
* ``<time>``	datetime	Indica una fecha/hora legible para humanos, con formato para máquinas opcional.
* ``<data>``	value	Información equivalente orientado a máquinas.
* ``<code>``		Fragmento de código fuente (en línea).
  
Un ejemplo práctico de la etiqueta ``<kbd>`` sería modificar sus estilos CSS para obtener algo similar a CTRL+T, simplemente combinando el siguiente código HTML y CSS:


````html
<p>
Pulsa las teclas <kbd>CTRL</kbd>+<kbd>T</kbd>...
</p>

<style>
kbd {
  font-family: "Victor Mono", monospace;
  padding: 2px 6px;
  background: #eee;
  border: 3px solid #bbb;
  border-top-width: 1px;
  border-bottom: 3px solid #777;
}
</style>
````

Si ``<kbd>`` muestra una entrada, por otro lado tenemos la etiqueta inversa, ``<samp>``, que muestra la salida de un programa (mensaje, error o información) o ``<var>`` que nos permite indicar variables utilizadas en ejemplos matemáticos o informáticos.

Con la etiqueta ``<time>`` podemos indicar una fecha y/o hora en formato legible para humanos, indicando de forma opcional el atributo datetime con la fecha en un formato orientado a máquinas. De la misma forma se utiliza la etiqueta ``<data>`` para información genérica, en la que se puede usar su atributo value para indicar el texto equivalente orientado a máquinas:

````html
<p>
  <time datetime="2001-01-04">4 de Enero</time>
  <data value="ESDLA3">El retorno del Rey</data>
</p>
````
> Nótese también que la etiqueta ``<code>`` se utiliza para fragmentos de código fuente cortos, en línea, o lo que es lo mismo, de una sola línea. Para bloques de código más extensos se usa combinándola con otra etiqueta que veremos más adelante.

## Etiquetas de edición 
Por último, tenemos unas etiquetas orientadas a la edición posterior a la publicación de un texto o página web:


* ``<ins>``		Fragmento de texto o información añadida a posteriori de la publicación inicial.
* ``<del>``		Fragmento de texto o información eliminada a posteriori de la publicación inicial.
  
Imaginemos que publicamos una página pero queremos editar la publicación para modificar o añadir información (o simplemente corregir errores), pero queremos reflejar esos cambios para que se vean que han sido insertados a posteriori.

Para ello podemos utilizar la etiqueta ``<ins>``, pudiendo asociarle unos estilos CSS determinados. De la misma forma, podemos utilizar ``<del>`` para la eliminación de información sin eliminarla por completo, sino que aparezca tachada o con algún estilo visual que sugiera que ya no es válida (en gris y tachada, por ejemplo).

> Ambas etiquetas admiten el uso de los atributos opcionales ``cite``, que permite incluir una URL con más información sobre la información añadida/eliminada (idéntico al atributo cite de la etiqueta q) y ``datetime``, que permite incluir la fecha/hora cuando se añadió/eliminó la información (funcionamiento idéntico al atributo datetime de la etiqueta time).