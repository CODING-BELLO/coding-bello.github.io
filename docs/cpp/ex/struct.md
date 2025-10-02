---
title: Esercizi struct
layout: default
nav_order: 3
parent: Esercizi in C++
---

# Esercizi costrutto struct in C++

## **Esercizio 1**

**Domanda:** Cosa stampa questo programma? Che valori assumono i campi non inizializzati?

```cpp
#include <iostream>
using namespace std;

struct Studente {
    string nome;
    int eta;
    float media;
};

int main() {
    Studente s1 = {"Marco", 17};
    Studente s2 = {"Luca"};
    Studente s3 = {};
    
    cout << "s1: " << s1.nome << ", " << s1.eta << ", " << s1.media << endl;
    cout << "s2: " << s2.nome << ", " << s2.eta << ", " << s2.media << endl;
    cout << "s3: " << s3.nome << ", " << s3.eta << ", " << s3.media << endl;
    
    return 0;
}
```

***

## **Esercizio 2**

**Domanda:** Cosa stampa questo programma? Come vengono valutate le espressioni?

```cpp
#include <iostream>
using namespace std;

struct Punto {
    int x, y;
};

int main() {
    Punto p = {3, 4};
    Punto array[3] = { {1, 2}, {3, 4}, {5, 6} };
    
    cout << p.x + p.y << endl;
    cout << array[1].x * 2 << endl;
    cout << array[0].x + array[2].y << endl;
    
    return 0;
}
```

***

## **Esercizio 3**

**Domanda:** Il seguente programma compila ed esegue? Correggerlo in caso di errori

```cpp
#include <iostream>
using namespace std;

struct Coordinate {
    int x, y;
};

int main() {
    Coordinate p1 = {5, 3};
    Coordinate p2 = {5, 3};
    Coordinate p3 = p1;
    
    if(p1.x == p2.x)
    {
        cout << "p1 e p2 sono uguali" << endl;
    } else {
        cout << "p1 e p2 sono diversi" << endl;
    }
    
    return 0;
}
```

***

## **Esercizio 4**

**Domanda:** Il seguente programma compila ed esegue? Correggerlo in caso di errori

```cpp
#include <iostream>
using namespace std;

struct Indirizzo {
    string via;
    int numero;
};

struct Persona {
    string nome;
    Indirizzo casa;
    int eta;
};

int main() {
    Persona p;
    p.nome = "Anna";
    p.casa.via = "Via Roma";
    p.casa.numero = 42;
    p.eta = 25;
    
    cout << p.nome << " abita in " << p.via << " " << p.numero << endl;
    cout << "Ha " << p.eta << " anni" << endl;
    
    return 0;
}
```

***

## **Esercizio 5**

**Domanda:** Il seguente programma compila ed esegue? Correggerlo in caso di errori

```cpp
#include <iostream>
using namespace std;

struct Voto {
    string materia;
    int valore;
};

int main() {
    Voto voti[4] = {
        {"Matematica", 8},
        {"Italiano", 7},
        {"Storia", 9}
    };
    
    voti[3].materia = "Inglese";
    voti[3].valore = 6;
    
    cout << voti[3].materia << ": " << voti[3].valore << endl;
    
    return 0;
}
```

***


## **Esercizio 6**

**Domanda:** Cosa stampa questo programma? Motivare la risposta

```cpp

#include <iostream>
using namespace std;

struct Studente {
    string nome;
    int voti[5];
};

int main() {
    Studente c1 = {"Marco", {8, 7, 9, 6, 10} };
    Studente c2 = {"Lucia", {8, 7, 7, 8, 6} };
    
    cout << "Studente " << c1.nome << ":" << endl;
    for(int i = 0; i < 5; i++) {
        if(c1.voti[i] < 5){  }
        cout << "Voto " << i << ": " << c1.voti[i] << endl;
    }
    
    
    
    return 0;
}
```

<!--
**Risposta:** 

***

## **Esercizio 7: Struct come parametri - Copia vs riferimento**

**Codice da analizzare:**

```cpp
#include <iostream>
using namespace std;

struct Contatore {
    int valore;
};

void incrementa1(Contatore c) {
    c.valore++;
    cout << "Dentro incrementa1: " << c.valore << endl;
}

void incrementa2(Contatore& c) {
    c.valore++;
    cout << "Dentro incrementa2: " << c.valore << endl;
}

int main() {
    Contatore cnt = {5};
    
    cout << "Valore iniziale: " << cnt.valore << endl;
    
    incrementa1(cnt);
    cout << "Dopo incrementa1: " << cnt.valore << endl;
    
    incrementa2(cnt);
    cout << "Dopo incrementa2: " << cnt.valore << endl;
    
    return 0;
}
```

**Domanda:** Che differenza c'è tra `incrementa1` e `incrementa2`? Cosa stampa il programma?

