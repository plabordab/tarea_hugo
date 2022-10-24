+++
title = "configuración de docker"
tags = ["docker"]
categories = ["docker"]
description = "Configuración DOCKER"
banner = "img/banners/hugo.jpeg"
authors = ["Pilar Laborda"]
+++

#### Las imágenes en Docker

- Se trata de un archivo que se encuentra compuesto de diversas capas y se utiliza con el objetivo de ejecutar un código dentro de un contenedor de Docker.
- Contienen todo el sistema de ficheros inicial en los que se va a basar el _contenedor_ para su funcionamiento, así como su punto de entrada (comando que deberá ejecutarse cuando el usuario lance un contenedor que esté asociado a esa imagen en Docker).
- Se encargan de actuar como un script para construir un contenedor en Docker, así como una plantilla, funcionando como un punto de partida cuando el usuario utiliza Docker.

    > La ejecución de una imagen dentro del sistema de Docker implica que esta tiene la posibilidad de convertirse en una o más instancias de un docker container o contenedor de Docker.

Una imagen en Docker puede compararse en un sistema de máquinas virtuales con la plantilla o instantánea que utiliza en los entornos de la virtual machine. En el caso de Java o un lenguaje orientado a objetos, esta imagen puede asemejarse a una clase.

#### Los contenedores en Docker 

- Son una forma de virtualización del sistema operativo. 
- Se instalan a partir de una imagen y siempre dependerá de ella, es decir,  la imagen no se podrá eliminar mientras tenga un contenedor asociado.
- Un solo contenedor se puede usar para ejecutar cualquier cosa, desde un microservicio o un proceso de software a una aplicación de mayor tamaño. 
- Dentro de un contenedor se encuentran todos los ejecutables, el código binario, las bibliotecas y los archivos de configuración necesarios. 
- No contienen imágenes del sistema operativo, haciéndolos más ligeros y portátiles, con una sobrecarga significativamente menor. 
- Se pueden poner en marcha varios contenedores como uno o varios clústeres de contenedores. Estos clústeres se pueden gestionar mediante un orquestador de contenedores, como Kubernetes.

![Imagen no encontrada](/img/docker_img_cont.png "Contendores e imágenes en Docker")


### Crear un contenedor

Para crear un contendor utilizamos el comando:

``` js
docker run -t -i --name web -p 8000:80 -v  /home/pi/web: var/www/html ubuntu:latest
```

Con el cual estamos haciendo lo siguiente:

1. Descargar una imagen: `docker run ubuntu:latest`

    > El comando `run` permite crear y arrancar un contenedor.

2. Hacerlo interactivo mediante una terminal 

    > Indicando _-t_ para abrir un terminal y _-i_ para que sea interactivo.

3. Asignarle un nombre `--name <nombre_contendor>`

4. Abrir los puertos para evitar que cualquiera entre a nuestro anfitrión y poder dejar el contenedor abierto:
  
    > **puerto anfitrión**: 8000 [reservados puestos hasta el 1024] 
    > 
    > **puerto http** (será apache del contenedor): 80
    > 
    > Para acceder desde otra máquina al contendor se tiene que mapear el puerto 80 con el puerto 8000 de la máquina anfitriona.
    > 
    > La petición se hace a la máquina anfitriona, al ver que la solicitud es por el puerto 8000 va directa al contendor, que devolverá el recurso solicitado.

5. Crear un volumen

    > Apache busca los recursos en un fichero de configuración `/var/www/html/`, lo que resulta peligroso, por 
    > Hay que mapear el directorio `/var/www/html` del contenedor con el directorio `/home/pi/web` del anfitrión.
    > 
    > Si el directorio anfitrión asignado en el mapeo de docker no existe, se creará automaticamente, pero se le deberá dar permisos:
    > 
    > ``` js
    > chown pi:pi /home/pi/web -R
    > 
    > ```



Para borrar un contenedor:

``` js
docker rm web
```

Podemos visualizar los contendores con el comando:

``` js
docker ps -a
```



