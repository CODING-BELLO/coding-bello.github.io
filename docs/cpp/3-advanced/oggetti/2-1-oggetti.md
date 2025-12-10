---
title: Programmazione a oggetti 1
layout: default
nav_order: 33
parent: Coding in C++
---
# Programmazione a Oggetti 

La programmazione a oggetti (OOP) è un paradigma di programmazione che tratta le componenti di un programma come ogetti aventi uno stato e un comportamento.

Con la programmazione a oggetti arriveremo a un nuovo livello di astrazione, per cui cominceremo a modellare la realtà dei nostri problemi mediante dei modelli, con delle caratteristiche e delle funzioni.

La programmazione a oggetti, come tutti i fondamentali concetti teorici dell'informatica, può essere affrontata senza toccare una singola linea di codice. Essa infatti è un paradigma e non un linguaggio, possiamo vederla come un nuovo modo di pensare più organizzato e strutturato, rispetto alla tradizionale programmazione procedurale. 

## Classi e oggetti
- Un Oggetto rappresenta un **concetto specifico del mondo reale** (es. Studente, Automobile, Rettangolo...).
- Una Classe rappresenta il **modello astratto a cui un oggetto fa riferimento**.

Es. 
Possiamo identificare Studente come il nostro modello astratto (Classe). Studente è un concetto, un'idea, un'astrazione di tutti gli studenti veri e propri, con un nome, una storia, degli amici.

Davide, che è uno studente di 3A, rappresenta invece un oggetto della Classe Studente. Davide è lo studente vero! 


Una classe rappresenta il modello astratto, l'Oggetto rappresenta l'espressione di quel modello in termini reali.

## Motivazioni

Spesso dopo questa introduzione viene da chiedersi cosa di nuovo si può fare con questo paradigma. La risposta è nulla più rispetto al codice scritto fino ad ora, ma scrivendo programmi più facili da leggere, meglio strutturati e più vicini al nostro modo di pensare. 

Negli anni ‘70 e ’80 i linguaggi più diffusi (C, Fortran, Pascal) erano procedurali. I programmi erano una sequenza di istruzioni e funzioni che manipolavano dati, e anche noi, fino ad ora, ci siamo concentrati su questo tipo di programmazione.

Man mano che i software prendevano sempre più piede, si inizarono a riscontrare alcuni problemi:
- difficoltà nella manutenzione e nella modifica
- difficoltà di riutilizzare pezzi di codice in contesti diversi (parti diverse del programma)
- forte dipendenza funzioni e dati


## Definizione di una classe

Di seguito una prima definizione per la Classe Studente. Questa Classe rappresenta il concetto di studente, avente un nome, un'età e una media.

```cpp
class Studente {
    public:
        /********   Attributi (Stato)   *******/
        string nome;
        int eta;
        float media;

        /********   Costruttore   *******/
        Studente(string n, int e, float m) : nome(n), eta(e), media (m) {}

        /********   Metodi (Comportamento)   *******/
        void stampa() const {
            cout << nome << ", " << eta << " anni, media " <<   media << endl;
        }
};
```

**Importante:** La scelta di attributi e metodi è specifica per il problema che si sta trattando, avremmo potuto avere un attributo "Nazione" se d'interesse.

## Componenti di una classe
Come si vede dall'esempio, una classe ha tre diverse componenti
- **Attributi**: rappresentano lo stato dell'oggetto
- **Costruttore**: permette di creare gli oggetti specifici che seguono il modello definito dalla classe
- **Metodi**: rappresentano il comportamento di un oggetto

## Attributi di una Classe
Gli attributi sono le variabili dichiarate all’interno della classe, e rappresentano lo stato interno di ogni oggetto.
Per **stato** si intende l'insieme dei valori delle variabili dichiarate dentro all'oggetto.

