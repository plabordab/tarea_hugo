+++
title = "Vinculación a git"
tags = ["git", "github"]
categories = ["git"]
description = "Vinculación a GIT"
banner = "img/banners/hugo.jpeg"
authors = ["Pilar Laborda"]
+++

## Repositorio local y repositorio remoto

Los **repositorios remotos** son versiones del proyecto hospedadas en Internet. Colaborar con otras personas implica gestionar estos repositorios enviando y recogiendo datos de ellos cuando sea necesario compartir el trabajo.

Las operaciones básicas entre un repositorio remoto y uno local son:

[**push**](/git_push/): Envía los cambios validados de la rama local a la rama remota.

[**pull**](/git_pull/): Descarga y combina automáticamente la rama remota con la rama actual.

Dentro de Git (no Github) existe lo que se conoce como las 3 zonas, que son la estructura base de Git en la que se divide este sistema de control de versiones:

![Imagen no encontrada](/img/git.png "git")

**[WORKING DIRECTORY]:** Copia de las versiones del proyecto en sí.

**[STAGING AREA]:** Lugar en el que se encuentran datos de un proyecto y sus cambios.

**[GIT REPOSITORY]:** Lugar donde se almacenan los datos de los elementos para el proyecto.

Pasos que sigue un fichero en el repositorio local hasta que su cambio está validado y preparado para enviarse al repositorio remoto mediante una acción push:

1. En primer lugar, debemos crear un repositorio y generar un token en GitHub.
2. Para vincularlo a nuestro directorio de trabajo inicializamos el repositorio local con `git init`.
3. Podemos quitar algún fichero para que no se vea con `git ignore` (se almacena dentro de temp).
4. Para añadir los ficheros al entorno de ensayo (staging area) usamos el comando `git add <nombre_archivo>`. Podemos sustituir el nombre del archivo por un "*" para incluir todos los ficheros.
5. Una vez añadidos, establecemos un commit con el comando `git commit -m "<mensaje>"` De esta manera, confirmamos los cambios y establecemos un checkpoint a los ficheros subidos, pudiendo acceder cuando sea necesario.
6. Si no nos hemos identificado previamente, GIT nos pedirá que lo hagamos, para ello usamos el comando `git config - - global`:

    ```
    git config - - global user.email “miemail@gmail.com”
    git config - - global user.name “MI NOMBRE”
    ```

7. Para crear una rama de nuestro repositorio utilizamos el comando `git branch -M main` (-M cambia automáticamente el nombre de la rama master a main).
8. Para vincular el repositorio local en el lugar de origen: `git remote add origin https://github.com/plabordab/portfolio_hugo.git`.
9. Y, finalmente para subir los cambios al remoto: `git push -u origin main` e incluimos el usuario y el token que hemos generado en GitHub.


#### Órdenes básicas:

`git init` Crea un subdirectorio nuevo llamado .git, que contiene todos los archivos necesarios del repositorio. Todavía no hay nada en el proyecto que esté bajo seguimiento.

`git fetch` Descarga los cambios realizados en el repositorio remoto, pero no los aplica a la rama local. 

`git merge <nombre_rama>` Fusiona una o más ramas dentro de la rama que tienes activa. 

`git pull <remote>` Unifica los comandos fetch y merge en un único comando. 

`git commit -m "<mensaje>"` Confirma los cambios realizados. El "mensaje" generalmente se usa para asociar al commit una breve descripción de los cambios realizados. 

`git push origin <nombre_rama>` Sube la rama "nombre_rama" al servidor remoto. 

`git status` Muestra el estado actual de la rama, con los cambios que hay sin commitear. 

`git add <nombre_archivo>` Añade el archivo "nombre_archivo" al entorno de ensayo (staging area).

`git branch <nombre_rama_nueva>` Crea una nueva rama.

`git checkout <nombre_rama_nueva>` Se sitúa sobre la rama local "nombre_rama_nueva", los cambios los hace sobre esa rama.

`git branch` Lista todas las ramas locales. 

`git branch -a` Lista todas las ramas locales y remotas. 

`git branch -d <nombre_rama>` Elimina la rama local con el nombre "nombre_rama".

`git push origin <nombre_rama> (git push *<REMOTE_NAME> <BRANCH_NAME>* )` Sube confirmaciones de cambios realizadas en la rama local a un repositorio remoto. 

`git revert <hash_commit>` Revierte el commit realizado, identificado por el "hash_commit". 