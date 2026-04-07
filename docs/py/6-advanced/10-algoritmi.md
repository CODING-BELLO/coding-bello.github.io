---
title: Algoritmi notevoli
layout: default
nav_order: 62
parent: Python
---

# Algoritmi notevoli

Un **algoritmo** è una sequenza finita di passi per risolvere un problema.

La programmazione non è solo sintassi: è soprattutto progettare buone soluzioni.

## Esempio: massimo tra elementi

```python
numeri = [7, 3, 12, 5, 9]

massimo = numeri[0]

for numero in numeri:
    if numero > massimo:
        massimo = numero

print(massimo)
```

## Esempio: conta occorrenze

```python
parola = "banana"
conteggio = 0

for lettera in parola:
    if lettera == "a":
        conteggio += 1

print(conteggio)
```

## Esempio: somma degli elementi

```python
numeri = [1, 2, 3, 4, 5]
totale = 0

for numero in numeri:
    totale += numero

print(totale)
```

## Cercare un elemento

```python
numeri = [4, 8, 15, 16, 23, 42]
trovato = False

for numero in numeri:
    if numero == 15:
        trovato = True

print(trovato)
```

## Progettare prima di scrivere

Prima di codificare conviene chiedersi:
- quali sono i dati di partenza?
- qual è il risultato da ottenere?
- quali passi servono?
- c'è un caso particolare da gestire?

## Algoritmi e funzioni

Spesso un algoritmo può essere trasformato in una funzione:

```python
def massimo_lista(lista):
    massimo = lista[0]
    for elemento in lista:
        if elemento > massimo:
            massimo = elemento
    return massimo
```

## Python offre anche strumenti già pronti

Per esempio:

```python
numeri = [7, 3, 12, 5, 9]
print(max(numeri))
print(sum(numeri))
```

Però prima è importante capire **la logica** dietro questi strumenti.

## Ricapitoliamo

- un algoritmo è una sequenza ordinata di passi;
- prima si ragiona, poi si scrive il codice;
- saper costruire algoritmi significa saper risolvere problemi;
- Python offre strumenti comodi, ma capire la logica resta la cosa più importante.

[Prossima lezione](../3-advanced/11-oggetti)
