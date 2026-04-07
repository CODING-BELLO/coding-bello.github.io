---
title: Eccezioni e collections
layout: default
parent: Java
nav_order: 10
---

# Eccezioni e collections

## Eccezioni

Le eccezioni servono a gestire situazioni di errore durante l'esecuzione.

```java
try {
    int risultato = 10 / 0;
    System.out.println(risultato);
} catch (ArithmeticException e) {
    System.out.println("Errore: divisione per zero");
}
```

## Perché servono

Per evitare che il programma fallisca in modo caotico e per gestire gli errori in modo controllato.

## Collections

Gli array sono utili, ma hanno dimensione fissa.  
Le **collections** sono strutture più flessibili.

### `ArrayList`

```java
import java.util.ArrayList;

ArrayList<String> nomi = new ArrayList<>();
nomi.add("Luca");
nomi.add("Anna");
nomi.add("Marco");

System.out.println(nomi.get(0));
```

### Ciclo su `ArrayList`

```java
for (String nome : nomi) {
    System.out.println(nome);
}
```

## Perché usare le collections

Perché permettono di gestire insiemi di dati in modo più dinamico rispetto agli array.

## Ricapitoliamo

- le eccezioni aiutano a gestire gli errori;
- `try` e `catch` permettono di intercettare problemi;
- `ArrayList` è una collection molto usata;
- le collections sono più flessibili degli array.

[Prossima lezione](../4-concorrenza/11-thread)
