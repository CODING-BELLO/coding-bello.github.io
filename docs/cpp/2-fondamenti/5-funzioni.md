---
title: Funzioni
layout: default
nav_order: 7
parent: Coding in C++
---
# Funzioni

## Cos’è una funzione
Una **funzione** è un **pezzo di codice autonomo** che esegue un compito specifico.  
Possiamo immaginarla come una “scatola nera” che:

1. Riceve **input** (i parametri)  
2. Esegue un insieme di istruzioni  
3. Restituisce un **output** (il valore di ritorno)

Questo modello mentale ci aiuta a pensare alle funzioni come **unità indipendenti**, utili a spezzare problemi complessi in parti più semplici.

---

## Parametri e valori di ritorno

- **Parametri**: dati che passiamo alla funzione perché possa lavorare su di essi.  
- **Valore di ritorno**: il risultato che la funzione restituisce quando termina.

Esempio in C++:

```cpp
#include <iostream>
using namespace std;

// Funzione che calcola la somma di due numeri
int somma(int a, int b) {
    return a + b; // restituisce il risultato
}

int main() {
    int x = 5;
    int y = 7;
    int risultato = somma(x, y);
    cout << "La somma è " << risultato << endl;
    return 0;
}
```

Qui:
- `int a, int b` sono i **parametri**  
- `return a + b;` restituisce il **valore di ritorno**  
- La funzione può essere riutilizzata con numeri diversi senza riscrivere il codice.

---

## Passaggio di parametri per valore e per riferimento

Quando chiamiamo una funzione, i **parametri** possono essere passati in due modi principali:

1. **Per valore** → viene passata **una copia** del dato.  
2. **Per riferimento** → viene passato **l’indirizzo del dato originale**, quindi la funzione può **modificarlo direttamente**.

In C++, **per default** tutti i parametri vengono passati **per valore**, ad eccezione degli **array**, che vengono passati automaticamente per riferimento (in realtà si “degradano” a puntatori).  
Questo significa che, se non specifichiamo diversamente, **le modifiche fatte ai parametri dentro la funzione non influenzano le variabili originali**.

---

### Esempio: passaggio per valore

```cpp
#include <iostream>
using namespace std;

void incrementa(int n) {
    n = n + 1;  // Modifica solo la copia locale
    cout << "Dentro la funzione: n = " << n << endl;
}

int main() {
    int x = 5;
    incrementa(x);
    cout << "Fuori dalla funzione: x = " << x << endl;
    return 0;
}
```

In questo caso:
- All'interno della funzione, la variabile `n` viene incrementata a 6.
- All'esterno, `x` rimane 5 perché è stata passata **una copia**, non la variabile originale.

---

### Esempio: passaggio per riferimento

Per passare un parametro per riferimento in C++, si usa la **&** (e commerciale) nel prototipo della funzione:

```cpp
#include <iostream>
using namespace std;

void incrementaRiferimento(int &n) {
    n = n + 1;  // Modifica direttamente la variabile originale
    cout << "Dentro la funzione: n = " << n << endl;
}

int main() {
    int x = 5;
    incrementaRiferimento(x);
    cout << "Fuori dalla funzione: x = " << x << endl;
    return 0;
}
```

In questo caso:
- `n` è un riferimento a `x`, quindi qualsiasi modifica a `n` **modifica direttamente `x`**.
- Alla fine, `x` risulta incrementato a 6 anche fuori dalla funzione.

---

**Ricapitolando**:

| Modalità            | Copia o originale? | Può modificare la variabile chiamante? |
|----------------------|----------------------|--------------------------------------------|
| Per valore           | Copia                | No                                     |
| Per riferimento      | Originale            | Sì                                     |

Il passaggio per riferimento è molto utile quando:
- Vogliamo **evitare copie inutili** di dati grandi (es. strutture, oggetti, array).  
- Vogliamo che la funzione **modifichi direttamente** le variabili passate.  

---

## Concetti fondamentali

### 1. Riuso

Scrivere una funzione significa poter **usare lo stesso codice più volte** senza copiarlo.  
Esempio:

```cpp
#include <iostream>
using namespace std;

int quadrato(int n) {
    return n * n;
}

int main() {
    cout << quadrato(3) << endl;
    cout << quadrato(5) << endl;
}
```

### 2. Modularità

Le funzioni ci permettono di **spezzare problemi complessi** in parti più piccole e comprensibili.  
Esempio:

- Problema: calcolare l’area di un rettangolo e di un triangolo  
- Soluzione modulare:

