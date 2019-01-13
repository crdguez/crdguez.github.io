---
layout: post
title: Puzzles Matemáticos al estilo Formulator Tarsia pero con $\LaTeX$ y Python
tags: Puzzle Tarsia
mathjax: true
eye_catch: 
---

Si tengo que recomendar una web de actividades matemáticas mediante juegos, esa sería el magnífico blog [Juegos y matemáticas](https://anagarciaazcarate.wordpress.com/) de [Ana García Azcarate](https://anagarciaazcarate.wordpress.com/author/anagarciaazcarate/) . Sirvan estas líneas de agradecimiento por tan fantástico trabajo.

El caso es que muchas de esas actividades están hechas con [Tarsia]( http://www.mmlsoft.com/index.php/products/tarsia). Por ejemplo: [este](https://anagarciaazcarate.wordpress.com/2018/11/20/puzle-hexagonal-de-las-rectas-paralelas/)

Buscando en Github alguna alternativa a Tarsia que fuera libre y que pudiera ejecutar en GNU-Linux, me topé con [Jigsaw-generator](https://github.com/juliangilbey/jigsaw-generator) de [Julian Gilbey](https://github.com/juliangilbey). ¡Muchas gracias, Julian!

Este es un ejemplo del aspecto que tienen los puzzles generados. Este en concreto se ha sacado de un ejemplo que el autor tiene colgado en el repositorio de la aplicación:

<img src="/assets/img/ejemplo_jigsaw.png" width="40%">

Vamos a ver cómo se instala y como se usa:

## Instalando Jigsaw-generator de Julian Gilbey

### Prerrequisitos

En el archivo [INSTALL](https://github.com/juliangilbey/jigsaw-generator/blob/master/INSTALL) del repositorio indica qué es necesario tener instalado:

* *Python 3.x* (¿A qué  estás esperando si todavía no usas *Python*?)
* Una distribución $\TeX$ ($\LaTeX$)
* Y el módulo *PyYaml* para manejar ficheros *Yaml*

Podemos instalar el módulo *PyYaml* con el siguiente comando:

```python
sudo -H pip3 install PyYAML
```

### Instalación propiamente dicha

Se da por descontado que has descargado el repositorio de la aplicación y que la ruta de trabajo apunta a esa carpeta.

Tal como pone en [INSTALL](https://github.com/juliangilbey/jigsaw-generator/blob/master/INSTALL) ,solo hay que ejecutar los típicos:

```bash
./configure
make
sudo make install
```

Si todo va bien hará la instalación sin errores

### Uso básico

El comando que genera el puzzle es:

```bash
$ jigsaw-generate
```

Si lo ejecutamos sin ningún parámetro devolverá lo siguiente:

<img src="/assets/img/cmd_jigsaw.png" width="40%">

El error que nos da indica que necesitamos pasarle un fichero *.yaml* con toda la información del puzzle

### Uso "pitónico"

...