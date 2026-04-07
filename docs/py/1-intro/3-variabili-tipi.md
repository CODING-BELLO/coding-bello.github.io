---
title: Variabili e tipi
layout: default
parent: Python
nav_order: 3
---

# Variabili e tipi in Python

Le **variabili** sono nomi a cui associamo un valore.

Servono per memorizzare informazioni che il programma può usare, modificare e stampare.

## Cos'è una variabile

```python
eta = 17
nome = "Anna"
```

Qui:
- `eta` è una variabile che contiene `17`
- `nome` è una variabile che contiene `"Anna"`

> Si può immaginare una variabile come una **scatola** con un'etichetta, all'interno della quale viene memorizzato un valore.  
> Il programma può utilizzare o modificare questo valore facendo riferimento al nome riportato sull'etichetta.

## Assegnazione

L'operatore `=` assegna alla variabile il valore che si trova a destra.

```python
x = 10
y = x
```

Dopo queste istruzioni:
- `x` vale `10`
- `y` vale `10`
## Tipi di dato di base

In Python ogni valore appartiene a un **tipo di dato**.

I tipi fondamentali che verranno usati più spesso sono:

- `int` → numeri interi
- `float` → numeri decimali
- `str` → testo
- `bool` → valori logici: `True` oppure `False`

Esempi:

```python
eta = 17
altezza = 1.78
nome = "Luca"
is_studente = True
```

## Python è un linguaggio tipizzato dinamicamente

Python distingue i diversi tipi di dato, quindi è un linguaggio **tipizzato**.

Tuttavia, non è necessario dichiarare prima il tipo di una variabile:  
il tipo viene determinato automaticamente in base al valore assegnato durante l'esecuzione del programma.

Ad esempio:

```python
eta = 17
nome = "Luca"
```

Nel primo caso Python riconosce che `17` è un valore di tipo `int`, mentre nel secondo caso riconosce che `"Luca"` è un valore di tipo `str`.

È possibile verificare il tipo di un valore usando la funzione `type()`:

```python
eta = 17
print(type(eta))

nome = "Luca"
print(type(nome))
```

> In Python il tipo viene riconosciuto automaticamente in base al valore assegnato.

## Riassegnazione

Una variabile può cambiare valore nel tempo:

```python
x = 5
print(x)

x = 9
print(x)
```

## Conversione di tipo

A volte serve convertire un valore da un tipo a un altro.

```python
numero_testo = "25"
numero = int(numero_testo)

print(numero)
print(type(numero))
```

Alcune conversioni comuni:
- `int()`
- `float()`
- `str()`
- `bool()`

## Errori comuni

### 1. Confondere numero e testo

```python
x = "5"
y = 2

# print(x + y)   # errore
print(int(x) + y)
```

### 2. Usare nomi poco chiari

```python
a = 17
b = 3
```

Meglio così:

```python
eta = 17
numero_tentativi = 3
```

### 3. Pensare che il nome imponga il tipo

```python
numero = "ciao"
```

Questo è perfettamente legale.  
Conta il **valore assegnato**, non il nome scelto.

## Ricapitoliamo

- una variabile è un nome associato a un valore;
- in Python non si dichiara il tipo prima;
- i tipi base sono `int`, `float`, `str`, `bool`;
- `type()` permette di vedere il tipo di un valore;
- si possono fare conversioni esplicite con funzioni come `int()` e `str()`.

[Prossima lezione](4_input)