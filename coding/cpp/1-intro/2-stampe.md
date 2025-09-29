---
title: Stampe
layout: default
parent: Introduzione alla programmazione in C++
nav_order: 1
---
# Stampe in C++

Il primo passo per far "parlare" il computer è mostrare messaggi sullo schermo. Questo permette di comprendere come funziona un programma e come comunica informazioni all'utente.

---

## Il primo programma completo in C++

```cpp
#include <iostream>  // Include la libreria per la stampa

int main() {
    std::cout << "Hello world!" << std::endl;  // Stampa il messaggio
    return 0;  // Termina il programma
}
```

**Funzionamento del programma:**

1. `#include <iostream>` importa la libreria necessaria per comunicare con la console.
2. `int main()` è la funzione principale da cui parte ogni programma C++.
3. `std::cout` stampa il messaggio `"Hello world!"` sullo schermo.
4. `std::endl` manda il cursore a capo, creando una nuova riga.
5. `return 0;` segnala la terminazione corretta del programma.

---

## Stampa e console

La stampa è il modo in cui un programma mostra informazioni. Senza la possibilità di stampare, non sarebbe possibile vedere i risultati dei calcoli o il comportamento del codice.


---

## Come funziona `std::cout`

L'operatore `<<` (si legge "inserisci") serve a mandare testo o valori nella console.

Esempio:

```cpp
std::cout << "Hello world!";
```

È possibile concatenare più elementi:

```cpp
std::cout << "Hello " << "world!";
```

---

## Ritorno a capo

Quando si mostrano più messaggi consecutivi, spesso è necessario andare a capo, cioè iniziare una nuova riga. Senza indicazioni, più istruzioni `std::cout` vengono visualizzate una dopo l’altra sulla stessa riga, senza spazi o interruzioni.

Esempio senza ritorno a capo:

```cpp
std::cout << "Hello";
std::cout << "world!";
```

**Output:**

```
Helloworld! //sbagliato!
```

Come si vede, i messaggi vengono uniti sulla stessa riga. Per separare le righe e migliorare la leggibilità, si usa `std::endl`:

```cpp
std::cout << "Hello" << std::endl;
std::cout << "world!" << std::endl;
```

**Output:**

```
Hello
world!
```

`std::endl` sposta il cursore all’inizio della riga successiva, creando un chiaro ritorno a capo.

---

## Semplificazione con `using namespace std;`

Scrivere sempre `std::cout` può risultare lungo. Aggiungendo all'inizio del codice:

```cpp
using namespace std;
```

è possibile scrivere direttamente:

```cpp
cout << "Hello world!" << endl;
```

---

## Riepilogo

- `std::cout` seguito da `<<` stampa messaggi sullo schermo.
- `std::endl` crea un ritorno a capo.
- `using namespace std;` semplifica la scrittura di `cout` e `endl`.