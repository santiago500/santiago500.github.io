---
layout: post
title:  "Instrucciones para copiar archivos en S3"
date:   2019-11-29 21:03:36 +0530
categories: AWS
---
En la actualidad pago los servicios de Amazon AWS para mantener mis proyectos en funcionamiento.

Me encontre con la necesidad de usar el servicio S3 para mantener copia de mis archivos en la nube, pero no estaba familiarizado con los comandos necesarios para realizar dicha actividad.

Para realizar la copia desde consola, instale el cliente


```shell
brew install awscli
```
Despues, sólo resta usar los siguiente comandos:

```shell
# Crear Buckets
aws s3 mb s3://lab01-storage

# Listar Buckets
aws s3 ls

# Eliminar Buckets
aws s3 rb s3://lab02-storage

# Copiar archivos - local Remoto
aws s3 cp foo.txt s3://lab01-storage

# Copiar archivos - Remoto local
aws s3 cp s3://lab01-storage/bar.txt bar.txt

# Listar archivos
aws s3 ls s3://lab01-storage

# Mover archivo remoto
aws s3 mv s3://lab01-storage/foo.txt s3://lab01-storage/bar.txt

# Borrar archivo remoto
aws s3 rm s3://lab01-storage/bar.txt

# sincronizar carpeta
aws s3 sync test/ s3://lab01-storage –recursive

# Sincronizar borrando los archivos que ya no estan en el local
aws s3 sync test s3://lab01-storage –delete

# Copiar carpeta - local Remoto
aws s3 cp foo.txt s3://lab01-storage –recursive –exclude "*.log"

# Comando suado para Sincronizar.
aws s3 sync . s3://hguzman-storage --delete

```

Puede verificar la lista de comandos en el [sitio oficial][sitio-oficial] para más información.

[sitio-oficial]: https://docs.aws.amazon.com/cli/latest/reference/s3/cp.html
