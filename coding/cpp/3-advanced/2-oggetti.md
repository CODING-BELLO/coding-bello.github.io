---
title: Programmazione a oggetti
layout: default
nav_order: 1
parent: Concetti avanzati programmazione in C++
---
# Programmazione a Oggetti in C++  
*Introduzione concettuale per studenti delle scuole superiori*

> “La programmazione a oggetti non è scrivere codice in un certo linguaggio, ma **pensare in termini di oggetti**.”  
> — Alan Kay (ideatore del termine “Object Oriented”)

## Obiettivi di questo documento

- Capire **perché** esiste la programmazione a oggetti (OOP)  
- Comprendere i **principi fondamentali**: astrazione, incapsulamento, modularità, ereditarietà e polimorfismo  
- Saper riconoscere e progettare **classi e oggetti**  
- Distinguere chiaramente **concetti teorici** da **costrutti del linguaggio C++**

## Perché la programmazione a oggetti?

Quando i programmi diventano più complessi (migliaia di righe), serve un modo per **organizzare il codice** in blocchi logici facilmente riutilizzabili e manutenibili.

### Programmazione procedurale (classica)

- Il codice è composto da **funzioni** e **variabili globali**.  
- Tutto è “sparso” e la complessità cresce velocemente.  
- Esempio: gestire uno studente con tante variabili globali → rischio errori.

```cpp
string nomeStudente;
int etaStudente;
float mediaStudente;

void stampaStudente() {
    cout << nomeStudente << ", " << etaStudente << " anni, media " << mediaStudente << endl;
}
```

### Programmazione a oggetti

- Si ragiona in termini di **oggetti** con proprietà e comportamenti.  
- Le informazioni e le funzioni sono **racchiuse insieme**.  

Spesso dopo questa introduzione viene da chiedersi cosa di nuovo si può fare con questo paradigma. La risposta è nulla di più, ma possiamo fare le stesse cose in modo più strutturato e naturale, più vicino al nostro modo di pensare.
È un po’ come indossare jeans comodi o skinny, sono effettivamente sempre pantaloni ma non scherziamo, NO SKINNY!!! :O (non aboliamo la programmazione procedurale pura ci serve un sacco)

Esempio parallelo:

```cpp
// Procedurale: stampa info di uno studente
string nome = "Luca";
int eta = 17;
float media = 8.5;

cout << nome << ", " << eta << " anni, media " << media << endl;

// A oggetti: stesso risultato, ma più chiaro e modulare
class Studente {
public:
    string nome;
    int eta;
    float media;

    void stampa() {
        cout << nome << ", " << eta << " anni, media " << media << endl;
    }
};

int main() {
    Studente s;
    s.nome = "Luca";
    s.eta = 17;
    s.media = 8.5;
    s.stampa();
}
```

- Gli oggetti rappresentano **concetti del mondo reale** (es. Studente, Automobile, Rettangolo...).

```cpp
class Studente {
public:
    string nome;
    int eta;
    float media;

    void stampa() {
        cout << nome << ", " << eta << " anni, media " << media << endl;
    }
};

int main() {
    Studente s;
    s.nome = "Luca";
    s.eta = 17;
    s.media = 8.5;
    s.stampa();
}
```

## Concetto chiave: Classe vs Oggetto

| **Classe**            | **Oggetto** |
|------------------------|------------|
| “Modello” o “progetto” | “Esemplare” creato da quel modello |
| Definisce struttura e comportamento | Ha valori concreti nei suoi campi |
| È come una *ricetta* | È la *torta* realizzata con quella ricetta |

```cpp
class Rettangolo {
public:
    int base;
    int altezza;

    int area() {
        return base * altezza;
    }
};

int main() {
    Rettangolo r1;  // primo oggetto
    r1.base = 5;
    r1.altezza = 3;

    Rettangolo r2;  // secondo oggetto
    r2.base = 10;
    r2.altezza = 2;

    cout << r1.area() << endl;  // 15
    cout << r2.area() << endl;  // 20
}
```

## Misconcezione comune 1: “La classe è come una variabile”

