---
title: Tuple
layout: default
nav_order: 53
parent: Strutture dati
---

# Strutture dati di base in Python

Quando i dati diventano tanti, una singola variabile non basta più.  
Servono strutture capaci di contenere più valori.

Le più importanti in Python sono:
- **liste**
- **tuple**
- **insiemi**
- **dizionari**

## Liste

Le liste sono sequenze ordinate e modificabili.

```python
numeri = [10, 20, 30, 40]
print(numeri)
```

### Accesso tramite indice

```python
print(numeri[0])
print(numeri[2])
```

### Modifica

```python
numeri[1] = 99
print(numeri)
```

### Aggiungere elementi

```python
numeri.append(50)
print(numeri)
```

## Tuple

Le tuple sono simili alle liste, ma **immutabili**.

```python
coordinate = (4, 7)
print(coordinate[0])
```

Sono utili quando i dati non devono cambiare.

## Insiemi (`set`)

Gli insiemi:
- non mantengono l'ordine;
- non ammettono duplicati.

```python
valori = {1, 2, 2, 3, 4}
print(valori)
```

Ottimi quando ci interessa sapere quali elementi sono presenti, senza ripetizioni.

## Dizionari

I dizionari memorizzano coppie **chiave → valore**.

```python
studente = {
    "nome": "Luca",
    "eta": 17,
    "classe": "4A"
}

print(studente["nome"])
print(studente["eta"])
```

Sono molto potenti perché permettono di rappresentare dati strutturati.

## Ciclo sulle liste

```python
frutti = ["mela", "banana", "pera"]

for frutto in frutti:
    print(frutto)
```

## Lunghezza

```python
print(len(frutti))
```

## Appartenenza

```python
print("mela" in frutti)
print("kiwi" in frutti)
```

## Ricapitoliamo

- le **liste** sono ordinate e modificabili;
- le **tuple** sono ordinate ma non modificabili;
- i **set** non hanno duplicati;
- i **dizionari** associano chiavi e valori;
- queste strutture servono per modellare meglio i dati.

[Prossima lezione](11-leggibilita)
