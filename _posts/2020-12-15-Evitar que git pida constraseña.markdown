---
layout: post
title:  "Evitar que git vuelva a pedir contraseña y usuario"
date:   2020-12-06 12:02:36 +0530
categories: git
---
En este post quiero incluir algunas notas sobre como evitar que git vuelva a pedir contraseña y usuario.



Almacenar credenciales

```shell
git config --global credential.helper store
git pull
```

Eliminar credenciales:

```shell
git config --global --unset credential.helper
```
