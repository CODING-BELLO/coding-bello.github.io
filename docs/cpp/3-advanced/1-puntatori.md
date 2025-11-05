---
title: Puntatori
layout: default
nav_order: 31
parent: Coding in C++
---

# Puntatori in C++

I puntatori sono una dei costrutti fondamentali del linguaggio C++ e permettono di lavorare direttamente con gli indirizzi di memoria. Comprendere i puntatori è essenziale per gestire la memoria, ottimizzare il codice e comprendere concetti avanzati come il passaggio per riferimento.

## Motivazioni

In C++, la gestione della memoria è manuale e diretta, a differenza di linguaggi più "alti" che si occupano automaticamente di allocare e liberare la memoria. Questo significa che il programmatore ha il controllo completo su come e dove i dati vengono memorizzati. I puntatori sono lo strumento che permette di manipolare gli indirizzi di memoria in modo preciso e flessibile. Grazie ai puntatori, è possibile creare strutture dati dinamiche, passare grandi quantità di dati alle funzioni senza copiarli, solamente passando l'indirizzo di memoria giusto. Questo si rivela molto utile soprattutto nel caso in cui ci troviamo a programmare ambienti dove le risorse sono scarse, come un microcontrollore con memoria limitata


## Cos'è un puntatore?

Un puntatore è una variabile che contiene l'indirizzo di memoria di un'altra variabile. In altre parole, invece di contenere un valore diretto, il puntatore "punta" a un indirizzo dove è memorizzato un valore.

### Sintassi base

```cpp
int x = 10;
int* p = &x;  // p è un puntatore a un intero, che contiene l'indirizzo di x
```

- `int* p` dichiara `p` come puntatore a un intero.
- `&x` restituisce l'indirizzo di `x`.
- `p` ora contiene l'indirizzo di `x`.

### Esempio visuale

![Rappresentazione visuale di un puntatore a un intero](1-puntatori.png)

### Usare il valore puntato

Per accedere o modificare il valore a cui punta un puntatore, si usa l'operatore di dereferenziazione `*`:

```cpp
std::cout << *p << std::endl;  // Stampa 10
*p = 20;                       // Cambia il valore di x a 20
std::cout << x << std::endl;   // Stampa 20
```

## Accesso ai membri di una struct tramite puntatore

Quando si ha un puntatore a una struct, per accedere ai membri della struct si usa l'operatore `->`. Questo operatore è una scorciatoia per dereferenziare il puntatore e accedere al membro in un solo passaggio.

Ad esempio, supponiamo di avere una struct semplice:

```cpp
struct Punto {
    int x;
    int y;
};

int main() {
    Punto p = {10, 20};
    Punto* ptr = &p;

    // Accesso ai membri tramite puntatore usando l'operatore ->
    std::cout << "x: " << ptr->x << ", y: " << ptr->y << std::endl;

    // Modifica dei membri tramite puntatore
    ptr->x = 30;
    ptr->y = 40;

    std::cout << "x: " << p.x << ", y: " << p.y << std::endl;

    return 0;
}
```

Output:
```
x: 10, y: 20
x: 30, y: 40
```

In questo esempio, `ptr->x` è equivalente a `(*ptr).x`, ma è più comodo e leggibile. Usare `->` è quindi il modo standard per lavorare con puntatori a struct o classi quando si vuole accedere ai loro membri.

---

## Aritmetica dei puntatori

L'aritmetica dei puntatori permette di eseguire operazioni matematiche sugli indirizzi memorizzati nei puntatori. Questo è particolarmente utile per scorrere gli elementi di un array, poiché i puntatori possono essere incrementati o decrementati per spostarsi da un elemento all'altro.

### Come funziona

Se `p` è un puntatore a un tipo di dato, ad esempio `int* p`, allora:

- `p + 1` punta all'elemento successivo dell'array (non semplicemente all'indirizzo successivo, ma all'indirizzo corretto considerando la dimensione del tipo `int`).
- `p - 1` punta all'elemento precedente.
- Si possono usare anche operatori come `++p` o `p++` per spostarsi avanti di un elemento.

Questo funziona perché le celle di memoria di un array sono adiacenti: gli elementi sono memorizzati uno dopo l'altro in memoria. Quindi, incrementando un puntatore, si passa automaticamente all'indirizzo della cella successiva, rispettando la dimensione del tipo di dato puntato.

### Esempio: scorrere un array con i puntatori

```cpp
#include <iostream>

int main() {
    int arr[] = {10, 20, 30, 40, 50};
    int* p = arr;  // p punta al primo elemento dell'array

    for (int i = 0; i < 5; ++i) {
        std::cout << *p << " ";  // Stampa il valore puntato
        p++;                     // Sposta il puntatore all'elemento successivo
    }
    std::cout << std::endl;

    return 0;
}
```

Output:
```
10 20 30 40 50 
```


### Il legame tra array e funzioni: passaggio come puntatore

In C e C++, quando si passa un array a una funzione, in realtà viene passato un puntatore al primo elemento dell'array. Questo perché il nome dell'array, usato come argomento, si "decade" automaticamente in un puntatore al suo primo elemento. 