```cpp
class Studente {
public:
    string nome;
    int eta;
    float media;
};

int main() {
    Studente s;

    /***      Stato dell'oggetto s      ***/
    s.nome = "Luca";
    s.eta = 17;
    s.media = 8.5; 


    /***      Modifica dello stato s    ***/
    s.media = 7; 
}
```

## Costruttore di una Classe
Un costruttore è un metodo speciale che ha lo stesso nome della classe, non ha tipo di ritorno (neanche void) e viene chiamato automaticamente quando si crea un oggetto.

Serve per inizializzare correttamente lo stato di uno studente al momento della creazione.


```cpp
// Costruttore per la classe studente definita sopra
    Studente(string n, int e, float m) {
        nome = n;
        eta = e;
        media = m;
    }
```


Utilizzo
```cpp
int main() {
    Studente s("Luca", 17, 8.5); // costruttore chiamato qui
    cout << s.getNome() << ", " << s.getEta() << " anni, media " << s.getMedia();
}
```

## Distruttore di una Classe
Un distruttore è un metodo speciale che viene chiamato automaticamente quando l’oggetto sta per essere distrutto (fine dello scope / fine della funzione / fine del programma). Serve per definire cosa deve accadere quando l’oggetto “finisce la sua vita”, ed eventualmente chiudere / liberare eventuali risorse usate dall'oggetto (sempre per il discorso che C++ è un linguaggio a basso livello in cui è il programmatore che deve gestire la memoria)

Se non scriviamo noi un distruttore, il compilatore ne genera comunque uno di default. Quindi gli oggetti che creiamo normalmente, quando escono dallo scope, vengono distrutti automaticamente.

```cpp
class Persona {
public:
    Persona() {
        cout << "Creo Persona" << endl;
    }

    ~Persona() {
        cout << "Distruggo Persona" << endl;
    }
};
```

Possiamo quindi intendere l’oggetto come qualcosa che **nasce (costruttore)** e **muore (distruttore)**. Per ora basta sapere che il distruttore serve a definire cosa succede quando l’oggetto termina.

## Metodi di una classe
I metodi definiscono il comportamento dell’oggetto, ovvero cosa può fare uno Studente.

E' possibile utilizzare i metodi per:
- modificare lo stato interno dell'oggetto (aggiornare la media)
- restituire informazioni (stampare i dati)
- implementare logiche più complesse (calcoli, ecc.)


## Visibilità degli attributi di una Classe

La keyword ```public``` rappresenta la visibilità delle componenti della classe al di fuori della classe stessa (dentro al main).

All’inizio, per semplicità, è comune dichiararli come public:
```cpp
class Studente {
public:
    string nome;
    int eta;
    float media;
};
```

per cui possiamo usarli liberamente dal main
```cpp
int main() {
    Studente s;
    s.nome = "Luca";
    s.eta = 17;
    s.media = 8.5;

    cout << s.nome << " ha " << s.eta << " anni e media " << s.media << endl;
}
```
Questo metodo funziona, ma può portare a problemi. Chiunque utilizzi la nostra classe Studente potrebbe fare questo:

```cpp
s.eta = -42;   // valore assurdo
s.media = 54;  // media no sense
```

E' quindi buona pratica dichiarare tutti gli attributi come private e accedere ai dati solo attraverso metodi (ovviamente pubblici). 
Questo permette di:
- proteggere l’integrità dello stato: nessuno può modificare i dati, se non utilizzando le funzioni che il creatore della classe ha messo a disposizione
- aggiungere controlli senza cambiare il codice utente
- rendere più chiara l’interfaccia pubblica

```cpp
class Studente {
private:
    string nome;
    int eta;
    float media;

public:
    void setNome(string n) { nome = n; }
    void setEta(int e) {
        if (e >= 0) eta = e;
    }
    void setMedia(float m) {
        if (m >= 1 && m <= 10) media = m;
    }

    string getNome() const { return nome; }
    int getEta() const { return eta; }
    float getMedia() const { return media; }
};
```

