---
layout: post
title:  "Borrar un archivo o directorio que se encuentra dentro de Time Machine"
date:   2019-04-19 21:03:36 +0530
categories: SO Time-Machine
---
En el día de hoy me encontré con el problema de tratar de borrar un archivo que tenía en un disco duro que use para realizar una con Time Machine.

Quería simplemente borrar ese archivo pero el sistema no lo permitía.


Simplemente use el comando:

```shell
sudo /System/Library/Extensions/TMSafetyNet.kext/Contents/Helpers/bypass rm -rfv /Volumes/[disk]/Backups.backupdb/[path]
```


Puede verificar la lista de comandos en el [sitio oficial][sitio oficial] para más información.

[sitio oficial]: https://superuser.com/questions/162690/how-can-i-delete-time-machine-files-using-the-commandline
