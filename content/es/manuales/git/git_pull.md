+++
title = "git pull"
tags = ["git", "github"]
categories = ["github"]
description = "descarga contenido desde un repositorio remoto, actualizando el repositorio local"
banner = "img/banners/hugo.jpeg"
authors = ["Pilar Laborda"]
+++

El comando `git pull` se emplea para extraer y descargar contenido desde un repositorio remoto y actualizar al instante el repositorio local. 

La fusión de cambios remotos de nivel superior en el repositorio local es una tarea habitual de los flujos de trabajo de colaboración basados en Git. 

El comando `git pull` es, en realidad, una combinación de dos comandos, `git fetch` seguido de `git merge`. 

> En la primera etapa de la operación `git pull` ejecutará un `git fetch` en la rama local a la que apunta HEAD. 
> 
> Una vez descargado el contenido, `git pull` entrará en un flujo de trabajo de fusión. Se creará una nueva confirmación de fusión y se actualizará HEAD para que apunte a la nueva confirmación.

## Uso de git pull

El comando `git pull` ejecuta en primer lugar `git fetch`, que descarga el contenido del repositorio remoto especificado. 

Después, se ejecuta `git merge` para fusionar las referencias y los encabezados del contenido remoto en una nueva confirmación de fusión local. 

![Imagen no encontrada](/img/pull1.png "git pull")

En el diagrama se puede ver que `git pull` descargará todos los cambios desde el punto de separación de la rama local y la rama principal. En el ejemplo es el punto E. 

El comando `git pull` recuperará las confirmaciones remotas divergentes, que son A, B y C. 

A continuación, el proceso de incorporación de cambios creará otra confirmación de fusión local que incluya el contenido de las nuevas confirmaciones remotas divergentes.

![Imagen no encontrada](/img/pull2.png "git pull")

Podemos ver la nueva confirmación H, que es una confirmación de fusión nueva que incluye el contenido de las confirmaciones remotas A, B y C, y tiene un mensaje de registro combinado. 

Este es un ejemplo de una de las estrategias de fusión de `git pull`. 

Una opción `--rebase` puede combinarse con `git pull` para usar una estrategia de fusión de reorganización en lugar de una confirmación de fusión. 

En el siguiente ejemplo se puede ver cómo funciona una incorporación de cambios de reorganización. Supongamos que nos encontramos en el punto de partida de nuestro primer diagrama y que hemos ejecutado `git pull --rebase`.

![Imagen no encontrada](/img/pull3.png "git pull")

En este diagrama, ahora podemos ver que la incorporación mediante cambio de base no ha creado la confirmación H, sino que el cambio de base ha copiado las confirmaciones remotas A, B y C y ha reescrito las confirmaciones locales E, F y G para que aparezcan después de ellas en el historial de confirmaciones principales o de origen locales.

### Opciones comunes


```js
git pull <remote> <branch>
```

Recupera la copia del origen remoto especificado de la rama actual y la fusiona de inmediato en la copia local. 

Esto equivale a `git fetch ＜remote＞` seguido de `git merge origin/＜current-branch＞`.

```js
git pull --no-commit <remote> 
```
De manera similar a la invocación predeterminada, extrae el contenido remoto, pero no crea una nueva confirmación de fusión.

```js
git pull --rebase <remote> 
```

Al igual que en la anterior incorporación de cambios, en lugar de utilizar `git merge` para integrar la rama remota en la local, usa `git rebase`.

```js
git pull <remote> --verbose
```

Proporciona una salida detallada durante una incorporación de cambios que muestra el contenido descargado y los detalles de la fusión.

## Análisis de git pull

`git push` es una forma sencilla de sincronizar tu repositorio local con los cambios anteriores. 

En el siguiente diagrama, se explica cada paso del proceso de incorporación de cambios.

![Imagen no encontrada](/img/git_pull.png "antes de git pull")


### Sicronización

`git pull` es uno de los muchos comandos que se encargan de "sincronizar" el contenido remoto. 

El comando `git remote` se utiliza para especificar los extremos remotos sobre los que operarán los comandos de sincronización. 

El comando `git pushsirve` para cargar contenido en un repositorio remoto.

El comando `git fetch` puede confundirse con `git pull`. Ambos se usan para descargar contenido remoto, pero existe una distinción importante de seguridad:
> `git fetch` descargará el contenido remoto sin modificar el estado del repositorio local. 
> 
> `git pull` descargará el contenido remoto y tratará inmediatamente de cambiar el estado del repositorio local para reflejar ese contenido. De modo accidental, esto puede provocar que el repositorio local entre en conflicto.

### Incorporación de cambios mediante la opción rebase

La opción `--rebase` se puede usar para garantizar que el historial sea lineal, evitando las confirmaciones de fusión innecesarias. 

Muchos desarrolladores prefieren esta opción antes que la fusión, porque es como decir "quiero que mis cambios prevalezcan sobre lo que han hecho los demás". 

Incorporar cambios con `--rebase` es un flujo de trabajo tan común que hay una opción de configuración específica para él:

```js
git config --global branch.autosetuprebase always
```
Después de ejecutar ese comando, se integrarán todos los comandos `git pull` mediante `git rebase` en lugar de `git merge`.