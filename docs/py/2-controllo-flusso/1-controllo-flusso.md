---
title: Controllo di flusso
layout: default
nav_order: 21
parent: Python
---

# Controllo di flusso

Finora sono state presentate istruzioni eseguite una dopo l'altra, in sequenza.  
Un programma, però, deve anche saper **prendere decisioni**.

Come persone ci capita continuamente di scegliere tra alternative:
- se piove, si prende l'ombrello, altrimenti si esce senza;
- se il semaforo è verde, si passa, altrimenti ci si ferma;
- se una password è corretta, si entra nel sistema, altrimenti l'accesso viene negato.

Nella programmazione, la possibilità di scegliere quale istruzione eseguire in base a una condizione prende il nome di **controllo di flusso**.

## `if`

La struttura più importante è `if`.

Dopo `if` deve essere presente una condizione che produce un valore booleano, cioè `True` oppure `False`.

Python valuta la condizione:
- se il risultato è `True`, esegue il blocco di codice interno a `if`;
- se il risultato è `False`, quel blocco non viene eseguito.

Esempio semplice:
```python
eta = 20

if eta >= 18:
    print("Sei maggiorenne")
```
In questo caso, la variabile "eta" contiene il valore di 20. Il valore è ovviamente maggiore di 18, quindi viene stampata la stringa "Sei maggiorenne".


## `else`
La struttura `else` viene usata insieme a `if` per indicare che cosa deve accadere quando la condizione di `if` risulta falsa.

Python valuta prima la condizione scritta dopo `if`:
- se la condizione è vera, esegue il blocco di `if`;
- se la condizione è falsa, esegue il blocco di `else`.

In questo modo il programma può scegliere tra due comportamenti alternativi.

Esempio:

```python
eta = 17

if eta >= 18:
    print("Sei maggiorenne")
else:
    print("Sei minorenne")
```

## `elif`

Quando ci sono più casi possibili usiamo `elif`.

```python
voto = 8

if voto < 6:
    print("Insufficiente")
elif voto == 6:
    print("Sufficiente")
elif voto <= 8:
    print("Buono")
else:
    print("Ottimo")
```


## Attenzione all'indentazione

Ogni blocco (dentro e fuori dall'if) si definisce con l'indentazione.
N.B. L'indentazione è definita con il tab e non con gli spazi!

```python
if x > 3:
    print("Dentro il blocco") # eseguito solo se x > 3
print("Fuori dal blocco") # eseguito sempre
```

Nel codice d'esempio, la prima print viene effettuata solo se x > 3, mentre la seconda viene sempre effettuata.

## Ricapitoliamo

- `if`, `elif`, `else` servono per scegliere;
- fare attenzione all'identazione del codice, per strutturare bene i blocchi del programma.

[Prossima lezione](6-controllo-flusso-operatori)
