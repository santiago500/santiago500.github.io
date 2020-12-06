---
layout: post
title:  "Colaborar en un proyecto open source GitHub"
date:   2020-04-05 13:00:00 +0530
categories: git GitHub
---

En este post quiero incluir algunas notas sobre colaborar en proyectos [OpenSource](https://en.wikipedia.org/wiki/Open_source)

### Fork del repositorio:

Realiza un copia exacta del repositorio en el perfil del usuario colaborador

### Clonar el repositorio:

Una vez se realiza el Fork, se debe clonar el repositorio forkeado

```shell
git clone https://github.com/User/NombreRepo.git
```

### Entrar en la carpeta clonada:

Para entrar a la carpeta clonada desde una consola ubuntu use el comando

```shell
cd NombreRepo
```

### Verificar las conexiones con fuentes remotas:

Por defecto se mostrara la conexión realizada cuando se clono el repositorio, por defecto es llamada origin

```shell
git remote -v
```

### Crear una conexión remota con el repositorio original

Se debe adicionar una conexión remota para el repositorio forkeado

```shell
git remote add upstream https://github.com/User/RepoOriginal(Forkeado)
```

### Renombrar conexiones remotas

Con el fin de tener un poco mas de claridad sobre cual es la conexión remota que estamos usando, se puede renombrar a gusto con el comando

```shell
git remote rename origin fork
```

## Trabajo diario con requerimientos

### Actualizar rama master con ultimos cambios:
Para tener actualizado nuestro repositorio local con las últimas actualizaciones del repositorio remoto original rama master

```shell
git pull -r upstream master
```

### Crear requerimiento ó funcionalidad:
Cree un nuevo requerimiento en su herramienta de trabajo preferida Ej: trello o GitHub
### Crear una rama donde se desarrollara la funcionalidad:
Se debe usar el siguiente comando para crear una rama donde se realizará la funcionalidad
    ```shell
    git checkout -b feature-nombre-rama
    ```
**Nota**: Podemos usar el comando `git branch` para saber en cual rama estamos trabajando
### Hacer los cambios en el código:
Estos cambios se realizan utilizando su IDE favorito
**Nota**: Los cambios no necesariamente deben ser pequeños, se puede trabajar por horas hasta conseguir una característica de la funcionalidad podemos usar `git status`
### Adicionar archivos que se incluiran en el próximo commit:
Para incluir un solo archivo utilizamos `git add archivo` y para incluir todos los archivos modificados `git add .`
**Nota**: Para confirmar el estado de los archivos podemos usar `git status`
### Commit a los cambios:
Una vez se logre un avance significativo de la funcionalidad o una característica importante se debe realizar un `git commit -m "Descripción del avance"`
**Nota**: Los commit se realizan para garantizar que no se pierdan las caracterisiticas desarrolladas y de esta manera avanzar a la siguiente
### Subir la rama con los cambios:
Una vez hemos desarrollado completamente la funcionalidad, procedemos a subirla con el comando `git push origin feature-nombre-rama`
**Nota**: Recordemos que se debe subir la rama al repositorio propiedad del colaborador (NO AL ORIGINAL)
### Solicitar que se incorporen cambios:
Entramos a nuestro usuario y realizamos una solicitud de incorporación del código al proyecto original utilizando la opción `Pull Request`
### Eliminar rama en local:
Para eliminar una rama después que fue incorporada por el propietario del repositorio, usaremos el comando `git branch -d feature-nombre-rama`
**Nota**: Si deseamos eliminarla sin usar el comando merge utilizaremos git branch -D feature-nombre-rama
### Eliminar rama en repositorio remoto:
Para eliminar una rama que está en un repositorio remoto usaremos `git push origin --delete feature-nombre-rama`
### Unir Ramas
Para unir ramas dentro de nuestro repositorio local usaremos el comando `git merge feature-nombre-rama`, debemos estar ubicado en la rama que deseamos actualizar
