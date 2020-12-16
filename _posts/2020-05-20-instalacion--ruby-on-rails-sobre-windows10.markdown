---
layout: post
title:  "Instalacion de Ruby on Rails sobre windows 10"
date:   2020-05-20 16:00:00 +0530
categories: so
---

# Pasos para instalar ruby on rails sobre windows 10 a traves de wsl

1. Requisitos para instalar wsl(subsystem linux for windows), en windows 10.

	Versión 16215.0 o Superior y Windows 10 de 64 bit.
	
	para verificar lo requisitos vamos a:
	
	inicio>configuracion>sistema>acerca de al final de todo estan las 
	
	Especificaciones del dispositivo:
	
		Tipo de sistema: Sistema operativo de 64 bits
	
	Especificaciones de windows:
	
		version del sistema operativo: Versión 16215.0 o Superior.
		
	Nota: Si cumplimos con el requisito del dispositivo de 64 bits, pero tenemos una version inferior a la solicitada, debeos acualizar
	windows 10 a traves de Windows Update una vez actualizado a la version mas actual de windows continuaremos al paso 2.
	
2.  Activar las opciones de desarrollador, vamos a inicio>configuracion>actaulizacion y seguridad>para programadores>

	selecionamos Mode de programador

3. Instalar wsl(subsystem linux for windows)

	1- Abrimos el powershell en modo administrador: 
	
		Click derecho en inicio>windows powershell(Administrator)
	
	2- Una vez en la consola (PS C:\Windows\system32>), Tipamos los siguentes comandos
	
		dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart

		dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart

		Estos comandos activan el wsl y la plataforma de la maquina virtual, que se encuentran en w10 por defecto deshabilitados.
		
	3- Cuando lo solicite reiniciamos el sistema.
	
4. Instalar bash de ubuntu 18.04 lts
	
	Una vez hemos habilitado e instalado el wsl, procedemos a buscar el bash de linux que vamos a utiizar, esto se realiza
	
	desde la tienda de windows, ya que funciona con las versiones desarrolladas por canonical que ahora es una division de microsoft,
	
	en este tutorial utilizaremos la version de linux 18.04 Lts, la descargamos e instalamos, cual si fuera un app tradicional de windows.
	
	Nos solicitara que elijamos un usuario y una contraseña, la cual vamos a requerir para trabajar como super usuario al interior del bash
	
	una vez hecho esto, procedemos a actualizar el bash de linux con los siguientes comandos:
	
		apt-get update
	
		apt-get upgrade
	
	con los cuales nos actualiza a la ultima version disponible en de las librerias utilizadas por linux para su funcionamiento.
	
	una vez hecho esto nos dirigimos al paso 5.


5. Instalar ruby mediante el manejador de paquetes rbenv

		sudo apt-get update
	
		sudo apt-get install git-core curl zlib1g-dev build-essential libssl-dev libreadline-dev libyaml-dev 
	
		libsqlite3-dev sqlite3 libxml2-dev libxslt1-dev libcurl4-openssl-dev software-properties-common libffi-dev	

		cd
	
		git clone https://github.com/rbenv/rbenv.git ~/.rbenv
	
		echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc
	
		echo 'eval "$(rbenv init -)"' >> ~/.bashrc
	
		exec $SHELL

		git clone https://github.com/rbenv/ruby-build.git ~/.rbenv/plugins/ruby-build
	
		echo 'export PATH="$HOME/.rbenv/plugins/ruby-build/bin:$PATH"' >> ~/.bashrc
	
		exec $SHELL

		rbenv install 2.6.6
	
		rbenv global 2.6.6
	
		ruby -v
		
		gem install bundler

6. Configurar parametros de git en el bash de linux

		git config --global color.ui true
	
		git config --global user.name "YOUR NAME"
	
		git config --global user.email "YOUR@EMAIL.com"
	
		ssh-keygen -t rsa -b 4096 -C "YOUR@EMAIL.com"
	
		cat ~/.ssh/id_rsa.pub
	
	Lo generado por la linea anterior lo pegamos en: 
	https://github.com/settings/keys creando con esto un codigo de acceso a git para trabajar de manera remota por consola
	
	en la consola ejecutar el siguiente codigo:
	
		ssh -T git@github.com

	respuesta satisfactoria a la linea anterior:
	Hi excid3! You've successfully authenticated, but GitHub does not provide shell access.

7. Instalar rails

		curl -sL https://deb.nodesource.com/setup_12.x | sudo -E bash -
	
		curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
	
		echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list

		sudo apt update

		sudo apt-get install -y nodejs yarn
	
		gem install rails -v 6.0.2.2
	
		rbenv rehash
	
		rails -v
	
		Respuesta esperada: Rails 6.0.2.2

8. Instalar postgresql para windows

	ejecutar en la consola: 
	
		sudo apt install libpq-dev
	
	descargar e instalar postgres para windows: https://www.postgresql.org/download/windows/
	tener a la mano usuario y contraseña (el user por defecto es postgres // pass el que le coloquemos)

9. Ejecutar rails

	rails s

## Fuente

  [Gorails.com](https://gorails.com/setup/windows/10)
