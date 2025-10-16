---
title: Array e vector
layout: default
nav_order: 16
parent: Coding in C++
---

# Strutture dati di base

Immaginiamo di dover gestire i dati di una piccola stazione meteorologica. La stazione registra ogni giorno, a diverse ore, la temperatura esterna. Abbiamo bisogno di mantenere lo storico di queste temperature, al fine di analizzarle quando necessario. Fortunatamente, con i linguaggi di programmazione moderni non dobbiamo creare centinaia di variabili `float` per mantenere la temperatura, esistono modi molto più comodi!. In questa sezione tratteremo due strutture dati di base in C++: gli **array** e i **vector**.

---

## Array

### Cos’è un array? 

Un **array** è come una fila di variabili, numerate, in fila e di una sola tipologia (tutte float, int ecc). La cosa importante è che il numero di scatole è deciso all’inizio e non cambia più.

In questo programma, abbiamo dichiarato un array che può contenere fino a 100 valori `double` rappresentanti la temperatura.

```cpp
double temperature[100]; // cinque temperature analizzate in laboratorio
```

### Come accedere agli elementi

Per leggere il valore di un elemento, viene utilizzato l’indice tra parentesi quadre: `temperature[0]` è il primo elemento, `temperature[1]` il secondo, e così via. **Importante** si parte sempre da zero, non da uno!


```cpp
double temperature[100]; // cinque temperature analizzate in laboratorio
temperature[0] = 23.5; // prima misurazione
temperature[1] = 24.1; // seconda misurazione
```

### Vantaggi dell’array

- **Velocità fulminea:** l’accesso agli elementi è immediato perché la macchina sa esattamente a che indirizzo andare a prendere l'n-esimo valore.
- **Uso efficiente della memoria:** nessun extra, solo lo spazio necessario per le tue scatole.

### Svantaggi dell’array

- **Rigidità:** una volta deciso il numero di elementi, non è possibile aggiungerne altri (è necessario creare un nuovo array).
- **Poca flessibilità:** togliere o aggiungere elementi è complicato, come cercare di infilare una nuova scatola in mezzo a una fila già stretta.

---

## Vector: il contenitore elastico

### Cos’è un vector?

Il **vector** è come una borsa magica: può espandersi o restringersi mentre ci metti dentro o togli elementi. È dinamico, quindi non devi sapere in anticipo quanti elementi conterrà.

### Esempio in C++

```cpp
#include <vector>

std::vector<float> temperature; // elenco dinamico delle misurazioni di temperature
```
Notare che non viene dichiarata una dimensione iniziale.

**Inserire un nuovo valore in un vector già istanziato**

```cpp
temperature.push_back(23.5); // aggiunge temperatura di 23.5° al vector
temperature.push_back(27.0); // aggiunge temperatura di 27.0° al vector
```

**Leggere un valore specifico dal vector**

```cpp
int temp1 = temperature[0]; // legge la prima temperatura 
```

### Come accedere agli elementi

Anche qui usi la stessa sintassi `temperature[indice]` per prendere la temperatura in posizione `indice`.

### Vantaggi del vector

- **Flessibilità:** puoi aggiungere o togliere elementi senza preoccuparti della dimensione iniziale.
- **Gestione automatica della memoria:** il vector si occupa di tutto da solo

### Svantaggi del vector

- **Leggermente più lento:** ogni tanto la borsa deve essere cambiata di dimensione, e questo richiede tempo.
- **Più memoria usata:** per essere elastico, il vector tiene un po’ di spazio extra a disposizione.

---

## array vs vector

Spesso per confrontare due strutture dati o due linguaggi di programmazione, ci riferiamo al "tempo computazionale", inteso come il tempo impiegato dalla nostra macchina per effettuare un operazione. Anche se spesso si parla di frazioni di tempo piccolissime, dai nanosecondi ai millisecondi, il numero di queste operazioni è altissimo e può quindi incidere sulle prestazioni del nostro programma.

