---
title: Funzioni in C++
layout: default
nav_order: 4
parent: Fondamenti di programmazione in C++
---

# Funzioni

## Cos’è una funzione

Una **funzione** è un **pezzo di codice autonomo** che esegue un compito specifico.  
Possiamo immaginarla come una “scatola nera” che:

1. Riceve **input** (i parametri)  
2. Esegue un insieme di istruzioni  
3. Restituisce un **output** (il valore di ritorno)

Questo modello mentale ci aiuta a pensare alle funzioni come **unità indipendenti**, utili a spezzare problemi complessi in parti più semplici.

---

## Parametri e valori di ritorno

- **Parametri**: dati che passiamo alla funzione perché possa lavorare su di essi.  
- **Valore di ritorno**: il risultato che la funzione restituisce quando termina.

Esempio in C++:

```cpp
#include <iostream>
using namespace std;

// Funzione che calcola la somma di due numeri
int somma(int a, int b) {
    return a + b; // restituisce il risultato
}

int main() {
    int x = 5;
    int y = 7;
    int risultato = somma(x, y);
    cout << "La somma è " << risultato << endl;
    return 0;
}
```

Qui:
- `int a, int b` sono i **parametri**  
- `return a + b;` restituisce il **valore di ritorno**  
- La funzione può essere riutilizzata con numeri diversi senza riscrivere il codice.

---

## Concetti fondamentali

### 1. Riuso

Scrivere una funzione significa poter **usare lo stesso codice più volte** senza copiarlo.  
Esempio:

```cpp
#include <iostream>
using namespace std;

int quadrato(int n) {
    return n * n;
}

int main() {
    cout << quadrato(3) << endl;
    cout << quadrato(5) << endl;
}
```

### 2. Modularità

Le funzioni ci permettono di **spezzare problemi complessi** in parti più piccole e comprensibili.  
Esempio:

- Problema: calcolare l’area di un rettangolo e di un triangolo  
- Soluzione modulare:

```cpp
float areaRettangolo(float base, float altezza) {
    return base * altezza;
}

float areaTriangolo(float base, float altezza) {
    return (base * altezza) / 2;
}
```

Ogni funzione si occupa di un **compito specifico**, più facile da leggere, testare e correggere.

---

## Misconcezioni comuni

1. **Variabili locali vs globali**  
   Le variabili dentro una funzione **non esistono fuori dalla funzione**. 
   ```cpp
   void prova() {
       int x = 10;
   }
   // x non è visibile qui
   ```

2. **Valore di ritorno obbligatorio**  
   Una funzione `int` deve sempre restituire un valore int.Altrimenti il comportamento è indefinito.

3. **Funzioni “ricordano” i valori tra chiamate**  
Le variabili locali **non mantengono il valore tra le chiamate**.  


4. **Passaggio dei parametri**  
In C i parametri vengono passati per **valore** (una copia), quindi modificare il parametro dentro la funzione **non cambia la variabile originale**. (Questo non vale per alcune strutture dati che vedremo successivamente)

```cpp
#include <iostream>
using namespace std;

void incrementa(int n) {
    n = n + 1;  // modifica solo la copia interna
}

int main() {
    int a = 5;
    incrementa(a);
    cout << a << endl;  // stampa 5, non 6
    return 0;
}
```