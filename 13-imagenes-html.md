
# Imágenes en HTML
Antes de colocar una imagen en una página web debemos tener claro en que clasificación se encuentra. Las imágenes utilizadas en una página web pueden ser de dos tipos: 
* de contenido
 * o de decoración.

En el primer caso, si la imagen pertenece al contenido y tema tratado en esa página, debería incluirse mediante una etiqueta HTML ``<img>``, pero si por el contrario pertenece a la decoración de la página, deberíamos incluirla como un fondo mediante la propiedad CSS background-image.

## Etiquetas para imágenes 
Para incluir imágenes en el contenido de una página utilizaremos la etiqueta ``<img>``, que es una etiqueta muy sencilla, que dispone de varios atributos para modificar como se verá la imagen (los atributos src y alt son siempre obligatorios):


* src	Indica el nombre o la URL de la imagen a mostrar. Atributo obligatorio.
* alt	Establece un texto alternativo que describa la imagen a mostrar. Atributo obligatorio.
* width	Indica el ancho de la imagen en píxels (sin la unidad). Se puede hacer desde CSS.
* height	Indica el alto de la imagen en píxels (sin la unidad). Se puede hacer desde CSS.

Un ejemplo básico para colocar una imagen sería el siguiente:

````html
<img src="https://lenguajehtml.com/img/logo.png"
     alt="Logotipo de HTML5" width="400" height="453" />
````
Nota que con los atributos width y height se fuerza a reservar el espacio indicado en la página (incluso antes de descargar y mostrar la imagen). Ten en cuenta que la imagen tendrá unas dimensiones concretas y se descargará siempre a máxima resolución. Con estos atributos redimensionas la imagen al tamaño de ancho y alto indicado, pero la imagen realmente tiene su propio tamaño.

Puedes omitir estos atributos siempre que quieras, ya que no son obligatorios, pero se consideran una buena práctica para evitar los molestos cambios repentinos de posición o tamaño en una página.

## Formatos de imágenes 
En el ámbito informático existen múltiples formatos de imágenes (¡muchísimos!) pero no todos son aptos para utilizar en web. Vamos a dar un repaso a los formatos más utilizados y cuales son más apropiados (Ponemos Sí o No):


* PNG	Soporta transparencia. Compresión sin pérdidas. Imágenes «lisas».	Sí
* JPG	Compresión con pérdidas. Ideal para imágenes con texturas.	Sí
* SVG	Formato vectorial. Ideal para imágenes escalables.	Sí
* GIF	Formato para imágenes pequeñas y animadas.	Intentar evitar.
* WEBP	Alternativa libre de Google al JPEG. Soporta transparencias.	Sí, con precaución
* JPEG2000	Evolución del JPEG.	No, solo Safari
* JPEG-XR	Alternativa libre de Microsoft al JPEG.	No, solo IE
* APNG	Alternativa libre a GIF. Compatible con PNG. Soporta animaciones.	Sí, con precaución
* AVIF	Formato de imagen basado en AV1. No confundir con videos AVI.	Aún no, poco soporte
* JPEG-XL	Alternativa competidora a AVIF.	Aún no, poco soporte

Cualquier otro formato no mostrado en esta lista no está recomendado para utilizar en web. Formatos como BMP, TIFF, RAW, NEF, PSD, CDR son formatos no orientados para su uso en la web, además de ser propietarios y muy pesados.

Muchos de los formatos no recomendados de la tabla superior pueden utilizarse hoy si se utiliza un enfoque progresivo con fallbacks, utilizando la etiqueta HTML ``<picture>``.

