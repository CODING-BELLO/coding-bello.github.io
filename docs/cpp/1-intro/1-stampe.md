---
title: Stampe
layout: default
nav_order: 2
parent: Coding in C++
---
# Stampe, comunichiamo con l'utente!

Il primo passo per far "parlare" il computer è mostrare messaggi sullo schermo. Questo permette di comprendere come funziona un programma e come comunica informazioni all'utente.

La **stampa** è il modo in cui un programma mostra informazioni. Senza la possibilità di stampare, non sarebbe possibile vedere i risultati dei calcoli o il comportamento del codice.

> Solitamente si italianizzano i verbi inglesi legati alla programmazione. In questo caso “print” diventa printare, “debug” diventa debuggare e così via. Chiedete scusa alla prof di inglese e ditele che sono solo modi comodi per parlare di azioni comuni nel coding! <3

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

## Ricapitoliamo

- `std::cout` seguito da `<<` stampa messaggi sullo schermo.
- `std::endl` crea un ritorno a capo.
- `using namespace std;` semplifica la scrittura di `cout` e `endl`.

[Prossima lezione](2-variabili_e_tipi)