---
layout: post
title: Probando ExamGen - Generador de exámenes con Python, Sympy y  LaTeX  (\( \LaTeX \))
tags: latex matemáticas sympy
mathjax: true
eye_catch: 
---

## [Enlace al Proyecto Original](https://github.com/thearn/examgen)

Gracias a [Thearn](https://github.com/thearn) por el [generador de exámenes](https://github.com/thearn/examgen)

## Cómo funciona
A tener en cuenta, solo funciona con python 2.7, i.e. ejecutar **python2**. 

  * *Opción 1*: Hay que descargar la carpeta examgen, y en la que lo contenga entrar en python, así no fallará las importaciones (lo más cómodo es clonar el repositorio del enlace y desde allí ejecutar python2). A la hora de pegar código desde github tener en cuenta los saltos de línea que se copian en el intérprete y dan error. 
  * *Opción 2*: Generar un fichero.py y ejecutar python2 fichero.py. Seguiremos investigando para ver cómo podemos adaptarlo a nuestras necesidades. 
  
## Algunos problemillas de novato con python

Para que no nos dé problemas con los caracteres propios del castellano (tildes y otros), hay que añadir al inicio del *fichero.py*:

```
# -*- coding: utf8 -*-
```
