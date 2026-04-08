---
title: While
layout: default
nav_order: 42
parent: Iterazione
---

# `while`

Il ciclo `while` serve a ripetere un blocco di istruzioni **finché una condizione rimane vera**.

È utile quando non interessa scorrere una lista o una sequenza di elementi, ma ripetere qualcosa controllando una condizione.

Per questo motivo il `while` viene normalmente introdotto prima del `for`.

Ad esempio, si può usare per:

- contare fino a un certo numero
- continuare a chiedere un valore finché non è corretto
- ripetere un menu finché l'utente non sceglie di uscire

```python
contatore = 1

while contatore <= 5:
    print(contatore)
    contatore = contatore + 1
```

In questo esempio il ciclo continua finché la condizione `contatore <= 5` è vera.

All'inizio `contatore` vale `1`, quindi la condizione è vera e il blocco viene eseguito.

Poi il valore di `contatore` aumenta di `1` a ogni iterazione.

Quando `contatore` diventa `6`, la condizione non è più vera e il ciclo termina.

---

## La condizione

Nel `while` la condizione viene controllata prima di ogni iterazione.

Se la condizione è vera, il blocco viene eseguito.

Se la condizione è falsa, il blocco non viene eseguito oppure il ciclo termina.

Per questo motivo è importante che, all'interno del ciclo, qualcosa cambi: altrimenti la condizione potrebbe restare sempre vera.

---

## Attenzione ai cicli infiniti

Se la condizione non diventa mai falsa, il ciclo continua senza fermarsi.

Ad esempio:

```python
contatore = 1

while contatore <= 5:
    print(contatore)
```

In questo caso `contatore` non cambia mai, quindi la condizione resta sempre vera e il ciclo non termina.

Questo tipo di situazione si chiama **ciclo infinito**.

---

## Ricapitoliamo

- il ciclo `while` ripete un blocco di istruzioni finché una condizione è vera
- la condizione viene controllata prima di ogni iterazione
- il `while` è utile quando si vuole ripetere qualcosa controllando una condizione
- all'interno del ciclo deve esserci qualcosa che può far cambiare la condizione
- se la condizione non diventa mai falsa, si crea un ciclo infinito

[Prossima lezione](3-iterazione-for)