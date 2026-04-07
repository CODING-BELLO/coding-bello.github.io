---
title: Ereditarietà e polimorfismo
layout: default
parent: Java
nav_order: 9
---

# Ereditarietà e polimorfismo

## Ereditarietà

L'ereditarietà permette a una classe di derivare da un'altra.

```java
public class Persona {
    protected String nome;

    public void saluta() {
        System.out.println("Ciao");
    }
}
```

```java
public class Studente extends Persona {
    private int classe;
}
```

La classe `Studente` eredita attributi e metodi di `Persona`.

## Override

Possiamo ridefinire un metodo ereditato.

```java
public class Studente extends Persona {
    @Override
    public void saluta() {
        System.out.println("Ciao, sono uno studente");
    }
}
```

## Polimorfismo

Il polimorfismo permette di trattare oggetti diversi attraverso un riferimento del tipo più generale.

```java
Persona p = new Studente();
p.saluta();
```

Anche se il riferimento è di tipo `Persona`, verrà eseguita la versione ridefinita in `Studente`.

## Perché è importante

Perché rende i programmi:
- più flessibili;
- più estendibili;
- meglio organizzati.

## Ricapitoliamo

- `extends` realizza l'ereditarietà;
- l'override ridefinisce un metodo;
- il polimorfismo permette comportamenti diversi dietro la stessa interfaccia.

[Prossima lezione](10-eccezioni-collections)
