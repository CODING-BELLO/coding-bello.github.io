---
title: Stampe
layout: default
parent: Coding in Python
nav_order: 2
---

# Stampe, facciamo parlare il programma

Il modo più veloce di un programma per comunicare è stampare valori.

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

Un modo molto comodo per stampare variabili è usare le **f-string**.
La lettera `f` sta per **formatted**, cioè "formattata": si tratta infatti di stringhe in cui è possibile inserire direttamente valori o variabili all'interno del testo in modo chiaro e leggibile.

Esempio:

```python
nome = "Marco"
eta = 17

print(f"Ciao {nome}, hai {eta} anni")
```

Le f-string sono spesso molto comode perché permettono di costruire frasi complete in modo semplice, leggibile e ordinato.

## Commenti

I commenti sono porzioni di testo NON considerate come parte del programma e quindi ignorate quando il programma stesso viene eseguito. Solitamente si utilizzano per spiegare parti di codice complesso, o appuntarsi velocemente parti ancora non implementate (scritte). 

In Python, i commenti su una riga iniziano con `#`:

```python
# Questo è un commento
# Possiamo scrivere quello che vogliamo ajdnfdjhsbgdjfh
# Meglio scrivere solo cose sensate :)
print("Hello world!")
```

## Ricapitoliamo

- `print()` serve per mostrare informazioni a schermo;
- ogni `print()` va a capo automaticamente;
- possiamo stampare testo, numeri e variabili;
- le **f-string** sono molto comode per inserire variabili dentro una frase;
- i commenti si scrivono con `#`.

[Prossima lezione](3-variabili_e_tipi)
