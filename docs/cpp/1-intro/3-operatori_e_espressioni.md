---
title: Operatori ed espressioni
layout: default
nav_order: 4
parent: Coding in C++
---
# Operatori ed espressioni

## Operatori aritmetici

Gli operatori aritmetici permettono di eseguire operazioni matematiche di base tra variabili e valori numerici.

- `+`  : somma (esempio: `a + b`)
- `-`  : sottrazione (esempio: `a - b`)
- `*`  : moltiplicazione (esempio: `a * b`)
- `/`  : divisione (esempio: `a / b`)
- `%`  : resto della divisione intera (modulo, esempio: `a % b`)

Esempio:
```cpp
int somma = 5 + 3;   // somma = 8
int resto = 10 % 3;  // resto = 1
```
**Importante:** Quando si scrive un'assegnazione come `somma = 5 + 3;;`, prima viene calcolato il valore dell'espressione a destra dell'uguale (`5 + 3`). Una volta che il risultato è stato ottenuto, questo valore viene assegnato alla variabile a sinistra (`x`). Quindi, la parte destra viene sempre valutata per prima.

## Operatori di incremento e decremento

Servono per aumentare o diminuire il valore di una variabile.

- `++` : incrementa di 1 (esempio: `x++` oppure `++x`)
- `--` : decrementa di 1 (esempio: `y--` oppure `--y`)
- `+=` : aggiunge un valore (esempio: `x += 5` è come scrivere `x = x + 5`)
- `-=` : sottrae un valore (esempio: `y -= 2` è come scrivere `y = y - 2`)

Esempio:
```cpp
int a = 1;
a++;      // a vale ora 2
a += 3;   // a vale ora 5
```

---

### Concetti chiave

- **Assegnazione**: L'operatore `=` serve per assegnare un valore a una variabile. Esempio: `int x = 5;`
- **Espressione**: Una combinazione di variabili, valori e operatori che produce un risultato. Esempio: `x + 2` è un'espressione.
- **Risultato degli operatori relazionali**: Gli operatori relazionali restituiscono sempre un valore booleano (`true` o `false`), utile per le condizioni nei costrutti come `if` o `while` (le vedremo successivamente).


[Prossima lezione](../2-fondamenti/4-controllo_flusso.md)