**Risposta:** `incrementa1` riceve una **COPIA** della struct, quindi le modifiche non si riflettono sulla variabile originale. `incrementa2` riceve un **RIFERIMENTO**, quindi modifica direttamente l'originale.

Il programma stampa:

- Valore iniziale: 5
- Dentro incrementa1: 6
- Dopo incrementa1: 5 ← **invariato!**
- Dentro incrementa2: 6
- Dopo incrementa2: 6 ← **modificato!**

***

## **Esercizio 8: Sizeof con struct - Calcolo della memoria**

**Codice da analizzare:**

```cpp
#include <iostream>
using namespace std;

struct Piccola {
    char c;
    int i;
};

struct Media {
    int a, b, c;
};

struct Grande {
    double d;
    char array[10];
    int numero;
};

int main() {
    cout << "sizeof(char): " << sizeof(char) << " byte" << endl;
    cout << "sizeof(int): " << sizeof(int) << " byte" << endl;
    cout << "sizeof(double): " << sizeof(double) << " byte" << endl;
    
    cout << "\nsizeof(Piccola): " << sizeof(Piccola) << " byte" << endl;
    cout << "sizeof(Media): " << sizeof(Media) << " byte" << endl;
    cout << "sizeof(Grande): " << sizeof(Grande) << " byte" << endl;
    
    return 0;
}
```

**Domanda:** Perché `sizeof(Piccola)` potrebbe non essere uguale a `sizeof(char) + sizeof(int)`?

**Risposta:** `sizeof(Piccola)` potrebbe essere maggiore della somma dei suoi campi a causa del **PADDING** (allineamento in memoria). Il compilatore può inserire byte extra per ottimizzare l'accesso alla memoria.

Tipicamente:

- char: 1 byte, int: 4 byte, double: 8 byte
- Ma Piccola potrebbe occupare **8 byte invece di 5** (1+4) per l'allineamento

Il sizeof di una struct **include anche il padding**!

***

## **Esercizio 9: Accesso con puntatori - Notazione freccia vs punto**

**Codice da analizzare:**

```cpp
#include <iostream>
using namespace std;

struct Prodotto {
    string nome;
    float prezzo;
};

int main() {
    Prodotto p = {"Laptop", 799.99};
    Prodotto* ptr = &p;
    
    cout << "Accesso diretto:" << endl;
    cout << p.nome << " - " << p.prezzo << "€" << endl;
    
    cout << "\nAccesso con puntatore (metodo 1):" << endl;
    cout << (*ptr).nome << " - " << (*ptr).prezzo << "€" << endl;
    
    cout << "\nAccesso con puntatore (metodo 2):" << endl;
    cout << ptr->nome << " - " << ptr->prezzo << "€" << endl;
    
    ptr->prezzo = 699.99;
    cout << "\nDopo modifica tramite puntatore:" << endl;
    cout << p.prezzo << "€" << endl;
    
    return 0;
}
```

**Domanda:** Che differenza c'è tra `(*ptr).nome` e `ptr->nome`? Cosa succede quando modifico `ptr->prezzo`?

**Risposta:** `(*ptr).nome` e `ptr->nome` sono **equivalenti**! L'operatore `->` è una scorciatoia per `(*ptr).`

Il programma stampa tre volte la stessa cosa: "Laptop - 799.99€"

Quando modifico `ptr->prezzo`, sto modificando direttamente il campo della struct originale p, quindi l'ultima stampa mostra **699.99€**. Il puntatore punta alla stessa area di memoria!

***

## **Esercizio 10: Struct temporanee - Creazione al volo**

**Codice da analizzare:**

```cpp
#include <iostream>
using namespace std;

struct Coordinate {
    int x, y;
};

void stampaCoordinate(Coordinate c) {
    cout << "(" << c.x << ", " << c.y << ")" << endl;
}

Coordinate creaOrigine() {
    return {0, 0};
}

int main() {
    stampaCoordinate({5, 3});
    stampaCoordinate({10, -2});
    
    Coordinate origine = creaOrigine();
    stampaCoordinate(origine);
    
    Coordinate somma = {5 + 3, 2 * 4};
    stampaCoordinate(somma);
    
    return 0;
}
```

**Domanda:** Come funziona la creazione di struct temporanee con `{5, 3}`? Cosa fa `creaOrigine()`?

**Risposta:** È possibile creare **struct temporanee** usando la sintassi `{valore1, valore2}` direttamente come parametro. Il compilatore crea automaticamente una struct Coordinate temporanea.

Il programma stampa:

- (5, 3)
- (10, -2)
- (0, 0)
- (8, 8)

`creaOrigine()` restituisce una struct inizializzata con `{0, 0}`. Si possono anche usare **espressioni** nei valori: `{5 + 3, 2 * 4}` diventa `{8, 8}`.
-->