Attraverso questa implementazione, abbiamo protetto eta e media da valori che non ci piacciono. Se qualcuno vuole impostare "eta" con un numero minore di zero, non potrà farlo, così come inserire una media che non rientra nell'intervallo 1 - 10.




>**Misconcezione comune**: private NON serve a rendere oscura la classe o nascondere il valore delle variabili da occhi indiscreti.
Il punto di mettere private sulle variabile, è quello di **proteggere l’integrità** dei dati e **definire un’interfaccia chiara** (per interagire con l'oggetto). 

Spesso ci si ritrova a sviluppare in contesti dinamici, con molte persone. Sviluppare una classe con solo alcuni metodi pubblici, significa comunicare alle persone che usano quella classe "ho pensato che voi potete fare questo -> metodi pubblici"


## Incapsulamento

**Incapsulamento** significa “racchiudere” dati e funzioni dentro l’oggetto e **controllare l’accesso** a questi dati.
- `public`: accessibile e modificabile da fuori
- `private`: accessibile e modificabile solo dall’interno della classe


## Comparazioni
### Classe vs Struct
I costrutti di Classe e Struct sono quasi equivalenti dal punto di vista tecnico. Entrambi possono avere uno stato, dei metodi e i costruttori, con l'unica differenza che 
- **struct**: visibilità public di default, usata per dati semplici, senza incapsulamento
- **class**: visibilità private di default, usata per oggetti con stato protetto e comportamento

### Classe vs Oggetto

| **Classe**            | **Oggetto** |
|------------------------|------------|
| Rappresenta il modello | E' l'esemplare specifico, creato da quel modello |
| Definisce struttura e comportamento | Ha valori concreti nei suoi campi |
| Automobile | Fiat 500 rossa, targa XXYY |

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

**Errore comune: utilizzare la classe come una variabile**

> *“Ho dichiarato la classe, quindi ho già creato un oggetto.”* a.k.a. scrivere codice tipo `Rettangolo.area()`. La Classe è **solo una definizione**. L’oggetto si crea con la **dichiarazione di una variabile di quel tipo** e **mantiene lo stato** dell'oggetto stesso. 

> In riferimento al codice sopra, quali base e altezza si utilizzano chiamando `Rettangolo.area()`?


# Naming convention per classi e oggetti

In C++ è buona pratica seguire alcune convenzioni di naming per migliorare la leggibilità del codice:

- Le **classi** seguono la convenzione **PascalCase**, cioè ogni parola inizia con lettera maiuscola, esempio: `Studente`, `Rettangolo`, `Automobile`.
- Gli **oggetti** seguono generalmente la convenzione **camelCase** (la prima parola minuscola, le successive con la lettera maiuscola), esempio: `studente1`, `rettangoloGrande`.
- Per gli oggetti, può essere utilizzato uno stile tutto minuscolo con parole separate da underscore, ad esempio: `studente_1`, `rettangolo_grande`.

Seguire queste convenzioni aiuta a distinguere facilmente classi e oggetti nel codice, e in generale a fare chiarezza.

# Riepilogo

- **Classe**: modello o progetto che definisce dati e comportamenti.
- **Oggetto**: istanza di una classe, con uno stato specifico.
- **Incapsulamento**: racchiudere dati e comportamenti, proteggere l'accesso tramite `private` e `public`.
- **Stato di un oggetto**: insieme dei valori delle proprietà in un dato momento.
- **Costruttori**: metodi speciali per inizializzare oggetti.
- **Ereditarietà**: permette di creare classi derivate riutilizzando caratteristiche di altre classi.

## Suggerimenti pratici

- Sempre pensare agli oggetti come **entità reali** con proprietà e comportamenti.
- Definire chiaramente l’**interfaccia pubblica** della classe (metodi `public`) e mantenere i dati sensibili `private`.
- Usare l’ereditarietà solo quando ha senso logico, altrimenti preferire la **composizione** (un oggetto dentro un altro).

[Prossima lezione](2-2-oggetti-overloading)