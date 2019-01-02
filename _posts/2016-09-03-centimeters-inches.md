---
layout: post
title: Centímetros a pulgadas
---

### Escribe un programa que convierta de centímetros a pulgadas y viceversa.

```python
print("1. Centimetros a pulgadas")
print("2. Pulgadas a centimetros")
o = int(input("Selecciona una opcion (1 o 2): "))
if o == 1:
    c = float(input("Centimetros: "))
    p = c * (1 / 2.54)
    print("Pulgadas: ", p)
elif o == 2:
    p = float(input("Pulgadas: "))
    c = p * 2.54
    print("Centimetros: ", c)
```
