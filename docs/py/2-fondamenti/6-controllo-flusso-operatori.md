---
title: Controllo di flusso (condizioni e operatori logici)
layout: default
nav_order: 12
parent: Coding in Python
---

# Controllo di flusso

## Operatori logici nelle condizioni
È possibile utilizzare gli **operatori logici** per combinare più condizioni all'interno della stessa istruzione `if`.

Gli operatori logici principali sono:
- `and`
- `or`
- `not`

## Operatore `and`

L'operatore `and` restituisce `True` solo se **tutte** le condizioni sono vere.

```python
eta = 17
ha_documento = True

if eta >= 16 and ha_documento:
    print("Puoi partecipare")
```

In questo caso il messaggio viene stampato solo se:
- `eta >= 16` è vera;
- `ha_documento` è vera.

## Operatore `or`

L'operatore `or` restituisce `True` se **almeno una** delle condizioni è vera.

```python
giorno_festivo = False
permesso_speciale = True

if giorno_festivo or permesso_speciale:
    print("Ingresso consentito")
```

In questo caso basta che una delle due condizioni sia vera perché il blocco venga eseguito.

## Operatore `not`

L'operatore `not` inverte il valore logico di una condizione:
- `True` diventa `False`;
- `False` diventa `True`.

```python
piove = False

if not piove:
    print("Si può uscire")
```

In questo caso il messaggio viene stampato perché `piove` è falso, quindi `not piove` è vero.

## Combinare più operatori logici

Gli operatori logici possono anche essere combinati tra loro.

```python
eta = 15
ha_documento = True
accompagnato = True

if (eta >= 16 and ha_documento) or accompagnato:
    print("Puoi partecipare")
```

In questo caso il messaggio viene stampato se:
- la persona ha almeno 16 anni **e** possiede un documento;
- **oppure** è accompagnata.

Le parentesi aiutano a rendere più chiara la logica della condizione.



## Ricapitoliamo

- `and` → tutte le condizioni devono essere vere;
- `or` → almeno una condizione deve essere vera;
- `not` → inverte il valore logico di una condizione.

[Prossima lezione](7-controllo-flusso-match)
