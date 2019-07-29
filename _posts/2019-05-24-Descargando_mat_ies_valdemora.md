---
layout: post
title: Probando pythontex
tags: Python Tex Latex
mathjax: true
eye_catch:
---

[PythonTeX](https://github.com/gpoore/pythontex) es un paquete de $ \LaTeX $ que permite añadir código Python directamente en $\LaTeX $ para ser ejecutado

## Instalación

```
 sudo apt-get-install texlive-extra-utils
```

## Ejecución

Aunque he intentado configurar Texmaker siguiendo este [enlace](https://tex.stackexchange.com/questions/431523/texmaker-miktex-using-pythontex), no lo he conseguido. Parece que hay problemas con *minted*

Para poder compilar documentos con pythontex he tenido que tirar de consola. Si nuestro fichero se llama *prueba.tex*:

```
pdflatex -shell-escape prueba.tex|pythontex prueba.tex|pdflatex -shell-escape prueba.tex

```

Aquí una [prueba](/assets/prueba_pythontex.pdf)




