---
title: Operatori ed espressioni
layout: default
parent: Coding in Java
nav_order: 4
---

# Operatori ed espressioni

Gli operatori permettono di costruire espressioni e calcoli.

## Operatori aritmetici

```java
int a = 10;
int b = 3;

System.out.println(a + b);
System.out.println(a - b);
System.out.println(a * b);
System.out.println(a / b);
System.out.println(a % b);
```

## Attenzione alla divisione intera

```java
System.out.println(10 / 3);      // 3
System.out.println(10.0 / 3);    // 3.333...
```

Quando entrambi gli operandi sono interi, il risultato viene troncato.

## Operatori di confronto

```java
int x = 5;

System.out.println(x == 5);
System.out.println(x != 5);
System.out.println(x > 3);
System.out.println(x <= 10);
```

Il risultato è sempre `true` oppure `false`.

## Operatori logici

```java
boolean a = true;
boolean b = false;

System.out.println(a && b);
System.out.println(a || b);
System.out.println(!a);
```

## Assegnazione vs confronto

- `=` assegna
- `==` confronta

```java
int x = 10;
System.out.println(x == 10);
```

## Incremento e decremento

```java
int n = 5;
n++;
n--;
```

## Ricapitoliamo

- gli operatori aritmetici servono per i calcoli;
- quelli di confronto producono valori booleani;
- quelli logici combinano condizioni;
- `=` e `==` non sono la stessa cosa.

[Prossima lezione](5-controllo-flusso)
