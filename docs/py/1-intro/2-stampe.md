---
title: Stampe
layout: default
parent: Coding in Python
nav_order: 2
---

# Stampe, facciamo parlare il programma

Uno dei primi modi per capire cosa sta facendo un programma è farlo **stampare a schermo**.

Stampare significa mostrare testo, numeri o risultati nella console.

In Python si usa la funzione `print()`.

## Come funziona `print()`

Esempio base:

```python
print("Hello world!")
```

## Stampare testo e numeri

```python
print("Ciao!")
print(42)
print(3.14)
```

## Più stampe una sotto l'altra

Ogni `print()` va automaticamente a capo:

```python
print("Prima riga")
print("Seconda riga")
print("Terza riga")
```

## Stampare più valori insieme

Possiamo passare più elementi a `print()` separandoli con una virgola:

```python
nome = "Marco"
eta = 17

print("Nome:", nome)
print("Età:", eta)
```

Python inserisce automaticamente uno spazio tra gli elementi.

## Concatenazione con `+`

Possiamo anche unire stringhe con `+`:

```python
nome = "Marco"
print("Ciao " + nome)
```

Attenzione però: con `+` stiamo unendo **stringhe**, quindi se ci sono numeri bisogna stare attenti.

```python
eta = 17
# print("Età: " + eta)   # errore
print("Età:", eta)       # corretto
```

## Le f-string

Un modo molto comodo e moderno per stampare variabili è usare le **f-string**:

```python
nome = "Marco"
eta = 17

print(f"Ciao {nome}, hai {eta} anni")
```

È un modo super leggibile e spesso è il migliore da usare.

## Commenti

Come in ogni linguaggio, possiamo scrivere commenti per spiegare il codice.

In Python, i commenti su una riga iniziano con `#`:

```python
# Questo è un commento
print("Hello world!")
```

## Ricapitoliamo

- `print()` serve per mostrare informazioni a schermo;
- ogni `print()` va a capo automaticamente;
- possiamo stampare testo, numeri e variabili;
- le **f-string** sono molto comode per inserire variabili dentro una frase;
- i commenti si scrivono con `#`.

[Prossima lezione](4-variabili_e_tipi)
