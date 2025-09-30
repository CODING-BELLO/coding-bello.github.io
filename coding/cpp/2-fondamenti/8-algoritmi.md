---
title: Primi algoritmi in C
layout: default
nav_order: 5
parent: Fondamenti di programmazione in C++
---

# Introduzione ai primi algoritmi in C

Un **algoritmo** è un insieme di istruzioni ordinate e finite che risolvono un problema specifico. Possiamo immaginare un algoritmo come un **pattern risolutivo**, cioè una strategia generale che può essere applicata a diversi casi simili. 

---

## Primo esempio: trovare un numero in un array

Supponiamo di avere una lista di numeri (un array) e vogliamo verificare se un certo numero è presente. Questo è un problema comune e semplice, che si può risolvere con un ciclo `for`.

Ecco un esempio di codice in C++:

```cpp
#include <iostream>
using namespace std;

int main() {
    int arr[] = {3, 7, 1, 9, 5};
    int n = 5;          // dimensione dell'array
    int target = 9;     // numero da cercare
    bool found = false; // variabile per indicare se il numero è stato trovato

    for (int i = 0; i < n; i++) {
        if (arr[i] == target) {
            found = true;
            break; // usciamo dal ciclo appena troviamo il numero
        }
    }

    if (found) {
        cout << "Numero " << target << " trovato nell'array." << endl;
    } else {
        cout << "Numero " << target << " non trovato." << endl;
    }

    return 0;
}
```

---

### Come funziona passo passo

1. **Inizializzazione:** la variabile `found` è impostata a `false` perché inizialmente non abbiamo trovato il numero.

2. **Scansione:** il ciclo `for` scorre tutti gli elementi dell'array da `i = 0` a `i = n-1`.

3. **Controllo:** a ogni iterazione, confrontiamo l'elemento `arr[i]` con il numero `target`.

4. **Aggiornamento:** se troviamo una corrispondenza, impostiamo `found` a `true` e usciamo dal ciclo con `break`.

5. **Risultato:** dopo il ciclo, controlliamo il valore di `found` per stampare il messaggio corretto.

---

### Attenzione
**Indice vs valore:** non confondere `i` (l'indice, cioè la posizione) con il valore `arr[i]` che si trova in quella posizione.

**Inizializzazione:** dimenticare di inizializzare `found` può portare a risultati imprevedibili.

**Uscita dal ciclo:** senza `break`, il ciclo continua anche dopo aver trovato il numero, sprecando tempo.

---

## Pattern più generali di algoritmi

Il nostro esempio è un caso di **scansione lineare**, ovvero visitare ogni elemento di una struttura dati uno per uno. Questo è un pattern base che si ritrova in molti algoritmi.

Altri pattern importanti sono:

- **Ordinamento:** organizzare gli elementi in un certo ordine (es. crescente). Ci sono vari metodi, come il bubble sort, la selezione e l'inserzione.
- **Ricerca binaria:** un metodo efficiente per trovare un elemento in una lista ordinata, dividendo ripetutamente l'insieme in metà.

Questi pattern rappresentano più una **logica di pensiero** che una semplice sintassi: capire come ragionare sul problema è fondamentale prima di scrivere il codice.

---

## Algoritmi notevoli da conoscere

Ecco una lista di algoritmi fondamentali che incontrerai spesso:

- **Bubble sort:** ordinamento scambiando elementi adiacenti
- **Selezione:** ordinamento scegliendo il minimo ad ogni passo
- **Inserzione:** ordinamento inserendo elementi nella posizione corretta
- **Ricerca lineare:** scansione sequenziale per trovare un elemento
- **Ricerca binaria:** ricerca efficiente in array ordinati

---

## Esempio semplice di bubble sort in C++

```cpp
#include <iostream>
using namespace std;

int main() {
    int arr[] = {5, 2, 8, 1, 3};
    int n = 5;

    for (int i = 0; i < n - 1; i++) {
        for (int j = 0; j < n - 1 - i; j++) {
            if (arr[j] > arr[j + 1]) {
                int temp = arr[j];
                arr[j] = arr[j + 1];
                arr[j + 1] = temp;
            }
        }
    }

    cout << "Array ordinato: ";
    for (int i = 0; i < n; i++) {
        cout << arr[i] << " ";
    }
    cout << endl;

    return 0;
}
```

---

In questa lezione abbiamo introdotto il concetto di algoritmo e alcuni esempi base per capire come funziona il flusso di esecuzione. Ricorda che la chiave è comprendere la logica dietro le istruzioni, non solo saper scrivere il codice.