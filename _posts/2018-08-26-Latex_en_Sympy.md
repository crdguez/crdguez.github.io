---
layout: post
title: Probando parse_latex o cómo pasar expresiones LaTeX a SymPy
tags: LaTeX, SymPy
mathjax: true
eye_catch: 
---

Antes de empezar, al final del documento vienen las referencias a la documentación de donde saqué la información. 
Conviene que le eches un vistazo antes de nada. 

## Requisitos previos

 - ANTLR

```bash
$ pip3 install antlr4-python3-runtime
```

 - SymPy 1.2 (las versiones anteriores no tienen la librería para "parsear" latex)

```bash
$ pip3 install -U sympy
```

## Uso de la función *parse_latex*
Importamos la función *parse_latex*:


```python
from sympy.parsing.latex import parse_latex
```

Solo nos queda pasar un *string* con la expresión LaTeX para que la función devuelva la expresión en código entendible por Sympy. **NOTA:** *El string conviene pasarlo en formato "raw string literal"*

**Ejemplo:**


```python
parse_latex(r'\frac{x^2}{\sqrt{y}}')
```




    x**2/sqrt(y)
    
### Referencias:

* [Documentación de SymPy](https://docs.sympy.org/latest/modules/parsing.html#experimental-parsing)
* [Instalación](https://docs.sympy.org/latest/modules/parsing.html#runtime-installation)
