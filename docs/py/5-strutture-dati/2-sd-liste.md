---
title: Liste
layout: default
nav_order: 52
parent: Strutture dati
---

# Liste

Una **lista** serve a memorizzare più valori in un'unica variabile.

È utile, ad esempio, quando si vogliono rappresentare:

- i voti di uno studente
- i nomi degli alunni di una classe
- una sequenza di numeri
- un elenco di prodotti

In Python una lista è una struttura dati **ordinata**: gli elementi hanno una posizione.

Inoltre è **modificabile**: gli elementi possono essere cambiati e se ne possono aggiungere di nuovi.

```python
numeri = [10, 20, 30, 40]
print(numeri)
```

In questo esempio la lista contiene quattro numeri.

---

## Accesso agli elementi

Ogni elemento della lista ha una posizione, chiamata **indice**.

Il primo elemento si trova in posizione `0`, il secondo in posizione `1`, e così via.

```python
print(numeri[0])
print(numeri[2])
```

---

## Modifica di un elemento

Una lista può essere modificata.

```python
numeri[1] = 99
print(numeri)
```

In questo caso il secondo elemento della lista viene sostituito con `99`.

---

## Aggiunta di un elemento

A una lista si possono aggiungere nuovi valori.

```python
numeri.append(50)
print(numeri)
```

Il metodo `append()` aggiunge un nuovo elemento in fondo alla lista.

---

## Ricapitoliamo

- una **lista** permette di memorizzare più valori in un'unica variabile
- gli elementi della lista hanno una posizione
- il primo elemento ha indice `0`
- una lista può essere modificata
- a una lista si possono aggiungere nuovi elementi

Nei prossimi esempi vedremo come leggere, scorrere e usare le liste nei programmi.