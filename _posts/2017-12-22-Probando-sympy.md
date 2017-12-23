---
layout: post
title: Probando Sympy - Recetas
tags: latex, matemáticas, sympy
mathjax: true
eye_catch: 
---

```
solve_univariate_inequality(x**2 >= 4, x, relational=False)
solve([x+4<0,x+1<x/2],x)
solve([Eq(x+y,3), Eq(x-y,1)],[x,y])

latex(solve_rational_inequalities([[((Poly(-x + 5), Poly(1, x)), '>='),((Poly(-x - 7), Poly(1, x)), '<')]]))
```
