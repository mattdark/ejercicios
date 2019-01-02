---
layout: post
title: "Calculadora de subredes"
description:
categories:
tags:
redirect_from:
---

#### Escribe un programa que reciba como entrada la dirección de red y el número de dispositivos a conectar, y devuelva la máscara de red y el rango de direcciones IP correspondiente.

Ejemplo:

- Se desea configurar una red de computadoras con la dirección de red <b>10.0.0.0</b> y se necesitan conectar <b>50</b> dispositivos (hosts).

Para obtener el número de hosts que se pueden conectar por subred, se realiza el siguiente cálculo:

Se tiene la fórmula <b>2<sup>m</sup> - 2</b>, que debe dar como resultado un número mayor o igual al total de dispositivos que se van a conectar a la red.

##### Hosts

- 2<sup>m</sup> - 2 >= 50
- 2x2x2x2x2x2 = 64
- m = 6
- 2<sup>m</sup> - 2 = 2<sup>6</sup> - 2 = 64 - 2 = 62

<b>62 hosts / subred</b>

##### Máscara de red
Una dirección IP es un valor númerico que identifica a un dispositivo dentro de una red. La dirección IP está formada por 4 números separados por punto (<b>.</b>), cada valor corresponde a un número binario de 8 bits (octeto), dando un total de 32 bits.
Para calcular la máscara de red, al número de bits totales (32) se resta el valor de <b>m</b> obtenido en el paso anterior.

- 32 - m = 32 - 6 = 26

26 es el número de bits a 1 dentro de la máscara de red- Por lo que la máscara de red queda como sigue:

11111111 . 11111111 . 11111111 . 11000000

Cada bit a 1 corresponde a un número en decimal cuya suma es 255 por cada octeto, como puede verse en la siguiente tabla.

| --- | --- | --- | --- | --- | --- | --- | --- |
| --- | --- | --- | --- | --- | --- | --- | --- |
|  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |
| 128 | 64  | 32  | 16  |  8  |  4  |  2  |  1  |

Por lo que la máscara de red sería la siguiente:

Máscara de red -> <b>255.255.255.192</b>

##### Direcciones IP 1<sup>a</sup> subred

<b>10.0.0.1 - 10.0.0.62</b>

#### Solución

El siguiente código realiza los cálculos anteriores a partir de la dirección de red (<b>10.0.0.0</b>) y el número de hosts (<b>50</b>) a conectar, que recibe como entrada.

```python
import re
from ipaddress import IPv4Address, IPv4Network, ip_network
classA = IPv4Network(("10.0.0.0", "255.0.0.0"))
classB = IPv4Network(("172.16.0.0", "255.240.0.0"))
classC = IPv4Network(("192.168.0.0", "255.255.0.0"))

h = int(input("Hosts: "))
net_address = input("Network: ")

m = 0
n = 2
b = False
while not b:
    if (n ** m) >= h:
        b = True
    m = m + 1

nh = (2 ** m) - 2
bits = 32 - (m - 1)
msk = ('1' * bits) + ('0' * (m-1))
octect = re.findall('.{1,8}', msk)
mask = ''

for i in octect:
    mask += str(int(i, 2)) + '.'
mask = mask[:-1]

print("Netmask:", mask)

range = list()
for x in ip_network(net_address + '/' + str(bits)).hosts():
    range.append(str(x))

print("Range",range[0] + " - " + range[len(range) - 1])
```
