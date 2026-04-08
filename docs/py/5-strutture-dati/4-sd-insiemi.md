---
title: Insiemi
layout: default
nav_order: 54
parent: Strutture dati
---

# Insiemi

Un **insieme** serve a raccogliere più valori in un'unica struttura.

Gli insiemi sono utili quando interessa sapere **quali valori sono presenti**, senza però considerare le ripetizioni.

Per questo motivo, in un insieme uno stesso valore compare una sola volta.

Ad esempio, un insieme può essere utile per rappresentare:

- le lettere presenti in una parola
- gli sport praticati in una classe
- i numeri già estratti in un gioco

```python
valori = {1, 2, 2, 3, 4}
print(valori)
```

In questo esempio il valore `2` è stato scritto due volte, ma nell'insieme compare una sola volta.

---

## Appartenenza

Gli insiemi sono particolarmente utili quando si vuole controllare se un valore è presente oppure no.

```python
frutti = {"mela", "pera", "banana"}

print("mela" in frutti)
print("kiwi" in frutti)
```

---

## Perché usare un insieme

Un insieme è adatto quando i duplicati non servono e conta soprattutto la presenza o l'assenza di un valore.

Per esempio, se si vogliono rappresentare le lettere presenti nella parola `banana`, non interessa salvare tutte le ripetizioni, ma sapere quali lettere compaiono.

In questo caso un insieme è più adatto di una lista.

---

## Ricapitoliamo

- un **insieme** permette di raccogliere più valori in un'unica struttura
- in un insieme i duplicati non vengono mantenuti
- un insieme è utile quando conta sapere se un valore è presente
- un insieme è adatto quando le ripetizioni non interessano
