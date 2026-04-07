---
title: Strutture dati avanzate
layout: default
nav_order: 64
parent: Coding in Python
---

# Strutture dati avanzate

Oltre alle strutture di base, Python offre strumenti più espressivi e potenti per lavorare sui dati.

## Liste annidate

Una lista può contenere altre liste.

```python
matrice = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]

print(matrice[1][2])
```

## Comprensioni di lista

Le **list comprehension** permettono di creare liste in modo compatto.

```python
quadrati = [x**2 for x in range(6)]
print(quadrati)
```

Con filtro:

```python
pari = [x for x in range(10) if x % 2 == 0]
print(pari)
```

## Dizionari più complessi

```python
studenti = {
    "Luca": {"eta": 17, "classe": "4A"},
    "Anna": {"eta": 18, "classe": "5B"}
}

print(studenti["Luca"]["classe"])
```

## Quando servono queste strutture

Servono quando i dati hanno una struttura più ricca:
- tabelle;
- griglie;
- raccolte di oggetti;
- informazioni organizzate per chiavi.

## Ricapitoliamo

- le liste annidate permettono di rappresentare matrici e tabelle;
- le list comprehension aiutano a scrivere codice più compatto;
- i dizionari possono contenere strutture complesse;
- scegliere bene la struttura dati rende il programma più chiaro ed efficace.

[Prossima lezione](13-algoritmi.md)
