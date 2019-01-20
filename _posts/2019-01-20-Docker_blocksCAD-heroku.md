---
layout: post
title: Docker de BlocksCAD y despliegue en Heroku
tags: docker heroku blockscad
mathjax: true
eye_catch: 
---

He estado probando [Docker](https://www.docker.com/) aprovechando que quería tener una imagen de un servidor de [Blockscad](https://www.blockscad3d.com/). La verdad es que la web oficial no suele fallar, pero con esto de Internet nunca se sabe. 

Es fácil instalar en local un servidor con el código que aparece en el [github de BlocksCAD](https://github.com/EinsteinsWorkshop/BlocksCAD), pero el hecho de crear una imagen **Docker** creo que me facilitará las cosas (sobre todo si aprendo a desplegarla en Windows que es lo que suele haber por todos los lados).

Además esa imagen la he desplegado en [Heroku](https://www.heroku.com/) con lo que puedo tener un servidor alternativo por si falla el oficial.

La imagen la tengo en *Docker Hub*: [https://cloud.docker.com/u/crdguez/repository/docker/crdguez/blockscad2](https://cloud.docker.com/u/crdguez/repository/docker/crdguez/blockscad2) y ahí aparecen las **instrucciones** para instalar en local (necesitas tener docker instalado) o desplegarla en *heroku*.

Así es como queda desplegada en **heroku** :

<img src="/assets/img/blockscad_heroku.gif" width="90%">