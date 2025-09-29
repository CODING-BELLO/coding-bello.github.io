---
title: Stampe
layout: default
parent: Introduzione alla programmazione in C++
nav_order: 1
---
# Introduzione alle stampe in C++

In questo tutorial impareremo come mostrare del testo o dei valori sulla console utilizzando C++. Questo è uno dei primi passi per comunicare con l'utente attraverso un programma.

---

## Cos'è la stampa in C++?

La stampa è il modo in cui un programma mostra informazioni sullo schermo. In C++, per fare questo, usiamo un oggetto chiamato `std::cout`.

---

## Come funziona `std::cout`

`std::cout` è un oggetto speciale che rappresenta la console (lo schermo). Per mandare del testo sullo schermo, usiamo l'operatore `<<`, che si legge "inserisci".

Per esempio:

```cpp
std::cout << "Ciao, mondo!";
```

Questo codice dice al programma di mostrare la scritta "Ciao, mondo!" sullo schermo.

---

## Aggiungere un ritorno a capo

Dopo aver mostrato un messaggio, spesso vogliamo andare a capo, cioè iniziare una nuova riga. Per farlo, usiamo `std::endl`.

Esempio:

```cpp
std::cout << "Ciao, mondo!" << std::endl;
```

Questo mostra "Ciao, mondo!" e poi va a capo.

---

## Un programma completo di esempio

Ecco un esempio completo di un programma che mostra un messaggio sullo schermo:

```cpp
#include <iostream>  // Include la libreria per la stampa

int main() {
    std::cout << "Ciao, mondo!" << std::endl;  // Stampa il messaggio
    return 0;  // Termina il programma
}
```

---

## Riepilogo

- Per stampare usiamo `std::cout`.
- Per inserire il testo usiamo `<<`.
- Per andare a capo usiamo `std::endl`.
- Un programma C++ inizia sempre con `int main()`.

Ora sei pronto per iniziare a mostrare messaggi nei tuoi programmi C++!
