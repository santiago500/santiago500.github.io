---
layout: post
title:  "Listado de comandos útiles para trabajar con VIM"
date:   2019-11-29 22:03:36 +0530
categories: Herramientas vim
---
Una de las herramientas que mas trabajo me ha dado para aprender a utilizar es VIM, en este documento describo algunos tips y comentarios para el manejo de la herramienta.

## Duplicar un archivo

```shell
:saveas %:h/nuevo_archivo
```

## Remplazar texto dentro de un archivo

Muchas veces se requiere remplazar textos dentro de un archivo, el comando para realizarlo desde VIM es:

```shell
:%s/texto_a_sustituir/texto_nuevo/g

:6,10s/texto_a_sustituir/text_nuevo/gc
```

## Remplazar información dentro de paréntesis

Para remplazar la información dentro de () se usa la instrucción:


```shell
ci)
```
## Realizar paginación en VIM

Para paginar hacia abajo se usa (page down) **CTRL-D** y para moverse hacia arriba page up **CTRL-U**

## Plegado de líneas de código

Para realizar el pegado se debe estar en modo visual y seleccionar el código que se desea plegar **zf** y para colocarlo como estaba se usa **za**

## Comandos para comentar código con tcomment_vim

**gcir / gcar** comment inside/around Ruby do/end block. **gcim / gcam** comment inside/around Ruby method. **gciM / gcaM** comment inside/around Ruby class.

Plus normal Commentary maps like **gcc** to comment a line, or 5: to comment 5 lines
Para ver un tutorial en consola **vimtutorial**

### Escribir después de una palabra

**wi** o **ea**

## Quitar el highlights despues de buscar

```shell
nmap <Leader><CR> :nohlsearch<cr>
```
## Realizar una busqueda en VIM


```shell
Vimgrep /búsqueda/g  **/*.rb
```

Después usas: :cp antes :cn siguiente :copen abrir :ccl cerrar

## Usar Vim desde cero

Buscando un poco en internet para intentar explicar algunos muchahos sobre como usar VIM, encontre este [enlace][introduccion]

## Utilizar "surroundings"

Para trabajar con paréntesis, corchetes y comillas, se debe utilizar el plugin [surround]

1. Cambiar comillas dobles por comillas sencillas
```shell
cs"'
```
2. Quitar comillas
```shell
ds"
```
3. Encerrar una palabra
```shell
ysiw]
```
4. Encerrar toda una línea
```shell
yss)
```
5. Encerrar dentro de una etiqueta
```shell
ysiw<em>
```
6. Cambiar tag en html sin cambiar atributos (Ejecutas el comando y mostrara en la parte de abajo el caracter '<' simplemente coloca el nuevo tag y enter)
```shell
cstt
```

## Copiar y pegar

1. Copiar 5 lineas
```shell
5yy
```
2. Copiar hasta el final en una fila
```shell
y$
```

## Crear migración Rails desde vim

Para crear un archivo de migración desde vim se debe usar el siguiente comando:
```shell
:Emigration AddNombreToPersonas!
```

## Hablemos VIM

1. Elimina la palabra donde esté el cursor (delete inside word):
```shell
diw
```
2. Cambia la frase en la que estas (change inside sentence):
```shell
cis
```
3. Cambia lo que haya hasta 'foo' (change search foo)
```shell
c/foo
```
4. Cambia todo lo que esta hasta la letra X:
```shell
ctX
```
5. Selecciona un párrafo (visual around paragraph):
```shell
vap
```
6. Borra una palabra
```shell
dw
```
7. Borrar lo que está a la derecha
```shell
D
```
8. Borrar lo que esté a la izquierda
```shell
d0
```
9. Borrar desde la línea actual hasta el final del fichero:
```shell
dG
```

## Listado de recursos para aprender VIM

Comandos básicos para [manejo de VIM][comandos] 
[Video][video] que muestra la forma de utilizar Ultisnips

## Utiizar el Quickfix

En este enlace podemos ver como se debe usar el [QuickFix][quickfix]

## Visualizar el tipo del archivo que esta en edicion

`:set filetype?`

## Cambiar dos ventanas de horizontal a vertical

`Ctrl+w t Ctrl+w K`
`Ctrl+w t Ctrl+w H`

Explicación: Con Ctrl+w t Nos ubicamos en la ventana de la parte superior izquierda y con K y H nos movemos

## Copiar información dentro de )

```yi)``` también se puede usar para borrar ```di]```
En modo visual se puede usar ```vi)``` ó para seleccionar inclusive el ) ```va)```

Otros movimientos en modo visual pueden encoentrarse en el [enlace][enlace]

## Grabar una macro
- q (Con esto entramos en modo de grabar)
- Una letra cualquiera, pongamos una a
- Aparecerá "grabando"
- /\.jpg\|\.gif  (estamos buscando la palabra .jpg o .gif)
- Enter
- dd (borramos la línea)
- Esc
- q (fin modo grabación)

Ahora tenemos guardado en la letra 'a' la macro. La podemos ejecutar 1 vez tecleando:

@a

O mil veces:

1000@a

[introduccion]: https://hipertextual.com/archivo/2014/09/como-usar-vim-1-introduccion-a-vim/
[surround]: https://github.com/tpope/vim-surround
[comandos]: https://vim.rtorr.com/lang/es_es
[vieo]: http://vimcasts.org/episodes/meet-ultisnips/
[quickfix]: https://stackoverflow.com/questions/1747091/how-do-you-use-vims-quickfix-feature
[enlace]: http://vimdoc.sourceforge.net/htmldoc/motion.html#object-select
