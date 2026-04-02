---
title: Race condition e synchronized
layout: default
parent: Coding in Java
nav_order: 12
---

# Race condition e `synchronized`

## Cos'è una race condition

Una **race condition** si verifica quando più thread accedono e modificano una risorsa condivisa senza coordinarsi bene.

Il risultato finale dipende dall'ordine temporale delle operazioni.

In pratica: il programma non è deterministico come pensavamo.

## Esempio classico

```java
public class Contatore {
    int valore = 0;

    public void incrementa() {
        valore++;
    }
}
```

A prima vista sembra innocuo.  
Ma `valore++` non è una singola magia atomica: sotto sotto è una sequenza di passi:
- leggi il valore;
- calcola il nuovo valore;
- riscrivi il risultato.

Se due thread si intrecciano male, si possono perdere aggiornamenti.

## Esempio concettuale

Se due thread incrementano 1000 volte ciascuno, ci aspetteremmo 2000.  
In presenza di race condition potremmo ottenere meno.

## Risorsa condivisa e sezione critica

La parte di codice che accede a una risorsa condivisa in modo delicato si chiama **sezione critica**.

Se due thread entrano insieme nella stessa sezione critica, possono nascere problemi.

## Mutua esclusione con `synchronized`

```java
public class Contatore {
    int valore = 0;

    public synchronized void incrementa() {
        valore++;
    }
}
```

Con `synchronized`, un solo thread alla volta può eseguire quel metodo sullo stesso oggetto.

## Blocco `synchronized`

```java
public void incrementa() {
    synchronized (this) {
        valore++;
    }
}
```

## Idea chiave

`synchronized` non rende il programma "magicamente veloce".  
Lo rende **corretto** quando c'è una sezione critica.

## Ricapitoliamo

- race condition = accesso concorrente non coordinato a dati condivisi;
- il problema nasce da interleaving sfortunati;
- la sezione critica va protetta;
- `synchronized` realizza mutua esclusione.

[Prossima lezione](13-deadlock-concorrenza)
