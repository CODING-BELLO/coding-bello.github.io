---
title: Programmazione a oggetti 2
layout: default
nav_order: 34
parent: Coding in C++
---
# Programmazione a oggetti 2 - Overloading


## Overloading

L’**overloading** (sovraccarico) permette di definire più funzioni o metodi con lo **stesso nome**, purché abbiano **parametri diversi** (per tipo o per numero).  
Non ha nulla a che fare con l’ereditarietà: avviene **all’interno della stessa classe** ed è risolto **a compile-time**.

### Perché è utile?
Permette di mantenere un nome coerente per operazioni simili, cambiando solo cosa accettano in input.

### Esempio

```cpp
class Math {
public:
    int somma(int a, int b) {
        return a + b;
    }

    double somma(double a, double b) {
        return a + b;
    }

    int somma(int a, int b, int c) {
        return a + b + c;
    }
};
```

Tutte queste funzioni si chiamano `somma`, ma il compilatore sceglie quella corretta in base ai **parametri**.

### Idee chiave
- stesso nome  
- parametri diversi  
- scelta a *compile-time*  
- nessun polimorfismo dinamico  


## Overloading degli operatori

Oltre a funzioni e metodi, in C++ è possibile ridefinire il comportamento degli **operatori** (come `+`, `-`, `==`, `<<`…), permettendo di usarli con gli oggetti e avere un comportamento personalizzato.

Questo rende il codice più naturale e leggibile, perché è possibile scrivere:

```cpp
v1 + v2;
```

anche se `v1` e `v2` sono oggetti.

### Esempio 1: somma tra oggetti

Immaginiamo una classe `Punto` che rappresenta un punto nel piano.

```cpp
class Punto {
public:
    int x, y;

    Punto(int x, int y) : x(x), y(y) {}
};

int main() {
    Punto a(2, 3);
    Punto b(4, 1);

    Punto c = a + b; //somma tra due punti: comportamento indefinito -> errore
}
```


Aggiungendo all'interno della classe la seguente funzione, viene ridefinito l'operatore +. 
```cpp
class Punto {
public:
    int x, y;

    Punto(int x, int y) : x(x), y(y) {}

    Punto operator+(const Punto &altroPunto) {
        return Punto(x + altroPunto.x, y + altroPunto.y);
    }
};
```

Qui `operator+` è una funzione speciale che dice al compilatore: quando vedi `oggetto1 + oggetto2`, chiama il metodo `operator+`.

Questa istruzione quindi:
```cpp
Punto c = a + b;
```
viene tradotta concettualmente in:
```cpp
Punto c = a.operator+(b);
```

### Esempio 2: ridefinire la stampa con cout

Nello stesso modo in cui possiamo ridefinire l’operatore `+`, possiamo ridefinire anche la **stampa di un oggetto** quando utilizziamo `cout <<`.

Questo significa che possiamo scrivere:
```cpp
cout << a;
```
e decidere noi come deve apparire l’oggetto a schermo.

Esempio con la classe `Punto`:

```cpp
class Punto {
public:
    int x, y;

    Punto(int x, int y) : x(x), y(y) {}

    friend ostream& operator<<(ostream &os, const Punto &p) {
        os << "(" << p.x << ", " << p.y << ")";
        return os;
    }
};
```

Ora possiamo fare:
```cpp
Punto p(3, 5);
cout << p;
```

e verrà stampato:
```
(3, 5)
```

Non c’è nessuna magia nella programmazione: stiamo solo dicendo al compilatore **cosa fare quando incontra `cout << oggetto`**.  
Stiamo nascondendo la complessità dietro una sintassi più leggibile, ma il comportamento è sempre definito in modo esplicito da noi.


[Prossima lezione](2-3-oggetti-composizione)