---
layout: post
title: Cálculo de hipotenusa
---

### Diseña un algoritmo que pida los catetos a y b de un triángulo rectángulo y calcule el valor de la hipotenusa c.

```python
import math
a = int(input("Introduce el valor de a: "))
b = int(input("Introduce el valor de b: "))
c = math.sqrt((a ** 2) + (b ** 2))
print("El valor de la hipotenusa es: ", c)
```
