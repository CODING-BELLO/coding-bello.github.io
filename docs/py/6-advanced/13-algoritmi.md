---
title: Algoritmi e STL
layout: default
nav_order: 23
parent: Coding in Python
---

# Algoritmi e strumenti avanzati di Python

Nel percorso C++ questa parte richiama la STL.  
In Python non esiste una STL con lo stesso nome, ma esistono tanti strumenti già pronti e molto potenti.

## Funzioni built-in utili

Python mette a disposizione funzioni comodissime:

```python
numeri = [4, 7, 1, 9]

print(len(numeri))
print(max(numeri))
print(min(numeri))
print(sum(numeri))
print(sorted(numeri))
```

## Iterare con `enumerate`

```python
frutti = ["mela", "banana", "pera"]

for indice, frutto in enumerate(frutti):
    print(indice, frutto)
```

## Iterare in parallelo con `zip`

```python
nomi = ["Luca", "Anna", "Marco"]
voti = [7, 9, 8]

for nome, voto in zip(nomi, voti):
    print(nome, voto)
```

## Ordinamenti con chiave

```python
parole = ["albero", "sole", "programmazione", "ciao"]

ordinate = sorted(parole, key=len)
print(ordinate)
```

## Un'idea importante

Un buon programmatore non riscrive sempre tutto da zero.  
Capisce:
- quale problema ha davanti;
- quali strumenti esistono già;
- quando usare una soluzione pronta e quando costruirla da sé.

## Ricapitoliamo

- Python ha molte funzioni built-in utili;
- `sorted()`, `enumerate()` e `zip()` sono strumenti super importanti;
- conoscere gli strumenti del linguaggio permette di scrivere soluzioni migliori;
- prima si capisce la logica, poi si sfruttano gli strumenti già disponibili.
