---
title: Esercizi Puntatori
layout: default
nav_order: 5
parent: Esercizi in C++
nav_exclude: true
---

# Esercizi di Lettura Codice - Puntatori in C++



## **Esercizio di comprensione**

Inserire all'interno delle stringhe di stampa ciò che stampa effettivamente il cout. Abbozzarlo prima di eseguire il codice

```cpp
#include <iostream>
using namespace std;

int main() {
    int a = 7;
    int* p = &a;
    cout << " Valore della variabile a: " << a << endl;
    cout << " Valore puntato da p: " << *p << endl;
    cout << " ... " << &a << endl;
    cout << " ... " << p << endl;
    cout << " ... " << &p << endl;

    int arr[] = {1, 34, 2, 29};
    int* parr = arr;

    cout << " ... " << *parr << endl;
    cout << " ... " << parr << endl;
    cout << " ... " << &arr[0] << endl;
    cout << " ... " << &arr << endl;
    cout << " ... " << *(parr + 1) << endl;

    return 0;
}
```

***

## **Esercizi di scrittura e applicazione con i puntatori**


**Esercizio 2 – Somma degli elementi di un array**  
Scrivere una funzione che calcoli la somma di tutti gli elementi di un array l’aritmetica dei puntatori (`*p`, `p++`, ecc.).

```cpp
int sommaArray(int* arr, int dim);
```

---

**Esercizio 3 - Struct e puntatori**

Il seguente codice definisce una struttura ContoBancario che rappresenta un conto corrente.
Nel main() viene istanziato un conto specifico e creato un puntatore a esso.

Si vuole scrivere una funzione preleva() esterna al main, che riceva come parametro un puntatore a ContoBancario e un importo da prelevare, e modifichi il saldo del conto decrementandolo solo se il saldo è sufficiente.

Se l’importo da prelevare è maggiore del saldo disponibile, la funzione deve:
- stampare un messaggio di errore: "Saldo insufficiente"
- non modificare il saldo

Completare il codice inserendo l’implementazione della funzione preleva() e la relativa chiamata nel main().


```cpp
#include <iostream>
using namespace std;

struct ContoBancario {
    int numeroConto;
    string intestatario;
    float saldo;
};

// Implementare funziona
void preleva(ContoBancario* conto, float importo);

int main() {
    ContoBancario c1 = {12345, "Mario Rossi", 250.50};
    ContoBancario* pc = &c1;

    cout << "Saldo iniziale di " << pc->intestatario << ": " << pc->saldo << " €" << endl;

    // TODO: chiama la funzione per prelevare una certa somma
    // preleva(...);

    cout << "Saldo dopo il prelievo: " << pc->saldo << " €" << endl;

    return 0;
}

```


**Esercizio 4 – Scambio di due variabili**  
Scrivere una funzione che scambi due variabili usando solo puntatori.

```cpp
void scambia(int* a, int* b);
```



**Esercizio 5 – Allocazione dinamica con new**

Scrivere un programma che:
1. Chieda all'utente di inserire la dimensione di un array di interi.  
2. Allochi dinamicamente un puntatore ad array.
3. Permetta all'utente di inserire i valori dell'array.

```cpp
#include <iostream>
using namespace std;

int main() {
    int n;
    cout << "Quanti numeri vuoi inserire? ";
    cin >> n;

    // TODO: Creare un puntatore a un array di interi -> necessario capire come fare (guardare sezione Stack e Heap)

    cout << "Inserisci " << n << " numeri:" << endl;
    for (int i = 0; i < n; i++) {
        // TODO: leggi un numero da tastiera e salvalo nell’array
    }

    // TODO: liberare la memoria...
    
    return 0;
}
```