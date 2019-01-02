---
layout: post
title: Volumen de un cubo
---

### Haz un programa que calcule el volumen de un cubo, sabiendo el área de una de las caras.

```python
import math
a = int(input("Introduce area: "))
v = math.sqrt((a / 6)) ** 3
print("El volumen es: ", v)
```
