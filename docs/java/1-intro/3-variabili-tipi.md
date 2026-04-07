---
title: Variabili e tipi
layout: default
parent: Java
nav_order: 3
---

# Variabili e tipi in Java

Una **variabile** è un nome associato a un valore.

In Java, a differenza di Python, il **tipo** deve essere dichiarato.

## Dichiarazione e inizializzazione

```java
int eta = 17;
double altezza = 1.78;
String nome = "Luca";
boolean isStudente = true;
```

## Tipi primitivi principali

- `int` → numeri interi
- `double` → numeri decimali
- `char` → singolo carattere
- `boolean` → `true` o `false`

## Tipo non primitivo molto importante

- `String` → testo

## Perché il tipo è importante

Il tipo dice al compilatore:
- che genere di dato stiamo memorizzando;
- quali operazioni hanno senso;
- quanta memoria serve;
- come controllare eventuali errori.

## Esempi

```java
int a = 10;
int b = 3;
int somma = a + b;

System.out.println(somma);
```

## Attenzione alle assegnazioni

```java
int numero = 5;
numero = 9;
```

La variabile può cambiare valore, ma deve restare compatibile con il suo tipo.

Questo non va bene:

```java
// int numero = "ciao";   // errore
```

## Stringhe

```java
String nome = "Anna";
System.out.println(nome);
```

Concatenazione:

```java
String nome = "Anna";
int eta = 18;

System.out.println("Ciao " + nome + ", hai " + eta + " anni");
```

## Ricapitoliamo

- in Java il tipo si dichiara;
- i tipi primitivi rappresentano valori semplici;
- `String` serve per il testo;
- il tipo aiuta il compilatore a controllare il programma.

[Prossima lezione](../2-fondamenti/4-operatori-espressioni)
