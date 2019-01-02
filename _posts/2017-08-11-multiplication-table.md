---
layout: post
title: "Tabla de multiplicar"
description:
categories:
tags:
redirect_from:
---

#### Escriba un programa que muestre una tabla de multiplicar como la siguiente:<sup>1</sup>

```
 1   2   3   4   5   6   7   8   9  10
 2   4   6   8  10  12  14  16  18  20
 3   6   9  12  15  18  21  24  27  30
 4   8  12  16  20  24  28  32  36  40
 5  10  15  20  25  30  35  40  45  50
 6  12  18  24  30  36  42  48  54  60
 7  14  21  28  35  42  49  56  63  70
 8  16  24  32  40  48  56  64  72  80
 9  18  27  36  45  54  63  72  81  90
10  20  30  40  50  60  70  80  90 100
```

##### Solución

```python
lst = [[None for _ in range(10)] for _ in range(10)]
for i in range(10):
    x = 0
    m = ""
    for j in range(10):
        x += i + 1
        lst[i][j] = x
        l = len(str(lst[i][j]))
        if l == 1:
            m += " "
        if l == 3:
            m = m.rstrip()
            m += " "
        m += str(lst[i][j])
        m += "  "
    print(m)
```

##### Referencia
<ol>
  <li>Tabla de multiplicar: <a href="http://progra.usm.cl/apunte/ejercicios/1/tablas-de-multiplicar.html">http://progra.usm.cl/apunte/ejercicios/1/tablas-de-multiplicar.html</a></li>
</ol>
