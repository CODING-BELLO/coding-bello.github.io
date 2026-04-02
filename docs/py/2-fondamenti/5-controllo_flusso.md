---
title: Controllo di flusso
layout: default
nav_order: 5
parent: Coding in Python
---

# Controllo di flusso

Finora abbiamo visto istruzioni eseguite una dopo l'altra, in sequenza.  
Ma un programma interessante deve anche saper **prendere decisioni**.

Qui entra in gioco il **controllo di flusso**.

## `if`

La struttura più importante è `if`.

```python
eta = 20

if eta >= 18:
    print("Sei maggiorenne")
```

Se la condizione è vera, il blocco indentato viene eseguito.

## `if` / `else`

```python
eta = 16

if eta >= 18:
    print("Sei maggiorenne")
else:
    print("Sei minorenne")
```

## `elif`

Quando ci sono più casi possibili usiamo `elif`.

```python
voto = 8

if voto < 6:
    print("Insufficiente")
elif voto == 6:
    print("Sufficiente")
elif voto <= 8:
    print("Buono")
else:
    print("Ottimo")
```

## Le condizioni

Le condizioni sono espressioni che producono `True` o `False`.

```python
x = 10

if x > 5:
    print("x è maggiore di 5")
```

## Operatori logici nelle condizioni

```python
eta = 17
ha_documento = True

if eta >= 16 and ha_documento:
    print("Puoi partecipare")
```

## Blocchi e indentazione

In Python i blocchi si definiscono con l'indentazione:

```python
if True:
    print("Dentro il blocco")
print("Fuori dal blocco")
```

Questa cosa è fondamentale: gli spazi fanno parte della sintassi.

## `while`

Il ciclo `while` ripete un blocco finché una condizione rimane vera.

```python
contatore = 1

while contatore <= 5:
    print(contatore)
    contatore = contatore + 1
```

## `for`

In Python il `for` viene spesso usato con `range()`.

```python
for i in range(5):
    print(i)
```

Questo stampa:
- 0
- 1
- 2
- 3
- 4

### `range(start, stop)`

```python
for i in range(1, 6):
    print(i)
```

### `range(start, stop, step)`

```python
for i in range(0, 10, 2):
    print(i)
```

## `break` e `continue`

### `break`
Interrompe il ciclo.

```python
for i in range(10):
    if i == 5:
        break
    print(i)
```

### `continue`
Salta l'iterazione corrente.

```python
for i in range(5):
    if i == 2:
        continue
    print(i)
```

## Ricapitoliamo

- `if`, `elif`, `else` servono per scegliere;
- `while` ripete finché una condizione è vera;
- `for` ripete un blocco un certo numero di volte o sugli elementi di una sequenza;
- l'indentazione in Python è essenziale;
- `break` interrompe, `continue` salta un giro.

[Prossima lezione](6-funzioni)
