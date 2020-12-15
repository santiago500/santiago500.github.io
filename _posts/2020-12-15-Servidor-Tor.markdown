---
layout: post
title:  "Ngrok"
date:   2020-12-06 12:02:36 +0530
categories: Ngrok
---
En este post quiero incluir algunas notas sobre Ngrok.


Descargar Ngrok [enlace][enlace]

instalacion servidor apache

```shell
apt install apache2
```

ubicacion:

```shell
cd /var/www/html
```

iniciar servidor apache2

```shell
/etc/init.d/apache2 start
```

iniciar Ngrok

```shell
./ngrok http 80
```

iniciar SSH

```shell
./ngrok tcp 22
```

ejemplo

```shell
kali@0.tcp.ngrok.io:10908
```

[enlace]: https://ngrok.com
