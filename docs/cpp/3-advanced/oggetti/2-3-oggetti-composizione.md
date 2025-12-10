---
title: Programmazione a oggetti 3
layout: default
nav_order: 35
parent: Coding in C++
---
# Programmazione a oggetti 3 - Composizione di oggetti

## Perché parlare di composizione?

La **composizione** rappresenta l’idea che un oggetto possa essere formato da **altri oggetti**.  
In pratica, si crea qualcosa di più complesso combinando più parti più semplici.

> Non tutto deve essere ereditato: spesso è meglio **usare un oggetto**, non estenderlo.  
> (Principio: **"has‑a" invece di "is‑a"**)

Esempio nella vita reale:

- Un **cliente** ha un **carrello**.
- Un carrello contiene **prodotti**.
- Un prodotto ha un **nome** e un **prezzo**.

Questa è composizione.

Non stiamo dicendo che un Cliente **è** un Carrello (sarebbe strano), ma che **ne possiede uno**.

## Primo step: definire un prodotto

Partiamo da qualcosa di semplice: un prodotto.

```cpp
class Prodotto {
public:
    string nome;
    double prezzo;

    Prodotto(string nome, double prezzo) : nome(nome), prezzo(prezzo) {}
};
```

Questo oggetto rappresenta una cosa singola che posso acquistare.

## Secondo step: il Carrello (versione semplice)

Un carrello è una raccolta di prodotti. Per ora non useremo array dinamici o vector: ci basta un array normale con una dimensione massima stabilita.

```cpp
class Carrello {
private:
    Prodotto prodotti[10]; // massimo 10 prodotti
    int count = 0;

public:
    void aggiungiProdotto(const Prodotto& p) {
        if (count < 10) {
            prodotti[count] = p;
            count++;
        } else {
            cout << "Carrello pieno!\n";
        }
    }

    double totale() {
        double somma = 0;
        for (int i = 0; i < count; i++) {
            somma += prodotti[i].prezzo;
        }
        return somma;
    }
};
```

Qui avviene la composizione: un **Carrello contiene Prodotti**.

## Terzo step: il Cliente

Il Cliente contiene un carrello, non serve ereditarietà qui.

```cpp
class Cliente {
public:
    string nome;
    Carrello carrello;

    Cliente(string nome) : nome(nome) {}

    void aggiungiAlCarrello(const Prodotto &p) {
        carrello.aggiungiProdotto(p);
    }

    void mostraTotale() {
        cout << "Totale carrello: €" << carrello.totale() << endl;
    }
};
```

## Utilizzo nel `main`

```cpp
int main() {
    Cliente c("Federico");

    Prodotto p1("Laptop", 1299.99);
    Prodotto p2("Mouse", 29.99);

    c.aggiungiAlCarrello(p1);
    c.aggiungiAlCarrello(p2);

    c.mostraTotale(); 
}
```

Output:

```
Totale carrello: €1329.98
```

## Idee chiave
- un oggetto può contenere altri oggetti
- relazione: **possiede** (has‑a)
- utile per modellare il mondo reale

## Quando usare la composizione?

Usala quando:

- un oggetto **dipende** da altri (come un auto con un motore)
- vuoi costruire sistemi modulari
- l’ereditarietà non ha senso logico:  
  “Un cliente è un carrello?” → No  
  “Un cliente ha un carrello?” → Sì

La composizione ti permette di creare oggetti complessi **mantenendo ordine, modularità e leggibilità**.

[Prossima lezione](2-4-oggetti-ereditarieta)