# Contenido externo
Cuando tenemos una página web y queremos mostrar contenido externo en ella, lo conveniente es utilizar formatos libres para garantizar que sean accesibles desde cualquier tipo de dispositivo.

¿Pero que ocurre si lo que quiero colocar no son formatos de video, de audio o de imagen? 

Por ejemplo, servicios como Youtube, Vimeo, SoundCloud, SlideShare u otros similares. Se trata de servicios que ofrecen contenido externo para incrustar en nuestra página, pero no nos proporcionan directamente imágenes, video o audio en formatos que reconozca el navegador, sino que nos ofrecen un enlace o contenidos que requieren un plugin externo instalado en el navegador. En esas situaciones, lo más probable es que necesites una de las siguientes etiquetas.

Las siguientes etiquetas sirven para incrustar contenido externo:


* iframe atributos:	src, srcdoc, name, width, height	Permite incrustar contenido externo en «vivo».
* embed	src, type, width, height	Permite incrustar contenido interactivo.
* object	data, type, name, form, width, height	Permite incrustar contenido externo con fallbacks.
* param	name, value	Define parámetros de un elemento ``<object>``.
Veamos ejemplos de cada una de ellas en los siguientes apartados.

## Marcos en línea (iframes) 
Antiguamente, en versiones anteriores de HTML, existieron unas etiquetas llamadas marcos, mediante las cuales se permitía dividir la pantalla en varias secciones. Actualmente, ese modo de desarrollo ya no se utiliza ya que acarreaba múltiples problemas de accesibilidad, posicionamiento, etc.

Sin embargo, de toda la familia de etiquetas de marcos ``frames``, han sobrevivido los ``<iframe>``, que siguen siendo útiles para incrustar contenido externo. Veamos un ejemplo extraído de servicios como YouTube o SoundCloud:
````html
<iframe src="https://www.youtube.com/embed/Imeq3GeRttw" width="560" height="315">
</iframe>
<a href="http://www.bing.com/" target="marco">Abrir buscador Bing</a>
<iframe name="marco" width="100%" height="450"
  src="https://w.soundcloud.com/player/?url=https%3A//api.soundcloud.com/tracks/38289724&visual=true">
</iframe>
````
Esta etiqueta permite incrustar contenido externo anidado en nuestro propio documento. Es decir, podemos crear un recuadro que en su interior va a tener otra dirección URL de otra página web, documento o recurso que queramos cargar en él. Generalmente, es la etiqueta más utilizada para todo tipo de contenido externo.

También podemos utilizar el atributo name para darle un nombre al marco y cargar direcciones URL diferentes a través de una etiqueta ``<a>``, haciendo referencia al marco a través del atributo target. Por su parte, el atributo srcdoc nos permite indicar directamente el código fuente del iframe en su valor:
````html
<iframe src="http://pagina.com/apartado/" srcdoc="<p>¡Hola! ¡Soy el <strong>texto del iframe</strong>!</p>"></iframe>
````
Como se puede ver, se puede indicar el atributo srcdoc y el atributo src a la misma vez, dando prioridad al atributo srcdoc y manteniendo el atributo src como fallback, para navegadores que no soporten srcdoc.



## Contenido incrustado 
La etiqueta ``<embed>`` se ideó antiguamente como una etiqueta no estándar para incluir contenido que requería el uso de un plugin externo para funcionar, ya que se trataba de tecnologías propietarias y los navegadores no las soportan. La etiqueta fue retirada en HTML4, pero en HTML5 fue incluída de nuevo. Se puede utilizar, por ejemplo, para incrustar contenido flash en una página web:
````html
<embed src="catgame.swf" width="400" height="250" />
````
Tradicionalmente, también se empezó a utilizar la etiqueta ``<object>`` para incrustar contenido flash, pudiendo especificar parámetros en su interior. El siguiente fragmento de código es equivalente al anterior:
````html
<object data="catgame.swf">
  <param name="quality" value="high" />
</object>
````
Así pues, la etiqueta ``<object>`` se ofrecía como una alternativa más apropiada para cargar todo tipo de contenidos. Y no sólo eso, sino que ofrece la posibilidad de especificar el tipo de formato del que se trata, así como añadir múltiples parámetros o la opción de añadir en su interior etiquetas HTML o texto que funcionen a modo de fallback (plan B), o lo que es lo mismo, en el caso de que el navegador no pueda cargar ese formato, cargará la imagen, video, texto o la etiqueta que se incluya en su interior. Algunos ejemplos:
````html
<object data="clock.html"></object>
<object type="application/x-shockwave-flash">
  <param name="movie" value="http://video.example.com/library/watch.swf" />
  <param name="allowfullscreen" value="true" />
  <param name="flashvars" value="http://video.example.com/vids/315981" />
  Contenido multimedia no soportado.
</object>
````