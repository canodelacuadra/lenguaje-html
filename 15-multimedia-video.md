En HTML5 se introduce la interesante posibilidad de mostrar videos directamente desde nuestro navegador. De hecho, si arrastramos un video a la ventana del navegador, veremos que comienza a reproducirse en él. Para poder insertar videos en nuestras páginas HTML tenemos que utilizar la etiqueta <video>, que junto a la etiqueta <source> podremos utilizar estas capacidades multimedia de HTML5.

Ojo: Si lo que quieres es insertar videos desde Youtube, Vimeo u otro servicio alternativo, debes utilizar la etiqueta HTML iframe en lugar de la etiqueta <video>.

Video (modo básico) 
La etiqueta <video> tiene varios atributos a nuestra disposición:

Atributo	Valor	Descripción
src	Dirección URL	Video a reproducir. Obligatoria si actua como etiqueta contenedora.
poster	Dirección URL	Muestra una imagen a modo de presentación.
preload	auto | metadata | none	Indica como realizar la precarga del video.
mediagroup	nombre	Establece un nombre para un grupo de contenidos multimedia.
autoplay		Comienza a reproducir el video automáticamente.
loop		Vuelve a iniciar el video cuando finaliza su reproducción (bucle).
muted		Establece el video sin sonido (silenciado).
controls		Muestra los controles de reproducción. Por defecto no se muestran.
width	tamaño	Indica el tamaño de ancho del video.
height	tamaño	Indica el tamaño de alto del video.
Un primer ejemplo muy básico para colocar un video en nuestra página web:

<video src="video.mp4" width="640" height="480"></video>
Sin embargo, esto mostrará el primer fotograma del video, con un tamaño de 640x480, pero se verá como una imagen, ya que no muestra los controles del video y tampoco tiene la autoreproducción activada. Podríamos solucionarlo indicando los atributos controls o autoplay.

Otro ejemplos básicos para colocar videos en nuestra página:

<!-- Ejemplo 1 -->
<video src="video.webm" poster="presentacion.jpg" controls></video>
<!-- Ejemplo 2 -->
<video src="video.mp4" autoplay muted loop></video>
En este caso cargamos un video, pero que no se mostrará porque se ha indicado que se utilice una imagen de presentación que se mostrará hasta que el usuario pulse en el botón de reproducir de los controles. En el segundo ejemplo, tenemos un video que se reproduce automáticamente al cargar la página, en silencio y en bucle, iniciándose una y otra vez.

Desde 2017, Chrome, Firefox y otros navegadores establecieron un cambio de políticas con el atributo de reproducción automática autoplay, por lo que no funcionará salvo que el usuario haya interactuado antes en la página.

Formatos de video 
Antes de continuar con el modo avanzado de etiquetas de video, debemos conocer una serie de conceptos básicos y los diferentes formatos de video que existen actualmente. En primer lugar, debemos saber que un archivo de video tiene dos partes principales: el formato contenedor, que es el formato del video en sí, mientras que en su interior puede tener múltiples componentes codificados con diferentes codecs.

Formato contenedor de video

De hecho, un video básico suele tener, como mínimo, un componente de video y otro de audio, pero puede tener muchos más (subtítulos, imágenes, etc...). Estos detalles son muy importantes, ya que dependiendo del formato y/o codec de un video, puede que sea factible utilizarlo para web o no, así que hay que conocer un poco sobre estos conceptos.

A continuación tenemos un listado de los formatos/codecs más conocidos y utilizados:

Formato	Codec utilizado	Características	¿Recomendado?
MP4	x264, DivX H264	Alta calidad. Codec x264 libre.	Sí, buen soporte
WebM	VP8, VP9	Alternativa libre a MP4 de Google.	Sí, soporte medio
AV1	Basado en VP10, Daala y Thor	Compite con HEVC/H.265	No, soporte bajo
HEVC	x265, DivX HEVC	Futura evolución de MP4.	No, poco soporte
OGV	Theora	Alternativa libre a MP4.	Con precaución
MKV	Matroska	Buena compresión. Potente.	No, alto consumo CPU
AVI	XviD, DivX 3/5	Menor compresión que MP4.	No, anticuado
Otros formatos como MOV, FLV, 3GP, MPG, RMVB o ASF/WMV no se recomiendan para su utilización en web ya que son anticuados, propietarios o poco eficientes. Si te interesa saber más sobre estos temas, aconsejo la lectura del artículo Formatos de video: Todo lo que deberías saber.

Video (modo avanzado) 
Sin embargo, aún con toda esta información, no hemos visto ni la mitad de posibilidades multimedia que tenemos con HTML5. La etiqueta <video> también puede actuar como etiqueta contenedora e incluir varias etiquetas HTML para dotar de mayor compatibilidad, o capacidades adicionales.

Etiqueta	Atributos	Descripción
<source>	src, type	Establece un archivo de video o lo añade como alternativa.
<track>	src, srclang, label, kind, default	Establece un archivo de subtítulos o lo añade como alternativa.
Videos alternativos 
Si utilizamos la etiqueta <video> como etiqueta contenedora, podemos incluir etiquetas <source> en su interior para proporcionar formatos alternativos y tener mayor compatibilidad con otros navegadores y navegadores antiguos que no soporten HTML5:

<video width="640" height="480">
  <source src="video.mp4" type="video/mp4" />
  <source src="video.webm" type="video/webm" />
  <source src="video.ogv" type="video/ogg" />
  <img src="imagen.png" alt="Video no soportado" />
  Su navegador no soporta contenido multimedia.
</video>
En este ejemplo, los navegadores no mostrarán todos los contenidos a la vez, sino que seguirán el siguiente procedimiento:

Intenta mostrar el primer formato (MP4). Si el navegador no soporta este formato, salta al siguiente.
Intenta mostrar el segundo formato (WEBM). Si el navegador no soporta este formato, salta al siguiente.
Intenta mostrar el tercer formato (OGV). Si el navegador no soporta este formato, salta al siguiente.
Si se trata de un navegador que no soporta HTML5, intentará mostrar la imagen.
Si se trata de un navegador de terminal de texto (o sin capacidades gráficas), mostrará el texto "Su navegador no soporta contenido multimedia".
De esta forma tenemos soporte completo para todo tipo de dispositivos.

Acceso a segundos concretos 
Utilizando los fragmentos multimedia se pueden conseguir algunas acciones interesantes, como por ejemplo especificar el momento concreto del video (o audio) en el que se quiere empezar a reproducir o terminar de reproducir. Veamos unos ejemplos:

<!-- Ejemplo 1 -->
<video autoplay controls src="video.mp4#t=15"></video>

<!-- Ejemplo 2 -->
<video autoplay controls src="video.mp4#t=25,45"></video>
En el primer caso, reproducimos el video a partir del segundo 15 del mismo, mientras que en el segundo caso, reproducimos el video a partir del segundo 25 y terminará de reproducirse en el segundo 45.