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

La imagen la tengo en *Docker Hub*: [imagen en Docker Hub](https://cloud.docker.com/u/crdguez/repository/docker/crdguez/blockscad2) y ahí aparecen las **instrucciones** para instalar en local (necesitas tener docker instalado) o desplegarla en *heroku*.

El código para construirla está en este  [enlace al código para crear la imagen](https://github.com/crdguez/mis_herokus/tree/master/blockscad_server):

Los fichero que le indican a Docker cómo crear la aplicación son:

* Dockerfile

* app.py


Código Dockerfile:



```
# Use an official Python runtime as a parent image
FROM python:2.7-slim

# Set the working directory to /app
WORKDIR /app

# Copy the current directory contents into the container at /app
COPY . /app

# Install any needed packages specified in requirements.txt
# RUN pip install --trusted-host pypi.python.org -r requirements.txt

# Make port 80 available to the world outside this container
EXPOSE 80

# Define environment variable
ENV NAME World

# Run app.py when the container launches
CMD ["python", "app.py"]
```

Y el de *app.py*:

```python
import os

# Para local:
#PORT = '9000'

#Para heroku
PORT = os.environ['PORT']

os.system('python -m SimpleHTTPServer ' + PORT)
```

**NOTA:** Según se vaya a construir en local o en *heroku* habrá que seleccionar las líneas del puerto correspondiente.

Así es como queda desplegada en **heroku** :

<img src="/assets/img/blockscad_heroku.gif" width="90%">