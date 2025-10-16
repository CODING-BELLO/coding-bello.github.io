---
title: Matrici
layout: default
nav_order: 17
parent: Coding in C++
---


# Matrici: array a due dimensioni

Si vuole registrare, per una stazione meteorologica, le temperature rilevate in **più giorni** e a **più orari**.  
Se proviamo a farlo con un semplice array o vector, ci accorgiamo subito che non basta: un array può memorizzare una sequenza di valori, ma non permette di associare facilmente ogni temperatura al suo orario.

La soluzione è usare una **matrice**, ovvero un array bidimensionale:  
- ogni **riga** rappresenta un giorno  
- ogni **colonna** rappresenta un orario di misurazione

Possiamo immaginarla come una tabella:

| Giorno ↓ / Ora → | 8:00 | 12:00 | 16:00 | 20:00 |
|------------------|------|-------|-------|-------|
| Lunedì           | 22   | 25    | 29    | 23    |
| Martedì          | 23   | 27    | 30    | 22    |
| …                |      |       |       |       |
| Venerdì          | 23   | 27    | 30    | 22    |
| …                |      |       |       |       |

---

### Cos’è una matrice?

Una **matrice** è un **array bidimensionale**, cioè una griglia di valori.  
In C++ si rappresenta come un array di array: ogni riga è a sua volta un array.

```cpp
double temperature[7][4];
```

In questo esempio stiamo dichiarando una matrice con 7 righe (giorni) e 4 colonne (ore di misurazione). 

---

### Come accedere agli elementi

Per accedere a un valore, dobbiamo specificare **due indici**:  
- il primo indica la **riga** (giorno)  
- il secondo indica la **colonna** (ora)

```cpp
temperature[0][0] = 22.0; // temperatura del primo giorno alle 8:00
temperature[0][1] = 25.0; // primo giorno alle 12:00
temperature[1][0] = 23.0; // secondo giorno alle 8:00
```

Gli indici partono sempre da **0**, quindi `temperature[0][0]` è il primo elemento in alto a sinistra della tabella.

---

### Visualizzare una matrice

Per leggere o stampare tutti i valori di una matrice, si usa **un doppio ciclo for**:  
uno scorre le righe, l’altro le colonne.

```cpp
#include <iostream>
using namespace std;

int main() {
    double temperature[2][3] = {
        {22.5, 26.0, 24.8},
        {21.8, 25.5, 23.9}
    };

    for (int i = 0; i < 2; i++) {          // scorre le righe -> 2 perchè abbiamo una matrice con 2 righe
        for (int j = 0; j < 3; j++) {      // scorre le colonne -> 3 perchè la matrice ha 3 colonne
            cout << temperature[i][j] << " ";
        }
        cout << endl;
    }
}
```

Output:

```
22.5 26.0 24.8
21.8 25.5 23.9
```

---

### Vantaggi delle matrici

- **Organizzazione chiara:** ideali per dati tabellari (piani di voto, immagini, mappe, tabelle di gioco).  
- **Accesso diretto:** come gli array, anche le matrici usano indici numerici e sono molto veloci.

---

### Svantaggi delle matrici

- **Dimensione fissa:** una volta dichiarata la grandezza (es. `[7][4]`), non può più cambiare.  
- **Gestione più complessa:** richiedono due indici e cicli annidati, quindi un po’ più di attenzione.

---

### Matrici e vector 2D

C++ permette anche di rappresentare una matrice con i **vector**, per ottenere una versione dinamica, che può crescere o ridursi:

```cpp
#include <vector>

std::vector<std::vector<double>> temperature(7, std::vector<double>(4));
temperature[0][0] = 22.5;
temperature[1][2] = 24.0;
```

Qui abbiamo una “matrice di vector”: 7 righe, ognuna con 4 elementi.  
La differenza è che possiamo modificare le dimensioni anche in esecuzione.

---

### Riepilogo differenze tra array e matrici

| Struttura | Dimensione | Accesso | Tipo di dati | Esempio d’uso |
|------------|-------------|---------|---------------|---------------|
| **Array**  | 1D fissa    | `arr[i]` | Sequenze lineari | Voti di una materia |
| **Matrice**| 2D fissa    | `mat[i][j]` | Dati tabellari | Temperature giornaliere |
| **Vector 2D** | 2D dinamica | `v[i][j]` | Dati tabellari flessibili | Tabelle di dimensione variabile |

---

### Errori comuni sulle matrici

1. **Dimenticare che l’indice parte da 0**
   ```cpp
   temperatura[1][1]; // è la seconda riga, seconda colonna!
   ```

2. **Invertire riga e colonna**
   - `temperature[i][j]` → riga `i`, colonna `j`
   - non confondere con `temperature[j][i]`!

3. **Dichiarare dimensioni sbagliate**
   - Un errore comune è dimenticare di fissare almeno la seconda dimensione in fase di dichiarazione:
     ```cpp
     int matrix[][3]; // ❌ errore: serve specificare la prima o la seconda dimensione
     ```

---


# Ricapitoliamo


Le **matrici** estendono il concetto di array a più dimensioni, permettendo di gestire dati strutturati come tabelle o griglie.  
Quando i dati sono bidimensionali e di dimensione nota, usa una matrice.  
Se invece hai bisogno di una struttura più flessibile, un **vector di vector** è la scelta migliore.

- **Concetto**: array bidimensionali → righe e colonne.
- **Accesso**:
    - accedere alle **righe** di una matrice
    - accedere alle **colonne** di una matrice
- **Scansione** / **iterazione** → sempre necessari **2 cicli annidati** per scorrere tutti gli elementi che compongono righe e colonne

#### Operazioni comuni
- Somma di tutti gli elementi
- Somma diagonale principale: elementi [i][j] dove i = j
- Conteggio di elementi secondo una condizione


#### Domande guida
- Come accedo a un elemento specifico di una matrice?
- Come scansiono tutte le righe e le colonne di una matrice usando cicli annidati?
- Come posso sommare tutti gli elementi di una matrice?
- Come sommo solo gli elementi della diagonale principale?
- Come conto quanti elementi soddisfano una certa condizione all’interno della matrice?

[Prossima lezione](10-algoritmi)