---
title: Esercizi array
layout: default
nav_order: 1
nav_exclude: true
---

# Esercizi di Lettura Codice - Array in C++

## **Esercizio 1**

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

**Domanda:** Il seguente programma compila ed esegue? Che cosa stampa?

***

## **Esercizio 2**

**Codice da analizzare:**

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

**Domanda:** Il seguente programma compila ed esegue? Che cosa stampa?


***

## **Esercizio 3: Modifica durante l'iterazione**

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

**Domanda:** Cosa stampa questo programma? Motivare brevemente la risposta
***

## **Esercizio 4**

**Codice da analizzare:**

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

**Domanda:** Cosa stampa questo programma e qual è lo scopo della variabile posizione?

***

## **Esercizio 5**

**Codice da analizzare:**

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
    
    return 0;
}
```

**Domanda:** Cosa fa questo programma?

***

## **Esercizio 6**


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

**Domanda:** Quanti voti sufficienti ed eccellenti conta questo programma?

***

## **Esercizio 7: Array multidimensionale - Accesso pericoloso**

**Codice da analizzare:**

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

**Domanda:** Cosa stampa questo programma? C'è qualche problema?

**Risposta:** La prima riga stampa 6 (elemento ). La seconda riga ha un errore: accede a matrice, ma la seconda dimensione va da 0 a 2. Questo causa un accesso fuori dai limiti con comportamento indefinito.[3][4][2]