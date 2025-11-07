---
title: Puntatori
layout: default
nav_order: 31
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

---

## Concetto chiave


Non tutta la memoria vive allo stesso modo: alcune variabili vivono automaticamente e muoiono da sole (stack), altre devi gestirle tu con attenzione (heap).

- stack → automatico  
- heap → manuale

---

## Prossima lezione

[1 - Puntatori](1-puntatori)