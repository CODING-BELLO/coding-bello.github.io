---
title: Variabili e tipi in Python
layout: default
parent: Introduzione alla programmazione in Python
nav_order: 1
---
# Variabili e tipi in Python

In questo tutorial esploreremo i concetti fondamentali delle **variabili** e dei **tipi** in Python. Impareremo cosa sono le variabili, come dichiararle, i tipi di dati principali e alcune nozioni importanti per evitare errori comuni.

---

## Cos'è una variabile?

Una variabile è un contenitore che serve a memorizzare un valore durante l'esecuzione del programma. Ogni variabile ha un **nome** e un **tipo**, che definisce il tipo di dato che può contenere (ad esempio numeri interi, numeri a virgola mobile, caratteri, ecc.).

### Sintassi per dichiarare una variabile

```cpp
tipo nome_variabile;
```

Esempio:

```cpp
int eta;
double peso;
char iniziale;
bool isStudente;
```

---

## Tipi di dati base in Python

Ecco alcuni dei tipi di dati più comuni:

- `int` — numeri interi (es. 5, -10)
- `double` — numeri in virgola mobile a doppia precisione (es. 3.14, -0.001)
- `char` — un singolo carattere (es. 'a', 'Z')
- `bool` — valore booleano, `true` o `false`
- `std::string` — stringhe di testo (richiede `#include <string>`)

---

## Inizializzazione e assegnazione

È possibile assegnare un valore a una variabile al momento della dichiarazione:

```cpp
int eta = 25;
double peso = 70.5;
char iniziale = 'M';
bool isStudente = true;
```

Oppure assegnare un valore successivamente:

```cpp
int eta;
eta = 25;
```

### Nota importante: l'assegnazione è sempre da destra a sinistra

L'operazione `=` assegna il valore della parte destra alla variabile a sinistra.  
Esempio corretto:

```cpp
int a = 22;
```

Esempio **sbagliato** che causa errore:

```cpp
22 = a;  // Errore: non si può assegnare un valore a un numero letterale
```

---

## Scope di una variabile

Lo **scope** indica la parte del programma in cui la variabile è visibile e utilizzabile. Ad esempio, una variabile dichiarata all'interno di una funzione o di un blocco `{ ... }` è visibile solo in quel blocco.

```cpp
void funzione() {
    int x = 10; // x è visibile solo dentro questa funzione
    {
        int y = 20; // y è visibile solo dentro questo blocco
    }
    // y non è visibile qui
}
```

---

## Assegnazione per valore vs riferimento

In Python, quando assegniamo una variabile a un'altra, per default si copia il valore (assegnazione per valore).

```cpp
int a = 5;
int b = a;  // b ora contiene 5, indipendentemente da a
```

Se vogliamo lavorare con riferimenti (alias di variabili), si usa il simbolo `&`:

```cpp
int a = 5;
int& ref = a;  // ref è un riferimento a a
ref = 10;      // modifica anche a, che diventa 10
```

---

## Esempio completo

```cpp
#include <iostream>
#include <string>

int main() {
    int eta = 30;
    double peso = 70.5;
    char iniziale = 'F';
    bool isStudente = false;
    std::string nome = "Federico";

    std::cout << "Nome: " << nome << std::endl;
    std::cout << "Età: " << eta << std::endl;
    std::cout << "Peso: " << peso << std::endl;
    std::cout << "Iniziale: " << iniziale << std::endl;
    std::cout << "Studente: " << (isStudente ? "Sì" : "No") << std::endl;

    return 0;
}
```

---

## Errori comuni

- Tentare di assegnare un valore a un letterale:

    ```cpp
    10 = a;  // Errore
    ```

- Usare variabili non inizializzate:

    ```cpp
    int x;
    std::cout << x;  // Valore indefinito, comportamento imprevedibile
    ```

- Confondere il tipo di dato e assegnare valori incompatibili:

    ```cpp
    char c = "abc";  // Errore: char può contenere un solo carattere
    ```

---

Conoscere bene le variabili e i tipi è fondamentale per scrivere programmi Python corretti e efficienti. Buon coding!