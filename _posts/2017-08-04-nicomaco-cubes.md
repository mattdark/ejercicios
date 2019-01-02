---
layout: post
title: Los cubos de Nicómaco
---

#### Desarrolla un programa que escriba los n primeros cubos de acuerdo a la propiedad descubierta por Nicómaco de Gerasa, que dice los siguiente:<sup>1</sup>

- Sumando el primer impar, se obtiene el primer cubo;
- Sumando los dos siguientes impares, se obtiene el segundo cubo;
- Sumando los tres siguientes, se obtiene el tercer cubo, etc.

Ejemplos:
- 1<sup>3</sup> = 1                 = 1
- 2<sup>3</sup> = 3 + 5             = 8
- 3<sup>3</sup> = 7 + 9 + 11        = 27
- 4<sup>3</sup> = 13 + 15 + 17 + 19 = 64

```python
n = int(input("n: ")) # Cantidad de cubos a imprimir

x = -1
y = 1
for i in range(1, n+1):
    z = y
    for j in range(0, i):
        x += 2
        if x > 1:
            y += x
    if y > 1:
        y = y - z
    print(i, "^3 =", y)
```

Referencia
<ol>
<li>Ejercicios de programación creativos y recreativos en C++: http://antares.sip.ucm.es/cpareja/libroCPP/ Página 76</li>
</ol>
