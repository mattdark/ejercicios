---
layout: post
title: "Signo zodiacal"
description:
categories:
tags:
redirect_from:
---
#### Escriba la función determinar_signo(fecha_de_nacimiento) que reciba como parámetro la fecha de nacimiento de una persona, representada como una tupla (dia, mes, año), y que retorne el signo zodiacal de la persona:<sup>1</sup>

```bash
>>> determinar_signo((1990, 5, 7))
'tauro'
```

El signo zodiacal de una persona está determinado por su día de nacimiento.

El diccionario signos asocia a cada signo el período del año que le corresponde. Cada período es una tupla con la fecha de inicio y la fecha de término, y cada fecha es una tupla (mes, dia):

```python
signos = {
    'aries':       (( 3, 21), ( 4, 20)),
    'tauro':       (( 4, 21), ( 5, 21)),
    'geminis':     (( 5, 22), ( 6, 21)),
    'cancer':      (( 6, 22), ( 7, 23)),
    'leo':         (( 7, 24), ( 8, 23)),
    'virgo':       (( 8, 24), ( 9, 23)),
    'libra':       (( 9, 24), (10, 23)),
    'escorpio':    ((10, 24), (11, 22)),
    'sagitario':   ((11, 23), (12, 21)),
    'capricornio': ((12, 22), ( 1, 20)),
    'acuario':     (( 1, 21), ( 2, 19)),
    'piscis':      (( 2, 20), ( 3, 20)),
}
```

Por ejemplo, para que una persona sea de signo libra debe haber nacido entre el 24 de septiembre y el 23 de octubre.

Solución:

```python
from datetime import date
def determinar_signo(birthday):

    signos = {
        'aries':       (( 3, 21), ( 4, 20)),
        'tauro':       (( 4, 21), ( 5, 21)),
        'geminis':     (( 5, 22), ( 6, 21)),
        'cancer':      (( 6, 22), ( 7, 23)),
        'leo':         (( 7, 24), ( 8, 23)),
        'virgo':       (( 8, 24), ( 9, 23)),
        'libra':       (( 9, 24), (10, 23)),
        'escorpio':    ((10, 24), (11, 22)),
        'sagitario':   ((11, 23), (12, 21)),
        'capricornio': ((12, 22), ( 1, 20)),
        'acuario':     (( 1, 21), ( 2, 19)),
        'piscis':      (( 2, 20), ( 3, 20)),
    }

    d, m, a = birthday
    d1 = date(a, m, d)

    for keys, values in signos.items():
        m, d = values[0]
        d2 = date(a, m, d)
        m, d = values[1]
        d3 = date(a, m, d)
        if d2 <= d1 <= d3:
            s = keys

    return s

print("Ingresa tu fecha de nacimiento")
d = int(input("Día: "))
m = int(input("Mes: "))
a = int(input("Año: "))
print("Signo zodiacal:", determinar_signo((d, m, a)).capitalize())
```

Referencia:
<ol>
<li>Signo zodiacal: http://progra.usm.cl/apunte/ejercicios/2/signo-zodiacal.html</li>
</ol>
