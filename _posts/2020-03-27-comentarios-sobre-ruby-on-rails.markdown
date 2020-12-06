---
layout: post
title:  "Comentarios sobre ruby on rails"
date:   2020-03-27 13:00:00 +0530
categories: css
---

En este post quiero incluir algunas notas sobre ruby on rails.

## Comentarios sobre routes

Trabajando con Oscar Silvera, aprendí a usar el comando ```rails routes -c admin``` para que solo muestre las rutas relacionadas

## Ejemplos I18n

Encontré en internet estos ejemplos de como [utilizar I18n][i18n] en Ruby on Rails 

## Remover un índice desde una migración

```
remove_index :completions, name: "index_completions_on_survey_id_and_user_id"
```

## Generar tabla intermedia en relación muchos a muchos

```
rails g model Author name:string
rails g model Book title:string
rails g migration CreateJoinTableAuthorsBooks authors books
```

## Listado de gemas utiles para desarrollo

* [chartkick][chartkick] Esta gema permite generar graficos en una aplicación ruby on rails
* [groupdate][groupdate] Permite utilizar metodos para agrupar fechas

[i18n]: https://kapeli.com/cheat_sheets/Rails_i18n.docset/Contents/Resources/Documents/index
[chartkick]: https://chartkick.com/
[groupdate]: https://github.com/ankane/groupdate
