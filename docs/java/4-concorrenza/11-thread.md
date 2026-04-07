---
title: Thread
layout: default
parent: Java
nav_order: 11
has_children: true
---

# Thread

## Programma, processo, thread

Prima di parlare di thread bisogna distinguere tre concetti:

- **programma**: sequenza di istruzioni, entità statica;
- **processo**: programma in esecuzione;
- **thread**: flusso di esecuzione interno a un processo.

Un processo può contenere uno o più thread.

## Perché i thread esistono

Servono per svolgere più attività nello stesso programma:
- interfaccia grafica + calcoli;
- download + aggiornamento schermata;
- gestione di client multipli;
- compiti paralleli o concorrenti.

## Creare un thread con `Thread`

```java
public class MioThread extends Thread {
    public void run() {
        for (int i = 0; i < 5; i++) {
            System.out.println("Thread in esecuzione: " + i);
        }
    }
}
```

Uso:

```java
MioThread t = new MioThread();
t.start();
```

## Perché si usa `start()` e non `run()`

- `run()` esegue il metodo come una chiamata normale;
- `start()` crea davvero un nuovo thread di esecuzione.

## Con `Runnable`

Spesso è preferibile implementare `Runnable`:

```java
public class Compito implements Runnable {
    public void run() {
        System.out.println("Sto lavorando in un thread");
    }
}
```

```java
Thread t = new Thread(new Compito());
t.start();
```

## Ricapitoliamo

- il thread è un flusso di esecuzione;
- più thread permettono più attività nello stesso processo;
- `start()` avvia davvero il thread;
- `Runnable` è spesso una soluzione elegante.

[Prossima lezione](12-race-condition-synchronized)
