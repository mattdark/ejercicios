---
layout: post
title: Multiplicación rusa
---

#### Escribir un programa que reciba como entrada el multiplicador y el multiplicando, y entregue como resultado el producto de ambos, calculado mediante el método de multiplicación rusa.

El método de multiplicación rusa consiste en multiplicar sucesivamente por 2 el multiplicando y dividir por 2 el multiplicador hasta que el multiplicador tome el valor 1. Luego, se suman todos los multiplicandos correspondientes a los multiplicadores impares.<sup>1</sup>

```python
multr = int(input("Ingrese multiplicador: ")) # Multiplicador
multn = int(input("Ingrese multiplicando: ")) # Multiplicando

r = 0
while multr >= 1:
    if multr % 2 == 1:
        r += multn
    multr = multr // 2
    multn = multn * 2

print("Resultado:", r)
```

Referencia
<ol>
<li>Multiplicación rusa: http://progra.usm.cl/apunte/ejercicios/1/multiplicacion-rusa.html</li>
</ol>
