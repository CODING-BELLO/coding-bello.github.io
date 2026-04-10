---
title: Turtle
layout: default
nav_order: 5
has_toc: false
has_children: true
---

# Primi passi con Python e Turtle

`Turtle` è un modulo di Python che permette di disegnare dando comandi a una "tartaruga" virtuale.

La tartaruga:

- ha una posizione
- ha una direzione verso cui guarda
- può avanzare
- può ruotare
- può disegnare mentre si muove

Per programmare in Python e Turtle, utilizzeremo [Trinket](https://trinket.io/turtle)

---

## Comandi base di Python base

| Comando | A cosa serve | Esempio |
|---|---|---|
| `print()` | Mostra un messaggio | `print("Ciao")` |
| `input()` | Chiede un valore all'utente | `nome = input("Come ti chiami? ")` |
| `int()` | Converte un testo in numero intero | `eta = int(input("Età: "))` |
| `str()` | Converte in testo | `str(15)` |
| `for` | Ripete un blocco di istruzioni | `for i in range(4):` |
| `range()` | Genera una sequenza di numeri | `range(4)` |
| `if` | Esegue istruzioni solo se una condizione è vera | `if eta >= 18:` |

## Comandi base di Turtle

| Comando | A cosa serve | Esempio |
|---|---|---|
| `import turtle` | Importa il modulo | `import turtle` |
| `turtle.Turtle()` | Crea la tartaruga | `t = turtle.Turtle()` |
| `forward()` | Va avanti | `t.forward(100)` |
| `backward()` | Va indietro | `t.backward(50)` |
| `left()` | Ruota a sinistra | `t.left(90)` |
| `right()` | Ruota a destra | `t.right(90)` |
| `penup()` | Alza la penna | `t.penup()` |
| `pendown()` | Abbassa la penna | `t.pendown()` |
| `goto()` | Va in un punto preciso | `t.goto(100, 50)` |
| `circle()` | Disegna un cerchio | `t.circle(40)` |
| `color()` | Cambia colore | `t.color("red")` |
| `pensize()` | Cambia spessore della linea | `t.pensize(3)` |
| `speed()` | Cambia velocità | `t.speed(5)` |
| `hideturtle()` | Nasconde la tartaruga | `t.hideturtle()` |
| `turtle.done()` | Mantiene aperta la finestra | `turtle.done()` |

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


# Esercizio 1
Disegnare un triangolo.

Concetto utile: con `forward()` la tartaruga avanza, con `left()` ruota.


# Esercizio 2
Disegnare un quadrato.


# Esercizio 3 - Miglioriamo il codice
Considerando il codice dell'esercizio 2, sono sicuramente state scritte delle ripetizioni. Per quattro volte infatti, diamo operazioni di `forward()` e `left()`

In Python esiste un modo più comodo per farlo: si usa il `for`

Il `for` serve a **ripetere automaticamente** un blocco di istruzioni più volte.

Esempio di utilizzo:

```python
for i in range(4):
    # qui le istruzioni che voglio ripetere
```

# Esercizio 4 - Poligoni regolari

Un poligono regolare ha tutti i lati uguali e tutti gli angoli uguali.

Per disegnarlo, si può calcolare l’angolo di rotazione con la formula:

`angolo = 360 / numero_lati`

Partendo dal codice dell’esercizio 3, è possibile creare un pentagono o un esagono con una minima variazione del codice?

# Esercizio 5 - Interazione con l'utente

Fino a questo momento, i valori usati nel programma sono stati scritti direttamente nel codice. L'obbiettivo di questo esercizio è chiedere a noi che usiamo l'applicazione dei valori.

Con la funzione `input()` è possibile far scegliere i valori all'utente mentre il programma viene eseguito.

In questo esercizio, l'utente deve poter scegliere:
- il numero di lati del poligono
- la lunghezza dei lati

In Python, `input()` legge un valore inserito da tastiera.

Per esempio:

```python
colore = input("Con che colore disegno il poligono? ")
numero_lati = int(input("Quanti lati ha il poligono?"))
```
Il valore letto con input() è testo.
Se serve un numero, bisogna trasformarlo con int().



# Esercizio 6 - Composizione libera

Disegnare un insieme di figure, ad esempio 4 quadrati uno di fianco all’altro, oppure inventare una composizione personale.

Per spostare la tartaruga in un nuovo punto senza disegnare una linea, si possono usare `penup()` e `pendown()`.