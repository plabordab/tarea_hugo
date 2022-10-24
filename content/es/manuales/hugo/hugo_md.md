+++
title = "Markdown"
tags = ["Markdown"]
categories = ["Markdown"]
description = "Markdown"
banner = "img/banners/hugo.jpeg"
authors = ["Pilar Laborda"]
+++

Markdown es un lenguaje de marcado como html, pero con la particularidad que es mucho más sencillo y práctico de usar. Además su curva de aprendizaje es extremadamente sencilla y proporciona ventajas en lo que a productividad se refiere. 

## FUNCIONALIDADES:

### SALTOS DE LÍNEA Y PÁRRAFOS

Para generar un nuevo párrafo tenemos que dejar una línea en blanco.

### ENCABEZADOS O TÍTULOS

Para crear un encabezado escribimos la cantidad de almohadillas (#) correspondientes al nivel de encabezado que queramos, seguido de un espacio:


# Título 1: Equivalente a h1
##  Título 2: Equivalente a h2 
###  Título 3: Equivalente a h3 
####  Título 4: Equivalente a h4 
##### Título 5: Equivalente a h5 
###### Título 6: Equivalente a h6 

```js
# Título 1: Equivalente a h1
##  Título 2: Equivalente a h2 
###  Título 3: Equivalente a h3 
####  Título 4: Equivalente a h4 
##### Título 5: Equivalente a h5 
###### Título 6: Equivalente a h6 
```

### CITAS

Para incluir una cita tenemos que usar el símbolo > seguido de un espacio antes del texto que queremos citar.

> Se puede incluir citas 
>> Y citas dentro de citas
>
> Y continuar en la anterior dejando una línea en blanco


```js
> Se puede incluir citas 
>> Y citas dentro de citas
>
> Y continuar en la anterior dejando una línea en blanco
```

### LISTAS

#### Listas desordenadas

Para crear una lista se utiliza cualquiera de los símbolos * , – o +  seguido de un espacio más el dato a incluir.

Para anidar una lista tan solo tenemos que incluir un espacio presionando la tecla Tab (Tabulador).

* enumeración 1
    - enumeración 2
        + enumeración 3

```js
* enumeración 1
    - enumeración 2
        + enumeración 3
```

#### Listas ordenadas

Para obtener listados ordenados numéricamente tenemos que escribir un número seguido de un punto y un espacio antes de comenzar a escribir.

Sean cual sea la secuencia de números, markdown creará una lista de números correlativos:

_Ejemplo 1:_

1. Listas
4. donde
2. el
12. orden
99. es
21. importante

_Ejemplo 2:_

1. Si sólo utiliza 1. 
1. para cada número, 
1. Markdown numerará automáticamente 
1. cada elemento

```js
1. Listas
4. donde
2. el
12. orden
99. es
21. importante

1. Si sólo utiliza 1. 
1. para cada número, 
1. Markdown numerará automáticamente 
1. cada elemento
```

#### Listas de tareas o checklist

Para crear listas de tareas se debe abrir corchete, dejar un espacio y cerrar el corchete. En el caso que querer marcar la tarea como realizada tenemos que reemplazar el espacio por una X.:

- [X] llevar los niños a natación
- [X] aprender markdown
- [ ] renovar mi suscripción del gimnasio

### SEPARACIONES ENTRE SECCIONES

Para incluir una separación física entre dos secciones de texto tenemos que escribir en otra línea 3 guiones bajos seguidos 

___

```js
Para incluir una separación física entre dos secciones de texto tenemos que escribir en otra línea 3 guiones bajos seguidos 

___
```

### FORMATO DE TEXTO

Cualquier texto que no empiece por un signo especial se escribirá como texto normal, sin formato, y se envolverá dentro de las etiquetas 
`<p></p>` en el HTML renderizado.

**negrita**

_cursiva_

*cursiva*

*****negrita y cursiva*****

~~tachado~~

~~***Tachado, Negrita y Cursiva***~~


```js
Cualquier texto que no empiece por un signo especial se escribirá como texto normal, sin formato, y se envolverá dentro de las etiquetas 
`<p></p>` en el HTML renderizado.

**negrita**

_cursiva_

*cursiva*

*****negrita y cursiva*****

~~tachado~~

~~***Tachado, Negrita y Cursiva***~~
```

### ENLACES DE TEXTO O DESCARGA

Para incluir enlaces en un texto tenemos que utilizar el siguiente tipo de sintaxis:

`[texto_de_ancla](URL_que_queremos_enlazar_o_enlace_de_descarga)`

Es posible añadir un título al enlace con la siguiente sintaxis:

`[texto_de_ancla](URL_que_queremos_enlazar ”titulo_del_enlace”)`

Ejemplo: 

[Sintaxis Markdown](https://geekland.eu/aprender-markdown-en-minutos/ "Opcionalmente, se puede añadir un globo con info de ayuda")

```js
[Sintaxis Markdown](https://geekland.eu/aprender-markdown-en-minutos/) "Opcionalmente, se puede añadir un globo con info de ayuda")
```

También se podría enlazar una URL sin poner título alternativo, sin texto de ancla ni título:

  <https://geekland.eu/instalar-servidor-dlna-readymedia-raspberry-pi-linux/>


#### ENLACES REPETIDOS

Para crear el enlace de una palabra que se repite, utilizamos la siguiente sintaxis:


Escribiremos un texto y cada vez que aparezca una palabra que queramos enlazar la definiremos del siguiente modo al final del documento:

[Geekland]: https://geekland.eu

De modo que las palabras Geekland del documento que estén entre corchetes se enlazarán con la URL geekland.eu:

[Geekland] es un blog que acostumbra a publicar tutoriales. [Geekland] también da soporte a los usuarios que lo píden.

### IMÁGENES

La sintaxis para insertar imágenes es:

`![texto_alternativo_imagen](URL_imagen) "Título opcional de la imagen"`

> La url puede ser una dirección local o una dirección que apunte a una imagen alojada en un servidor web.

![Imagen no encontrada](/img/template-LOGO.png "Este es mi logo")

```js
![Imagen no encontrada](/img/template-LOGO.png "Este es mi logo")
```

La imagen siempre se insertará en tamaño real. Si la queremos redimensionar lo deberemos hacer en función del editor de markdown que usemos. Muchos editores de Markdown permitirán redimensionar las imágenes mediante código html.


> Importante meter en las imgénes el valor del alt (texto alternativo si no carga la imagen)
>
> Creamos en la carpeta static la carpeta imagen
>
> En la carpeta public se guarda toda la estructura a partir de la carpeta static

#### IMÁGENES REPETIDAS

Para insertar una imagen en varias partes del documento definiremos la URL de la imagen al final del documento:

[incrustar imagen exerna]: https://cdn.icon-icons.com/icons2/2389/PNG/512/markdown_logo_icon_145085.png

Imagen 1, primera vez:

  ![incrustar imagen exerna]

Imagen 1, segunda vez:

  ![incrustar imagen exerna]

 
### VÍDEOS

El procedimiento puede variar según el editor de Markdown.

Ejemplo en Nextcloud: ![vimeo](https://vimeo.com/76979871)

```js
![vimeo](https://vimeo.com/76979871)
```

Sintaxis para editores de markdown sin ningún tipo de soporte:

```js
[![texto_alternativo_imagen](url_imagen_que_representará_el_video)](url_del_vídeo_que_queremos_insertar)
```

```js
[![Aprender markdown](https://i.ytimg.com/vi/POWdnjYfWDo/hqdefault.jpg)](https://www.youtube.com/watch?v=oxaH9CFpeEE)
```

[![Aprender markdown](https://i.ytimg.com/vi/POWdnjYfWDo/hqdefault.jpg)](https://www.youtube.com/watch?v=oxaH9CFpeEE)


### CÓDIGO
    
#### CÓDIGO DENTRO DE CAJETINES


Para incluir cajetines de código en cualquier lenguaje de programación, se debe escribir con 3 comillas `(```)` en el inicio y 3 comillas `(```)` en el final. Es decir: 

`(```)` 

  **CODIGO**

 `(```)`


_Por ejemplo:_

    ```
    <!DOCTYPE HTML>
    <html>
      <head>
        <title>Ejemplo</title>
      </head>
      <body>

        <?php
         echo "¡Hola, mundo PHP!";
        ?>

      </body>
    </html>
    ```

Para resaltar la sintaxis, añadimos la extensión de archivo del lenguaje que se desea utilizar después de las comillas (```js).

```js
grunt.initConfig({
  assemble: {
    options: {
      assets: 'docs/assets',
      data: 'src/data/*.{json,yml}',
      helpers: 'src/custom-helpers.js',
      partials: ['src/partials/**/*.{hbs,md}']
    },
    pages: {
      options: {
        layout: 'default.hbs'
      },
      files: {
        './': ['src/templates/pages/index.hbs']
      }
    }
  }
};
```

#### CÓDIGO DENTRO DE PÁRRAFO

Para resaltar código dentro de una frase tenemos que usar el símbolo de acento grave o abierto `. 

El comando para instalar LibreOffice es `sudo apt install libreoffice`.

#### ANULAR CÓDIGO 

Para anular el código Markdown tendremos que usar el carácter `\`.

Si escribimos: *geekland* Se mostrará el texto geekland en cursiva.

Si queremos que no se aplique el código markdown y se muestre el texto real que hemos escrito tendremos que añadir una contrabarra \ al inicio de la palabra: \*geekland*

### TABLAS

Para generar tablas en Markdown usaremos los siguientes símbolos:

|

:

\-


Primero tenemos que definir los títulos de las columnas. Para ello los escribiremos separados por tuberías (|).

Después repetiremos la línea sustituyendo los títulos de las columnas por 3 giones (---)

Finalmente añadiremos el resto de filas de la misma manera:

Si además queremos alinear el contenido de una columna a la izquierda o a la derecha, usaremos el símbolo : antes o después, respectivamente, de los 3 giones (---) de la segunda fila.

| Hora | Lunes | Martes | Miércoles | Jueves | Viernes|
| ------: | ------ | ------ | ------ | ------ | ------ | 
| 1 | Cliente | Despliegue | ------ | Cliente | Servidor | 
| 2 | Cliente | Despliegue | ------ | Cliente | Servidor | 
| 3 | Cliente | Servidor | Interfaces | Cliente | Servidor | 
| 4 | Interfaces | Servidor | Interfaces | Servidor | Interfaces | 
| 5 | Despliegue | Servidor | ------ | Servidor | Interfaces | 
| 6 | Despliegue | ------ | ------ | Servidor | Interfaces | 


### COMENTARIOS O NOTAS AL PIE

Para insertar una nota al pie de página escribiremos `[^1]` justo después de la palabra.

_Por ejemplo:_

Este año visitaremos la Giralda[^1]. Será una visita importante.

_Y al final del documento añadimos:_

`[^1]: Nombre que recibe la torre campanario de la catedral de Santa Maria de la Sede.`

Los comentarios se escriben de la siguiente manera:

```HTML
    <!--
    comentario
    -->
```

### ABREVIACIONES 

El TAS aprobó su solicitud.

*[TAS]: Tribunal de arbitraje del deporte.

A partir de estos momentos siempre que escribamos TAS tendremos su definición disponible.

### DEFINICIONES

Markdown
: Es un lenguaje de marcado ligero creado por John Gruber
: Es una palabra inglesa que significa reducción de precio.





[Geekland]: https://geekland.eu
[incrustar imagen exerna]: https://cdn.icon-icons.com/icons2/2389/PNG/512/markdown_logo_icon_145085.png
[^1]: Nombre que recibe la torre campanario de la catedral de Santa Maria de la Sede.