Al igual que vimos en el tema anterior con los videos, es posible añadir archivos de audio a nuestras páginas web para colocar música, sonidos o simplemente usar música como ambientación. En versiones anteriores de HTML se usaba una etiqueta HTML obsoleta denominada <bgsound> que realizaba algo similar.

En este caso, utilizaremos la etiqueta <audio> que funciona exactamente igual que <video>, pero con relación a archivos de audio.

Audio (modo básico) 
La etiqueta <audio> tiene varios atributos a nuestra disposición:

Atributo	Valor	Descripción
src	Dirección URL	Audio a reproducir. Obligatoria si actua como etiqueta contenedora.
preload	auto | metadata | none	Indica como realizar la precarga del audio.
mediagroup	nombre	Establece un nombre para un grupo de contenidos multimedia.
autoplay		Comienza a reproducir el audio automáticamente.
loop		Vuelve a iniciar el audio cuando finaliza su reproducción (bucle).
muted		Establece el audio sin sonido (silenciado).
controls		Muestra los controles de reproducción. Por defecto no se muestran.
Un primer ejemplo muy básico para colocar un audio en nuestra página web:

<audio src="audio.mp3"></audio>
Sin embargo esto no mostrará nada visualmente, ni reproducirá ningún sonido. Realmente, el audio está ahí, pero no le hemos indicado el atributo controls para que muestre los controles y que el usuario pueda pulsar el botón «play». Tampoco le hemos colocado el atributo autoplay, en cuyo caso tampoco mostraría nada visualmente, pero si que se empezaría a escuchar el sonido o pista de música.

Otro ejemplos básicos para colocar audios en nuestra página:

<audio src="audio.mp3" preload="none" controls></audio>
<audio src="audio.ogg" autoplay loop></audio>
En el primer ejemplo, cargamos un audio en formato MP3, pero indicamos que no precargue nada. Empezará a descargarse sólo cuando el usuario pulse en los controles de reproducción. Este escenario puede ser interesante para evitar consumo de ancho de banda de archivos que es probable que el usuario no escuche o en dispositivos móviles donde las tarifas de datos son costosas.

Por otro lado, el segundo ejemplo, carga un archivo de audio en formato OGG y lo reproduce automáticamente y en bucle, de modo que vuelve a empezar cuando termina.

OJO: Los navegadores han cambiado la política de autoreproducción con autoplay. Para evitar el uso abusivo de audio en una página sin permiso del usuario, los navegadores exigen que el usuario haya interactuado con la página con anterioridad (y posterior a la carga inicial). Lo aconsejable sería utilizar botones o areas pulsables para activar el sonido mediante JS.

Formatos de audio 
Los archivos de audio estan codificados mediante un codec específico, y es importante conocer estos detalles para saber que formatos están soportados por los diferentes navegadores.

A continuación tenemos un listado de los formatos/codecs de audio más conocidos y utilizados:

Formato	Codec utilizado	Características	¿Recomendado?
MP3	MPEG Layer-3	Buena calidad.	Sí, buen soporte
AAC	Advanced Audio Coding	Mejora el MP3. Usado como audio en MP4.	Sí, buen soporte
OGG	Ogg Vorbis	Buena calidad. Alternativa libre a MP3.	Sí, soporte medio
Opus	Opus	Buena calidad. Alternativa libre a MP3.	Sí, soporte medio
FLAC	FLAC Audio Lossless	Compresión sin pérdidas. Alto tamaño.	Sí, buen soporte.
WAV	Wave sound	Formato de Microsoft. Está soportado.	No, muy pesado
Otros formatos como ASF/WMA, RA u otros no son apropiados para web. Si te interesa saber más sobre estos temas, aconsejo la lectura del artículo Formatos de audio: Todo lo que deberías saber.

Audio (modo avanzado) 
La etiqueta <audio> también puede actuar como etiqueta contenedora e incluir varias etiquetas HTML para dotar de mayor compatibilidad, o capacidades adicionales.

Etiqueta	Atributos	Descripción
<source>	src, type	Establece un archivo de audio o lo añade como alternativa.
<track>	src, srclang, label, kind, default	Establece un archivo de subtítulos o lo añade como alternativa.
De esta forma, pasamos de un esquema donde solo usabamos una etiqueta <audio> a otro un poco más avanzado, donde <audio> contiene múltiples etiquetas que actúan sobre ese audio en cuestión. Dichas etiquetas pueden ser <source> o <track>:

<audio>
  <!-- Aquí etiquetas para añadir funcionalidad extra -->
</audio>
La etiqueta de subtítulos <track> la veremos un poco más adelante, en el capítulo de etiquetas HTML de subtítulos.

Audio alternativo (fallback) 
Si utilizamos la etiqueta <audio> como etiqueta contenedora, podemos incluir etiquetas <source> en su interior para proporcionar formatos alternativos y tener mayor compatibilidad con otros navegadores y navegadores antiguos que no soporten HTML5:

<audio>
  <source src="audio.opus" />
  <source src="audio.ogg" />
  <source src="audio.mp3" />
</audio>
En este ejemplo, el navegador intentará reproducir el archivo de audio en formato Opus, en caso de no estar soportado por el navegador, intentará reproducir el formato Ogg Vorbis, y en caso de tampoco soportarlo, reproducirá el formato MP3.