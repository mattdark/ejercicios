---
layout: post
title: "Triángulo de Pascal"
description:
categories:
tags:
redirect_from:
---

#### Desarrolla un programa que dibuje un [triángulo de Pascal](https://es.wikipedia.org/wiki/Tri%C3%A1ngulo_de_Pascal)<sup>1</sup>, o sea, una disposición de números enteros tales que cada uno sea la suma de los dos que están por encima de él:<sup>2</sup>

<figure>
  <img src="https://upload.wikimedia.org/wikipedia/commons/d/d5/Tri%C3%A1ngulo_de_Pascal.svg" alt="Triángulo de Pascal" width="30%">
</figure>

Genere las primeras 20 líneas. Considere que en la línea 20 aparecen números de cinco dígitos.

##### Solución

```python
for i in range(20):
    lst = list()
    for j in range(i+1):
        lst.append(1)
    if len(lst) > 2:
        for k in range(i-1):
            lst[k+1] = lst2[k] + lst2[k+1]
    lst2 = lst
    print(lst)
```

##### Referencia
<ol>
  <li>Triángulo de Pascal: <a href="https://es.wikipedia.org/wiki/Tri%C3%A1ngulo_de_Pascal">https://es.wikipedia.org/wiki/Tri%C3%A1ngulo_de_Pascal</a></li>
  <li>Triángulo de Pascal: <a href="http://progra.usm.cl/apunte/ejercicios/1/triangulo-pascal.html">http://progra.usm.cl/apunte/ejercicios/1/triangulo-pascal.html</a></li>
</ol>
