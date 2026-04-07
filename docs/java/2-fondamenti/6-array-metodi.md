---
title: Array e metodi
layout: default
parent: Java
nav_order: 6
---

# Array e metodi

## Array

Un array contiene più valori dello stesso tipo.

```java
int[] numeri = {10, 20, 30, 40};
System.out.println(numeri[0]);
System.out.println(numeri[2]);
```

Gli indici partono da `0`.

## Modifica di un elemento

```java
numeri[1] = 99;
```

## Lunghezza

```java
System.out.println(numeri.length);
```

## Ciclo su array

```java
for (int i = 0; i < numeri.length; i++) {
    System.out.println(numeri[i]);
}
```

Oppure con il for-each:

```java
for (int numero : numeri) {
    System.out.println(numero);
}
```

## Metodi

I metodi permettono di raggruppare istruzioni riutilizzabili.

```java
public static int somma(int a, int b) {
    return a + b;
}
```

Uso:

```java
int risultato = somma(3, 5);
System.out.println(risultato);
```

## Parametri e valore di ritorno

- i parametri sono i dati in ingresso;
- `return` restituisce il risultato.

## Esempio completo

```java
public class Main {
    public static int massimo(int[] numeri) {
        int max = numeri[0];

        for (int numero : numeri) {
            if (numero > max) {
                max = numero;
            }
        }

        return max;
    }

    public static void main(String[] args) {
        int[] valori = {4, 8, 2, 10};
        System.out.println(massimo(valori));
    }
}
```

## Ricapitoliamo

- gli array permettono di memorizzare più valori dello stesso tipo;
- i metodi servono a organizzare il codice;
- `return` restituisce un risultato;
- separare il problema in metodi rende il programma più pulito.

[Prossima lezione](../3-oop/7-classi-oggetti)
