---
title: Primo programma
layout: default
parent: Coding in Java
nav_order: 2
---

# Il primo programma in Java

Iniziamo con il classico programma che stampa un messaggio.

```java
public class Main {
    public static void main(String[] args) {
        System.out.println("Hello world!");
    }
}
```

## Cosa stiamo vedendo

### `public class Main`
Definisce una **classe** chiamata `Main`.

### `public static void main(String[] args)`
È il punto di ingresso del programma.

Quando eseguiamo il programma Java, la JVM cerca proprio questo metodo.

### `System.out.println(...)`
Serve per stampare a schermo.

## Perché Java sembra più verboso

Rispetto a Python, Java richiede più struttura già dall'inizio.  
Questa cosa può sembrare pesante, ma ha un senso: ci abitua a pensare ai programmi come sistemi organizzati.

## Stampare testo e numeri

```java
System.out.println("Ciao");
System.out.println(42);
System.out.println(3.14);
```

## Differenza tra `print` e `println`

```java
System.out.print("Ciao ");
System.out.print("mondo");
```

stampa sulla stessa riga.

```java
System.out.println("Ciao");
System.out.println("mondo");
```

va a capo dopo ogni stampa.

## Commenti

```java
// commento su una riga

/*
   commento
   su più righe
*/
```

## Ricapitoliamo

- ogni programma Java vive dentro classi;
- il metodo `main` è il punto di partenza;
- `System.out.println()` serve per stampare;
- Java richiede una struttura più esplicita rispetto ad altri linguaggi.

[Prossima lezione](3-variabili-tipi)
