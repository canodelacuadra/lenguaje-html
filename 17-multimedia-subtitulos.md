# Subtítulos en vídeos
Con la llegada de HTML5 se introduce WebVTT, un formato abierto orientado a utilizarse en web para la creación de subtítulos, que proviene del extendido formato SRT.

## Formato WebVTT 
La sintaxis del formato de texto WebVTT es bastante legible:
````
WEBVTT
00:04.000 --> 00:07.000
<v Capitán América>Hola <i>Tony</i>.

00:09.000 --> 00:11.000
<v Ironman>¿Me echabas de menos?

00:12.000 --> 00:14.000 align:end size:50%
*ruido*
````
Como se puede ver, el archivo empieza con el texto WEBVTT y continua con una línea que indica el inicio y final que permanecerá visible la frase de la siguiente línea. En la frase, se puede indicar el personaje que está hablando (para posteriormente aplicar estilos) e incluso incluir etiquetas simples para dar formato al texto. También se pueden alinear textos, modificar su tamaño o cambiar la posición, entre otras cosas.

## Etiquetas para subtítulos 
Este formato se puede utilizar mediante la etiqueta ``<track>`` dentro de una etiqueta contenedora ``<video>`` y después de las etiquetas ``<source>``.

 La etiqueta ``<track>`` soporta varios atributos:


* src	Dirección URL	Archivo o ruta del archivo de subtítulos WebVTT. Atributo obligatorio.
* srclang	idioma	Código ISO 639-1 del idioma de los subtítulos.
* label	nombre	Título que verá el usuario para elegir el canal de subtítulos.
* kind	subtitles | captions
* descriptions
* chapters | metadata	Indica el tipo o género de subtítulos enlazados.
* default		Utiliza este canal de subtítulos por defecto.

En el siguiente fragmento de código vemos un ejemplo de uso, en el cuál, en la barra de los controles de reproducción, se nos mostrará un icono CC donde el usuario puede elegir uno de los canales de subtítulos indicados, que por defecto utiliza el primero que encuentra o el que tenga el atributo default:
````html
<video controls>
  <source src="video.mp4" />
  <source src="video.webm" />
  <track src="subs-es.vtt" srclang="es" label="Español" default />
  <track src="subs-en.vtt" srclang="en" label="English" />
  <track src="subs-fr.vtt" srclang="fr" label="Français" />
</video>
````
De la misma forma también es posible utilizar subtítulos en etiquetas ``<audio>`` contenedoras, algo que puede ser muy útil por ejemplo para podcasts o reproducciones de audio donde se cuentan detalles y se quiere subtitular o describir de forma textual.

