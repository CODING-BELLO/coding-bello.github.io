---
title: Operatori e espressioni
layout: default
parent: Coding in Python
nav_order: 3
---

# Operatori ed espressioni

Gli **operatori** servono a costruire espressioni, cioè combinazioni di valori, variabili e simboli che producono un risultato.

## Operatori aritmetici

In Python abbiamo gli operatori matematici principali:

```python
a = 10
b = 3

print(a + b)   # somma
print(a - b)   # sottrazione
print(a * b)   # moltiplicazione
print(a / b)   # divisione
print(a // b)  # divisione intera
print(a % b)   # resto
print(a ** b)  # potenza
```

## Differenza tra `/` e `//`

```python
print(10 / 3)   # 3.333...
print(10 // 3)  # 3
```

- `/` restituisce una divisione "vera";
- `//` restituisce solo la parte intera.

## Operatori di confronto

Servono per confrontare valori.  
Il risultato è sempre `True` oppure `False`.

```python
x = 5

print(x == 5)   # uguale
print(x != 5)   # diverso
print(x > 3)    # maggiore
print(x < 8)    # minore
print(x >= 5)   # maggiore o uguale
print(x <= 4)   # minore o uguale
```

## Attenzione: `=` non è `==`

Questa è una delle cose più importanti all'inizio.

- `=` significa **assegnazione**
- `==` significa **confronto**

```python
x = 10        # assegna 10 a x
print(x == 10)  # controlla se x vale 10
```

## Operatori logici

Servono per combinare condizioni:

```python
a = True
b = False

print(a and b)
print(a or b)
print(not a)
```

## Espressioni

Un'espressione è tutto ciò che Python può valutare per ottenere un risultato.

Esempi:

```python
2 + 3
eta >= 18
nome == "Luca"
(10 + 2) * 3
```

## Precedenza degli operatori

Python segue un ordine nelle operazioni, come in matematica.

```python
print(2 + 3 * 4)      # 14
print((2 + 3) * 4)    # 20
```

Le parentesi aiutano tantissimo a rendere il codice più chiaro.

## Ricapitoliamo

- gli operatori servono a costruire espressioni;
- quelli aritmetici fanno calcoli;
- quelli di confronto producono `True` o `False`;
- quelli logici combinano condizioni;
- `=` assegna, `==` confronta;
- le parentesi aiutano a controllare l'ordine delle operazioni.
