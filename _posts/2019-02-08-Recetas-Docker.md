---
layout: post
title: Recetas Docker
tags: docker recetass
mathjax: true
eye_catch: 
---

Esto no es más que una lista de instrucciones para manejar docker. Esta lista no es ningún tutorial, solo una serie de instrucciones que he ido necesitando conforme iba aprendiendo docker:



- docker exec -dt mi_bs sh -c "python3.7 -m http.server 9000 -d /home/BlocksCAD"r
- docker run -it --name mi_bs -p 9000:9000 6098f0ec3553 sh -c "python3.7 -m http.server 9000 -d /home/BlocksCAD"
- [subir a heroku](https://medium.com/travis-on-docker/how-to-run-dockerized-apps-on-heroku-and-its-pretty-great-76e07e610e22)
- [https://serene-refuge-50391.herokuapp.com/](https://serene-refuge-50391.herokuapp.com/)
- docker exec -i -t container  /bin/bash (abre una terminal en el contenedor)
- docker run -v $(pwd):/app -p 8050:8050 --name mi_name image (monta la carpeta actual en el host en la que digas del contenedor)
- docker build -t use/image_namer:version .   (ojo, lleva el punto. Genera una imagen a partir del Dockerfile que haya en la carpeta actual)