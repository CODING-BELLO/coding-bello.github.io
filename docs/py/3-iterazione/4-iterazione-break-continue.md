---
title: Break e continue
layout: default
nav_order: 33
parent: Iterazione
---

# Cicli e iterazioni

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

- `break` interrompe, `continue` salta un giro.

[Prossima lezione](9-funzioni)
