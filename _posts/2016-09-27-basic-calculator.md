---
layout: post
title: Calculadora Básica
---

### Ejemplo de calculadora

```python
import os
import time

def suma():
    os.system('clear')
    print("Suma")
    a = float(input("Introduce 1er numero: "))
    b = float(input("Introduce 2do numero: "))
    r = a + b
    print("La suma es: ", r)
    time.sleep(3)

def resta():
    os.system('clear')
    print("Resta")
    a = float(input("Introduce 1er numero: "))
    b = float(input("Introduce 2do numero: "))
    r = a - b
    print("La resta es: ", r)
    time.sleep(3)

def multiplicacion():
    os.system('clear')
    print("Multiplicacion")
    a = float(input("Introduce 1er numero: "))
    b = float(input("Introduce 2do numero: "))
    r = a * b
    print("La multiplicacion es: ", r)
    time.sleep(3)

def division():
    os.system('clear')
    print("Division")
    a = float(input("Introduce 1er numero: "))
    b = float(input("Introduce 2do numero: "))
    if b == 0:
        print("Division por cero")
    else:
        r = a / b
        print("La division es: ", r)
    time.sleep(3)

o = 0
while o != 5:
    os.system('clear')    
    print("***Calculadora***")
    print("*****************")
    print("*******Menu******")
    print("*****************")
    print("1. Suma")
    print("2. Resta")
    print("3. Multiplicacion")
    print("4. Division")
    print("5. Salir")
    o = int(input("Selecciona una opcion: "))
    if o == 1:
        suma()
    elif o == 2:
        resta()
    elif o == 3:
        multiplicacion()
    elif o == 4:
        division()
```
