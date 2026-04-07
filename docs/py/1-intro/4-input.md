---
title: Input
layout: default
parent: Coding in Python
nav_order: 4
---

# Input in Python

In molti casi è utile permettere di **inserire dei dati** "da fuori al programma", ovvero valori decisi da chi esegue il programma stesso.
Per fare questo si utilizza la funzione `input()`.

## La funzione `input()`

La funzione `input()` permette di leggere un valore digitato dall'utente tramite la tastiera.
Il programma si ferma in attesa che l'utente scriva qualcosa e prema `Invio`.

Esempio:

```python
nome = input("Come ti chiami? ")
print("Ciao", nome)
```

In questo codice c'è praticamente scritto questo: inserisci all'interno della variabile "nome" il valore che leggi da tastiera (in input) e poi stampa la stringa "Ciao" e il valore inserito all'interno della variabile "nome" (che era stato preso in input da tastiera)

Scritto in maniera più ordinata:
- il programma mostra la frase `Come ti chiami?`;
- l'utente scrive un valore;
- il valore inserito viene memorizzato nella variabile `nome`.

## Attenzione al tipo: il valore restituito da `input()` è una stringa

È importante ricordare che `input()` restituisce sempre un valore di tipo `str`, cioè una stringa.
Questo accade anche quando l'utente inserisce numeri.

Esempio:

```python
numero = input("Scrivi un numero da 1 a 6")

risultato = numero + 3
print(risultato)
```

In questo caso il programma restituirà **errore**, perchè "numero" è in realtà una stringa e non un numero!

## Convertire l'input in numero

Se si vuole usare il valore inserito per fare calcoli, è necessario convertirlo nel tipo corretto.

### Conversione in intero con `int()`

```python
numero = int(input("Scrivi un numero da 1 a 6"))

risultato = numero + 3
print(risultato)
```

In questo esempio:
- `input()` legge il valore inserito dall'utente;
- `int()` converte quel valore in un numero intero;
- il programma può usare il valore per eseguire calcoli.

### Conversione in decimale con `float()`

```python
altezza = float(input("Quanto sei alto? "))
print(altezza)
```

`float()` viene usato quando il valore può contenere cifre decimali.

## Attenzione agli errori di conversione

Quando scriviamo:

```python
numero = int(input("Inserisci un numero: "))
```

stiamo dicendo che il programma si aspetta un intero, ma l'utente può comunque inserire un valore diverso (lettere, stringhe, simboli). Il programma legge il valore e restituisce errore quando prova a convertirlo in intero, e questo è...normale!

## Esempio completo

```python
nome = input("Come ti chiami? ")
eta = int(input("Quanti anni hai? "))

print(f"Ciao {nome}, l'anno prossimo avrai {eta + 1} anni")
```

## Ricapitoliamo

- `input()` permette di leggere un valore inserito dall'utente;
- il valore restituito da `input()` è sempre una stringa;
- per usare numeri è necessario convertire il valore con `int()` oppure `float()`.

---

[Prossima lezione](5-operatori_e_espresioni)