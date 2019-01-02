---
layout: post
title: "Suma de dígitos al cubo"
description:
categories:
tags:
redirect_from:
---

#### Entre todos los enteros mayores a 1 hay solamente cuatro que pueden ser representados por la suma de los cubos de sus dígitos.<sup>1</sup>

Uno de esos números es 153 pues:
- 13 + 53 + 33 = 1 + 125 + 27 = 153

Desarrolle un programa para poder determinar los otros tres números.

Tenga en cuenta que los números se encuentran entre 150 y 410.

##### Solución

```python
for i in range(150, 411):
    n = 0
    x = str(i)
    for j in x:
        n += int(j) ** 3
    if i == n:
        print(i)
```

##### Resultado
Los números buscados son:

- 153
- 370
- 371
- 407

##### Referencia
<ol>
  <li>Suma de dígitos al cubo: <a href="http://progra.usm.cl/apunte/ejercicios/1/suma-digitos-cubo.html">http://progra.usm.cl/apunte/ejercicios/1/suma-digitos-cubo.html</a></li>
</ol>
