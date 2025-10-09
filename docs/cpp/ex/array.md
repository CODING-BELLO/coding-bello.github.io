---
title: Esercizi array
layout: default
nav_order: 1
parent: Esercizi in C++
---

# Esercizi di Lettura Codice - Array in C++

## **Esercizio 1**

**Domanda:** Il seguente programma compila ed esegue? Che cosa stampa?

```cpp
#include <iostream>
using namespace std;

int main() {
    int numeri[5] = {10, 20, 30, 40, 50};
    
    for(int i = 0; i < 5; i++) {
        cout << numeri[i++] << " ";
    }
    
    return 0;
}
```

***

## **Esercizio 2**

**Domanda:** Il seguente programma compila ed esegue? Che cosa stampa?

```cpp
#include <iostream>
using namespace std;

int main() {
    int array[6] = {1, 2, 3};
    
    for(int i = 0; i < 6; i++) {
        cout << array[i] << " ";
    }
    
    return 0;
}
```

***

## **Esercizio 3**

**Domanda:** Cosa stampa questo programma? Motivare brevemente la risposta

```cpp
#include <iostream>
using namespace std;

int main() {
    int numeri[5] = {1, 2, 3, 4, 5};
    
    for(int i = 0; i < 5; i++) {
        if(numeri[i] % 2 == 0) {
            numeri[i] = numeri[i] * 10;
        }
        cout << numeri[i] << " ";
    }
    
    return 0;
}
```

***

## **Esercizio 4**

**Domanda:** Cosa stampa questo programma e qual è lo scopo della variabile posizione?

```cpp
#include <iostream>
using namespace std;

int main() {
    int numeri[5] = {10, 25, 30, 45, 60};
    int cerca = 35;
    int posizione = -1;
    
    for(int i = 0; i < 5; i++) {
        if(numeri[i] == cerca) {
            posizione = i;
        }
    }
    
    if(posizione == -1) {
        cout << "Numero non trovato" << endl;
    } else {
        cout << "Trovato in posizione: " << posizione << endl;
    }
    
    return 0;
}
```

***

## **Esercizio 5**

**Domanda:** Cosa fa questo programma?

```cpp
#include <iostream>
using namespace std;

int main() {
    int numeri[6] = {1, 2, 3, 4, 5, 6};
    
    for(int i = 0; i < 3; i++) {
        int temp = numeri[i];
        numeri[i] = numeri[5-i];
        numeri[5-i] = temp;
    }
    
    for(int i = 0; i < 6; i++) {
        cout << numeri [i] << endl;
    }
    
    return 0;
}
```

***

## **Esercizio 6**

**Domanda:** Quanti voti sufficienti e quanti voti eccellenti conta questo programma? Che cosa stampa?

```cpp
#include <iostream>
using namespace std;

int main() {
    int voti[7] = {5, 7, 10, 6, 9, 7, 10};
    int sufficienti = 0;
    int eccellenti = 0;
    
    for(int i = 0; i < 7; i++) {
        if(voti[i] >= 6) {
            sufficienti++;
        }
        if(voti[i] >= 9) {
            eccellenti++;
        }
    }
    
    cout << "Sufficienti: " << sufficienti << endl;
    cout << "Eccellenti: " << eccellenti << endl;
    
    return 0;
}
```

***

## **Esercizio 7**

**Domanda:** Il seguente programma è corretto? Che cosa stampa?
```cpp
#include <iostream>
using namespace std;

int main() {
    int matrice[2][3] = { {1, 2, 3}, {4, 5, 6} };
    
    cout << matrice[1][2] << endl;
    cout << matrice[0][3] << endl;
    
    return 0;
}
```



***

## **Esercizio 8**

Scrivere un programma che legge un array di 10 interi dall’utente

```cpp

```

***

## **Esercizio 9**


Scrivere un programma che conta il numero di vocali presenti in un vettore
di caratteri di lunghezza 10 inseriti dall’utente.

```cpp

```

***

## **Esercizio 10**

Scrivere un programma che legge un array di 10 interi dall’utente
e ne calcola la somma.


```cpp

```

***

## **Esercizio 11**

Scrivere un programma che verifica quale tra due array di caratteri
    di lunghezza 10, inseriti dall’utente, contiene un maggior numero di vocali.

    Attenzione: non scrivere codice ridondante

```cpp

```

***

## **Esercizio 12**

Leggere in input un vettore di caratteri con al massimo 100 caratteri
e contare quante volte compare il carattere 'a'.

```cpp

```
