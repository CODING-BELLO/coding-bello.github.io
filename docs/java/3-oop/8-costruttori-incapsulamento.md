---
title: Costruttori e incapsulamento
layout: default
parent: Coding in Java
nav_order: 8
---

# Costruttori e incapsulamento

## Costruttore

Il costruttore serve per inizializzare un oggetto nel momento in cui viene creato.

```java
public class Studente {
    String nome;
    int eta;

    public Studente(String nome, int eta) {
        this.nome = nome;
        this.eta = eta;
    }
}
```

Uso:

```java
Studente s1 = new Studente("Luca", 17);
```

## `this`

`this` serve a riferirsi all'oggetto corrente.

## Incapsulamento

L'incapsulamento consiste nel proteggere lo stato interno dell'oggetto.

Per esempio possiamo rendere privati gli attributi:

```java
public class Studente {
    private String nome;
    private int eta;
}
```

e accedere tramite metodi:

```java
public String getNome() {
    return nome;
}

public void setNome(String nome) {
    this.nome = nome;
}
```

## Perché è utile

Perché evita modifiche disordinate e ci permette di controllare meglio i dati.

## Ricapitoliamo

- il costruttore inizializza l'oggetto;
- `this` indica l'istanza corrente;
- `private` aiuta a proteggere i dati;
- getter e setter permettono un accesso controllato.

[Prossima lezione](9-ereditarieta-polimorfismo)
