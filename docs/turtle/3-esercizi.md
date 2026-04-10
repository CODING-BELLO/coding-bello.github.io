---
title: Esercitazione guidata
layout: default
nav_order: 3
parent: Turtle
---

## Esercizio 1
Disegnare un triangolo.

Concetto utile: con `forward()` la tartaruga avanza, con `left()` ruota.


## Esercizio 2
Disegnare un quadrato.


## Esercizio 3 - Miglioriamo il codice
Considerando il codice dell'esercizio 2, sono sicuramente state scritte delle ripetizioni. Per quattro volte infatti, diamo operazioni di `forward()` e `left()`

In Python esiste un modo più comodo per farlo: si usa il `for`

Il `for` serve a **ripetere automaticamente** un blocco di istruzioni più volte.

Esempio di utilizzo:

```python
for i in range(4):
    ## qui le istruzioni che voglio ripetere
```

## Esercizio 4 - Poligoni regolari

Un poligono regolare ha tutti i lati uguali e tutti gli angoli uguali.

Per disegnarlo, si può calcolare l’angolo di rotazione con la formula:

`angolo = 360 / numero_lati`

Partendo dal codice dell’esercizio 3, è possibile creare un pentagono o un esagono con una minima variazione del codice?

## Esercizio 5 - Interazione con l'utente

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



## Esercizio 6 - Composizione libera

Disegnare un insieme di figure, ad esempio 4 quadrati uno di fianco all’altro, oppure inventare una composizione personale.

Per spostare la tartaruga in un nuovo punto senza disegnare una linea, si possono usare `penup()` e `pendown()`.