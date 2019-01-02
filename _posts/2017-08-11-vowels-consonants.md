---
layout: post
title: "Vocales y consonantes"
description:
categories:
tags:
redirect_from:
---

#### Escribe un programa que pida al usuario ingresar una palabra y muestre cuántas vocales y consonantes tiene:<sup>1</sup>

##### Ejemplo

Ingrese palabra: edificio<br>
Tiene 5 vocales y 3 consonantes

##### Solución

```python
p = input("Ingresa una palabra: ")

v = ["a", "e", "i", "o", "u"] # Vocales

nv = 0 # Número de vocales
nc = 0 # Número de consonantes

for i in p:
    if i in v:
        nv += 1
    else:
        nc += 1

print("Tiene", nv, "vocales y", nc, "consonantes")
```

###### Referencia

<ol>
  <li>Vocales y consonantes: <a href="http://progra.usm.cl/apunte/ejercicios/2/vocales-y-consonantes.html">http://progra.usm.cl/apunte/ejercicios/2/vocales-y-consonantes.html</a></li>
</ol>
