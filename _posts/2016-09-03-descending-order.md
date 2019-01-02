---
layout: post
title: Números de mayor a menor
---

### Haz un programa que pida tres números y los ordene de mayor a menor.

```python
lista = list()
for i in range(3):
    lista.append(int(input("Introduce un numero: ")))
lista.sort(reverse = True)
print(lista)
```
