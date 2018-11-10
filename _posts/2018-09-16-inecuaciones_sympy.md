---
layout: post
title: Resolviendo inecuaciones con SymPy
tags: SymPy
mathjax: true
eye_catch: 
---

En el siguiente enlace puedes probar todo lo que se explica en este artículo:

[View in Colaboratory](https://colab.research.google.com/github/crdguez/aprendiendo_sympy/blob/master/inecuaciones.ipynb)


Lo primero que necesitamos hacer es importar las librerias de *Python* que necesitaremos


```
from sympy import *
from IPython.display import Markdown as md
from IPython.display import display

from __future__ import division
from sympy import *
x, y, z, t = symbols('x y z t')
k, m, n = symbols('k m n', integer=True)
f, g, h = symbols('f g h', cls=Function)
init_printing(use_latex=False)
```

## Resolviendo inecuaciones

### Inecuaciones con  valores absolutos
Para poder resolver inecuaciones con valores absolutos hay que utilizar la función *reduce_abs_inequality*.

La función recibe tres parámetros resuelve inecuaciones con el miembro de la derecha 0 (por lo tanto hay que ):


*   La expresión algebraica del miembro de la izquierda
*   El símbolo de la desigualdad
*   La variable, normalmente x





#### Ejemplo:

Resuelve la inecuación $$\lvert x-2 \rvert \leq 1 $$



> La inecuación anterior es equivalente a $\lvert x-2 \rvert -1 \leq 0$  y se resuelve con el siguiente código:




```
reduce_abs_inequality(Abs(x-2)-1,'<=',x)
```

**Solución:**


    1 ≤ x ∧ x ≤ 3



### Referencias

- [Documentación oficial de SymPy](https://docs.sympy.org/latest/modules/solvers/inequalities.html#sympy.solvers.inequalities.reduce_abs_inequality)