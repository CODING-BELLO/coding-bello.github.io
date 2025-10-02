---
title: Controllo di flusso
layout: default
nav_order: 5
parent: Coding in C++
---
# Controllo di flusso

Abbiamo visto come un programma venga eseguito sempre in sequenza, dalla prima all'ultima istruzione. A volte però, è necessario **prendere decisioni**: scegliere quali istruzioni eseguire in base a certe condizioni. 

Ad esempio potremmo decidere di far avere due comportamenti diversi al nostro programma in base alla condizione di qualche variabile. In questa sezione, valuteremo come il programma "decide" quale strada seguire.

---


# Operatori Relazionali e Logici

Quando programmiamo, spesso dobbiamo **confrontare valori** o **combinare più condizioni** per decidere che azioni eseguire.  
Ad esempio:
- “L’età è maggiore di 18 anni?”  
- “La temperatura è sotto lo zero **e** sta nevicando?”  

Per farlo, usiamo **operatori relazionali** e **operatori logici**.

---

## Operatori Relazionali

Gli **operatori relazionali** servono per confrontare due valori e restituiscono un risultato **booleano**, cioè:
- `true` → se la condizione è vera  
- `false` → se la condizione è falsa

| Operatore | Significato           | Esempio (`a = 5`, `b = 10`) | Risultato |
|-----------|-------------------------|-----------------------------|-----------|
| `==`      | Uguale a               | `a == b`                   | `false`   |
| `!=`      | Diverso da             | `a != b`                   | `true`    |
| `<`       | Minore di              | `a < b`                    | `true`    |
| `>`       | Maggiore di            | `a > b`                    | `false`   |
| `<=`      | Minore o uguale a     | `a <= b`                   | `true`    |
| `>=`      | Maggiore o uguale a   | `a >= b`                   | `false`   |


## Operatori Logici

Gli **operatori logici** servono per **combinare più condizioni booleane** (vero/falso) in un’unica espressione.  
Li usiamo spesso in strutture di controllo come `if`, `while`, `for`, ecc.

Ad esempio:
- “La temperatura è sotto zero **e** sta nevicando?”  
- “L’utente è maggiorenne **oppure** ha un permesso speciale?”  
- “La condizione non è vera?”

---

## Tabella degli Operatori Logici

| Operatore | Nome          | Significato                                                                 | Esempio                        | Risultato |
|-----------|---------------|------------------------------------------------------------------------------|---------------------------------|-----------|
| `&&`      | AND logico    | Vero solo se **entrambe** le condizioni sono vere                             | `true && false`                | `false`   |
| `||`      | OR logico     | Vero se **almeno una** delle condizioni è vera                                | `true || false`               | `true`    |
| `!`       | NOT logico    | **Inverte** il valore: `true` diventa `false` e viceversa                     | `!true`                       | `false`   |

---

# Le istruzioni di decisione

## `if`, `else`, `else if`

L'istruzione `if` permette di eseguire una o più istruzioni **solo se una condizione è vera**. Puoi aggiungere `else` per gestire il caso in cui la condizione sia falsa, e `else if` per controllare condizioni alternative.

### 1. Solo `if`
Il codice racchiuso tra parentesi graffe, viene eseguito **solo se la condizione è vera**. Il codice all'interno delle graffe possiamo indicarlo come "codice dentro l'if".
```cpp
if (x > 0) {
    cout << "x è positivo" << endl;
}
```

### 2. `if` con `else`
Il blocco dentro l'`else` viene eseguito **solo se la condizione dell'if è falsa**.
```cpp
if (x > 0) {
    cout << "x è positivo" << endl;
} else {
    cout << "x NON è positivo" << endl;
}
```

### 3. `if` con `else if` e `else`
Puoi controllare più condizioni in sequenza. Appena una condizione è vera, il relativo blocco viene eseguito e gli altri vengono saltati.
```cpp
if (x > 0) {
    cout << "x è positivo" << endl;
} else if (x == 0) {
    cout << "x è zero" << endl;
} else {
    cout << "x è negativo" << endl;
}
```

**Nota:** Solo il blocco corrispondente alla prima condizione vera viene eseguito; tutti gli altri vengono saltati.


## Esempi Pratici

#### Verifica della maggiore età
```cpp
int eta;
cout << "Quanti anni hai? ";
cin >> eta;

if (eta >= 18) {
    cout << "Sei maggiorenne." << endl;
} else {
    cout << "Sei minorenne." << endl;
}
```

#### Pari o dispari
```cpp
int n;
cout << "Inserisci un numero: ";
cin >> n;

if (n % 2 == 0) {
    cout << "Il numero è pari." << endl;
} else {
    cout << "Il numero è dispari." << endl;
}
```

#### Controllo temperatura sotto zero e neve
Vogliamo controllare se fa freddo **e** nevica:

```cpp
#include <iostream>
using namespace std;

int main() {
    int temperatura = -3;
    bool nevica = true;

    if (temperatura < 0 && nevica) {
        cout << "Sta nevicando e fa freddo!" << endl;
    }

    return 0;
}
```

