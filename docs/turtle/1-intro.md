---
title: Introduzione
layout: default
nav_order: 1
parent: Turtle
---


# Primo esempio

```python
import turtle

t = turtle.Turtle()

t.forward(100)
t.left(90)
t.forward(100)

turtle.done()
```

Questo programma:

1. crea la tartaruga
2. la fa avanzare
3. la fa ruotare a sinistra
4. la fa avanzare di nuovo

# Le funzioni `forward()` e `backward()`

Le funzioni `forward()` e `backward()` servono per muovere la tartaruga.

- `forward(numero)` fa avanzare la tartaruga
- `backward(numero)` fa arretrare la tartaruga

Il numero indica di quanto deve muoversi.

## Esempio

```python
import turtle

t = turtle.Turtle()

t.forward(100)
t.backward(50)

turtle.done()
```

# Le funzioni `penup()` e `pendown()`

La tartaruga, quando si muove, normalmente disegna una linea.

Le funzioni `penup()` e `pendown()` servono a decidere se deve disegnare oppure no.

- `penup()` alza la penna: la tartaruga si muove senza disegnare
- `pendown()` abbassa la penna: la tartaruga torna a disegnare

## Esempio

```python
import turtle

t = turtle.Turtle()

t.forward(100)

t.penup()
t.forward(50)

t.pendown()
t.forward(100)

turtle.done()
```

In questo esempio:

- il primo tratto viene disegnato
- poi la tartaruga si sposta senza disegnare
- infine ricomincia a disegnare

# Le funzioni `right()` e `left()`

Le funzioni `right()` e `left()` servono per ruotare la tartaruga.

- `right(numero)` ruota la tartaruga verso destra
- `left(numero)` ruota la tartaruga verso sinistra

Il numero indica l'angolo di rotazione, espresso in gradi.

## Esempio

```python
import turtle

t = turtle.Turtle()

t.forward(100)
t.left(90)
t.forward(100)
t.right(90)
t.forward(50)

turtle.done()
```

In questo esempio la tartaruga:

1. va avanti
2. gira a sinistra di 90 gradi
3. va avanti
4. gira a destra di 90 gradi
5. va avanti di nuovo