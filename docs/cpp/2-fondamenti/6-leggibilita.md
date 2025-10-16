---
title: Leggibilità del codice
layout: default
nav_order: 14
parent: Coding in C++
---
# Leggibilità del codice

La **leggibilità del codice** è un aspetto fondamentale nella programmazione. Significa scrivere il codice in modo chiaro e comprensibile, così che sia facile da leggere, capire e modificare, sia da te che da altri programmatori. Un codice leggibile aiuta a ridurre gli errori e rende più semplice la manutenzione e l’aggiornamento del programma.

## Perché è importante la leggibilità?

- Un codice chiaro riduce il rischio di errori perché è più facile capire cosa fa ogni parte.
- Facilita la collaborazione con altri programmatori.
- Permette di trovare e correggere problemi più rapidamente.
- Aiuta a mantenere il programma nel tempo senza dover riscrivere tutto da capo.

## Concetti chiave per migliorare la leggibilità

### 1. Naming convention (Convenzioni sui nomi)

Scegliere nomi chiari e significativi per variabili, funzioni e classi è fondamentale. Un buon nome descrive esattamente cosa rappresenta o cosa fa l’elemento.

**Esempio:**

```cpp
int tempoAttesa;    // chiaro: indica il tempo di attesa
int ta;             // poco chiaro: cosa significa "ta"?
```

**Suggerimenti:**

- Usa nomi descrittivi, come `numeroStudenti`, `calcolaMedia()`.
- Evita abbreviazioni troppo criptiche.
- Segui uno stile coerente (es. camelCase o snake_case).

**Stili comuni in C++:**

In C++ esistono diversi stili per scrivere i nomi di variabili, funzioni, costanti e classi. È importante conoscerli per scegliere quello più adatto e mantenere coerenza nel codice.

- **camelCase:** la prima parola in minuscolo e ogni parola successiva con la prima lettera maiuscola, senza spazi o underscore.  
  Esempio: `numeroStudenti`, `calcolaMedia()`.  
  Questo stile è spesso usato per variabili e funzioni.
  In alternativa è anche possibile utilizzare tutte le lettere minuscole, con parole separate da underscore `_`.  
  Esempio: `numero_studenti`, `calcola_media()`.  

- **CONSTANT_CASE:** tutte le lettere maiuscole con underscore per separare le parole.  
  Esempio: `MAX_VALORE`, `NUMERO_MASSIMO`.  
  Usato per le costanti.

### 2. Indentazione

L’indentazione consiste nel rientrare il codice all’interno di blocchi logici, come cicli, condizioni o funzioni. Questo aiuta a visualizzare la struttura del programma.

**Esempio senza indentazione:**

```cpp
if (x > 0) {
cout << "Positivo"; 
}
```

**Esempio con indentazione corretta:**

```cpp
if (x > 0) {
    cout << "Positivo";
}
```

**Suggerimenti:**

- Usa il tasto tab coerentemente (di solito 4 spazi per livello).
- Indenta sempre il codice dentro parentesi graffe `{}`.
- Mantieni la stessa indentazione per blocchi di codice simili.

### 3. Commenti

I commenti sono spiegazioni scritte nel codice che non vengono eseguite dal computer. Servono a chiarire il funzionamento o lo scopo di parti complesse del codice.

**Esempio:**

```cpp
// Calcola la media di due numeri
double media = (num1 + num2) / 2.0;
```

**Suggerimenti:**

- Commenta il “perché” del codice, non solo il “cosa” fa.
- Evita commenti ovvi o ridondanti.
- Aggiorna i commenti se modifichi il codice.

## Esempio pratico completo

```cpp
#include <iostream>
using namespace std;

// Funzione che calcola la somma di due numeri interi
int somma(int primoNumero, int secondoNumero) {
    return primoNumero + secondoNumero;
}

int main() {
    int numeroUno = 5;
    int numeroDue = 7;

    // Calcola la somma dei due numeri
    int risultato = somma(numeroUno, numeroDue);

    cout << "La somma è: " << risultato << endl;

    return 0;
}
```

In questo esempio:

- I nomi delle variabili e della funzione sono chiari e descrittivi.
- Il codice è ben indentato per mostrare la struttura.
- I commenti spiegano cosa fa la funzione e alcune parti del codice.

## Suggerimenti per evitare errori

- Scrivi codice leggibile fin dall’inizio, non aspettare di doverlo correggere dopo.
- Testa spesso il programma mentre lo scrivi.
- Usa strumenti di formattazione automatica se disponibili.
- Rileggi il codice come se dovessi spiegarlo a qualcun altro.

---

[Prossima lezione](7-strutture)