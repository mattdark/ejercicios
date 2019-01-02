---
layout: post
title: Sucesión de Fibonacci
---

### Escribir un programa que imprima la sucesión de Fibonacci, solicitando previamente la cantidad de números a imprimir.

```python
# Sucesion de Fibonacci
def fibonacci(n):
    a, b = 1, 1
    lista = list()
    for i in range(n):
        a, b = b, a + b
        lista.append(a)
    print(lista)
n = int(input("Introduce un numero: "))
fibonacci(n)
```
Solución encontrada en: [5 Ways of Fibonacci in Python](https://technobeans.wordpress.com/2012/04/16/5-ways-of-fibonacci-in-python/)
