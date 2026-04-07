---
title: Match Case
layout: default
nav_order: 23
parent: Controllo di flusso
---

# Controllo di flusso

## La struttura `match`

Quando si devono controllare molti casi diversi dello stesso valore, invece di scrivere molti `if` ed `elif`, si può usare la struttura `match`.

La struttura `match` confronta un valore con più possibilità alternative, in modo simile a uno `switch` presente in altri linguaggi di programmazione.

Ad esempio, questo codice:

```python
giorno = 2

if giorno == 1:
    print("Lunedì")
elif giorno == 2:
    print("Martedì")
elif giorno == 3:
    print("Mercoledì")
elif giorno == 4:
    print("Giovedì")
elif giorno == 5:
    print("Venerdì")
elif giorno == 6:
    print("Sabato")
elif giorno == 7:
    print("Domenica")
else:
    print("Errore")
```

può essere scritto anche nel seguente modo:

```python
giorno = 2

match giorno:
    case 1:
        print("Lunedì")
    case 2:
        print("Martedì")
    case 3:
        print("Mercoledì")
    case 4:
        print("Giovedì")
    case 5:
        print("Venerdì")
    case 6:
        print("Sabato")
    case 7:
        print("Domenica")
    case _:
        print("Altro giorno")
```         

### Spiegazione 

- `match` indica il valore da controllare.
- Ogni `case` rappresenta una possibile alternativa.
- `case _` rappresenta il caso finale, eseguito se nessun altro caso corrisponde.

> La struttura `match` è utile quando si devono gestire molti casi in modo più ordinato e leggibile rispetto a una lunga sequenza di `if`, `elif` ed `else`.

## Ricapitoliamo

- Gli operatori `match` e `case` vengono utilizzati insieme per confrontare un valore con più casi possibili.


[Prossima lezione](8-iterazione)
