---
title: Funzioni in Python
layout: default
nav_order: 15
parent: Coding in Python
---

# Funzioni in Python

Le **funzioni** servono per raggruppare istruzioni che svolgono un compito preciso.

Sono utilissime perché:
- evitano ripetizioni;
- rendono il codice più ordinato;
- permettono di riutilizzare una soluzione più volte.

## Definire una funzione

In Python si usa `def`:

```python
def saluta():
    print("Ciao!")
```

La funzione viene definita, ma non eseguita subito.

Per eseguirla bisogna chiamarla:

```python
saluta()
```

## Parametri

Le funzioni possono ricevere dati in ingresso.

```python
def saluta(nome):
    print(f"Ciao {nome}!")
```

```python
saluta("Luca")
saluta("Anna")
```

## Più parametri

```python
def somma(a, b):
    print(a + b)
```

```python
somma(3, 5)
```

## `return`

Molto spesso una funzione non deve solo stampare, ma **restituire** un valore.

```python
def somma(a, b):
    return a + b

risultato = somma(3, 5)
print(risultato)
```

## Differenza tra `print` e `return`


```python
def esempio1():
    print(10)

def esempio2():
    return 10
```

- `print()` mostra un valore a schermo;
- `return` restituisce un valore al punto in cui la funzione è stata chiamata.

## Parametri e argomenti

- i **parametri** sono i nomi nella definizione della funzione;
- gli **argomenti** sono i valori passati quando la chiamiamo.

```python
def saluta(nome):   # nome = parametro
    print(nome)

saluta("Marta")     # "Marta" = argomento
```

## Esempio completo

```python
def area_rettangolo(base, altezza):
    return base * altezza

area = area_rettangolo(5, 3)
print(f"L'area vale {area}")
```

## Perché le funzioni sono importanti

Una funzione ci permette di trasformare questo:

```python
print(5 * 3)
print(7 * 2)
print(10 * 4)
```

in qualcosa di più generale:

```python
def area_rettangolo(base, altezza):
    return base * altezza

print(area_rettangolo(5, 3))
print(area_rettangolo(7, 2))
print(area_rettangolo(10, 4))
```

Questa è programmazione vera: prendere uno schema e renderlo riutilizzabile.

## Ricapitoliamo

- una funzione è un blocco di codice riutilizzabile;
- si definisce con `def`;
- può ricevere parametri;
- può restituire un valore con `return`;
- aiuta a scrivere codice più ordinato, generale e leggibile.

[Prossima lezione](10-strutture_dati-base)
