+++
title = "Proceso de carga de una página Web"
tags = ["web"]
categories = ["web"]
description = "Carga web"
banner = "img/banners/hugo.jpeg"
authors = ["Pilar Laborda"]
+++

El proceso de carga de una página web tiene una complejidad invisible para el usuario, que indica qué página web quiere ver y ésta se carga en segundos. 

En fracciones de segundo, el navegador entra en contacto con servidores web repartidos por todo el mundo, consulta allí los paquetes de datos almacenados y entrega, a partir de estos, una página web en la pantalla del dispositivo. 

De manera resumida podríamos describir el proceso en los siguientes pasos:

1. El usuario indica qué página web quiere ver.
2. Se pide a un servidor DNS la IP de la página.
3. Se accede a la máquina enviando un mensaje HTTP con la solicitud.
4. El servidor puede verificar credenciales, acceder a la BD, buscar datos en otras máquinas (webservices)...
5. Compone el recurso en un HTML y lo pone en la red para enviarlo al cliente.
6. El cliente visualiza la página web en su dispositivo.


### GRÁFICO MERMAID

De manera más explicita, todo comienza cuando se introduce una dirección en la barra de búsqueda del navegador. Esta dirección identifica de forma inequívoca a toda página web, permitiendo localizarla en Internet. 

Esta URL está compuesta de los siguientes elementos:

![Imagen no encontrada](/img/uri.png "URI")

Internet consiste en un sistema de documentos de hipertexto almacenados electrónicamente. 

> Para transferir los datos de una web desde el servidor al navegador, se utiliza el  **protocolo HTTP** y su variante encriptada **HTTPS**.
> 
> Después le sigue el **nombre de dominio**, la denominación que identifica a un computador en la red, formado por un dominio de nivel superior y un dominio de segundo nivel. 
> 
> Este dominio de segundo nivel aún podría incluir un dominio de tercer nivel o subdominio. 
> 
> Si se quiere acceder a un determinado directorio o a un archivo en una página web, se debe indicar el recurso.

La representación del URL con letras, tiene como objetivo la comprensión humana, ya que los ordenadores trabajan con direcciones IP. 

###  De URL a dirección IP

Para que un navegador pueda acceder a los contenidos de una web, es necesario convertir la URL de la página solicitada en una dirección IP. 

###  Servidores DNS: la agenda de direcciones IP

De esto se encargan los servidores DNS, responsables de la gestión del sistema de nombres de dominio o DNS (Domain Name Server).

> Al introducir una dirección en la barra de búsqueda, el navegador la dirige a un router que busca la dirección IP correspondiente para esta página web. 
> 
> La información necesaria se la proporciona un servidor DNS, un servidor web especial responsable de la resolución de nombres. 
> 
> Se puede configurar el servidor DNS desde el router o desde el sistema operativo. 
> 
> Dado que la consulta en el DNS requiere algo de tiempo, las direcciones IP de páginas ya visitadas se almacenan en el caché DNS del sistema operativo, descongestionando el servidor DNS y agilizando el acceso a las webs.

###  Router: el eslabón entre el ordenador y el servidor

El puesto intermedio entre Internet y la red local lo constituye el router. 

> El router solicita los datos desde Internet y los distribuye entre los dispositivos de la red (ordenadores, portátiles o tablets). 
> 
> La función del router es necesaria porque, aunque los dispositivos en la red local se comunican entre ellos con direcciones IP locales, hacia el exterior comparten la dirección IP pública del router. 
> 
> El procedimiento de traducción de las direcciones de la red (NAT) que realiza el router ya no es necesario en las modernas conexiones Ipv6, pues cada dispositivo de la red local recibe una dirección IP pública.

###  Transferencia de datos mediante HTTP

Una vez el router ha encontrado la dirección IP de la página solicitada, pide en el servidor web correspondiente los datos necesarios para mostrar la página en el navegador. 

> Esta consulta se produce mediante HTTP, que forma un paquete de datos con la información que necesita el servidor web para entregar los datos de la página web.
> 
> Además de la dirección IP de la página web solicitada, el router comunica su propia dirección IP como emisor y proporciona información sobre el sistema operativo, el navegador y el tipo de dispositivo que ha de mostrar la página web. 
> 
> El servidor web evalúa esta información y emite un código de estado HTTP. 
> 
> - Si la solicitud tiene éxito, el servidor envía un paquete de datos al navegador con toda la información necesaria para la visualización de la página web.
> - Si el servidor no encuentra la página web en la dirección solicitada, o bien emite un código de error 404 (página web no encontrada) o redirige a la nueva dirección si la conoce.

###  Último paso: la página web se muestra en el navegador web

Los paquetes de datos entrantes desde Internet son redirigidos por el router al ordenador en el cual se solicitó la página web, donde son analizados por el navegador web. 

> Las páginas web suelen estar constituidas por archivos cuyas líneas de código contienen información que indica al navegador cómo ha de mostrar la página web:
> 
>- Los **documentos HTML** definen la estructura y los elementos de uso de una página web.
> 
>- Las **hojas de estilo** en cascada o archivos CSS se usan para definir aspectos de diseño.
> 
>- Los **elementos interactivos** del usuario con la página web (formularios, etc.) suelen realizarse con JavaScript.
> 
> El motor de renderizado del navegador ocasiona diferencias en la visualización de una página en diferentes navegadores. 
> 
> Este también dispone de un caché que almacena temporalmente los datos cuando se abre una página, de manera que cuando se acceda a una página que ya se visitó, no habrá que solicitar de nuevo todos los datos. 
> 
> El navegador web solo carga los archivos que se han modificado desde la última visita, lo que repercute favorablemente en la velocidad de carga de una página.