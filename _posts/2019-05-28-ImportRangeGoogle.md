---
layout: post
title: Importando celdas de una hoja 
tags: Google Sheets
mathjax: true
eye_catch:
---

[Solución](https://tecnocentres.org/es/funcion-importrange-en-hojas-de-calculo-de-google/)

La función ImportRange da error de referencia cuando se ejecuta la primera vez, hasta que damos permisos.

El caso es que solo nos deja dar el permiso cuando la ejecutamos sola, sin encadenarla, por ejemplo en VLOOKUP.

La solución por tanto, está en una celda aparte hacer una referencia al alguna celda concreta. Por ejemplo:

```
=importrange("https://docs.google.com/spreadsheets/d/1kphmjSpqzT4SDbgpiemgx_-n0r38BjsrCI-NRvs7LuM/";"nota evaluación!G4")
```
