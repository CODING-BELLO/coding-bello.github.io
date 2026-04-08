---
title: For
layout: default
nav_order: 43
parent: Iterazione
---

# `for`

Il ciclo `for` è particolarmente utile quando si vogliono leggere o scorrere gli elementi di una struttura dati, ad esempio una lista.

Per questo motivo, ha senso affrontarlo dopo aver già visto almeno l'idea di **lista**. Se ancora non è stato il caso, non andare avanti con la lettura, per tutti gli altri, andiamo!

Il `for` permette di lavorare in modo molto naturale sugli elementi di una sequenza, uno alla volta.

Ad esempio, se si ha una lista di nomi:

```python
nomi = ["Luca", "Anna", "Marco"]

for nome in nomi:
    print(nome)
```

In questo caso il ciclo legge gli elementi della lista uno per volta.

Ad ogni ripetizione, la variabile `nome` contiene un elemento diverso della lista.

---

## `for` e `range()`

In Python il `for` viene usato spesso anche insieme a `range()`.

`range()` non crea una lista qualsiasi di numeri, ma rappresenta una sequenza di valori interi che il ciclo può scorrere uno alla volta.

Questo è utile quando non interessa leggere gli elementi di una lista, ma ripetere un blocco di istruzioni più volte.

```python
for i in range(5):
    print(i)
```

Questo ciclo stampa:

- `0`
- `1`
- `2`
- `3`
- `4`

Quindi `range(5)` rappresenta i numeri da `0` a `4`.

Il valore `5` non è compreso.

---

## `range(start, stop)`

Con due valori, `range()` permette di specificare il numero iniziale e il numero finale escluso.

```python
for i in range(1, 6):
    print(i)
```

In questo caso vengono prodotti i valori da `1` a `5`.

Anche qui il valore finale non è compreso.

---

## `range(start, stop, step)`

Con tre valori, `range()` permette anche di indicare il passo, cioè di quanto aumenta il valore a ogni iterazione.

```python
for i in range(0, 10, 2):
    print(i)
```

In questo caso vengono stampati i numeri pari da `0` a `8`.

---

## Ricapitoliamo

- il ciclo `for` è utile per scorrere gli elementi di una sequenza
- il `for` è particolarmente comodo quando si lavora con le liste
- ad ogni iterazione viene letto un elemento alla volta
- `range()` permette di generare una sequenza di numeri
- `range(stop)` parte da `0` e arriva fino a `stop - 1`
- `range(start, stop)` parte da `start` e si ferma prima di `stop`
- `range(start, stop, step)` permette anche di indicare il passo

[Prossima lezione](4-iterazione-break-continue)
