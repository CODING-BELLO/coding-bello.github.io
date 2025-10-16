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
**Importante:** Quando si scrive un'assegnazione come `somma = 5 + 3;`, prima viene calcolato il valore dell'espressione a destra dell'uguale (`5 + 3`). Una volta che il risultato è stato ottenuto, questo valore viene assegnato alla variabile a sinistra (`x`). Quindi, la parte destra viene sempre valutata per prima.

## Operatori di incremento e decremento

Servono per aumentare o diminuire il valore di una variabile.

- `++` : incrementa di 1 (esempio: `x++` oppure `++x`)
- `--` : decrementa di 1 (esempio: `y--` oppure `--y`)
- `+=` : aggiunge un valore (esempio: `x += 5` è come scrivere `x = x + 5`)
- `-=` : sottrae un valore (esempio: `y -= 2` è come scrivere `y = y - 2`)

Esempio:
```cpp
    int a = 1;
    
    a++;      
    std::cout << a << std::endl; // stampa 2
    
    a += 3;
    std::cout << a << std::endl; // stampa 5
```

---

## Ricapitoliamo

- Gli operatori aritmetici eseguono operazioni matematiche di base: somma, sottrazione, moltiplicazione, divisione e modulo.
- L'assegnazione valuta prima l'espressione a destra, poi assegna il valore alla variabile a sinistra.
- Gli operatori di incremento e decremento modificano il valore di una variabile di 1 (`++`, `--`) o di un valore specificato (`+=`, `-=`).
- Questi operatori sono fondamentali per aggiornare rapidamente i valori delle variabili nel codice.

[Prossima lezione](../2-fondamenti/4-controllo_flusso)