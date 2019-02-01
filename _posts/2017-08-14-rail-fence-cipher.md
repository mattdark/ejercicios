---
layout: post
title: "Cifrado Rail Fence"
description:
categories:
tags:
redirect_from:
---

#### Escribe una función que se encargue de cifrar un texto mediante el cifrado Rail Fence.

##### Cifrado Rail Fence<sup>1</sup>
El cifrado Rail Fence es una forma de cifrado por transposición que debe su nombre a la forma en que se realiza la codificación de los textos. Era usado por los antiguos griegos.

En el cifrado Rail Fence, el texto plano se escribe hacia abajo diagonalmente a través de sucesivos raíles de una valla imaginaria y luego se escribe hacia arriba también diagonalmente. Dicho proceso se repite hasta que se acaba el mensaje que se quiere cifrar. El mensaje cifrado se obtiene tomando los caracteres fila a fila. Por ejemplo, si tenemos 3 "raíles" y el mensaje 'WE ARE DISCOVERED FLEE AT ONCE', haremos lo siguiente:

```
W . . . E . . . C . . . R . . . L . . . T . . . E
. E . R . D . S . O . E . E . F . E . A . O . C .
. . A . . . I . . . V . . . D . . . E . . . N . .
```

Obteniendo este resultado:

```
WECRL TEERD SOEEF EAOCA IVDEN
```

##### Solución

```python
def railfence(text):

    text = text.replace(" ", "")
    r1 = ""
    r2 = ""
    r3 = ""
    for i in range(len(text)):
        if i == 0 or i % 4 == 0:
            r1 += text[i]
            text
        if i % 2 == 1:
            r2 += text[i]
        if i % 2 == 0 and i % 4 >= 1:
            r3 += text[i]

    text = r1 + r2 + r3
    return text

text = "WE ARE DISCOVERED FLEE AT ONCE" # Texto a cifrar
print(railfence(text))
```

#### Escribe una función que reciba el texto cifrado y devuelva el texto original

El código anterior devuelve la siguiente cadena que corresponde al cifrado de <b>"WE ARE DISCOVERED FLEE AT ONCE"</b>:

```
WECRL TEERD SOEEF EAOCA IVDEN
```

Para descifrar el texto y obtener la cadena original, el código debe determinar que caracteres forman parte de cada fila. Para ello he pensado en las siguientes formulas:

Para obtener los caracteres de la primer fila, realizamos el siguiente cálculo:

- redondeo(tamaño / 3) - 1

Donde <b>tamaño</b> es el número total de caracteres en la cadena. Por lo tanto:

- redondeo(25 / 3) - 1
- redondeo(8.3333) - 1
- 8 - 1 = 7 --> fila1

Lo cual significa que en la primera fila están los primeros 7 caracteres:

```
WECRL TE
```

Luego, para calcular los caracteres de la segunda fila, realizamos lo siguiente:

- redondeo(((tamaño - fila1) / 3) x 2)

Donde <b>fila1</b> es el número de caracteres de la primera fila. La formula anterior nos da el siguiente resultado:

- redondeo(((25 - 7) / 3) x 2)
- redondeo((18 / 3) x 2)
- redondeo(6 x 2)
- redondeo(12)
- 12 --> fila2

Es decir, en la fila dos están los próximos 12 caracteres:

```
ERD SOEEF EAOC
```

Y el resto de caracteres corresponde a la terecera fila:

```
AIVDEN
```

Ahora colocamos los caracteres de cada fila en el orden correspondiente:

```
W . . . E . . . C . . . R . . . L . . . T . . . E
. E . R . D . S . O . E . E . F . E . A . O . C .
. . A . . . I . . . V . . . D . . . E . . . N . .
```

En el código, después de obtener los caracteres de cada fila, convertimos el texto cifrado a una lista:

```python
text = list(text)
```

Para poder reemplazar cada caracter en la lista por los caracteres de cada fila, realizamos lo siguiente:

- Los caracteres de la primer fila se colocan cada 4 posiciones dentro de la lista, empezando por la posición 0

```python
c = 0
    for i in range(len(r1)):
        text[c] = r1[i]
        c += 4
```

Lo anterior modifica la lista, quedando de la siguiente manera:

```python
text = ["W","E","C","R","E","T","E","E","C","D","S","O","R","E","F","E","L","O","C","A","T","V","D","E","E"]
```

- Para la segunda fila, los caracteres se colocan cada dos posiciones, empezando en la posición 1:

```python
c = 1
    for i in range(len(r2)):
        text[c] = r2[i]
        c += 2
```

Ahora la lista queda de la siguiente manera:

```python
text = ["W","E","C","R","E","D","E","S","C","O","S","E","R","E","F","F","L","E","C","A","T","O","D","C","E"]
```

- Y finalmente se colocan los caracteres de la tercera fila cada 4 posiciones, empezando en la posición 2:

```python
c = 2
    for i in range(len(r3)):
        text[c] = r3[i]
        c += 4
```

La lista queda de la siguiente manera:

```python
text = ["W","E","A","R","E","D","I","S","C","O","V","E","R","E","D","F","L","E","E","A","T","O","N","C","E"]
```

Por último hay que unir todos los elementos de la lista para poder imprimir una sola cadena:

```python
text = "".join(text)
```

Y de esa manera logramos descifrar el texto y obtener la cadena original.

Nota: Las formulas descritas anteriormente no aparecen en algún libro o sitio web, las he obtenido después de analizar varios ejemplos.

##### Solución

```python
def decipher(text):
    l = len(text) #Número de caracteres
    c1 = round(l / 3) - 1 # Caracteres en primera fila
    c2 = round(((l - c1) / 3) * 2) # Caracteres en segunda fila
    r1 = text[0:c1]
    r2 = text[c1:c1+c2]
    r3 = text[c1+c2:l]
    text = list(text)
    c = 0
    for i in range(len(r1)):
        text[c] = r1[i]
        c += 4
    c = 1
    for i in range(len(r2)):
        text[c] = r2[i]
        c += 2
    c = 2
    for i in range(len(r3)):
        text[c] = r3[i]
        c += 4
    text = "".join(text)
    return text
    
text = "WECRLTEERDSOEEFEAOCAIVDEN"
print(decipher(text))
```

##### Referencia
<ol>
  <li>Cifrado Rail Fence: <a href="https://es.wikipedia.org/wiki/Cifrado_Rail_Fence">https://es.wikipedia.org/wiki/Cifrado_Rail_Fence</a></li>
</ol>
