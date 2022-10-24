+++
title = "INSTALACIÓN DE HUGO"
tags = ["hugo"]
categories = ["hugo"]
description = "Instalación HUGO"
banner = "img/banners/hugo.jpeg"
authors = ["Pilar Laborda"]
+++


Para instalar la versión más estable de hugo en la terminal de linux escribimos: 

``` js
sudo snap install hugo --classic
```


Podemos ver la versión con el comando:

``` js
hugo version
```

Trabajaremos con VS code, por lo que si no lo tenemos instalado en nuestra máquina lo hacemos:
``` js
sudo snap install code --classic
```

Creamos una carpeta en nuestro directorio para almacenar los proyectos:

``` js
mkdir hugo
```

Y nos movemos allí para empezar a crear un nuevo sitio de contenido:

``` js
cd hugo
hugo new site proyecto_hugo
```

Para abrir el proyecto que hemos creado en el IDE, estando ubicados en el directorio escribimos:

``` js
code .
```

Para empezar a trabajar con Hugo tenemos que descargarnos un [tema](https://themes.gohugo.io/themes/ "Haz clic para descubrir la biblioteca de temas de hugo").

Una vez elegido, antes de descargarlo, debemos desplazarnos a la carpeta themes de nuestro proyecto:

``` js
cd themes
```

Para duplicar el proyecto incluimos junto al comando git clone, la dirección de GitHub correspondiente y el nombre con el que queremos nombrarlo. Ejemplo:

``` js
git clone https://github.com/McShelby/hugo-theme-relearn relearn
```

Y, para que se haga efectivo, añadimos en el fichero *****config.toml*****  nuevo parámetro theme con el nombre que le acabamos de asignar:

``` js
theme=[‘relearn’]
```


Ahora ya podemos volver al directorio en la terminal para arrancar el servidor de desarrollo en segundo plano: 
``` js
hugo server &
```

De esta manera, nos permitirá ver el sitio en local a medida que lo vayamos construyendo.