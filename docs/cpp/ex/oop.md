---
title: Esercizi Oggetti
layout: default
nav_order: 6
parent: Esercizi in C++
nav_exclude: true
---

# Esercizi di Lettura Codice - Oggetti in C++

## **Esercizio 1**

**Domanda:** Il seguente programma compila ed esegue? Cosa stampa? Spiega la differenza tra passaggio per valore e per riferimento degli oggetti.

```cpp
#include <iostream>
using namespace std;

class Punto {
public:
    int x, y;
    Punto(int a, int b) : x(a), y(b) {}
    void sposta(int dx, int dy) {
        x += dx; y += dy;
    }
};

void spostaPerValore(Punto p) {
    p.sposta(10, 10);
}

void spostaPerRiferimento(Punto& p) {
    p.sposta(10, 10);
}

int main() {
    Punto p(1, 1);
    spostaPerValore(p);
    cout << "Dopo spostaPerValore: (" << p.x << ", " << p.y << ")" << endl;
    spostaPerRiferimento(p);
    cout << "Dopo spostaPerRiferimento: (" << p.x << ", " << p.y << ")" << endl;
    return 0;
}
```

***

## **Esercizio 2**

**Domanda:** Osserva il seguente codice. Quante volte viene chiamato il costruttore e il distruttore? Qual è l’ordine di chiamata? Spiega cosa succede.

```cpp
#include <iostream>
using namespace std;

class Test {
public:
    Test() { cout << "Costruttore\n"; }
    ~Test() { cout << "Distruttore\n"; }
};

void funzione() {
    Test t;
    cout << "Dentro funzione\n";
}

int main() {
    cout << "Inizio main\n";
    funzione();
    cout << "Fine main\n";
    return 0;
}
```

***

## **Esercizio 3**

**Domanda:** Il metodo `getX` è dichiarato `const`. Cosa significa? Il codice compila? Cosa succede se proviamo a modificare `x` dentro `getX`?

```cpp
#include <iostream>
using namespace std;

class Punto {
    int x, y;
public:
    Punto(int a, int b) : x(a), y(b) {}
    int getX() const {
        // x = 10; // Cosa succede se decommentiamo questa riga?
        return x;
    }
};

int main() {
    Punto p(5, 6);
    cout << p.getX() << endl;
    return 0;
}
```

***

## **Esercizio 4**

**Domanda:** Il seguente programma utilizza un oggetto come parametro e come valore di ritorno. Cosa stampa? Spiega il comportamento del ritorno per valore.

```cpp
#include <iostream>
using namespace std;

class Numero {
    int val;
public:
    Numero(int v) : val(v) {}
    Numero raddoppia() {
        return Numero(val * 2);
    }
    int getVal() const { return val; }
};

Numero modifica(Numero n) {
    return n.raddoppia();
}

int main() {
    Numero n(3);
    Numero m = modifica(n);
    cout << "n: " << n.getVal() << ", m: " << m.getVal() << endl;
    return 0;
}
```

***

## **Esercizio 5**

**Domanda:** Considera la classe `ArrayDinamico`. Il programma compila? Cosa succede alla fine del `main`? Spiega il problema relativo al copy constructor implicito.

```cpp
#include <iostream>
using namespace std;

class ArrayDinamico {
    int* dati;
    int size;
public:
    ArrayDinamico(int s) : size(s) {
        dati = new int[size];
        for(int i=0; i<size; i++) dati[i] = i;
        cout << "Costruttore chiamato\n";
    }
    ~ArrayDinamico() {
        delete[] dati;
        cout << "Distruttore chiamato\n";
    }
    void stampa() {
        for(int i=0; i<size; i++) cout << dati[i] << " ";
        cout << endl;
    }
};

void funzione(ArrayDinamico a) {
    a.stampa();
}

int main() {
    ArrayDinamico arr(5);
    funzione(arr);
    arr.stampa();
    return 0;
}
```

***

## **Esercizio 6**

**Domanda:** Nel seguente codice, la variabile membro `val` è ombreggiata dal parametro del costruttore. Il codice compila? Qual è il valore di `val` dopo la costruzione? Come correggere il problema?

```cpp
#include <iostream>
using namespace std;

class Valore {
    int val;
public:
    Valore(int val) {
        val = val;
    }
    int getVal() const { return val; }
};

int main() {
    Valore v(10);
    cout << v.getVal() << endl;
    return 0;
}
```

***

## **Esercizio 7**

**Domanda:** Il seguente codice mostra un esempio di copy constructor personalizzato per una classe con risorsa dinamica. Spiega cosa succede se non fosse definito. Cosa stampa il programma?

```cpp
#include <iostream>
using namespace std;

class Stringa {
    char* s;
public:
    Stringa(const char* str) {
        int len = 0;
        while(str[len] != '\0') len++;
        s = new char[len + 1];
        for(int i=0; i<=len; i++) s[i] = str[i];
        cout << "Costruttore\n";
    }
    Stringa(const Stringa& other) {
        int len = 0;
        while(other.s[len] != '\0') len++;
        s = new char[len + 1];
        for(int i=0; i<=len; i++) s[i] = other.s[i];
        cout << "Copy constructor\n";
    }
    ~Stringa() {
        delete[] s;
        cout << "Distruttore\n";
    }
    void stampa() const {
        cout << s << endl;
    }
};

Stringa creaStringa() {
    Stringa temp("ciao");
    return temp;
}

int main() {
    Stringa s1 = creaStringa();
    s1.stampa();
    return 0;
}
```