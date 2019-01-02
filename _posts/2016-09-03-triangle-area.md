---
layout: post
title: Área de un triángulo
---

### Diseña un programa que pida el valor de los tres lados de un triángulo y muestre el valor de su área.

```python
import math
a = int(input("Introduce el valor de a: "))
b = int(input("Introduce el valor de b: "))
c = int(input("Introduce el valor de a: "))
p = (a + b + c) / 2 # Perimetro
area = math.sqrt(p * (p - a) * (p - b) * (p - c))
print("El area es: ", area)
```
