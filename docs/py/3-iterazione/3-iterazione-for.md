---
title: For
layout: default
nav_order: 33
parent: Iterazione
---

# Cicli e iterazioni

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


## Ricapitoliamo

- `if`, `elif`, `else` servono per scegliere;
- `while` ripete finché una condizione è vera;
- `for` ripete un blocco un certo numero di volte o sugli elementi di una sequenza;
- l'indentazione in Python è essenziale;
- `break` interrompe, `continue` salta un giro.

[Prossima lezione](9-funzioni)
