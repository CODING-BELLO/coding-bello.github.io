---
title: Esercizi Puntatori
layout: default
nav_order: 5
parent: Esercizi in C++
nav_exclude: true
---

# Esercizi di Lettura Codice - Puntatori in C++

## **Esercizio 1**

**Domanda:** Il seguente programma compila ed esegue? Cosa stampa? Spiega la differenza tra passaggio del puntatore per valore e passaggio per riferimento.

```cpp
#include <iostream>
using namespace std;

void modificaPuntatore(int* p) {
    int val = 10;
    p = &val;  // modifica solo la copia locale del puntatore
}

void modificaPuntatoreRiferimento(int*& p) {
    int val = 20;
    p = &val;  // modifica il puntatore originale
}

int main() {
    int x = 5;
    int* ptr = &x;
    modificaPuntatore(ptr);
    cout << *ptr << endl;  // Cosa stampa qui?
    modificaPuntatoreRiferimento(ptr);
    cout << *ptr << endl;  // E qui?
    return 0;
}
```

***

## **Esercizio 2**

**Domanda:** Cosa stampa questo programma? Spiega il significato di `*` e `&` nel contesto della dichiarazione e dell'uso di puntatori.

```cpp
#include <iostream>
using namespace std;

int main() {
    int a = 7;
    int* p = &a;
    cout << "a = " << a << endl;
    cout << "*p = " << *p << endl;
    cout << "&a = " << &a << endl;
    cout << "p = " << p << endl;
    cout << "&p = " << &p << endl;
    return 0;
}
```

***

## **Esercizio 3**

**Domanda:** Il seguente codice compila? Qual è il problema? Spiega cosa succede con il puntatore `p` e la variabile locale `val`.

```cpp
#include <iostream>
using namespace std;

int* creaPuntatore() {
    int val = 100;
    return &val;
}

int main() {
    int* p = creaPuntatore();
    cout << *p << endl;  // Cosa succede qui?
    return 0;
}
```

***

## **Esercizio 4**

**Domanda:** Cosa stampa il seguente programma? Spiega la differenza tra `arr`, `&arr`, e `*arr` in relazione agli array e ai puntatori.

```cpp
#include <iostream>
using namespace std;

int main() {
    int arr[3] = {10, 20, 30};
    cout << "arr = " << arr << endl;
    cout << "&arr = " << &arr << endl;
    cout << "*arr = " << *arr << endl;
    cout << "arr[0] = " << arr[0] << endl;
    cout << "*(&arr[0]) = " << *(&arr[0]) << endl;
    return 0;
}
```

***

## **Esercizio 5**

**Domanda:** Il seguente programma compila ed esegue? Cosa stampa? Spiega il comportamento di `p = p + 1` e `*p++`.

```cpp
#include <iostream>
using namespace std;

int main() {
    int arr[3] = {1, 2, 3};
    int* p = arr;
    cout << *p << endl;    // Cosa stampa?
    p = p + 1;
    cout << *p << endl;    // Cosa stampa ora?
    cout << *p++ << endl;  // Cosa stampa? E cosa succede a p?
    cout << *p << endl;    // Cosa stampa qui?
    return 0;
}
```

***

## **Esercizio 6**

**Domanda:** Cosa succede se si dereferenzia un puntatore nullo? Il seguente codice compila? Cosa succede in fase di esecuzione?

```cpp
#include <iostream>
using namespace std;

int main() {
    int* p = nullptr;
    if (p != nullptr) {
        cout << *p << endl;
    } else {
        cout << "Puntatore nullo, non si può dereferenziare." << endl;
    }
    return 0;
}
```

***

## **Esercizio 7**

**Domanda:** Il seguente codice contiene un “trabocchetto”. Cosa stampa? Spiega il comportamento del puntatore e la modifica del valore puntato.

```cpp
#include <iostream>
using namespace std;

int main() {
    int x = 5;
    int* p = &x;
    *p++ = 10;
    cout << "x = " << x << endl;
    cout << "*p = " << *p << endl;
    return 0;
}
```

***