Inoltre, passare un array come `int arr[]` a una funzione è del tutto equivalente a passare `int* arr`. Entrambe le dichiarazioni indicano che la funzione riceve un puntatore al primo elemento dell'array, e non una copia dell'intero array.

La funzione quindi, non riceve una copia dell'array, ma semplicemente l'indirizzo del suo primo elemento. Di conseguenza, scorrere e modificare un array all'interno di una funzione tramite puntatori è un'operazione naturale ed essenziale.

Ecco due esempi di funzioni che modificano un elemento di un array originale in due modi diversi: usando l'operatore di indice `arr[i]` e usando la dereferenziazione del puntatore `*(arr + i)`.

```cpp
#include <iostream>

// Modifica usando sintassi int arr[]
// Questa funzione prende un array come parametro usando la sintassi tradizionale int arr[]
// e modifica l'elemento all'indice specificato.
void modificaClassica(int arr[], int indice, int nuovoValore) {
    arr[indice] = nuovoValore; // Modifica l'elemento all'indice specificato
}

// Modifica usando l'operatore di indice arr[i]
// Questa funzione prende un puntatore a int e usa la sintassi arr[i] per modificare l'elemento.
void modificaConIndice(int* arr, int indice, int nuovoValore) {
    arr[indice] = nuovoValore; // Modifica l'elemento all'indice specificato
}

// Modifica usando la dereferenziazione del puntatore *(arr + i)
// Questa funzione prende un puntatore a int e usa la dereferenziazione per modificare l'elemento.
void modificaConPuntatore(int* arr, int indice, int nuovoValore) {
    *(arr + indice) = nuovoValore; // Modifica l'elemento all'indice specificato
}

int main() {
    int numeri[] = {1, 2, 3, 4, 5};

    modificaClassica(numeri, 1, 66);    // Modifica il secondo elemento (indice 1)
    modificaConIndice(numeri, 2, 99);    // Modifica il terzo elemento (indice 2)
    modificaConPuntatore(numeri, 4, 77); // Modifica il quinto elemento (indice 4)

    for (int i = 0; i < 5; ++i) {
        std::cout << numeri[i] << " ";
    }
    std::cout << std::endl;

    return 0;
}
```

Output:
```
1 66 99 4 77 
```


Come si vede dall'esempio, entrambe le funzioni modificano direttamente il contenuto dell'array originale, dimostrando che passare un array a una funzione equivale a passare un puntatore al suo primo elemento.

---

## Passaggio per valore, riferimento e puntatore

Quando si passa un argomento a una funzione, si può farlo in tre modi principali:

### Passaggio per valore

La funzione riceve una copia del valore, quindi modifiche all'interno della funzione non influenzano la variabile originale.

```cpp
void incrementa(int n) {
    n = n + 1;
}

int main() {
    int x = 5;
    incrementa(x);
    std::cout << x << std::endl; // Stampa 5, non cambia
}
```

### Passaggio per riferimento

Si passa una "alias" della variabile originale, quindi le modifiche dentro la funzione si riflettono fuori.

```cpp
void incrementa(int& n) {
    n = n + 1;
}

int main() {
    int x = 5;
    incrementa(x);
    std::cout << x << std::endl; // Stampa 6
}
```

### Passaggio per puntatore

Si passa l'indirizzo della variabile. La funzione può modificare il valore puntato.

```cpp
void incrementa(int* n) {
    if (n != nullptr) {
        *n = *n + 1;
    }
}

int main() {
    int x = 5;
    incrementa(&x);
    std::cout << x << std::endl; // Stampa 6
}
```

---

## Puntatori e nullptr

In C++ moderno (C++11+), è buona pratica inizializzare i puntatori a `nullptr` quando non puntano a nulla, per evitare comportamenti indefiniti.

```cpp
int* p = nullptr;  // Puntatore che non punta a nulla
if (p) {
    // Questo blocco non verrà eseguito perché p è nullptr
}
```

### Controllare sempre i puntatori

Prima di dereferenziare un puntatore, è importante controllare che non sia `nullptr`:

```cpp
if (p != nullptr) {
    std::cout << *p << std::endl;
}
```

---

## Dangling pointer (puntatori pendenti)

Un dangling pointer è un puntatore che punta a una zona di memoria non più valida, ad esempio perché l'oggetto a cui puntava è stato deallocato o è uscito dallo scope.

```cpp
int* creaPuntatore() {
    int x = 10;
    return &x;  // ERRORE: x esce dallo scope, puntatore pendente
}

int main() {
    int* p = creaPuntatore();
    // p punta ad una variabile non più valida
    std::cout << *p << std::endl; // Comportamento indefinito
}
```

---

## Riassunto e best practice

- Usare sempre `nullptr` per inizializzare puntatori non assegnati.
- Controllare i puntatori prima di usarli.
- Evita dangling pointer non mantenendo riferimenti a variabili locali fuori dallo scope (non dichiarate nel main o globalmente).
- I puntatori possono essere usati per lavorare con array, considerando la struttura a indirizzi adiacenti degli array.

---

## Prossima lezione

[2 - Oggetti](2-oggetti)