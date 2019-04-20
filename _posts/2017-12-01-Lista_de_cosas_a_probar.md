---
layout: post
title: Listado de cosas a probar
tags: latex, matemáticas
mathjax: true
eye_catch: 
---

Esa pila de cosas a probar pero que nunca hay tiempo:

  * [Generador de exámenes resueltos con sympy y latex](https://github.com/thearn/examgen). Bien, probado. A tener en cuenta, solo funciona con python 2.7, i.e. ejecutar **python2**. *Opción 1*: Hay que descargar la carpeta examgen, y en la que lo contenga entrar en python, así no fallará las importaciones (lo más cómodo es clonar el repositorio del enlace y desde allí ejecutar python2). A la hora de pegar código desde github tener en cuenta los saltos de línea que se copian en el intérprete y dan error. *Opción 2*: Generar un fichero.py y ejecutar python2 fichero.py. Seguiremos investigando para ver cómo podemos adaptarlo a nuestras necesidades. Gracias a [Thearn](https://github.com/thearn)
  * [Generador de stl a partir de, por ejemplo, latex](https://github.com/thearn/stl_tools)
  * [Generador de puzzles matemáticos libre - clon de Tarsia's Formulator](https://github.com/juliangilbey/jigsaw-generator)
  * [Paquete probsoln para generar exámenes](https://ctan.org/pkg/probsoln) --> [¿Tutorial en español?](http://www.dmae.upct.es/~gabi/CursoTeX/Presentacion01.pdf)
  * [Aprender Sympy](http://rua.ua.es/dspace/handle/10045/1522?offset=20). [Curso de Python Universidad Alicante](https://www.youtube.com/playlist?list=PLoGFizEtm_6jCjWqRU8A-dQYQuo5q5KNc). [1a edicion curso](https://www.youtube.com/playlist?list=PLGBbVX_WvN7bMwYe7wWV5TZt1a58jTggB) Ya lo he empezado!!
  * [Insertar python en documento latex](https://tex.stackexchange.com/questions/397234/h-do-mathematical-programming-in-latex?atw=1)
  * [Fotomatón](https://makezine.com/projects/raspberry-pi-photo-booth/)
  * [Curso sobre el procedimiento administrativo](https://catedu.gitbooks.io/el-procedimiento-administrativo/content/). Estoy intentando pasar el gtibook a pdf con la información de este [enlace](https://help.coderdojo.com/hc/en-us/articles/115001543063-Generating-a-PDF-from-GitBook)
  * [Pentominos, ajedrez y más](https://crieventa.webnode.es/)
  * [Dominando ensamblador z80](http://www.cpcwiki.eu/index.php/DEZ80)
  * [pivot tables con R](https://trendct.org/2015/08/21/tutorial-pivot-tables-with-r/), [excel2R](http://excel2r.com/)
  * [Para que el blog esté visible o no](https://help.github.com/articles/search-engine-optimization-for-github-pages/)
  * [Diagramas de gantt con Python](https://www.pythoniza.me/python-gantt/)
  * [web scraping](https://www.seleniumhq.org/)
  * [Lektor - Generador de web estática](https://www.getlektor.com/) y [https://www.staticgen.com/](https://www.staticgen.com/)
  * [uso de docker](https://www.muylinux.com/2016/04/19/tutorial-docker/)
      * docker exec -dt mi_bs sh -c "python3.7 -m http.server 9000 -d /home/BlocksCAD"r
      * docker run -it --name mi_bs -p 9000:9000 6098f0ec3553 sh -c "python3.7 -m http.server 9000 -d /home/BlocksCAD"
      * [subir a heroku](https://medium.com/travis-on-docker/how-to-run-dockerized-apps-on-heroku-and-its-pretty-great-76e07e610e22)
      * [https://serene-refuge-50391.herokuapp.com/](https://serene-refuge-50391.herokuapp.com/)
      * docker exec -i -t container  /bin/bash (abre una terminal en el contenedor)
      * docker run -v $(pwd):/app -p 8050:8050 --name mi_name image (monta la carpeta actual en el host en la que digas del contenedor)
  * [filtros pandoc para pasar tikz a imágenes](https://tex.stackexchange.com/questions/445051/pandoc-exporting-tikz-figures-and-other-environments-from-latex-to-other-format)
  * [Curso de Python](http://www.educoteca.com/curso_python.html)

Habrá que probarlos. 