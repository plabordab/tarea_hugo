+++
title = "instalación de docker"
tags = ["docker"]
categories = ["docker"]
description = "Instalación DOCKER"
banner = "img/banners/hugo.jpeg"
authors = ["Pilar Laborda"]
+++


Antes de instalar Docker debemos desinstalar versiones antiguas, para ello ejecutamos el comando: 

``` js
sudo apt-get remove docker docker-engine docker.io containerd runc
```

Ahora ya lo podemos instalar usando el repositorio de docker para Ubuntu:

``` js
sudo apt-get install  ca-certificates   curl   gnupg-agent  lsb-release
```

Añadimos la clave GPG oficial de docker:

``` js
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
```

Y el repositorio _stalbe_. Se podría añadir uno _nightly_ o _test_, modificando la palabra _stalbe_ por el tipo de vesión que se desee instalar:

``` js
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

```

**Tip**: 

> `lsb_release -cs`; `-c`, `codename`: para mostrar el nombre de código de la distribución
>
> `-s`: short para solo mostrar el valor del nombre

Actualizamos el índice de los paquetes apt e instalamos docker

``` js
sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io
```

Para poder ejecutar docker el usuario actual sin usar sudo agragamos el usuario al grupo de docker:

``` js
sudo usermod -a -G docker $USER
```

Cambiamos el grupo de usuarios actual al grupo de usuarios de docker:

``` js
newgrp docker
```

> Si no funciona, intentamos dar los permisos para la conexión al socket del dominio Docker:
> 
>> ``` js
>> 
>> sudo chmod 666 /var/run/docker.sock
>> 
>> ```

Para consultar los comandos de docker:

``` js
docker help
```