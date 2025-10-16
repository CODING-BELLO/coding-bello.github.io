---
title: Strutture dati base struct
layout: default
nav_order: 15
parent: Coding in C++
---



# Il costrutto struct

Una **struct** (abbreviazione di structure) è una **struttura dati composta**:  
permette di **raggruppare più variabili di tipi diversi** sotto un unico nome, così da trattarle come un’unica entità.

Può essere utile, ad esempio, per rappresentare un concetto reale (come uno studente, un punto, una data) mettendo insieme dati diversi ma logicamente collegati.

---

## Dichiarazione di una struct

La sintassi base è:

```cpp
struct NomeStruttura {
    tipo campo1;
    tipo campo2;
    // ...
};
```

Esempio:

```cpp
struct Studente {
    string nome;
    int eta;
    float media;
};
```

La dichiarazione definisce solo un "modello", non crea ancora variabili.

---

## Creazione e valorizzazione di variabili struct

Per creare una variabile di tipo `Studente`:

```cpp
Studente s;
s.nome = "Anna";
s.eta = 17;
s.media = 8.5;
```

Oppure si può inizializzare direttamente:

```cpp
Studente s{"Anna", 17, 8.5};
```

I campi si accedono con l'operatore `.`:

```cpp
cout << s.nome << " ha " << s.eta << " anni." << endl;
```

---

## Passare struct a funzioni

Le struct si possono passare a funzioni come qualunque altro tipo:

```cpp
void stampaStudente(Studente s) {
    cout << s.nome << " (" << s.eta << " anni) - media: " << s.media << endl;
}

int main() {
    Studente a{"Luca", 18, 7.9};
    stampaStudente(a);
    return 0;
}
```

---

## Perchè utilizzare il costrutto `struct`

- **Chiarezza**: i dati correlati stanno insieme  
- **Modularità**: possiamo ragionare su blocchi separati 
- **Riuso**: possiamo creare tante variabili di quel tipo senza riscrivere nulla 
- **Manutenibilità**: se devo aggiungere un campo, lo aggiungo nella struct e tutto il resto resta coerente

---

### Spoiler: le `struct` possono avere anche funzioni

In C++ le `struct` non servono solo a raccogliere dati: possono anche **contenere funzioni** al loro interno.

Questo è un primo passo verso la **programmazione a oggetti**, dove dati e operazioni stanno insieme nella stessa entità logica.

Esempio semplice:

```cpp
#include <iostream>
using namespace std;

struct Punto {
    int x;
    int y;

    void stampa() {
        cout << "(" << x << ", " << y << ")" << endl;
    }
};

int main() {
    Punto p{3, 4};
    p.stampa();  // chiama la funzione interna alla struct
    return 0;
}
```

In questo esempio, la `struct Punto` non contiene solo i dati `x` e `y`, ma anche una **funzione membro** `stampa()` che sa come mostrare quei dati.

# Ricapitoliamo
- **Motivazioni**: perchè utilizzare la struttura struct?
- **Concetto**: raggruppare più dati correlati sotto un unico nome.
- **Differenza** tra una struct e una variabile di tipo struct
- **Dichiarazione** di una struct e successiva valorizzazione

#### Domande guida
- Perché è utile usare una struct invece di tante variabili separate?
- Come si dichiara una struct e come si valorizzano i suoi campi?
- Come posso creare un array di struct e accedere ai singoli campi?
- Come passo una struct o un array di struct a una funzione per leggerla o modificarla?

[Esercizi](../ex/struct)

[Prossima lezione](8-strutture-dati-base)