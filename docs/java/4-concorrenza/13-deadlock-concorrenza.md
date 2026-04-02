---
title: Deadlock e concorrenza
layout: default
parent: Coding in Java
nav_order: 13
---

# Deadlock e concorrenza

## Concorrenza e parallelismo

Due concetti vicini ma non identici:

- **concorrenza**: più attività avanzano nello stesso intervallo di tempo, anche alternandosi;
- **parallelismo**: più attività vengono eseguite davvero nello stesso istante su più unità di calcolo.

La concorrenza può essere reale o apparente.  
Il problema dei thread nasce già con la concorrenza, anche senza parallelismo fisico perfetto.

## Deadlock

Il **deadlock** è una situazione di blocco reciproco.

Due o più thread:
- possiedono una risorsa;
- aspettano una seconda risorsa;
- nessuno può proseguire.

## Esempio concettuale

Thread A:
1. prende risorsa 1
2. aspetta risorsa 2

Thread B:
1. prende risorsa 2
2. aspetta risorsa 1

Risultato: stallo.

## Esempio Java semplificato

```java
Object lock1 = new Object();
Object lock2 = new Object();

Thread t1 = new Thread(() -> {
    synchronized (lock1) {
        synchronized (lock2) {
            System.out.println("t1");
        }
    }
});

Thread t2 = new Thread(() -> {
    synchronized (lock2) {
        synchronized (lock1) {
            System.out.println("t2");
        }
    }
});
```

L'ordine opposto di acquisizione dei lock può generare deadlock.

## Come prevenirlo

Una strategia base super importante è:

**ordine globale nell'acquisizione delle risorse**

Cioè: tutti i thread devono richiedere i lock nello stesso ordine.

## Perché questi temi contano

Perché mostrano una cosa profonda:
scrivere programmi concorrenti non vuol dire solo "fare più cose".  
Vuol dire coordinare correttamente l'accesso a risorse condivise.

## Ricapitoliamo

- concorrenza e parallelismo non sono la stessa cosa;
- i thread introducono problemi reali di coordinamento;
- la race condition nasce da accessi concorrenti non protetti;
- il deadlock nasce da attese circolari tra risorse;
- una strategia base è imporre un ordine globale sui lock.
