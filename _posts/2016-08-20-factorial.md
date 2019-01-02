---
layout: post
title: Factorial de un número
---

### Escribir una función que calcule el factorial de un número.

Sin definir una función:

```python
factorial = 1
n = int(input("Introduce un numero: "))
for i in range(n):
    factorial *= n
    n = n - 1
print("El factorial es ", factorial)
```

Definiendo una función:

```python
def factorial(n):
    factorial = 1
    for i in range(n):
        factorial *= n
        n = n - 1
    return factorial
n = int(input("Introoduce un numero: "))
print("El factorial es ", factorial(n))
```
