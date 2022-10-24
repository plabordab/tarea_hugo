+++
title = "tema universal"
tags = ["tema"]
categories = ["tema"]
description = "Tema HUGO"
banner = "img/banners/hugo.jpeg"
authors = ["Pilar Laborda"]
+++

Universal es una plantilla web limpia y elegante construida con Bootstrap. Destaca por su diseño limpio y su elegante tipografía.

> [Sitio de demostración](https://devcows.github.io/hugo-universal-theme) 

## FUNCIONALIDADES:

### Idioma

Las traducciones disponibles están en el directorio /i18n. Se puede configurar el idioma modificando la siguiente clave.

``` js
defaultContentLanguage = "en"
```

### Estilo

Para cambiar el color del tema se debe modificar:

``` js
style = "default"
```

> Las opciones disponibles son: por defecto (azul claro), azul, verde, marsala, rosa, rojo, turquesa, violeta. Existe la posibilidad de anular el CSS _(anulando el archivo static/css/custom.css)_ y establecer estilos personalizados.

### Comentarios

El sistema de comentarios opcional es impulsado por Disqus. Para habilitarlos, es necesario crear una cuenta en Disqus y escribir nuestro nombre corto.

``` js
disqusShortname = "plabordab"
```

Es posible desactivar el sistema de comentarios dejando el disqusShortname vacío.

### Google Analytics

Se puede habilitar opcionalmente Google Analytics escribiendo el código de seguimiento en el campo:

``` js
googleAnalytics = "UA-XXXXX-X"
```

Dejando la clave googleAnalytics vacía se desactiva.

### Logotipo

Se puede seleccionar un logotipo, se pueden definir dos parámetros logo y logo_small. Por defecto el logo se utiliza para pantallas medianas y grandes y el valor logo_small se utilizará cuando el sitio se renderice en pantallas pequeñas. También existe la posibilidad de desactivar el logotipo y mostrar un texto alternativo.

``` js
[params]

   disabled_logo = false
   logo_text = "Universal"
   logo = "img/logo.png"
   logo_small = "img/logo-small.png"
```

### Formulario de contacto

Opcionalmente, se puede crear una página de contacto e incluir un formulario de contacto.

Una página de contacto es como una página normal de Hugo. Pero debe incluir el campo id con el valor contacto.

``` js
+++
title = "Contact"
id = "contact"
+++
```

Es posible habilitar o deshabilitar el widget de Google Maps en la página de contacto estableciendo `params.enableGoogleMaps` en _true_ o _false_ en *****config.toml*****. 

Para habilitar este widget es imprescindible asegurarse de proporcionar una googleMapsApiKey válida; de lo contrario, es probable que no funcione. 

Al hacer clic en el pin, Google Maps abre una descripción de la ruta con las coordenadas de latitud y longitud. Además, se pueden definir la dirección si quieres tener otro destino para las direcciones o la entrada de Google Maps de la empresa. 

Por otro lado, si `enableGoogleMaps` está configurado como _false_, se ignorarán el googleMapsApiKey, la latitud, la longitud y la dirección subsiguientes.

*Ejemplo de configuración:*

``` js
[params]

   enableGoogleMaps = true
   googleMapsApiKey = "site_key_for_google_maps"
   latitude = "-12.043333"
   longitude = "-77.028333"
   direction = "Desamparados Station, Distrito de Lima 15001, Peru"
```

Como los sitios de Hugo son estáticos, el formulario de contacto utiliza [Formspree](https://formspree.io/) como proxy. 

> El formulario hace una solicitud POST a sus servidores para enviar el correo electrónico real. Formspree y los envíos para el plan gratuito son limitados, revisa los planes para más detalles. Para habilitar el formulario en la página de contacto, sólo tiene que escribir su correo electrónico Formspree en el archivo _config.toml_, y especificar si desea utilizar ajax (pagado) para enviar la solicitud o HTTP POST (libre). 

También existe la posibilidad de habilitar un captcha usando recaptcha.

``` js
[params]

   email = "your@email.com"
   contact_form_ajax = false
   enableRecaptchaInContactForm = true
   googleRecaptchaKey = "site_key_for_google_recaptcha"
```

### Menú

Se pueden definir los elementos del menú que aparecerán en la barra superior editando las entradas de `[[params.menu]]` para crear el menú.

``` js
[[params.menu]]

   name = "Contact"
   url  = "/contact"
   weight = 4
```

El parámetro _weight_ determinará el orden de las entradas del menú. Un elemento de menú de nivel superior puede contener un desplegable con una imagen opcional, secciones y múltiples columnas de elementos de menú.

Para crear una lista única de elementos de menú en el desplegable, primero hay que dar al elemento de menú de nivel superior un identificador único:

``` js
[[menu.main]]

   name       = "Home"
   identifier = "menu.home"
   url        = "/"
   weight     = 1
```

### Widgets de la barra lateral

Se pueden activar o desactivar los widgets de la barra lateral que se mostrarán en la sección del blog. Actualmente están disponibles los siguientes:

- Barra de búsqueda (impulsada por Google)
- Lista de categorías
- Lista de etiquetas

Para habilitarlos o deshabilitarlos:

``` js
[params.widgets]

   search = true
   categories = true
   tags = true
```

### Barra superior

La barra superior se utiliza normalmente para proporcionar información de contacto y enlaces sociales. Está desactivada por defecto, y se puede activar dentro de los ajustes de params.topbar:

``` js
[params.topbar]

   enable = true
   text = "<p>Contact us on +420 777 555 333 or hello@universal.com.</p>"
```

> El texto aparece en el lado izquierdo y acepta HTML.

Los enlaces sociales del lado derecho se configuran como un menú de nivel superior.

``` js
[[menu.topbar]]

   weight = 1
   name = "GitHub"
   url = "https://github.com/devcows/hugo-universal-theme"
   pre = "<i class='fas fa-2x fa-github'></i>"


[[menu.topbar]]

   weight = 2
   name = "Facebook"
   url = "http://facebook.com"
   pre = "<i class='fas fa-2x fa-facebook'></i>"
```

#### _Comportamiento del menú_

El menú desplegable se muestra por defecto cuando el usuario hace clic en el elemento del menú. Sin embargo, también puede utilizar el ajuste `dropdown_mouse_over` para cambiar este comportamiento y utilizar el _mouse over_ en su lugar.

``` js
[params]

   dropdown_mouse_over = true
```

### Miniaturas de entradas del blog

Después de crear una nueva entrada se puede definir un banner introduciendo la ruta relativa a la imagen.

``` js
banner = "img/banners/banner-4.jpg"
```

Debe contener una ruta relativa al banner dentro del directorio estático.

### Página de destino

La página de destino consta de muchas secciones que pueden ser activadas y configuradas individualmente:

#### Carrusel 

El contenido del carrusel (carousel) se configura en el directorio de `data`.

Cada entrada del carrusel se representa como un archivo _.yaml_ dentro de `data/carousel`. 

``` js
weight: 4
title: "Easy to customize"
description: >
  <ul class="list-style-none">
    <li>7 preprepared colour variations.</li>
    <li>Easily to change fonts</li>
  </ul>
image: "img/carousel/template-easy-code.png"
href: "https://devcows.github.io/hugo-universal-theme/"
```

> El campo _weight_ determina la posición de la entrada. El _title_ es un campo de sólo texto. El campo _description_ acepta código HTML. La _image_ debe contener la ruta relativa a la imagen dentro del directorio estático. El campo opcional _href_ contiene una url relativa o absoluta a la que el usuario será redirigido al hacer clic en el carrusel _(específica para cada elemento del carrusel)_.
Una vez configurado el carrusel, se pueden definir algunas opciones como: reproducción automática, velocidad, ... en el archivo _config.toml_:

``` js
[params.carouselHomepage]

   enable = true
   auto_play = true
   slide_speed = 2000
   pagination_speed = 1000
```

#### Características

Las características (features) también se definen en el directorio `data` y el contenido del archivo tiene el siguiente aspecto:

``` js
weight: 4
name: "Consulting"
icon: "fas fa-lightbulb"
url: ""
description: "Fifth abundantly made Give sixth hath. Cattle creature i be don't them behold green moved fowl Moved life us beast good yielding. Have bring."
```

El significado de cada una de las claves YAML es el siguiente:

| Clave          | Descripción |
| ---------- | --------- |
| *peso* | Un medio para establecer el orden de las características múltiples; las características con un peso menor se muestran primero (de izquierda a derecha, de arriba a abajo) |
| *nombre* | El texto del título debajo del icono de la característica; se admite Markdown |
| *icono* | La clase CSS del icono de la característica; en este ejemplo hemos utilizado iconos de FontAwesome |
| *url* | Una URL opcional a la que debe apuntar el icono de la función; si se especifica, el icono se convertirá en un hipervínculo en el que se puede hacer clic |
| *descripción* | Un texto breve debajo del texto del título para describir la característica; se admite Markdown |


> Una vez completadas las características, se deben habilitar en el archivo _config.toml_. También se puede definir el número de elementos por fila, por defecto es 3 (debe ser un divisor de 12).

``` js
[params.features]

   enable = true
   cols = 3
```

#### Testimonios 

Los testimonios (testimonials) se definen en el directorio de datos.

Se pueden añadir tantos archivos de testimonios como desee. Sólo hay que asegurarse de rellenar todos los campos.

``` js
text: "One morning, when Gregor Samsa woke from troubled dreams, he found himself transformed in his bed into a horrible vermin. He lay on his armour-like back, and if he lifted his head a little he could see his brown belly, slightly domed and divided by arches into stiff sections."
name: "John McIntyre"
position: "CEO, TransTech"
avatar: "img/testimonials/person-1.jpg"
```

A continuación, es necesario habilitarlo en el archivo de configuración y añadir un título y un subtítulo.

``` js
[params.testimonials]

   enable = true
   title = "Testimonials"
   subtitle = "We have worked with many clients and we always like to hear they come out from the cooperation happy and satisfied. Have a look what our clients said about us."
```

#### Ver más

Esta sección se utiliza para proporcionar un enlace a otro sitio. Puede ser un sitio externo, o una página o entrada dentro de su sitio Hugo.
Se puede habilitar en el archivo de configuración.

``` js
[params.see_more]

   enable = true
   icon = "far fa-file-alt"
   title = "Do you want to see more?"
   subtitle = "We have prepared for you more than 40 different HTML pages, including 5 variations of homepage."
   link_url = "http://your-site.com/more"
   link_text = "Check other homepages"
```

#### Clientes 

La sección de clientes (clients) se utiliza para mostrar una lista de logotipos de empresas con las que se ha colaborado. Los clientes se definen en el directorio de datos como archivos _.yaml_.

Cada archivo de cliente contiene la siguiente información:

``` js
name: "customer-1"
image: "img/clients/customer-1.png"
url: "http://www.customer-1.com"
```

- _name:_ nombre del cliente
- _image:_ ruta relativa al logo dentro del directorio estático
- _url:_ campo opcional en caso de querer enlazar el logo con el sitio web del cliente.

A continuación, se puede habilitar la sección en el archivo de configuración.

``` js
[params.clients]

   enable = true
   title = "Our Partners"
   subtitle = "We have proudly collaborated with the following companies."
```

#### Entradas recientes

La sección de publicaciones recientes muestra las cuatro últimas publicaciones del blog, con su imagen destacada y un resumen opcional. Por defecto, muestra las publicaciones recientes de todas las secciones principales. Se trata de la sección con más publicaciones o puede establecerse explícitamente en el archivo de configuración.

Puedes activarlo en el archivo de configuración.

`summaryLength = 70`

``` js
[params.recent_posts]

   enable = true
   title = "From our blog"
   subtitle = "Pellen"
   hide_summary = false
```

Las publicaciones recientes utilizan la propiedad `.Summary` y, por defecto, Hugo toma automáticamente las primeras 70 palabras de su contenido como su resumen y lo almacena en la variable de página `.Summary` para utilizarlo en sus plantillas. 

Se puede personalizar la longitud del resumen estableciendo `summaryLength` en la configuración de tu sitio. Si estableces la propiedad de configuración `hide_summary` a true, el resumen se ocultará en las entradas recientes y en la página de la lista de blogs.

#### Pie de página

En el pie de página hay tres bloques personalizables: Acerca de nosotros, Mensajes recientes y Contacto. Cada bloque se puede configurar mediante parámetros.

##### Acerca de nosotros

Se puede definir un texto, en caso de que no haya texto definido todo el bloque estará oculto:

``` js
[params]

   about_us = "<p>Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas.</p>"
```

##### Mensajes recientes

El bloque de publicaciones recientes puede activarse o desactivarse (ocultarse).

``` js
[params.footer.recent_posts]

   enable = true
```
##### Contacto

En la sección de contacto hay un botón para redirigir a la página de contacto, existe la posibilidad de personalizar la _url_. También se puede definir un texto de contacto, en caso de no haber texto definido todo el bloque estará oculto:

``` js
[params]

   contact_url = "/contact"
   address = """<p class="text-uppercase"><strong>Universal Ltd.</strong>
       <br>13/25 New Avenue
       <br>Newtown upon River
       <br>45Y 73J
       <br>England
       <br>
       <strong>Great Britain</strong>
     </p>
     """
```

### Meta etiquetas

Los siguientes metadatos HTML pueden establecerse para cada página. Aunque el valor por defecto de algunos de ellos puede definirse en _config.toml_, todas estas propiedades también pueden establecerse a través de las respectivas variables Hugo **front matter**:

| HTML meta name/property | Hugo front matter variable | Default variable in config.toml |
| ---------- | --------- |--------- |
| article:author | facebook_author  | - |
| article:publisher | facebook_site | facebook_site |
| author |  author | - |
| description / og:description / twitter:description | description | defaultDescription |
| keywords | keywords | defaultKeywords |
| og:image / twitter:image | banner | default_sharing_image |
| title / og:title / twitter:title | title | - |
| twitter:creator | twitter_author | - |
| twitter:site | twitter_site | twitter_site |

Además, ciertos metadatos de Open Graph se establecen automáticamente:
- **article:published_time, article:modified_time, og:updated_time y article:** expiration_time se establecen en base a las variables de portada (predefinidas) de Hugo date, publishDate, lastmod y expiryDate.
- **article:section y article:** tag se establecen en base a las taxonomías de categorías y etiquetas de Hugo. Como sólo puede haber un `article:section`, sólo el primer elemento de la matriz de categorías se utiliza como _article:section_.

Se establecen valores por defecto para todas las páginas en el archivo _config.toml_ como se indica a continuación:

``` js
[params]

   defaultKeywords = ["devcows", "hugo", "go"]
   defaultDescription = "Site template made by Devcows using Hugo"
   default_sharing_image = "img/sharing-default.png"
   facebook_site = "https://www.facebook.com/GolangSociety/"
   twitter_site = "GoHugoIO"
```

El HTML resultante será el siguiente:

``` html
    <meta name="keywords" content="devcows, hugo, go">
    <meta name="description" content="Site template made by Devcows using Hugo">
    <meta property="og:description" content="Site template made by Devcows using Hugo">
    <meta property="og:image" content="img/sharing-default.png">
    <meta property="og:image:type" content="image/png">
    <meta property="og:image:width" content="800">
    <meta property="og:image:height" content="420">
    <meta property="article:publisher" content="https://www.facebook.com/GolangSociety/">
    <meta name="twitter:description" content="Site template made by Devcows using Hugo">
    <meta name="twitter:site" content="@GoHugoIO">
```

También puede anular los valores por defecto del _config.toml_ estableciendo las claves respectivas en la portada de las páginas individuales. Como ejemplo, aquí está el asunto principal del archivo faq.md en el directorio _exampleSite_:

``` js
    +++
    title = "FAQ"
    description = "Frequently asked questions"
    keywords = ["FAQ","How do I","questions","what if"]
    +++
```

Lo que da como resultado el siguiente HTML:

``` html
    <title>FAQ</title>
    <meta name="keywords" content="FAQ,How do I,questions,what if">
    <meta name="description" content="Frequently asked questions">
    <meta property="og:description" content="Frequently asked questions">
    <meta name="twitter:description" content="Frequently asked questions">
```

En caso de necesitar una biblioteca de Javascript personalizada o un estilo CSS, se puede anular este archivo `layouts/partials/custom_headers.html` con el contenido adecuado como:

``` js
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.4.1/jquery.min.js"></script>    
```