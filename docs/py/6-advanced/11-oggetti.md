---
title: Programmazione a oggetti
layout: default
nav_order: 63
parent: Python
---

# Programmazione a oggetti

La programmazione a oggetti permette di modellare il mondo attraverso **oggetti** che hanno:
- **attributi**: dati;
- **metodi**: azioni o comportamenti.

## Classi e oggetti

Una **classe** è come un progetto, un modello.  
Un **oggetto** è un'istanza concreta di quella classe.

## Definire una classe

```python
class Studente:
    def __init__(self, nome, eta):
        self.nome = nome
        self.eta = eta
```

## Creare un oggetto

```python
s1 = Studente("Luca", 17)

print(s1.nome)
print(s1.eta)
```

## `self`

`self` rappresenta l'oggetto stesso.  
Serve per accedere agli attributi e ai metodi dell'istanza corrente.

## Metodi

```python
class Studente:
    def __init__(self, nome, eta):
        self.nome = nome
        self.eta = eta

    def saluta(self):
        print(f"Ciao, sono {self.nome}")
```

```python
s1 = Studente("Anna", 18)
s1.saluta()
```

## Perché usare gli oggetti

Gli oggetti aiutano a:
- raggruppare dati e comportamenti;
- modellare entità reali o concettuali;
- organizzare meglio programmi grandi.

## Esempio

```python
class Rettangolo:
    def __init__(self, base, altezza):
        self.base = base
        self.altezza = altezza

    def area(self):
        return self.base * self.altezza
```

```python
r = Rettangolo(5, 3)
print(r.area())
```

## Ricapitoliamo

- una classe è un modello;
- un oggetto è un'istanza concreta;
- `__init__` inizializza l'oggetto;
- `self` indica l'istanza corrente;
- i metodi descrivono i comportamenti dell'oggetto.