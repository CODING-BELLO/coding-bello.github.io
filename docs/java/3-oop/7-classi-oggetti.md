---
title: Classi e oggetti
layout: default
parent: Coding in Java
nav_order: 7
has_children: true
---

# Classi e oggetti

La programmazione a oggetti è uno dei cuori di Java.

## Classe e oggetto

- una **classe** è un modello;
- un **oggetto** è un'istanza concreta di quel modello.

## Esempio

```java
public class Studente {
    String nome;
    int eta;
}
```

Creazione dell'oggetto:

```java
Studente s1 = new Studente();
s1.nome = "Luca";
s1.eta = 17;
```

## Perché servono

Le classi permettono di:
- rappresentare entità del mondo reale;
- raggruppare dati e comportamenti;
- costruire programmi più ordinati e modulari.

## Attributi e metodi

```java
public class Studente {
    String nome;
    int eta;

    void saluta() {
        System.out.println("Ciao, sono " + nome);
    }
}
```

## Uso

```java
Studente s1 = new Studente();
s1.nome = "Anna";
s1.eta = 18;
s1.saluta();
```

## Ricapitoliamo

- la classe è il progetto;
- l'oggetto è l'istanza concreta;
- gli attributi rappresentano dati;
- i metodi rappresentano comportamenti.

[Prossima lezione](8-costruttori-incapsulamento)
