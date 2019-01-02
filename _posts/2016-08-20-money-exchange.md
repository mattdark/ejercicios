---
layout: post
title: Conversor de divisas
---

### Diseña un algoritmo que convierta de dólares a pesos y viceversa.

```python
print("1. Dolares a pesos")
print("2. Pesos a dolares")
o = int(input("Selecciona una opcion (1 o 2): "))
if o == 1:
    d = float(input("Dolares: "))
    p = d * 18.0822017
    print("Pesos: ", p)
elif o == 2:
    p = float(input("Pesos: "))
    d = p / 18.0822017
    print("Dolares: ", d)
```
