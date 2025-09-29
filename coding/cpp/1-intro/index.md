---
title: Introduzione alla programmazione in C++
layout: default
nav_order: 1
parent: Coding in C++
has_children: true
---

## Da zero

Un programma C++ deve sempre avere una funzione principale chiamata `main`. Tutto quello che viene scritto **all'interno del `main`** viene eseguito dal computer, riga per riga.

Ecco un esempio di programma vuoto:

```cpp
#include <iostream>

int main() {
    // Istruzioni da eseguire qui
    return 0;
}
```

Per esempio, questo primo programma mostra un messaggio sullo schermo (torneremo su queste istruzioni più avanti)

```cpp
#include <iostream>

int main() {
    std::cout << "Hello world!" << std::endl;
    return 0;
}
```


# Esecuzione delle istruzioni

Anche se non sono ancora conosciuti tutti i dettagli del linguaggio, è importante capire che il codice all'interno di ```main``` viene sempre **eseguito dall'alto verso il basso in sequenza**.

# Commenti

Non tutto quello che scriviamo all'interno di un programma diventa una istruzione eseguibile. Possiamo inserire **commenti** per spiegare il codice, renderlo più chiaro e più facile da leggere.

**Commenti su una riga:** I commenti su una singola riga si scrivono con `//`. Tutto ciò che segue le due barre viene ignorato dal compilatore:

```cpp
#include <iostream>

int main() {
    // Questo è un commento su una riga
    std::cout << "Hello world!" << std::endl; // Commento alla fine di una istruzione
    return 0;
}
```

**Commenti su più righe:**
E' anche possibile inserire commenti multilinea

```cpp
#include <iostream>

int main() {
    /*
      Questo è un commento
      su più righe.
      Utile per spiegazioni più lunghe
      o note dettagliate.
    */
    std::cout << "Hello world!" << std::endl;
    return 0;
}
```

[Prossima lezione: stampe](2-stampe)