### Errori comuni e chiarimenti didattici

- **Confusione tra `=` e `==`:**
  - `=` serve per assegnare un valore (`a = 5;`)
  - `==` serve per confrontare due valori (`if (a == 5)`)
  - Errore tipico: scrivere `if (a = 5)` invece di `if (a == 5)`. Così facendo, si assegna 5 ad `a` e la condizione risulta sempre vera (perché `a = 5` restituisce 5, che è diverso da zero)!

- **`else` senza `if`:**
  - L'`else` deve sempre essere collegato a un `if` precedente. Non può esistere da solo!
  - Esempio errato:
    ```cpp
    else {
        cout << "Errore!" << endl;
    }
    ```
    Questo genera errore di compilazione.

- **Mancata indentazione:**
  - Anche se C++ permette di scrivere:
    ```cpp
    if (condizione)
    istruzione;
    ```
    è buona norma racchiudere sempre le istruzioni tra `{}` se si usano più righe, per evitare errori.
  - Esempio:
    ```cpp
    if (x > 0)
        cout << "Positivo";
        cout << "Test";
    // Solo la prima riga è condizionata, la seconda viene eseguita sempre!
    ```

### Esempio con più condizioni
```cpp
int voto;
cout << "Inserisci il voto (0-10): ";
cin >> voto;

if (voto == 10) {
    cout << "Ottimo!" << endl;
} else if (voto >= 6) {
    cout << "Promosso." << endl;
} else if (voto >= 0) {
    cout << "Bocciato." << endl;
} else {
    cout << "Voto non valido." << endl;
}
```

---

## `switch`

Lo `switch` è utile quando si hanno molte scelte in base al valore di una variabile intera o carattere.

### Esempio base
```cpp
#include <iostream>
using namespace std;

int main() {
    int giorno;
    cout << "Inserisci un numero da 1 a 3: ";
    cin >> giorno;

    switch (giorno) {
        case 1:
            cout << "Hai scelto Lunedì" << endl;
            break;
        case 2:
            cout << "Hai scelto Martedì" << endl;
            break;
        case 3:
            cout << "Hai scelto Mercoledì" << endl;
            break;
        default:
            cout << "Scelta non valida" << endl;
    }
    return 0;
}
```
**Output esempio:**
```
Inserisci un numero da 1 a 3: 2
Hai scelto Martedì
```

### Esempi pratici aggiuntivi

#### Calcolatrice semplice
```cpp
char operazione;
int a = 5, b = 3;
cout << "Scegli operazione (+, -, *, /): ";
cin >> operazione;

switch (operazione) {
    case '+':
        cout << a + b << endl;
        break;
    case '-':
        cout << a - b << endl;
        break;
    case '*':
        cout << a * b << endl;
        break;
    case '/':
        if (b != 0)
            cout << a / b << endl;
        else
            cout << "Divisione per zero!" << endl;
        break;
    default:
        cout << "Operazione non riconosciuta." << endl;
}
```

#### Giorni della settimana (con più casi)
```cpp
int giorno;
cout << "Inserisci un numero da 1 a 7: ";
cin >> giorno;

switch (giorno) {
    case 7:
        cout << "Weekend!" << endl;
        break;
    case 1:
    case 2:
    case 3:
    case 4:
    case 5:
    case 6:
        cout << "Giorno lavorativo." << endl;
        break;
    default:
        cout << "Numero non valido." << endl;
}
```

### Errori comuni e chiarimenti didattici

- **Dimenticare il `break`:**
  - Se ometti `break`, il programma continua ad eseguire anche i casi successivi ("fall-through").
  - Esempio:
    ```cpp
    int x = 2;
    switch (x) {
        case 1:
            cout << "Uno";
        case 2:
            cout << "Due";
        case 3:
            cout << "Tre";
    }
    // Output: "DueTre"
    ```
    Per evitare comportamenti inattesi, **usa sempre `break`** (tranne quando vuoi appositamente il "fall-through").

- **Tipi compatibili:**
  - Lo `switch` funziona solo con tipi interi o caratteri (`int`, `char`, `enum`). Non puoi usarlo con `float`, `double` o stringhe.

- **Valori duplicati nei `case`:**
  - Ogni valore di `case` deve essere unico.

- **Mancanza del `default`:**
  - Il ramo `default` gestisce i casi non previsti. Non è obbligatorio, ma è buona pratica aggiungerlo.

---

# Sommario

- Usa `if`, `else if`, `else` e `switch` per prendere decisioni.
- Fai attenzione ai principali errori: confusione tra `=` e `==`, `else` senza `if`, dimenticare il `break` nello `switch`.
- Commenta sempre il tuo codice e prova a scrivere piccoli esempi per capire come funzionano questi costrutti!

[Esercizi Switch Case e Do-while](../ex/switch-case)

[Prossima lezione](5-cicli)