Si quieres saber más sobre formatos de imágenes y como conseguir reducir su tamaño sin disminuir su calidad, te sugiero leer [Formatos de imagen: Guía de optimización](https://www.emezeta.com/articulos/formatos-de-imagen-guia-de-optimizacion).

## Nuevas etiquetas de imágenes 
HTML 5.1 incorporará un nuevo sistema para utilizar imágenes en nuestros documentos HTML de forma mucho más flexible que la antigua etiqueta ``<img>`` que nos permitirá mostrar imágenes dependiendo de nuestras necesidades. Para ello, utilizaremos las dos siguientes etiquetas:


* ``<picture>``		Agrupa una serie de imágenes. Etiqueta contenedora.
* ``<source>``	srcset, sizes, media, type	Mostrará la imagen que cumpla una serie de criterios opcionales.
Como podemos ver, lo interesante está en la etiqueta`` <source>``, que tiene una serie de atributos disponibles para utilizar. Vamos a ver para que sirve cada uno:


* srcset	Serie de imágenes (separadas por coma) que se utilizarán. Atributo obligatorio.
sizes	Tamaño específico de la imagen que finalmente se mostrará.
* media	Condición que se debe cumplir para que muestre la imagen. Ver media queries.
* type	Tipo de formato de imagen. Opcional.
## Imágenes alternativas 
Una de las primeras ventajas que nos ofrecen estas etiquetas es la de utilizar formatos diferentes, dependiendo del soporte del navegador. Así pues, podríamos hacer algo como esto:
````
<picture>
  <source srcset="imagen.webp" />
  <!-- Formato WebP -->
  <source srcset="imagen.jxr" />
  <!-- Formato JPEG XR -->
  <img src="imagen.jpg" alt="Descripción de la imagen" />
  <!-- Fallback -->
</picture>
````
En este caso, indicamos que el navegador utilice la imagen con el formato WebP. En caso de no soportarlo, lo intentará con el formato JPEG XR. Si tampoco lo soporta, mostrará la imagen en formato JPEG, que es la que está soportada por todos los navegadores, y si utilizamos algún navegador de texto como Lynx u otro que no pueda mostrar imágenes, mostrará el texto alternativo.




## Imágenes responsive 
Otra ventaja interesante es que con ``<picture>`` podemos crear imágenes responsive que cambien dependiendo de características de las media queries (CSS). Por ejemplo, utilicemos min-width (tamaño mínimo de ancho de la pantalla) en el siguiente ejemplo:
````
<picture>
  <source media="(min-width: 600px)"
          srcset="html5-logo-xl.png" />
  <source media="(min-width: 300px) and (max-width: 600px)"
          srcset="html5-logo-large.png" />
  <source media="(max-width: 50px)"
          srcset="html5-logo-small.png" />
  <img src="html5-logo-medium.png" alt="HTML5 logo" />
</picture>
````
De esta forma, estamos indicando que se muestren diferentes imágenes dependiendo de la resolución de pantalla (ancho) del dispositivo:

* Dispositivos muy grandes (más de 600px): Muestra la imagen html5-logo-xl.png
* Dispositivos grandes (entre 300-600px): Muestra la imagen html5-logo-large.png
* Dispositivos pequeños (menos de 50px): Muestra la imagen html5-logo-small.png
* Si no cumple las anteriores (o no soporta HTML5.1): Muestra la imagen html5-logo-medium.png

> Nótese que esto sólo hará cambio de imagen efectivo justo en los límites indicados (50, 300, 600). Si se desea que la imagen se adapte proporcionalmente, lo mejor es recurrir a tamaños máximos y mínimos de CSS.

## Diferentes densidades 
Además, este sistema también permite especificar diferentes imágenes dependiendo de la densidad de pantalla del dispositivo (alto que varía actualmente en las diferentes gamas de smartphones). Para ello, tenemos que usar un descriptor después del nombre de la imagen utilizado en el atributo srcset (si no se incluye, por omisión es igual a 1x):
````
<picture>
  <source media="(min-width: 600px)"
    srcset="html5-logo-xl.png, html5-logo-xl-hd.png 2x, html5-logo-xl-fhd.png 3x" />
  <source media="(min-width: 300px) and (max-width: 600px)"
    srcset="html5-logo-large.png, html5-logo-large-hd.png 2x, html5-logo-large-fhd.png 3x" />
  <source media="(max-width: 50px)"
    srcset="html5-logo-small.png, html5-logo-small-hd.png 2x, html5-logo-small-fhd.png 3x" />
  <img srcset="html5-logo-medium.png, html5-logo-medium-hd.png 2x, html5-logo-medium-fhd.png 3x"
    alt="HTML5 logo" />
</picture>
````
Nótese que en cada etiqueta ``<source>``, e incluso en la etiqueta ``<img>``, se puede especificar el atributo srcset e indicar varias imágenes preparadas para pantallas de alta densidad.

Por último, recuerda que la etiqueta ``<picture>`` y la etiqueta ``<source>``dentro de la anterior son características de HTML5.1 y aún no están soportadas en todos los navegadores. Se recomienda ser cuidadoso con este detalle.