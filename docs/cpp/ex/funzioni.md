---
title: Esercizi Funzioni
layout: default
nav_order: 2
parent: Esercizi in C++
---

# Esercizi - Funzioni in C++

## **Esercizio 1**

**Domanda:** Il seguente programma compila ed esegue? Qual è il valore stampato? Qual è lo scope della variabile `x` dentro e fuori dalla funzione?

```cpp
#include <iostream>
using namespace std;

void cambiaX() {
    int x = 10;
    cout << "Dentro cambiaX: " << x << endl;
}

int main() {
    int x = 5;
    cambiaX();
    cout << "Dentro main: " << x << endl;
    return 0;
}
```

## **Esercizio 2**

**Domanda:** Il seguente programma compila ed esegue? Cosa stampa in output ciascuna funzione? Qual è la differenza tra le due funzioni?

```cpp
#include <iostream>
using namespace std;

void incrementa1(int n) {
    n = n + 1;
}

void incrementa2(int& n) {
    n = n + 1;
}

int main() {
    int numero = 5;
    incrementa1(numero);
    cout << "Dopo incrementa1: " << numero << endl;

    incrementa2(numero);
    cout << "Dopo incrementa2: " << numero << endl;

    return 0;
}
```

---

## **Esercizio 3**

**Domanda:** Sulla base dell'esercizio precedente:
    1. prevedere l'output del programma, motivando la risposta
    2. eseguire il programma
    3. scrivere considerazione finale, il passaggio di un array avviene per valore o riferimento?

```cpp
#include <iostream>
using namespace std;

void modificaArray(int arr[], int size) {
    for(int i = 0; i < size; i++) {
        arr[i] = arr[i] * 2;
    }
}

int main() {
    int numeri[3] = {1, 2, 3};
    modificaArray(numeri, 3);
    for(int i = 0; i < 3; i++) {
        cout << numeri[i] << " ";
    }
    cout << endl;
    return 0;
}
```

---

## **Esercizio 4**

**Domanda:** Sulla base dell'esercizio precedente
1. prevedere l'output del programma, motivando la risposta
2. eseguire il programma
3. scrivere considerazione finale, il passaggio di un array avviene per valore o riferimento?

```cpp
#include <iostream>
using namespace std;

struct Contenitore {
    int arr[3];
};

void modificaOggetto(Contenitore c) {
    c.arr[0] = 100; // modifica su copia
}

void modificaOggettoRiferimento(Contenitore& c) {
    c.arr[0] = 200; // modifica sull'oggetto originale
}

int main() {
    Contenitore obj = {{1, 2, 3}};

    modificaOggetto(obj); //chiamata funzione su copia
    cout << "Dopo modificaOggetto: " << obj.arr[0] << endl;

    modificaOggettoRiferimento(obj); //chiamata funzione su riferimento
    cout << "Dopo modificaOggettoRiferimento: " << obj.arr[0] << endl;

    return 0;
}
```

***

## **Esercizio 5**

**Domanda:** Questo codice è scritto in maniera chiara? Migliorare la sua leggibilità creando una funzione per ogni funzionalità. 

**tip** Che cosa fa la funzione `stampaMedia`?

```cpp
#include <iostream>
using namespace std;

void stampaMedia(string nomeStudente, int voti[], int n) {
    int somma = 0;
    for(int i = 0; i < n; i++) {
        somma += voti[i];
    }
    double media = double(somma) / n;
    cout << "La media di " << nomeStudente << " è: " << media << endl;
}

int main() {
    string studente = "Mario Rossi";
    const int NUM_VOTI = 5;
    int voti[NUM_VOTI] = {7, 8, 6, 9, 10};

    stampaMedia(studente, voti, NUM_VOTI);

    return 0;
}
```

***

## **Esercizio 6**

**Domanda:** Modificare la funzione `doppio` in modo che cambi effettivamente il valore della variabile passata, senza usare il valore di ritorno.

```cpp
#include <iostream>
using namespace std;

int doppio(int n) {
    return n * 2;
}

int main() {
    int numero = 7;
    numero = doppio(numero);
    cout << numero << endl;
    return 0;
}
```

***

## **Esercizio 7**

**Domanda:** Valutare il seguente codice
    1. Prevedere l'output o eventuale errore motivando la risposta
    2. Eseguire il programma e verificare la previsione
    3. In caso di errore, modificare

```cpp
#include <iostream>
using namespace std;

void stampaStudente(string nome) {
    cout << "Studente: " << nome << endl;
}

int main() {
    string studente = "Luca Bianchi";
    
    cout << stampaStudente(studente) << endl;

    return 0;
}
```