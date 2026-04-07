---
title: Controllo di flusso
layout: default
nav_order: 14
parent: Coding in Python
---

# Cicli e iterazioni

## `while`

Il ciclo `while` ripete un blocco finché una condizione rimane vera.

```python
contatore = 1

while contatore <= 5:
    print(contatore)
    contatore = contatore + 1
```

## `for`

In Python il `for` viene spesso usato con `range()`.

```python
for i in range(5):
    print(i)
```

Questo stampa:
- 0
- 1
- 2
- 3
- 4

### `range(start, stop)`

```python
for i in range(1, 6):
    print(i)
```

### `range(start, stop, step)`

```python
for i in range(0, 10, 2):
    print(i)
```

## `break` e `continue`

### `break`
Interrompe il ciclo.

```python
for i in range(10):
    if i == 5:
        break
    print(i)
```

### `continue`
Salta l'iterazione corrente.

```python
for i in range(5):
    if i == 2:
        continue
    print(i)
```

## Ricapitoliamo

- `if`, `elif`, `else` servono per scegliere;
- `while` ripete finché una condizione è vera;
- `for` ripete un blocco un certo numero di volte o sugli elementi di una sequenza;
- l'indentazione in Python è essenziale;
- `break` interrompe, `continue` salta un giro.

[Prossima lezione](9-funzioni)