Il tempo computazionale indica quanto tempo impiega il computer per completare un’operazione su una struttura dati. Per le strutture come array e vector, si può distinguere tra lettura e scrittura:
- Lettura: il computer individua l’indirizzo di memoria dell’elemento richiesto e ne legge il valore. 
- Scrittura: il computer individua l’indirizzo di memoria dell’elemento e ne modifica il valore.
    
### Lettura: array vs vector


Sia gli **array** che i **vector** sono molto veloci in lettura perché i loro elementi sono memorizzati in posizioni di memoria contigue, cioè una dopo l’altra, proprio come una fila ordinata di scatole. Questo permette al computer di calcolare rapidamente l’indirizzo esatto dove si trova l’elemento che vogliamo leggere, senza dover cercare altrove.

```cpp
//array di temperature
double temperature[3] = {20.5, 21.0, 19.8};
double temp = temperature[1]; // legge il valore nella seconda posizione, cioè 21.0
```

```cpp
//vector di temperature
#include <vector>
std::vector<double> temperature = {20.5, 21.0, 19.8};
double temp = temperature[1]; // legge il valore nella seconda posizione, cioè 21.0
```


---

### Scrittura: array vs vector
Per l'**array**, la scrittura è semplice e veloce. L’indirizzo di memoria è fisso e noto:

```cpp
double temperature[3];
temperature[0] = 20.5; // scrive il valore 20.5 nella prima posizione
temperature[1] = 21.0; // scrive il valore 21.0 nella seconda posizione
```


Anche per i **vector** aggiungere un elemento è generalmente veloce come un array, ma abbiamo visto come possa cambiare dimensione. Inizialmente viene predisposta nella memoria una certa quantità di "spazio" per il vector. Quando questo spazio finisce, il computer sposta tutto il vector dove c'è posto. **Questa operazione di spostamento è lenta** e rappresenta la **differenza più importante tra array e vector**.

```cpp
#include <vector>

std::vector<double> temperature;
temperature.push_back(20.5); // aggiunge un elemento alla fine del vector
temperature.push_back(21.0); // aggiunge un altro elemento
```

**In sintesi**, se si sa già quanti elementi servono, usare un array può essere più efficiente per accesso e modifica. Se invece hai bisogno di una struttura che cresca durante l’esecuzione del programma, il vector è la scelta migliore.

### Riepilogo differenze

| Struttura | Dimensione | Accesso | Modifica dimensione | Vantaggi | Svantaggi |
|-----------|------------|---------|---------------------|----------|-----------|
| **Array** | Fissa      | Molto veloce | No                  | Efficienza, semplicità | Rigidità nella dimensione |
| **Vector**| Dinamica   | Veloce  | Sì                  | Flessibilità, facile da usare | Leggermente meno efficiente |

---

## Errori più comuni su array e vector

### 1. "L’indice degli array parte sempre da 1"

Molti studenti si aspettano che il primo elemento di un array sia in posizione 1, in realtà, in C++ e in molti altri linguaggi l’indice parte da 0, quindi il primo elemento è `array[0]`.

```cpp
int numeri[3] = {5, 10, 15};
std::cout << numeri[0] << std::endl; // stampa 5, il primo elemento
```


# Ricapitoliamo
- **Concetto**: sequenze ordinate di elementi dello stesso tipo.
- **Accesso**: array[i] → i parte da 0.
- **Scansione** / **iterazione** → sempre necessario un ciclo (for/while) per scorrere tutti gli elementi

#### Operazioni comuni
- Somma o media
- Ricerca minimo / massimo
- Conteggio elementi che soddisfano una condizione
- Modifica/scambio elementi di un array

#### Domande guida
- Come accedo a un elemento specifico di un array?
- Come posso scorrere tutti gli elementi di un array usando un ciclo?
- Come trovo il valore minimo o massimo in un array?
- Come calcolo la somma o la media di tutti gli elementi?
- Come posso contare quanti elementi soddisfano una certa condizione (es. pari, multipli di 4)?
- Come modifico un elemento specifico o scambio due elementi di un array?
- Come trovo il primo elemento che soddisfa una condizione specifica?
- Come posso rilevare il primo numero mancante in una sequenza ordinata?

[Esercizi su array e scansioni](../ex/array)

[Prossima lezione](9-strutture-dati-base-matrici)