---
title: Stack e Heap
layout: default
nav_order: 32
parent: Coding in C++
---

# Stack e Heap in C++

## Due aree principali della memoria

In C++ la memoria dei nostri programmi viene principalmente gestita in due zone:

| Zona | Chi la gestisce | Quando viene allocata | Quando viene liberata |
|------|-----------------|------------------------|------------------------|
| **Stack** | il compilatore | quando una variabile entra nello scope | automaticamente quando esce dallo scope |
| **Heap** | il programmatore (manuale) | quando viene usata una `new` | deve essere liberata manualmente (`delete`) |

---

## Stack

Lo stack è l'area in cui vivono le variabili normali che dichiariamo dentro funzioni o blocchi `{ }`.

```cpp
int main() {
    int x = 10;  // x vive nello stack
} // qui x viene distrutto automaticamente
```

Le variabili sullo stack non richiedono nessuna azione manuale: vengono gestite dal C++ automaticamente.

- è veloce
- è gestito automaticamente
- quando lo scope finisce → la variabile muore

Lo stack è perfetto per variabili locali e oggetti che "vivono" solamente dentro una funzione. Per questo in C++ è comune creare oggetti semplicemente scrivendo il loro nome (senza new): questa scelta è considerata sicura e non comporta rischi di dimenticare di liberare memoria. Quando si esce dalla funzione o dal blocco, tutto quello che si trova sullo stack viene liberato automaticamente.

---

## Heap

Nell'heap la memoria viene richiesta e gestita in modo dinamico.  
Questa zona è utile quando servono dati che non devono sparire appena termina una funzione, ma devono restare disponibili più a lungo.

Se però la memoria non viene restituita correttamente al sistema, rimane occupata e inutilizzabile fino a fine programma. Questo problema si chiama *memory leak*.

Nei programmi molto semplici, o su computer moderni con tanta RAM, questi sprechi possono non apparire immediatamente. Ma in sistemi con poca memoria (come sistemi embedded, microcontrollori, o piccoli dispositivi) ogni spreco pesa e può portare rallentamenti o malfunzionamenti.

Più avanti verranno introdotti strumenti per gestire questa memoria in modo corretto e sicuro.

### Attenzione importante: dangling pointer

Se dentro una funzione dichiari una variabile locale sullo stack e provi a ritornare un puntatore verso quella variabile, quel puntatore diventa immediatamente pericoloso. Quando la funzione termina, lo stack frame viene distrutto e quella variabile non esiste più.

```cpp
int* crea() {
    int x = 10;
    return &x;   // ERRORE: x era sullo stack, fuori da questa funzione non esiste più
}
```

Il puntatore che ritorna non punta più ad una memoria valida → questo si chiama *dangling pointer* e porta a undefined behavior.

---

## Concetto chiave


Non tutta la memoria vive allo stesso modo: alcune variabili vivono automaticamente e muoiono da sole (stack), altre devi gestirle tu con attenzione (heap).

- stack → automatico  
- heap → manuale

---

### Esempio pratico di funzioni: stack vs heap

```cpp
#include <iostream>
using namespace std;

// funzione che ritorna un puntatore a variabile sullo stack
int* creaStack() {
    int x = 42;        // vive nello stack
    return &x;         
}

// funzione che ritorna un puntatore a variabile nell'heap
int* creaHeap() {
    int* p = new int(99); // vive nell'heap
    return p;             // ok, rimane valida finché non facciamo delete
}

int main() {
    int* pStack = creaStack();
    int* pHeap  = creaHeap();

    cout << "Valore stack: " << *pStack << endl; // comportamento indefinito
    cout << "Valore heap: " << *pHeap << endl;   // stampa correttamente 99
}
```

Nell'esempio sopra:
- `creaStack()` ritorna un puntatore a una variabile sullo stack → questo porta a *dangling pointer*.
- `creaHeap()` ritorna un puntatore a una variabile nell'heap → funziona correttamente 

Questo mostra chiaramente la differenza di *lifetime*: le variabili sullo stack vivono solo durante la funzione, mentre quelle nell'heap rimangono finché non le liberiamo manualmente.

---

### Soluzione preferibile: tornare un valore invece di un puntatore

```cpp
#include <iostream>
using namespace std;

// funzione che ritorna un valore direttamente
int creaValore() {
    int x = 42; // vive nello stack, ma viene copiato nel return
    return x;   // sicuro, non c'è dangling pointer
}

int main() {
    int valore = creaValore();
    cout << "Valore restituito: " << valore << endl; // stampa correttamente 42
}
```

In questo caso:
- La variabile `x` vive nello stack, ma viene **copiata** nel momento del return.
- Non ci sono puntatori coinvolti → niente dangling pointer.
- Questa è la soluzione più sicura e consigliata in C++ quando possibile, perché sfrutta lo stack in modo automatico e sicuro.

[Prossima lezione](2-oggetti)