```cpp
float areaRettangolo(float base, float altezza) {
    return base * altezza;
}

float areaTriangolo(float base, float altezza) {
    return (base * altezza) / 2;
}
```

Ogni funzione si occupa di un **compito specifico**, più facile da leggere, testare e correggere.

---

## Errori comuni

1. **Variabili locali vs globali**  
   Le variabili dentro una funzione **non esistono fuori dalla funzione**. 
   ```cpp
   void prova() {
       int x = 10;
   }
   // x non è visibile qui
   ```

2. **Valore di ritorno obbligatorio**  
   Una funzione `int` deve sempre restituire un valore int.Altrimenti il comportamento è indefinito.

3. **Funzioni “ricordano” i valori tra chiamate**  
Le variabili locali **non mantengono il valore tra le chiamate**.  


4. **Passaggio dei parametri**  
In C i parametri vengono passati per **valore** (una copia), quindi modificare il parametro dentro la funzione **non cambia la variabile originale**. (Questo non vale per alcune strutture dati che vedremo successivamente)

```cpp
#include <iostream>
using namespace std;

void incrementa(int n) {
    n = n + 1;  // modifica solo la copia interna
}

int main() {
    int a = 5;
    incrementa(a);
    cout << a << endl;  // stampa 5, non 6
    return 0;
}
```


---

# Ricorsione

La **ricorsione** è una tecnica in cui **una funzione chiama se stessa**. Tipicamente è utilizzata all'interno di algoritmi in cui è neccessario effettuare qualcosa di ripetitivo, sostituendo `for` e `while`. Nella realtà, la ricorsione non sostituisce solamente i costrutti di ripetizione, è molto più potente. 
Problemi come il calcolo fattoria, la sequenza di numeri di Fibonacci, possono essere rappresentati mediante un algoritmo ricorsivo.

Questo è un primo esempio di algoritmo ricorsivo...

```cpp
int fattoriale(int n) {
    return n * fattoriale(n - 1); // passo ricorsivo
}
```

...che se eseguito non termina mai! La chiamata di questa funzione genererebbe infatti un ciclo(loop) infinito di chiamate alla funzione fattoriale().

### Componenti di una funzione ricorsiva

Per funzionare correttamente, una funzione ricorsiva deve sempre avere:

1. **Caso base** → la condizione che **ferma** la ricorsione.  
2. **Passo ricorsivo** → la chiamata a se stessa su un “problema più piccolo”.

>**Intuizione**: una funzione con ricorsione funziona proprio per la presenza del caso base. Ad ogni chiamata ricorsiva, viene eseguita la funzione, passandogli come input un nuovo valore (N.B. le variabili primitive in C++ vengono passate come valore e non come riferimento!)

---

#### Esempio: fattoriale di un numero

Il **fattoriale** di un numero `n` (scritto `n!`) è definito così:

- `0! = 1`  (caso base)  
- `n! = n × (n - 1)!` per `n > 0`  (passo ricorsivo)

Ecco la versione ricorsiva in C++:

```cpp
#include <iostream>
using namespace std;

int fattoriale(int n) {
    if (n == 0) {
        return 1; // caso base
    } else {
        return n * fattoriale(n - 1); // passo ricorsivo
    }
}

int main() {
    cout << fattoriale(5) << endl; // stampa 120
    return 0;
}
```

Chiamata per `n = 5`:

```
fattoriale(5)
= 5 × fattoriale(4)
= 5 × 4 × fattoriale(3)
= 5 × 4 × 3 × fattoriale(2)
= 5 × 4 × 3 × 2 × fattoriale(1)
= 5 × 4 × 3 × 2 × 1 × fattoriale(0)
= 5 × 4 × 3 × 2 × 1 × 1
= 120
```

---

### Errore comune nella ricorsione

Un errore **frequentissimo** è **dimenticare il caso base**, oppure scriverlo in modo sbagliato.  
Questo, come detto in precedenza, porta a **chiamate infinite** → la funzione continua a chiamare se stessa senza mai fermarsi → il programma va in **stack overflow** (esaurisce la memoria dedicata alle chiamate).

Esempio **sbagliato**:

```cpp
int fattoriale(int n) {
    return n * fattoriale(n - 1); // manca il caso base!
}
```

Questo codice continuerà a chiamare `fattoriale(-1)`, `fattoriale(-2)`, ecc. fino a crashare.

---

### Quando usare la ricorsione?

- Quando il problema può essere **spezzato in sottoproblemi simili all’originale**.  
- Quando si vuole una soluzione **più leggibile** ed elegante rispetto a quella con cicli `for` e `while`.  

[Prossima lezione](6-leggibilita)