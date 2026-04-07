---
title: Operatori e espressioni
layout: default
parent: Coding in Python
nav_order: 5
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

Un'espressione è una parte di codice che Python può valutare per ottenere un valore.

In pratica, è qualcosa che, una volta elaborata da Python, produce un risultato.
Questo risultato può essere, ad esempio, un numero oppure un valore booleano (`True` o `False`).

Esempi:

```python
2 + 3           # produce 5
eta >= 18       # produce True oppure False
nome == "Luca"  # produce True oppure False
(10 + 2) * 3    # produce 36
```

## Precedenza degli operatori

Python segue un ordine nelle operazioni, come in matematica.

```python
print(2 + 3 * 4)      # 14
print((2 + 3) * 4)    # 20
```

## Ricapitoliamo

- gli operatori servono a costruire espressioni;
- quelli aritmetici fanno calcoli;
- quelli di confronto producono `True` o `False`;
- quelli logici combinano condizioni;
- `=` assegna, `==` confronta;
- le parentesi aiutano a controllare l'ordine delle operazioni.

[Prossima lezione](4-variabili_e_tipi)