+++
title = "apache"
tags = ["docker", "apache"]
categories = ["docker"]
description = "APACHE"
banner = "img/banners/hugo.jpeg"
authors = ["Pilar Laborda"]
+++

![Imagen no encontrada](/img/apache.jpeg "Apache")

### Instalación y ejecución

Empezamos con la instalación de apache:

``` js
apt-get install apache2
```

Podemos ver el estado del servicio con el comando:

``` js
service apache2 status
```

Comando para arrancar apache:

``` js
service apache2 start <nombre_contendor>
```

### Apache dentro de un contenedor

Se puede ejecutar un comando sobre un contenedor: 

``` js
docker exec <nombre_contendor> <comando>
```

_Por ejemplo:_

``` js
docker exec web service apache2 status
```

Para iniciar el contenedor de docker: 

``` js
docker start web
```

Para ejecutar el contenedor en la terminal: 

``` js
docker exec -ti web bash
```

Para parar el contenedor de docker: 

``` js
docker stop web
```

### Shell para arranchar apache

Creamos un fichero de ejecución por comandos para arranchar nuestro contenedor y apache automáticamente:

``` js
vim (gedit/nano) web.sh
```

Pasamos de modo edición a modo comando: `ESC`

``` js
docker start web
docker exec web service apache2 start
```

Guardamos y salimos: `:wq`

Le damos permisos de ejecución: 

``` js
sudo chmod +x web.sh
```

Y lo invocamos: 


``` js
./web.sh
```

