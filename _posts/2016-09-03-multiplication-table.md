---
layout: post
title: Tabla de multiplicar
---

### Haz un programa que muestre la tabla de multiplicar de un número introducido por teclado por el usuario.

```python
n = int(input("Introduce un numero: "))
print("Tabla de multiplicar de ", n)
for i in range(1, 11, 1):
    print(n, "x ", i, " = ", n * i)
```
