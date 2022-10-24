+++
title = "git push"
tags = ["git", "github"]
categories = ["github"]
description = "cargar contenido del repositorio local a un repositorio remoto"
banner = "img/banners/hugo.jpeg"
authors = ["Pilar Laborda"]
+++

El comando `git push` se usa para cargar contenido del repositorio local a un repositorio remoto. 

El envío es la forma de transferir confirmaciones desde tu repositorio local a un repositorio remoto. Es el equivalente a git fetch, pero mientras que al recuperar se importan las confirmaciones a ramas locales, al enviar estas se exportan a ramas remotas. Las ramas remotas se configuran mediante el comando git remote. Los envíos pueden sobrescribir los cambios, por lo que se debe tener cuidado a la hora de realizarlos. Estos problemas se describen a continuación.

## Uso de git push

```js
git push <remote> <branch>
```

Envía la rama especificada al servidor remoto, junto con todos los commits y objetos internos necesarios. De este modo se crea una rama local en el repositorio de destino. Para evitar que se sobrescriban los commits, Git no te permitirá enviarlos cuando el resultado en el repositorio de destino sea una fusión sin avance rápido.

```js
git push <remote> --force
```


Es igual que el comando anterior, pero fuerza el envío incluso si el resultado es una fusión sin avance rápido. No se debe usar `--force` sin la absoluta certeza de saber lo que se está haciendo.

```js
git push <remote> --all
```
Envía todas las ramas locales a una rama remota especificada.

```js
git push <remote> --tags
```

Las etiquetas no se envían automáticamente cuando envías una rama o usas la opción `--all`. La marca `--tags` envía todas las etiquetas locales al repositorio remoto.

## Análisis de git push

`git push` se usa sobre todo para publicar y cargar cambios locales a un repositorio central. Después de modificar el repositorio local, se ejecuta un envío para compartir las modificaciones con los miembros remotos del equipo.

### Uso de git push para publicar cambios

En el siguiente diagrama se muestra lo que pasa cuando el progreso de la rama principal local ha sobrepasado a la rama principal del repositorio central y publicas los cambios ejecutando `git push origin main`. 

![Imagen no encontrada](/img/git_push.png "antes de git push")

Ejecutar `git push` es, en esencia, lo mismo que ejecutar `git merge main` desde el repositorio remoto.


### Sicronización

`git push` es uno de los muchos componentes que se usan en el proceso general de "sincronización" de Git. 

Los comandos de sincronización funcionan en ramas remotas que se configuran mediante el comando `git remote`. 

A `git push` se le puede considerar un comando de carga, mientras que, a `git fetch` y a `git pull`, comandos de descarga. 

Una vez movidos los conjuntos de cambios mediante una descarga o una carga, se puede ejecutar un comando `git merge` en el destino para integrarlos.

### Eliminación de una rama remota

En ocasiones, se deben limpiar las ramas por motivos de organización y mantenimiento de registros. 

Para eliminar una rama por completo, se debe eliminar tanto de forma local como de forma remota.

Para eliminar la rama remota denominada "nombre_rama" tenemos dos opciones:

1. Con el comando `git branch`:

    ```js
    git branch -D <nombre_rama>`
    ```

2. O pasándola como argumento al comando `git push` con el prefijo dos puntos (:).

    ```js
    git push origin :<nombre_rama>`
    ```