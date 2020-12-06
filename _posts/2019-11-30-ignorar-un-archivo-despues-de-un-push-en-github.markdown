---
layout: post
title:  "Ignorar un archivo después de un push en GitHub"
date:   2019-11-30 21:03:36 +0530
categories: GitHub
---

Estoy desarrollando un software con Ruby on Rails que maneja imagenes, me gusta usar GitHub para mantener mi codígo actualizado. Despues de varios commits y push me pude dar cuenta que en el archivo .gitignore NO incluí la linea para evitar que las imagenes de ejemplo fueran objeto de control de código.

Googleando un poco encontre este recurso [Git Ready][git-ready], donde el autor explica como sacar el archivo para luego ignorarlo.

El comando es muy sencillo git rm --cached <file>

```shell
git rm --cached <file>
```
Creo que es un problema muy común y que se debe tener en cuenta para los proyectos.



[git-ready]:http://es.gitready.com/beginner/2009/01/19/ignoring-files.html
