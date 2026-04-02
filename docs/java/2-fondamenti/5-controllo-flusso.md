---
title: Controllo di flusso
layout: default
parent: Coding in Java
nav_order: 5
---

# Controllo di flusso

Il controllo di flusso decide **quali istruzioni eseguire** e **quante volte**.

## `if`

```java
int eta = 20;

if (eta >= 18) {
    System.out.println("Maggiorenne");
}
```

## `if / else`

```java
if (eta >= 18) {
    System.out.println("Maggiorenne");
} else {
    System.out.println("Minorenne");
}
```

## `else if`

```java
int voto = 8;

if (voto < 6) {
    System.out.println("Insufficiente");
} else if (voto == 6) {
    System.out.println("Sufficiente");
} else {
    System.out.println("Buono o ottimo");
}
```

## `while`

```java
int i = 1;

while (i <= 5) {
    System.out.println(i);
    i++;
}
```

## `for`

```java
for (int i = 0; i < 5; i++) {
    System.out.println(i);
}
```

## `break` e `continue`

```java
for (int i = 0; i < 10; i++) {
    if (i == 5) {
        break;
    }
    System.out.println(i);
}
```

```java
for (int i = 0; i < 5; i++) {
    if (i == 2) {
        continue;
    }
    System.out.println(i);
}
```

## `switch`

```java
int giorno = 2;

switch (giorno) {
    case 1:
        System.out.println("Lunedì");
        break;
    case 2:
        System.out.println("Martedì");
        break;
    default:
        System.out.println("Altro");
}
```

## Ricapitoliamo

- `if` sceglie tra alternative;
- `while` ripete finché una condizione è vera;
- `for` è ottimo quando il numero di ripetizioni è noto;
- `switch` è utile in presenza di casi distinti.

[Prossima lezione](6-array-metodi)
