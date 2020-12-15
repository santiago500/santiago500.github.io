---
layout: post
title:  "Servidor Tor"
date:   2020-12-06 12:02:36 +0530
categories: Tor
---
En este post quiero incluir algunas notas sobre la instalacion del servidor Tor.



instalacion servidor python3

```shell
sudo apt-get install python3
```

instalacion Tor:

```shell
sudo apt-get tor
```

iniciar servidor python3

```shell
python3 -m http.server --bind 127.0.0.1 8080
```

O

```shell
python3 -m http.server 8080
```


Descomentar

```shell
nano /etc/tor/torrc
```

<img src="{{ "/assets/img/tor.jpg" | relative_url }}" alt="{{ site.plainwhite.name }}">


Direccion del hostname

```shell
cat /var/lib/tor/hidden_service/hostname
```

iniciar servidor Tor

```shell
sudo tor
```