> ❌ *“Ho dichiarato la classe, quindi ho già creato un oggetto.”*  
> ✅ No! La classe è **solo una definizione**. L’oggetto si crea con la **dichiarazione di una variabile di quel tipo** (es. `Studente s;`).

## Incapsulamento e visibilità

- **Incapsulamento** significa “racchiudere” dati e funzioni dentro l’oggetto e **controllare l’accesso** a questi dati.
- `public`: accessibile da fuori  
- `private`: accessibile solo dall’interno della classe

### Stato di un oggetto e incapsulamento

- Lo **stato** di un oggetto è l’insieme dei valori delle sue proprietà in un dato momento.
- Cambiando i dati interni tramite i metodi, **lo stato dell’oggetto cambia**.

```cpp
class Lampadina {
private:
    bool accesa;

public:
    void accendi() { accesa = true; }
    void spegni() { accesa = false; }
    bool stato() { return accesa; }
};

int main() {
    Lampadina l;
    l.accendi();          
    cout << l.stato();    // true
    l.spegni();           
    cout << l.stato();    // false
}
```

> ⚠️ Misconcezione comune: lo stato non è “qualcosa di automatico” o invisibile: è sempre definito dai valori dei dati interni.

```cpp
class ContoBancario {
private:
    double saldo;

public:
    ContoBancario() {
        saldo = 0;
    }

    void deposita(double x) {
        saldo += x;
    }

    double ottieniSaldo() {
        return saldo;
    }
};

int main() {
    ContoBancario c;
    c.deposita(100);
    cout << c.ottieniSaldo();  // ✅ 100
}
```

## Misconcezione comune 2: “Private serve solo a non far vedere le cose”

> ❌ *“Metto tutto public così è più facile accedere.”*  
> ✅ No! Il punto non è “nascondere” ma **proteggere l’integrità** dei dati e **definire un’interfaccia chiara**.

## Costruttori e stato iniziale

```cpp
class Punto {
private:
    int x, y;

public:
    Punto(int _x, int _y) {
        x = _x;
        y = _y;
    }

    void stampa() {
        cout << "(" << x << "," << y << ")";
    }
};

int main() {
    Punto p(3, 4);
    p.stampa();  // (3,4)
}
```

## Ereditarietà: riuso e specializzazione

```cpp
class Persona {
public:
    string nome;
    int eta;

    void presenta() {
        cout << "Ciao, sono " << nome << " e ho " << eta << " anni." << endl;
    }
};

class Studente : public Persona {
public:
    string scuola;

    void presenta() {
        cout << "Ciao, sono " << nome << ", ho " << eta << " anni e frequento " << scuola << "." << endl;
    }
};

int main() {
    Studente s;
    s.nome = "Anna";
    s.eta = 16;
    s.scuola = "Liceo Scientifico";
    s.presenta();
}
```

## Riepilogo e altri concetti utili

In questa lezione abbiamo visto i concetti fondamentali della programmazione a oggetti in C++:

- **Classe**: modello o progetto che definisce dati e comportamenti.
- **Oggetto**: istanza di una classe, con uno stato specifico.
- **Incapsulamento**: racchiudere dati e comportamenti, proteggere l'accesso tramite `private` e `public`.
- **Stato di un oggetto**: insieme dei valori delle proprietà in un dato momento.
- **Costruttori**: metodi speciali per inizializzare oggetti.
- **Ereditarietà**: permette di creare classi derivate riutilizzando caratteristiche di altre classi.
- **Polimorfismo** (concetto introduttivo): capacità di un oggetto di comportarsi in modi diversi in base al contesto, spesso tramite funzioni virtuali (non approfondito qui).

### Suggerimenti pratici

- Sempre pensare agli oggetti come **entità reali** con proprietà e comportamenti.
- Definire chiaramente l’**interfaccia pubblica** della classe (metodi `public`) e mantenere i dati sensibili `private`.
- Usare l’ereditarietà solo quando ha senso logico, altrimenti preferire la **composizione** (un oggetto dentro un altro).
- Annotare sempre il codice con commenti chiari, soprattutto quando si introducono concetti OOP.

Questo riepilogo ti aiuterà a costruire una **solida base concettuale** prima di approfondire altri aspetti avanzati come polimorfismo dinamico, template e gestione della memoria in C++.