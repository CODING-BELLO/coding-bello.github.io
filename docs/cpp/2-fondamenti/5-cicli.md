---
title: Cicli
layout: default
nav_order: 6
parent: Coding in C++
---
# I cicli, le ripetizioni, le ripetizioni, le ripetizioni

Nei programmi, spesso è necessario ripetere un'azione più volte. I cicli permettono di fare questo in modo efficiente, evitando di scrivere più volte lo stesso codice.

---

## Concetti chiave sulla macchina e i cicli

Tipicamente un ciclo è composto da
- **Corpo del ciclo**: le istruzioni che vengono ripetute n volte
- **Condizione**: questa condizione è una condizione booleana e viene valutata a ogni ripetizione, per capire se continuare a ripetere oppure uscire

Quando il programma esegue un ciclo, vengono seguiti questi passaggi fondamentali:

- **Valuta la condizione**: decide se entrare o continuare il ciclo.
- **Esegue il corpo del ciclo**: il codice che deve essere ripetuto.
- **Aggiorna le variabili**: spesso si modifica una variabile in modo che a un certo punto si verifichi la condizione di uscita.
- **Ripete**: torna a valutare la condizione.


---
# Tipi di ciclo

## Ciclo `for`

Il ciclo `for` è ideale quando si conosce in anticipo quante volte eseguire un'azione.

### Sintassi di base

```cpp
for (inizializzazione; condizione; aggiornamento) {
    // corpo del ciclo
}
```

- **inizializzazione**: si esegue una sola volta all'inizio (es. `int i = 1;`)
- **condizione**: viene controllata prima di ogni iterazione
- **aggiornamento**: eseguito dopo ogni iterazione (es. `i++`)

### Esempio pratico: stampare i numeri da 1 a 5

```cpp
#include <iostream>
using namespace std;

int main() {
    for (int i = 1; i <= 5; i++) {
        cout << "Iterazione numero: " << i << endl;
    }
    return 0;
}
```

**Output:**
```
Iterazione numero: 1
Iterazione numero: 2
Iterazione numero: 3
Iterazione numero: 4
Iterazione numero: 5
```

### Spiegazione passo passo

1. `i` viene inizializzato a 1.
2. La condizione `i <= 5` viene controllata: se è vera, si entra nel ciclo.
3. Viene eseguito il corpo del ciclo, che stampa il valore di `i`.
4. Alla fine del ciclo, `i` viene incrementato di 1 (`i++`).
5. Si torna a controllare la condizione.
6. Quando `i` diventa 6, la condizione è falsa e il ciclo termina.

### Possibili errori comuni

- **Incremento dimenticato**: se non si incrementa `i`, il ciclo sarà infinito.
- **Condizione sbagliata**: ad esempio usare `i < 5` invece di `i <= 5` cambia il numero di iterazioni.
- **Inizializzazione errata**: iniziare da un valore diverso da quello desiderato può confondere.

---

## Ciclo `while`

Il ciclo `while` è usato quando non si sa esattamente quante volte ripetere, ma si vuole continuare finché una condizione è vera.

### Sintassi di base

```cpp
while (condizione) {
    // corpo del ciclo
}
```

### Esempio pratico: contare da 0 a 2

```cpp
#include <iostream>
using namespace std;

int main() {
    int n = 0;
    while (n < 3) {
        cout << "n vale: " << n << endl;
        n++;
    }
    return 0;
}
```

**Output:**
```
n vale: 0
n vale: 1
n vale: 2
```

### Spiegazione passo passo

1. `n` è inizializzato a 0.
2. La condizione `n < 3` viene controllata.
3. Se vera, si esegue il corpo del ciclo: stampa e incremento di `n`.
4. Si torna a controllare la condizione.
5. Quando `n` diventa 3, la condizione è falsa e il ciclo termina.

### Errori comuni

- **Condizione mai vera**: se `n` fosse inizializzato a 5, il ciclo non partirebbe mai.
- **Incremento mancante**: senza `n++`, il ciclo non termina mai (ciclo infinito).
- **Modifica della variabile fuori dal ciclo**: può causare confusione nel flusso.

---

## Ciclo `do-while`

Il ciclo `do-while` è simile al `while`, ma garantisce che il corpo venga eseguito almeno una volta, perché la condizione viene controllata dopo l'esecuzione.

### Sintassi di base

```cpp
do {
    // corpo del ciclo
} while (condizione);
```

### Esempio pratico: contare da 5 a 1

```cpp
#include <iostream>
using namespace std;

int main() {
    int x = 5;
    do {
        cout << "x vale: " << x << endl;
        x--;
    } while (x > 0);
    return 0;
}
```

**Output:**
```
x vale: 5
x vale: 4
x vale: 3
x vale: 2
x vale: 1
```

### Spiegazione passo passo

1. Il ciclo entra nel corpo senza controllare la condizione.
2. Stampa il valore di `x` e lo decrementa.
3. Dopo il corpo, controlla se `x > 0`.
4. Se vero, ripete il ciclo; altrimenti termina.

### Quando usare `do-while`

- Quando vuoi che il ciclo venga eseguito almeno una volta, ad esempio per chiedere un input all'utente e poi verificare se continuare.

### Attenzione

- Anche qui, senza decremento o modifica della variabile, si rischia un ciclo infinito.

---


[Prossima lezione](5-funzioni)