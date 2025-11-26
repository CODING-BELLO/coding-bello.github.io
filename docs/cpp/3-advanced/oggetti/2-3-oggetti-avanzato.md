---
title: Programmazione a oggetti 2
layout: default
nav_order: 34
parent: Coding in C++
---
# Programmazione a oggetti 3 - Ereditarietà e polimorfismo

## Ereditarietà

#### Riuso e specializzazione

L’ereditarietà permette di creare nuove classi partendo da una classe esistente.  
La classe derivata **eredita automaticamente** attributi e metodi della classe base, così può riusarli senza riscriverli.  
Inoltre può **specializzare o modificare** il comportamento ridefinendo i metodi, oppure aggiungere nuovi attributi e funzionalità.  
Si usa quando esiste una relazione naturale “è un”: uno Studente *è una* Persona, quindi ha tutte le caratteristiche della Persona, più le sue specifiche.

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


## Polimorfismo

Il polimorfismo è la capacità di un oggetto di comportarsi in modi diversi pur condividendo la stessa interfaccia.  
In pratica, ti permette di scrivere codice che lavora con un *tipo generale* (per esempio `Persona`), ma che a runtime si adatta automaticamente al *tipo concreto* dell’oggetto (`Studente`, `Docente`, ecc.).  
È quello che rende possibile trattare oggetti diversi allo stesso modo, lasciando però che ciascuno esegua la propria versione di un metodo.

Quando ereditiamo da una classe base, spesso vogliamo che le classi derivate possano **specializzare** alcuni comportamenti. Qui entra in gioco il **polimorfismo**, una delle idee chiave dell’OOP:  
> oggetti diversi possono rispondere allo stesso messaggio in modi differenti.

### Perché serve?
Immagina di avere un puntatore alla classe base, ad esempio `Persona* p`.  
Quel puntatore potrebbe in realtà riferirsi a:
- una `Persona`
- uno `Studente`

Il punto è: **quando chiamo `p->presenta()`, quale versione voglio?**  
Quella di Persona o quella di Studente?

### Early binding vs Late binding
Di default, C++ sceglie la funzione in base al **tipo del puntatore** (early binding).  
Per ottenere un comportamento più flessibile, vogliamo invece che la decisione avvenga **a runtime**, guardando il tipo reale dell’oggetto (late binding).

Per abilitarlo, si usa la keyword **`virtual`**.

### Esempio senza `virtual`

```cpp
class Persona {
public:
    void presenta() {
        cout << "Sono una persona." << endl;
    }
};

class Studente : public Persona {
public:
    void presenta() {
        cout << "Sono uno studente!" << endl;
    }
};

int main() {
    Persona* p = new Studente();
    p->presenta();  // stampa: "Sono una persona."
}
```

Il tipo del puntatore è `Persona*`, quindi viene chiamata la versione di Persona.

### Con `virtual`

```cpp
class Persona {
public:
    virtual void presenta() {
        cout << "Sono una persona." << endl;
    }
};

class Studente : public Persona {
public:
    void presenta() override {
        cout << "Sono uno studente!" << endl;
    }
};

int main() {
    Persona* p = new Studente();
    p->presenta();  // stampa: "Sono uno studente!"
}
```

Ora la funzione è scelta in base al tipo reale dell’oggetto (`Studente`), non al tipo del puntatore.


### Idea chiave
Una funzione virtuale dice al compilatore:  
> “questa funzione può cambiare nelle classi derivate; scegli quella giusta in base all’oggetto vero.”


# Riepilogo

- **Ereditarietà**: permette a una classe derivata di riutilizzare e specializzare attributi e metodi della classe base.
- **Polimorfismo e funzioni virtuali**: consente a oggetti diversi di rispondere allo stesso metodo in modi differenti, grazie al late binding abilitato da `virtual`.


[Prossima lezione](../3-strutture-dati)