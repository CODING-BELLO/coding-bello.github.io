---
title: Controllo di flusso
layout: default
nav_order: 1
parent: Fondamenti di programmazione in C++
---
# Leggibilità del codice

Per rendere un programma facile da leggere e capire, è importante curare:

- **Naming convention**: dare nomi chiari e significativi alle variabili e alle funzioni.
- **Indentazione**: organizzare il codice con spazi o tabulazioni per mostrare la struttura.
- **Commenti**: scrivere brevi spiegazioni nel codice per chiarire cosa fa ogni parte.

**Concetto chiave:** codice chiaro = meno errori e più facile manutenzione.

---

# Controllo del flusso: le decisioni in C++

Un programma non esegue sempre le istruzioni in sequenza: a volte deve **prendere decisioni**, cioè scegliere quali istruzioni eseguire in base a certe condizioni.

- **Decisione**: scegliere tra opzioni diverse.  
  Esempi in C++: `if / else`, `switch`

**Concetto chiave:** capire come il programma "decide" quale strada seguire è fondamentale per scrivere codice corretto e senza errori logici.

---

# Le istruzioni di decisione in C++

## `if`, `else if`, `else`

L'istruzione `if` permette di eseguire una parte di codice solo se una condizione è vera. Puoi aggiungere `else if` e `else` per gestire più casi.

### Esempio base
```cpp
#include <iostream>
using namespace std;

int main() {
    int numero;
    cout << "Inserisci un numero: ";
    cin >> numero;

    if (numero > 0) {
        cout << "Il numero è positivo." << endl;
    } else if (numero < 0) {
        cout << "Il numero è negativo." << endl;
    } else {
        cout << "Il numero è zero." << endl;
    }
    return 0;
}
```
**Output esempio:**
```
Inserisci un numero: -5
Il numero è negativo.
```

### Esempi pratici aggiuntivi

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
    case 1:
    case 7:
        cout << "Weekend!" << endl;
        break;
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