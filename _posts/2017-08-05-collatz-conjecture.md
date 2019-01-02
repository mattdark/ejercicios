---
layout: post
title: "Conjetura de Collatz"
description:
categories:
tags:
redirect_from:
---

#### Desarrolle un programa que entregue la secuencia de Collatz de un número entero<sup>1</sup>

La secuencia de Collatz de un número entero se construye de la siguiente forma:

- si el número es par, se lo divide por dos;
- si es impar, se le multiplica tres y se le suma uno;
- la sucesióń termina al llegar a uno.

La [conjetura de Collatz](http://es.wikipedia.org/wiki/Conjetura_de_Collatz) afirma que, al partir desde cualquier número, la secuencia siempre llegará a 1. A pesar de ser una afirmación a simple vista muy simple, no se ha podido demostrar si es cierta o no.

Usando computadores, se ha verificado que la sucesión efectivamente llega a 1 partiendo desde cualquier número natural menor que 2<sup>58</sup>.

##### Solución:

```python
n = int(input("n: "))
list = list()
list.append(n)

while n > 1:
    if n % 2 == 0:
        n = n // 2
    elif n % 2 == 1:
        n = n * 3 + 1
    list.append(n)

print(list)
```

##### Referencia
<ol>
<li>Secuencia de Collatz: http://progra.usm.cl/apunte/ejercicios/1/collatz.html</li>
</ol>
