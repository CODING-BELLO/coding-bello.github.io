---
title: Altri esercizi
layout: default
nav_order: 999
has_toc: false
has_children: true
parent: Esercizi
---

# Altri esercizi

## Dizionari e strutture dati

---

## E1. Frequenza dei caratteri

Scrivere una funzione che riceva una stringa e costruisca un dizionario in cui:

- le chiavi siano i caratteri
- i valori indichino quante volte ogni carattere compare

---

## E2. Registro di segreteria

Scrivere una funzione che riceva una lista di dizionari, in cui ogni dizionario rappresenti uno studente con:

- nome
- cognome
- classe
- lista dei voti

La funzione deve stampare i dati degli studenti e calcolare la media dei voti di ciascuno.

---

## E3. Il sistema solare

Creare una tupla contenente, per ogni pianeta del sistema solare:

- nome
- tipologia (roccioso o gassoso)
- numero di satelliti naturali conosciuti

Successivamente, stampare il contenuto della tupla e calcolare il numero totale di satelliti.

---

## Funzioni e piccoli problemi più articolati

---

## E1. Il linguaggio dei furfanti

Nel cosiddetto *rövarspråket* ogni consonante viene raddoppiata e tra le due viene inserita una `o`.

Ad esempio:

```text
mangiare -> momanongogiarore
```

Scrivere una funzione che traduca una parola o una frase in questo linguaggio e, al termine, chieda se si desidera tradurre un altro testo.

---

## E2. Rimario

Scrivere una funzione che riceva una lista di parole e chieda poi all'utente di inserire una parola.

La funzione deve cercare le rime, intese come parole che abbiano uguali le ultime 3 lettere.

Le parole trovate devono essere mostrate in output come un'unica stringa, ad esempio usando `join()`.

---

## E3. Crittografia ROT13

Il cifrario ROT13 sostituisce ogni lettera con quella che si trova 13 posizioni più avanti nell'alfabeto.

Scrivere una funzione in grado di cifrare una stringa con ROT13 e anche di decifrarla.

---

## E4. Fattoriale ricorsivo

Scrivere una funzione ricorsiva che calcoli il fattoriale di un numero.

---

## E5. Successione di Fibonacci

Scrivere una funzione ricorsiva che generi i numeri della successione di Fibonacci fino a una soglia scelta dall'utente.

Esempio iniziale della successione:

```text
1, 1, 2, 3, 5, 8, 13, ...
```

---

## E6. Cifrario di Cesare

Il Cifrario di Cesare sposta ogni lettera di un certo numero di posizioni nell'alfabeto.

Scrivere una funzione che riceva:

- una stringa
- una chiave numerica

La funzione deve restituire la stringa cifrata applicando lo spostamento indicato dalla chiave.

---

## Moduli, file e sistema operativo

---

## E1. Generatore di indirizzi MAC

Scrivere una funzione che generi un indirizzo MAC casuale nel formato:

```text
AA:BB:CC:DD:EE:FF
```

Si può usare il modulo `random`.

---

## E2. Informazioni sul sistema

Scrivere una funzione che stampi il nome del sistema operativo in uso e la relativa release.

Suggerimento: usare il modulo `platform`.

---

## E3. Gestione utenti con CSV

Scrivere un programma che memorizzi i dati di alcuni utenti in un file CSV.

Per ogni utente devono essere salvati:

- username
- password
- email
- data di registrazione

Il programma deve anche leggere il file e mostrarne il contenuto.

---

## E4. Salvataggio di un testo in file

Scrivere una funzione che chieda all'utente il titolo di una canzone e il relativo testo, quindi salvi il contenuto in un file chiamato con il titolo della canzone.

Esempio:

```text
titolo_canzone.txt
```

Suggerimento: usare `with` per gestire il file.

---

## E5. Generatore di password

Scrivere una funzione che generi password casuali.

Il programma deve poter creare:

- una password semplice di 8 caratteri alfanumerici
- una password complessa di 20 caratteri, includendo anche simboli ASCII

---

## E6. Peso totale di una cartella

Scrivere una funzione che calcoli la somma, espressa in MB, delle dimensioni dei file presenti nella cartella di lavoro.

Si può usare il modulo `os`.

---

## E7. Ricerca di file PDF

Scrivere una funzione che esplori un percorso di sistema alla ricerca di file PDF.

La funzione deve:

- verificare che il percorso indicato esista realmente
- mostrare i PDF trovati durante la scansione
- stampare il numero totale di file `.pdf` individuati

---
