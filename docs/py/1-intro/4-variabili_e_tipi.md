---
title: Variabili e tipi in Python
layout: default
parent: Coding in Python
nav_order: 4
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

In Python non dobbiamo dichiarare prima il tipo come in C++.  
Scriviamo direttamente il nome, `=`, e il valore.

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

In Python i tipi fondamentali che useremo spesso sono:

- `int` → numeri interi
- `float` → numeri con la virgola
- `str` → testo
- `bool` → `True` o `False`

Esempi:

```python
eta = 17
altezza = 1.78
nome = "Luca"
is_studente = True
```

## Python è tipizzato, ma in modo dinamico

Python controlla comunque i tipi, ma il tipo viene associato al valore durante l'esecuzione.

Possiamo verificarlo con `type()`:

```python
eta = 17
print(type(eta))

nome = "Luca"
print(type(nome))
```

## Riassegnazione

Una variabile può cambiare valore nel tempo:

```python
x = 5
print(x)

x = 9
print(x)
```

## Operazioni con variabili

```python
a = 10
b = 3

somma = a + b
print(somma)
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

[Prossima lezione](../2-fondamenti/5-controllo_flusso)
