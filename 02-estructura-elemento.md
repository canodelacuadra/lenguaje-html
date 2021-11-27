# Estructura de un elemento html

- **Tag** - Nombre de elemento (_example:_ `a`)
- **Attribute** - modificadores HTML (_example:_ `href`)
- **Value** - valor aplicado a un atributo (_example:_ `http://tania.dev`)
- **Element** -todo dentro de la etiqueta HTML: atributos, valores y contenido..
  
![tag html](images/estructura-etiqueta-html.png)

Ejemplo:

```html
<tag attribute="value">Contenidos del elemento</tag>
```

Un ejemplo real:

```html
<a href="http://tania.dev">La Web de Tania</a>
```

Esto nos llevará a la web de Tania

### HTML Reference

| Sintaxis    | Ejemplo                                          |
| --------- | ------------------------------------------------- |
| Tag       | `a`, `img`, `h1`                                  |
| Attribute | `href`, `src`, `alt`                              |
| Value     | `http://tania.dev`, `avatar.png`, `Some alt text` |
| Element   | `<img src="avatar.png">`                          |


<p class="codepen" data-height="265" data-theme-id="light" data-default-tab="js,result" data-user="canodelacuadra"
    data-slug-hash="PoGMKpY"
    style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;"
    data-pen-title="Anatomía de un elemento html">
    <span>Ver el pen <a href="https://codepen.io/canodelacuadra/pen/PoGMKpY">
            Anatomía de un elemento html</a> por José Antonio Cano (<a
            href="https://codepen.io/canodelacuadra">@canodelacuadra</a>)
       en <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>



## Etiqueta HTML 

La parte esencial de una etiqueta HTML es lo que se denomina la etiqueta de apertura. Se trata de escribir el nombre de la etiqueta en cuestión, colocándola entre los carácteres ````< y >````. Aunque no es terminantemente obligatorio, se recomienda y considera una buena costumbre escribir las etiquetas siempre en minúsculas.

En HTML5 no se puede colocar cualquier palabra como etiqueta, sino que existen una serie específica de etiquetas, cada una con una misión y objetivo diferente. Por ejemplo, la etiqueta ````<strong>````:
````
<strong>Contenido</strong>
````
Como se puede ver, la mayoría de las etiquetas requieren que se especifique un cierre de etiqueta para saber donde termina de actuar. Se caracteriza en que se escribe igual que la etiqueta de apertura, pero con la barra / inmediatamente después del ````<````.

### Atributos 
En algunas etiquetas HTML, existen algunos atributos específicos (que pueden ser opcionales u obligatorios). Los atributos determinan cierta información sobre la etiqueta (o su modo de actuar) y generalmente van asociados a un valor determinado. Este par atributo-valor se escribe después del nombre de la etiqueta, separándola por espacio y antes del carácter > de la etiqueta de apertura:
````
<strong id="dato">Contenido</strong>
````
En este caso, la etiqueta sería strong, el atributo id, el valor de id sería dato, mientras que el contenido de la etiqueta es Contenido. Por otro lado, y al igual que las etiquetas, cada atributo tiene una misión y comportamiento concreto. Aunque los valores pueden ir rodeados por comillas simples, se recomienda escribir el valor siempre entre comillas dobles.

Existen 3 tipos de atributos dependiendo de sus valores:

* Conjunto finito de valores: Son los atributos en los que puedes especificarle una serie de valores limitada. Cualquier otro valor que no sea uno de ellos, no será válido.````lang="es"````
* Valores libres: Son los atributos en los que puedes especificar un valor libremente, como una dirección URL o un texto, y no existe una serie de valores específicos para escribir.
* Valores booleanos: Son los atributos que deben tener un valor verdadero (true) o un valor falso (false). En HTML5 estos atributos se escriben sin valor (solo el atributo) si son verdaderos y se omiten para indicar que son falsos.
## Contenido del elemento
En el interior de la etiqueta HTML (después de la etiqueta de apertura y antes de la etiqueta de cierre) se debe colocar la información que queremos que sea afectada por dicha etiqueta. En el siguiente ejemplo se ve como contiene un fragmento de texto:
````
<strong id="dato" class="clase1" lang="es">Contenido de texto</strong>
````
Ten en cuenta que una etiqueta puede tener varios pares atributo-valor, como se ve en el ejemplo anterior, pero nunca se debe repetir el mismo atributo en una misma etiqueta varias veces, ya que sobreescribiría al anterior. El orden de los atributos no importa. Más adelante explicaremos que tipos de atributos existen y para que sirven.

Sin embargo, una etiqueta puede contener desde un fragmento de texto hasta un grupo de etiquetas. Esto depende mucho de la etiqueta a utilizar, y se verá más adelante en el apartado de etiquetas. Un posible ejemplo sería el siguiente:
````
<div id="pagina">
  <strong>Contenido importante</strong>
</div>
````
Nótese que dentro de la etiqueta ````<div>```` vemos que no sólo hay un fragmento de texto, sino que además incluye otra etiqueta, ````<strong>```` en este caso. Esto ocurre en las etiquetas de agrupación, que veremos más adelante.

## Comentario HTML 
Los comentarios son una práctica muy común y habitual en los desarrolladores o programadores. Se basa en introducir breves fragmentos de texto que el navegador ignora y no tendrá en cuenta a la hora de crear la página visualmente, pero que a nosotros nos sirven de ayuda para documentar algún detalle, explicar algo importante o simplemente introducir algún texto que consideramos relevante:
````html
<!-- Esto es un comentario de ejemplo que el navegador ignorará -->
````
Como se puede ver, para introducir estos comentarios en el código HTML, basta con escribir los fragmentos de texto ````<!-- y -->```` entre el comentario en cuestión que queramos incluir.

## Entidades HTML
Una entidad HTML es un conjunto de caracteres ("string") que comienza con un ampersand (&) y termina con un punto y coma (;) . 
Las entidades son utilizadas frecuentemente para imprimir en pantalla caracteres reservados (aquellos que serían interpretados como HTML por el navegador) o invisibles (cómo tabulaciones). También pueden usarse para representar caracteres que no existan en algunos teclados, por ejemplo caracterés con tilde o diéresis. 

La estructura de la entidad HTML es un ampersand(&) seguido del código o nombre de la entidad y terminado en un punto y coma.
````html
&codigo;
````


Algunos de las entidades más utilizadas son los acentos:
````
á	&aacute;
é	&eacute;
í	&iacute;
````
Los símbolos que utiliza el propio lenguaje HTML:
````
&	        &amp;
<	        &lt;
>	        &gt;
" 	      &quot;
espacio   &nbsp;
````
U otros comunes:
````
€	&euro;
£	&pound;
©	&copy;
®	&reg;
````