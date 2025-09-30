---
title: Primi algoritmi notevoli in C
layout: default
nav_order: 5
parent: Fondamenti di programmazione in C++
---

Capire come funzionano gli algoritmi di base è fondamentale per chi inizia a programmare. Questi algoritmi non sono solo esempi di codice, ma veri e propri strumenti per sviluppare il pensiero logico e le capacità di risolvere problemi. Imparare a scriverli e comprenderli aiuta a capire come affrontare situazioni complesse, anche prima di utilizzare librerie avanzate o strumenti già pronti. In questo modo, si costruisce una solida base che rende più facile affrontare sfide più grandi nel mondo della programmazione.

Un concetto importante da conoscere è il tempo computazionale, cioè quanto tempo un algoritmo impiega per risolvere un problema in base alla dimensione dei dati. Capire il tempo computazionale ci aiuta a scegliere o sviluppare algoritmi più efficienti, che funzionano più velocemente o usano meno risorse. Questo è fondamentale quando lavoriamo con grandi quantità di dati o programmi complessi. Per questo motivo, oltre a imparare algoritmi semplici, è utile studiare versioni ottimizzate che migliorano le prestazioni e rendono il codice più efficace.

## Ricerca lineare — prima occorrenza

```cpp
#include <iostream>
using namespace std;

int main() {
    const int N = 6;
    int a[N] = {7, 2, 9, 4, 2, 9};
    int key = 9;

    int pos = -1;
    for (int i = 0; i < N; i++) {
        if (a[i] == key) { pos = i; break; }
    }

    if (pos != -1) cout << "Trovato a indice " << pos << "\n";
    else cout << "Non trovato\n";
    return 0;
}
```


***

## Ricerca lineare — tutte le occorrenze

```cpp
#include <iostream>
using namespace std;

int main() {
    const int N = 7;
    int a[N] = {3, 5, 3, 1, 3, 9, 5};
    int key = 3;
    bool found = false;

    for (int i = 0; i < N; i++) {
        if (a[i] == key) {
            cout << "Trovato a indice " << i << "\n";
            found = true;
        }
    }
    if (!found) cout << "Mai trovato\n";
    return 0;
}
```


***

## Ricerca binaria (array ordinato)

```cpp
#include <iostream>
using namespace std;

int main() {
    const int N = 7;
    int a[N] = {1, 3, 3, 4, 8, 10, 15}; // deve essere ordinato
    int key = 4;

    int sin = 0, des = N - 1;
    int pos = -1;

    while (sin <= des) {
        int mid = sin + (des - sin) / 2;
        if (a[mid] == key) { pos = mid; break; }
        else if (a[mid] < key) sin = mid + 1;
        else des = mid - 1;
    }

    if (pos != -1) cout << "Trovato a indice " << pos << "\n";
    else cout << "Non trovato\n";
    return 0;
}
```


***

## Sorting base — Bubble sort (semplicissimo, con early-exit)

```cpp
#include <iostream>
using namespace std;

int main() {
    const int N = 5;
    int a[N] = {5, 2, 8, 1, 3};

    for (int i = 0; i < N - 1; i++) {
        bool scambio = false;
        for (int j = 0; j < N - 1 - i; j++) {
            if (a[j] > a[j + 1]) {
                int t = a[j]; a[j] = a[j + 1]; a[j + 1] = t;
                scambio = true;
            }
        }
        if (!scambio) break; // già ordinato
    }

    for (int i = 0; i < N; i++) cout << a[i] << " ";
    cout << "\n";
    return 0;
}
```


***

## Sorting migliore ma ancora semplice — Insertion sort

```cpp
#include <iostream>
using namespace std;

int main() {
    const int N = 6;
    int a[N] = {9, 4, 7, 1, 2, 6};

    for (int i = 1; i < N; i++) {
        int key = a[i];
        int j = i - 1;
        while (j >= 0 && a[j] > key) {
            a[j + 1] = a[j];
            j--;
        }
        a[j + 1] = key;
    }

    for (int i = 0; i < N; i++) cout << a[i] << " ";
    cout << "\n";
    return 0;
}
```