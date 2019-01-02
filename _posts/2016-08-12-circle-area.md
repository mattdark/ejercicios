---
layout: post
title: Área de un círculo
---

### Escribir un programa que pida el radio de un círculo y calcule el área.

```python
# Calculo del area de un circulo
# Formula: pi * (r ** 2)
r = int(input(“Introduce el radio del circulo: ”))
pi = 3.1416
area = pi * (r ** 2)
print(“El area del circulo es: ”, area)
```

```python
# Calculo del area de un circulo
# Formula: pi * (r ** 2)
from math import pi
r = int(input(“Introduce el radio del circulo: ”))
area = pi * (r ** 2)
print(“El area del circulo es: ”, area)
```
