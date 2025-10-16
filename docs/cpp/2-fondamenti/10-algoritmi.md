---
title: Algoritmi di ricerca e ordinamento
layout: default
nav_order: 18
parent: Coding in C++
---

# Algoritmi notevoli e costo computazionale
Capire come funzionano gli algoritmi di base è fondamentale per chi inizia a programmare. Questi algoritmi non sono solo esempi di codice, ma veri e propri strumenti per sviluppare il pensiero logico e le capacità di risolvere problemi. Imparare a scriverli e comprenderli aiuta a capire come affrontare situazioni complesse, anche prima di utilizzare librerie avanzate o strumenti già pronti. In questo modo, si costruisce una solida base che rende più facile affrontare sfide più grandi nel mondo della programmazione.

Un concetto importante da conoscere è il tempo computazionale, cioè quanto tempo un algoritmo impiega per risolvere un problema in base alla dimensione dei dati. Capire il tempo computazionale ci aiuta a scegliere o sviluppare algoritmi più efficienti, che funzionano più velocemente o usano meno risorse. Questo è fondamentale quando lavoriamo con grandi quantità di dati o programmi complessi. Per questo motivo, oltre a imparare algoritmi semplici, è utile studiare versioni ottimizzate che migliorano le prestazioni e rendono il codice più efficace.

## Ricerca lineare — tutte le occorrenze

La **ricerca lineare** è il modo più semplice per cercare un valore in un array: si controllano tutti gli elementi, uno dopo l’altro, fino a trovare ciò che serve.  
Quindi, più grande è l’array, più tempo ci vuole: se l’array ha 100 elementi, il programma può arrivare a fare anche 100 confronti.

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

### Ottimizzazione della ricerca lineare classica

Un’ottimizzazione semplice ma utile della ricerca lineare è quella di **interrompere la scansione appena viene trovata la prima occorrenza** dell’elemento cercato.  
Per farlo, si utilizza l’istruzione `break`, che **interrompe immediatamente il ciclo in corso** e fa proseguire l’esecuzione del programma dal punto successivo al ciclo stesso.

Ecco un esempio:

```cpp
#include <iostream>
using namespace std;

int main() {
    const int N = 7;
    int a[N] = {3, 5, 3, 1, 3, 9, 5};
    int key = 3;

    for (int i = 0; i < N; i++) {
        if (a[i] == key) {
            cout << "Trovato a indice " << i << "\n";
            break; // interrompe il ciclo appena trova l’elemento
        }
    }

    return 0;
}
```

In questo modo, se l’elemento cercato si trova **nelle prime posizioni dell’array**, il programma termina il ciclo subito, evitando confronti inutili e migliorando l’efficienza media.  
Nel caso peggiore (se il valore non è presente o è all’ultima posizione) il programma deve comunque controllare tutti gli elementi, ma se il valore è vicino all’inizio, la ricerca termina molto prima.

---

## Ricerca binaria — introduzione e vantaggi

La **ricerca binaria** è un algoritmo molto più efficiente, ma può essere usato **solo su array ordinati**.  
L’idea è dividere l’array a metà a ogni passo:  
- Se il valore centrale è quello cercato → trovato!  
- Se è minore → cerco nella metà destra.  
- Se è maggiore → cerco nella metà sinistra.

In questo modo il numero di elementi da controllare si dimezza a ogni passo: in pochi controlli si riesce a trovare l’elemento anche in liste molto lunghe, quindi è molto più veloce della ricerca lineare.

---

## Ricerca binaria — versione iterativa

```cpp
#include <iostream>
using namespace std;

int ricercaBinariaIterativa(int arr[], int n, int target) {
    int inizio = 0;
    int fine = n - 1;

    while (inizio <= fine) {
        int meta = (inizio + fine) / 2;
        if (arr[meta] == target)
            return meta;
        else if (arr[meta] < target)
            inizio = meta + 1;
        else
            fine = meta - 1;
    }
    return -1; // non trovato
}

int main() {
    int a[] = {1, 3, 4, 7, 9, 11, 15};
    int n = 7;
    int key = 9;

    int pos = ricercaBinariaIterativa(a, n, key);
    if (pos != -1) cout << "Trovato a indice " << pos << "\n";
    else cout << "Non trovato\n";
}
```

---

## Ricerca binaria — versione ricorsiva

La versione **ricorsiva** fa la stessa cosa, ma richiama sé stessa con un sottointervallo dell’array.

```cpp
#include <iostream>
using namespace std;

int ricercaBinariaRicorsiva(int arr[], int inizio, int fine, int target) {
    if (inizio > fine) return -1;

    int meta = (inizio + fine) / 2;

    if (arr[meta] == target)
        return meta;
    else if (arr[meta] < target)
        return ricercaBinariaRicorsiva(arr, meta + 1, fine, target);
    else
        return ricercaBinariaRicorsiva(arr, inizio, meta - 1, target);
}

int main() {
    int a[] = {1, 3, 4, 7, 9, 11, 15};
    int n = 7;
    int key = 7;

    int pos = ricercaBinariaRicorsiva(a, 0, n - 1, key);
    if (pos != -1) cout << "Trovato a indice " << pos << "\n";
    else cout << "Non trovato\n";
}
```

La differenza principale è che la versione iterativa usa un ciclo `while`, mentre quella ricorsiva chiama la funzione più volte, riducendo l’intervallo ogni volta.

[Prossima lezione](../3-advanced/1-puntatori)