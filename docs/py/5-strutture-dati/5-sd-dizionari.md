
---
title: Dizionari
layout: default
nav_order: 55
parent: Strutture dati
---

# Dizionari

Un **dizionario** serve a raccogliere più informazioni in un'unica struttura.

A differenza di una lista o di una tupla, in un dizionario ogni valore è associato a un nome.

Questo lo rende utile quando i dati non sono soltanto in sequenza, ma rappresentano informazioni con un significato preciso.

Ad esempio, un contatto può essere descritto da:

- nome
- telefono
- email

Oppure uno studente può essere descritto da:

- nome
- età
- classe

```python
studente = {
    "nome": "Luca",
    "eta": 17,
    "classe": "4A"
}

print(studente)
```

In questo esempio il dizionario raccoglie più informazioni sullo stesso studente.

---

## Accesso ai valori

In un dizionario i valori non vengono letti tramite posizione, ma tramite il nome a cui sono associati.

```python
print(studente["nome"])
print(studente["eta"])
```

---

## Perché usare un dizionario

Un dizionario è utile quando si vuole rappresentare una scheda o un oggetto descritto da campi diversi.

Per esempio, nel caso di uno studente, scrivere `nome`, `eta` e `classe` è molto più chiaro che usare semplicemente una sequenza di valori senza significato esplicito.

Per questo motivo i dizionari sono molto usati quando si vogliono organizzare dati eterogenei riferiti alla stessa entità.

---

## Ricapitoliamo

- un **dizionario** permette di raccogliere più informazioni in un'unica struttura
- in un dizionario ogni valore è associato a un nome
- i valori si leggono usando il nome a cui sono associati
- un dizionario è utile per rappresentare dati con campi ben distinti

[Prossima lezione](11-leggibilita)
