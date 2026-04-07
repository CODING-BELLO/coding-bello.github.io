---
title: Leggibilità
layout: default
nav_order: 61
parent: Coding in Python
---

# Leggibilità del codice

Scrivere codice che funziona è importante.  
Scrivere codice che si capisce è ancora meglio.

Python nasce proprio con questa idea: il codice deve essere leggibile.

## Perché la leggibilità conta

Un programma non viene letto solo dal computer.  
Viene letto anche:
- da chi lo ha scritto;
- dai compagni;
- dal docente;
- dal nostro "io del futuro".

Se il codice è confuso, anche correggerlo o migliorarlo diventa molto più difficile.

## Nomi chiari

Meglio:

```python
numero_studenti = 25
media_voti = 7.4
```

che:

```python
a = 25
b = 7.4
```

## Indentazione coerente

In Python è obbligatoria, ma deve anche essere ordinata.

```python
if eta >= 18:
    print("Maggiorenne")
```

## Commenti utili

I commenti servono quando aggiungono chiarezza.

```python
# Calcola l'area del rettangolo
area = base * altezza
```

Non ha senso commentare l'ovvio:

```python
# assegna 5 a x
x = 5
```

## Una cosa per volta

Blocchi troppo lunghi e disordinati sono difficili da leggere.  
Meglio dividere in funzioni e parti logiche.

## Stile Pythonico

In Python esistono convenzioni condivise. Le più famose sono raccolte nel **PEP 8**.

A livello base, alcune buone pratiche sono:
- usare nomi in `snake_case`;
- lasciare spazi attorno agli operatori;
- evitare righe inutilmente lunghe;
- mantenere uno stile coerente.

Esempio:

```python
totale_punti = punti_base + bonus
```

## Leggibilità e debug

Un codice leggibile è anche più facile da correggere.  
Quando capiamo bene cosa fa ogni parte, troviamo gli errori più facilmente.

## Ricapitoliamo

- codice leggibile = codice più facile da capire, correggere e migliorare;
- scegli nomi chiari;
- usa bene l'indentazione;
- commenta solo quando serve davvero;
- dividi il problema in parti più piccole;
- segui uno stile coerente.

[Prossima lezione](12-algoritmi)
