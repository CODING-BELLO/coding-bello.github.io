---
title: Break e continue
layout: default
nav_order: 44
parent: Iterazione
---

# `break` e `continue`

Le istruzioni `break` e `continue` si usano all'interno dei cicli.

Possono essere usate sia con `while` sia con `for`, ma in questa pagina vengono presentate con esempi basati sul `while`, così risultano comprensibili anche dopo aver studiato soltanto questo ciclo.

---

## `break`

L'istruzione `break` serve a **interrompere subito un ciclo**, anche se la condizione del ciclo sarebbe ancora vera.

Questo è utile quando, durante l'esecuzione del ciclo, si verifica una situazione per cui non ha più senso continuare.

Ad esempio:

```python
contatore = 1

while contatore <= 10:
    if contatore == 5:
        break
    print(contatore)
    contatore = contatore + 1
```

In questo caso il ciclo potrebbe andare avanti fino a `10`, ma quando `contatore` diventa `5` viene eseguito `break` e il ciclo termina immediatamente.

Quindi vengono stampati solo i valori:

- `1`
- `2`
- `3`
- `4`

---

## `continue`

L'istruzione `continue` serve a **saltare l'iterazione corrente** e passare subito alla successiva.

Il ciclo non termina, ma quel singolo giro viene interrotto.

Ad esempio:

```python
contatore = 0

while contatore < 5:
    contatore = contatore + 1
    if contatore == 3:
        continue
    print(contatore)
```

In questo caso, quando `contatore` vale `3`, il `print()` non viene eseguito e il ciclo passa direttamente all'iterazione successiva.

Quindi vengono stampati:

- `1`
- `2`
- `4`
- `5`

---

## Attenzione

Quando si usa `continue` in un ciclo `while`, bisogna fare attenzione all'ordine delle istruzioni.

Se la variabile che controlla la condizione non viene aggiornata nel momento giusto, si può creare un ciclo infinito.

Per questo motivo, negli esempi con `while`, l'aggiornamento della variabile viene spesso fatto prima del controllo che può portare a `continue`.

---

## Ricapitoliamo

- `break` interrompe subito il ciclo
- `continue` salta solo l'iterazione corrente
- entrambe le istruzioni possono essere usate sia con `while` sia con `for`
- con `while` bisogna fare particolare attenzione a come cambia la variabile di controllo

[Prossima lezione](../5-strutture-dati/1-sd)