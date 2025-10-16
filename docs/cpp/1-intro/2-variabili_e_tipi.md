---
title: Variabili e tipi
layout: default
nav_order: 3
parent: Coding in C++
---
# Variabili e tipi

In questo tutorial esploreremo i concetti fondamentali delle **variabili** e dei **tipi** in C++. Impareremo cosa sono le variabili, come dichiararle, i tipi di dati principali e alcune nozioni importanti per evitare errori comuni.

---

## Cos'è una variabile?

Una variabile è un contenitore che serve a memorizzare un valore durante l'esecuzione del programma. Ogni variabile è composta nel modo seguente
- **tipologia**: definisce il **tipo di dato** che può contenere (ad esempio numeri interi, numeri a virgola mobile, caratteri, ecc.)
- **nome**: definisce un nome, utilizzabile per chiamare quel concetto e utilizzarlo in parti diverse del codice


---

## Tipi di dato base in C++

Questi sono i tipi di dato primitivi, rappresentano la minima informazione che possiamo rappresentare nel nostro linguaggio

- `int` — numeri interi (es. 5, -10)
- `double` — numeri con la virgola (es. 3.14, -0.001)
- `char` — singolo carattere (es. 'a', 'Z')
- `bool` — valore booleano, `true` o `false`

Introduciamo, perchè ci servirà subito, anche il tipo di dato
- `string` — qualsiasi insieme di caratteri, numeri, simboli, sempre trattati come testo
Le stringhe sono un tipo di dato molto potente e non primitivo, ma per noi ora è trascurabile.


---

# Passiamo alla pratica

## Dichiarare una variabile

**Dichiarare una variabile** significa far sapere a chi legge il nostro programma (il computer) che esiste un informazione che ha un certo nome. E' quindi sempre necessario effettuare la dichiarazione di una variabile prima di utilizzarla. 

Nel codice sotto, stiamo semplicemente dicendo che all'interno del nostro programma, esiste una variabile chiamata a!

```cpp
int a;
```

---

### Assegnazione di una variabile
Una volta che la nostra variabile è stata dichiarata, possiamo assegnare un valore a quella variabile, coerente con il tipo che abbiamo dichiarato durante la dichiarazione;

```cpp
int a;
a = 42;
```

E' possibile dichiarare e assegnare una variabile in un colpo solo

```cpp
int a = 42;
```


```cpp
int b;
b = 'c'; //sbagliato :(
b = 12.2 //sbagliato :(
b = 13 // corretto :)
```

---

### Inizializzazione e assegnazione di tutti i tipi primitivi


```cpp
int eta = 25;
double peso = 70.5;
char iniziale = 'M';
bool isStudente = true;
string studente = "Marco";
```

### L'assegnazione è sempre da destra a sinistra

L'operazione `=` assegna il valore della parte destra alla variabile a sinistra.  
Esempio corretto:

```cpp
int a = 22;
```

Esempio **sbagliato** che causa errore:

```cpp
22 = a;  // Errore: non si può assegnare un valore a un numero letterale
```

---

### Assegnare una variabile a un'altra  variabile

Cosa succede quando assegniamo una variabile a un'altra variabile?

```cpp
int a = 5;
int b = a; 
```

Con questa istruzione stiamo dicendo: "a vale 5, b vale lo stesso valore contenuto in a". Viene quindi effettuata una **copia del valore** della variabile. Questo tipo di assegnazione prende il nome di **assegnazione per valore**.

**Domanda:** quanto vale a dopo aver eseguito tutte e 3 le istruzioni?

```cpp
int a = 5;
int b = a; 
b = b + 1;
```

**Risposta:** **a** vale 5, perchè a **b** è stato assegnato solo il valore di a (5). 

> Importante ricordare: `a` = `b` non significa che `a` e `b` sono la stessa cosa, ma che hanno stesso valore.

---

### Assegnare un tipo diverso da quello dichiarato
C++ è un linguaggio **fortemente tipato**, questo significa che viene sempre eseguito un controllo sui tipi delle variabili. Questo esempio: 

```cpp
int a = 5;
double b;

b = a; // Errore :( 
```
`b` e `a` non hanno stesso tipo, pertanto non possiamo assegnare a `b` il valore di `a` e viceversa.

---

## Esempio completo

```cpp
#include <iostream>

int main() {
    int eta = 30;
    double peso = 70.5;
    char iniziale = 'F';
    bool isStudente = false;

    std::cout << "Età: " << eta << std::endl;
    std::cout << "Peso: " << peso << std::endl;
    std::cout << "Iniziale: " << iniziale << std::endl;
    std::cout << "Studente: " << (isStudente ? "Sì" : "No") << std::endl;

    return 0;
}
```

---

## Errori comuni

- Valorizzazione al contrario

    ```cpp
    10 = a;  // Errore
    ```

- Usare variabili non inizializzate:

    ```cpp
    int x;
    std::cout << x;  // Valore indefinito, comportamento imprevedibile
    ```

- Confondere il tipo di dato e assegnare valori incompatibili:

    ```cpp
    char c = "abc";  // Errore: char può contenere un solo carattere
    ```

- Pensare che il computer che esegue il nostro codice sia intelligente

    ```cpp
    string numero = "fregato";  // Questo è corretto!! Sebbene la variabile si chiami numero, è di tipo stringa
    ```

---

## Ricapitoliamo

- Una **variabile** è un contenitore per memorizzare dati durante l'esecuzione del programma.
- Ogni variabile ha un **tipo** che definisce il tipo di dato che può contenere (es. `int`, `double`, `char`, `bool`, `string`).
- Prima di usare una variabile, bisogna **dichiararla** specificando il tipo e il nome.
- L'**assegnazione** (`=`) assegna un valore alla variabile, sempre da destra verso sinistra.
- Non si possono assegnare valori di tipo diverso senza conversione esplicita.
- Assegnare una variabile a un'altra copia il valore, non la variabile stessa.
- Attenzione agli **errori comuni** come usare variabili non inizializzate o assegnare tipi incompatibili.

[Prossima lezione](3-operatori_e_espressioni)