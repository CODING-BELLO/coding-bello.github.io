---
title: Tuple
layout: default
nav_order: 53
parent: Strutture dati
---

## Tuple

Le tuple sono simili alle liste, ma **immutabili**.

```python
coordinate = (4, 7)
print(coordinate[0])
```

Sono utili quando i dati non devono cambiare.

## Ricapitoliamo

- le **tuple** sono ordinate ma non modificabili;
- ...

[Prossima lezione](11-leggibilita)

---
title: Tuple
layout: default
nav_order: 53
parent: Strutture dati
---

# Tuple

Una **tupla** serve a raccogliere più valori in un'unica struttura.

Da questo punto di vista è simile a una lista, perché anche una tupla contiene più elementi in un certo ordine.

La differenza principale è che una tupla, una volta creata, **non viene modificata**.

Le tuple sono utili quando più valori appartengono allo stesso gruppo e hanno senso insieme.

Ad esempio:

- le coordinate di un punto
- una data, formata da giorno, mese e anno
- i dati essenziali di un contatto

```python
coordinate = (4, 7)
print(coordinate)
```

In questo esempio la tupla contiene due valori che rappresentano le coordinate di un punto.

---

## Accesso agli elementi

Anche nelle tuple gli elementi hanno una posizione, chiamata **indice**.

Il primo elemento si trova in posizione `0`, il secondo in posizione `1`, e così via.

```python
print(coordinate[0])
print(coordinate[1])
```

---

## Perché usare una tupla

Una tupla è utile quando i valori formano un gruppo stabile.

Per esempio, le coordinate di un punto rappresentano un'unica informazione: non sono semplicemente una lista generica di numeri, ma due valori collegati tra loro.

La tupla è quindi adatta quando si vuole rappresentare un piccolo insieme di dati che stanno insieme.

---

## Ricapitoliamo

- una **tupla** permette di raccogliere più valori in un'unica struttura
- gli elementi della tupla hanno una posizione
- il primo elemento ha indice `0`
- una tupla è ordinata
- una tupla, una volta creata, non viene modificata
