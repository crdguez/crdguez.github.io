---
layout: post
title: Convirtiendo Markdown a Jupyter notebooks
tags: ipython notebook jupyter
mathjax: true
eye_catch: 
---

[nbconvert](https://nbconvert.readthedocs.io/en/latest/#) permite exportar un [jupyter](https://jupyter.org/) (antes llamados ipython) notebook a diferentes formatos, entre ellos [markdown](https://daringfireball.net/projects/markdown/). Sin embargo, yo buscaba lo contrario, pasar de un fichero en markdown a notebook. 

La razón principal, es que markdown lo edito con cualquier editor de texto, y por eso me resulta muy cómodo documentar en markdown.

Cuando quiero documentar algo relacionado con *Python* me gusta hacerlo en un notebook de Jupyter. Si lo que documento tiene mucho texto me resulta útil escribirlo en markdown y luego convertirlo a notebook. 

¿Cómo lo hago?:

### Convirtiendo ficheros *Markdown* a *Jupyter Notebooks* con [notedown](https://github.com/aaren/notedown)

[Aaron O'Leary](https://github.com/aaren) ha desarrollado la fantástica aplicación [notedown](https://github.com/aaren/notedown) que permite pasar de markdown a notebook. Tal como pone en su documentación:



#### Instalación

```bash
pip install notedown
```

#### Uso

```bash
notedown input.md > output.ipynb

```

¡ Gracias Aaron, me ha resultado muy útil

