---
title: Esercizi switch
layout: default
nav_order: 1
nav_exclude: true
---

# Menu con Switch-Case e Do-While

## **Esercizio 1**

**Codice da analizzare:**

```cpp
#include <iostream>
using namespace std;

int main() {
    int scelta = 2;
    
    switch(scelta) {
        case 1:
            cout << "Opzione 1 selezionata" << endl;
        case 2:
            cout << "Opzione 2 selezionata" << endl;
        case 3:
            cout << "Opzione 3 selezionata" << endl;
        default:
            cout << "Opzione non valida" << endl;
    }
    
    return 0;
}
```

**Domanda:** Cosa stampa questo programma?

**Risposta:** Il programma stampa:

- Opzione 2 selezionata
- Opzione 3 selezionata
- Opzione non valida

**Mancano i break!** Quando entra nel case 2, esegue quel blocco, poi **continua con il case 3** (fall-through) e il default.
***

## **Esercizio 2**

**Codice da analizzare:**

```cpp
#include <iostream>
using namespace std;

int main() {
    int opzione;
    
    do {
        cout << "=== MENU ===" << endl;
        cout << "1. Calcola" << endl;
        cout << "2. Stampa" << endl;
        cout << "0. Esci" << endl;
        cout << "Scelta: ";
        cin >> opzione;
        
        switch(opzione) {
            case 1:
                cout << "Eseguo calcolo..." << endl;
                break;
            case 2:
                cout << "Stampo risultato..." << endl;
                break;
            case 0:
                cout << "Arrivederci!" << endl;
                break;
            default:
                cout << "Opzione non valida!" << endl;
        }
        
    } while(opzione = 0);
    
    return 0;
}
```

**Domanda:** Questo programma visualizza un menu con diverse scelte:
- utente inserisce 1, il programma esegue un calcolo (non riportato perchè non d'interesse)
- utente inserisce 2, stampa
- utente inserisce 0, termina.

Il seguente programma è corretto? Testarlo e, se errato, modificarlo.


**Risposta:** Il programma **esce subito dopo il do**! L'errore è nella condizione del while: `opzione = 0` è un'**ASSEGNAZIONE** (non un confronto) ed è valutata come false.

Se si modifica con  `opzione != 0`, il programma viene corretto.

***

## **Esercizio 3**

**Codice da analizzare:**

```cpp
#include <iostream>
using namespace std;

int main() {
    char comando;
    
    do {
        cout << "Comandi: (S)alva, (C)arica, (E)sci: ";
        cin >> comando;
        
        switch(comando) {
            case 'S':
                cout << "File salvato!" << endl;
                break;
            case 'C':
                cout << "File caricato!" << endl;
                break;
            case 'E':
                cout << "Uscita..." << endl;
                break;
            default:
                cout << "Comando '" << comando << "' non riconosciuto!" << endl;
        }
        
    } while(comando != 'E');
    
    return 0;
}
```

**Domanda:** Cosa stampa il programma se l'utente inserisce 'e'? 

- Il programma stampa "Uscita..."
- Il programa stampa "Comando 'e' non riconosciuto!"
- Nulla, il programma esce dal do-while e termina

***

## **Esercizio 4**

```cpp
#include <iostream>
using namespace std;

int main() {
    int scelta;
    int contatore = 0;

    do {
        cout << "\n=== MENU PRINCIPALE ===" << endl;
        cout << "1. Incrementa contatore" << endl;
        cout << "2. Decrementa contatore" << endl;
        cout << "3. Stampa contatore" << endl;
        cout << "0. Esci" << endl;
        cout << "Scelta: ";
        cin >> scelta;

        switch(scelta) {
            case 1:
                contatore++;
                cout << "Contatore incrementato!" << endl;
                break;
            case 2:
                contatore--;
                cout << "Contatore decrementato!" << endl;
                break;
            case 3:
                cout << "Valore contatore: " << contatore << endl;
                break;
            case 0:
                cout << "Arrivederci!" << endl;
                break;
            default:
                cout << "Opzione non valida, riprova!" << endl;
        }

    } while(scelta != 0);

    return 0;
}
```

**Domanda:** A partire dal codice, scrivi la specifica funzionale che qualcuno avrebbe potuto scrivere per sviluppare questo programma.

***

## **Esercizio 5**

**Codice da analizzare:**

```cpp
#include <iostream>
using namespace std;

int main() {
    char scelta;
    
    do {
        cin >> scelta;
        
        switch(scelta) {
            case 'J':
            case 'I':
                cout << "Hai scelto Inter!" << endl;
                break;
            case 'M':
                cout << "Hai scelto Milan!" << endl;
                break;
            case 'Q':
                cout << "Uscita dal programma" << endl;
                break;
            default:
                cout << "Scelta non valida!" << endl;
        }
        
    } while(scelta != 'Q');
    
    return 0;
}
```

**Domanda:** Cosa fa questo programma se l'utente inserisce 'J'?

**Opzioni di risposta**

- Il programma non eseguito nulla e si rimette in attesa di un nuovo cin
- Il programma stampa "JUVE STORIA DI UN GRANDE AMORE BIANCO CHE ABBRACCIA IL NERO" e si rimette in attesa di un nuovo cin
- Il programma stampa "Hai scelto Inter!" e si rimette in attesa di un nuovo cin
- Il programma stampa "Scelta non valida!"


## **Esercizio 6**

```cpp
#include <iostream>
using namespace std;

int main() {
    int conta1 = 5;
    int conta2 = 5;
    
    cout << "=== CICLO WHILE ===" << endl;
    while(conta1 < 3) {
        cout << "While: " << conta1 << endl;
        conta1++;
    }
    
    cout << "\n=== CICLO DO-WHILE ===" << endl;
    do {
        cout << "Do-while: " << conta2 << endl;
        conta2++;
    } while(conta2 < 3);
    
    cout << "\nValori finali:" << endl;
    cout << "conta1 = " << conta1 << endl;
    cout << "conta2 = " << conta2 << endl;
    
    return 0;
}
```

**Domanda:** Cosa stampa questo programma?

**Risposta:** Il programma stampa:

Opzione 1
```
=== CICLO WHILE ===
While: 5
=== CICLO DO-WHILE ===
Do-while: 5
Valori finali:
conta1 = 6
conta2 = 6
```


Opzione 2
```
=== CICLO WHILE ===
=== CICLO DO-WHILE ===
Do-while: 5
Valori finali:
conta1 = 5
conta2 = 6
```

Opzione 3
```
=== CICLO WHILE ===
=== CICLO DO-WHILE ===
Do-while: 5
Do-while: 6
Valori finali:
conta1 = 5
conta2 = 7
```

Opzione 4
```
=== CICLO WHILE ===
While: 5
=== CICLO DO-WHILE ===
Valori finali:
conta1 = 6
conta2 = 5
```


## **Esercizio 6**

Scrivere un programma in C++ che mantenga un contatore, inizialmente valorizzato a 0.
Il programma deve offrire all'utente diverse scelte: incrementare il contatore di 1, decrementare il contatore di 2, azzerare il contatore, uscire dal programma. 

Ogni volta che il programma esegue un'operazione, comunica a schermo l'operazione effettuata e il nuovo valore del contatore. 
Il programma gestisce il caso in cui l'utente non sceglie tra queste opzioni, mostrando un messaggio di errore.