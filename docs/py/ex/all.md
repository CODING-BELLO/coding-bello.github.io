---
title: Esercizi
layout: default
nav_order: 999
has_toc: false
has_children: true
parent: Python
---

# Esercizi Python

---

## 1. Maggiore tra due numeri

Scrivi un programma che legga due numeri da tastiera e mostri quale dei due è il più grande.

Se i due valori sono uguali, il programma deve segnalarlo chiaramente.

---

## 2. Maggiore tra tre numeri

Leggi tre numeri e stampa il valore massimo tra i tre.

---

## 3. Il più grande della lista

Data una lista di numeri già definita nel codice, trova e stampa l’elemento con valore più alto senza usare `max()`.

---

## 4. È una vocale?

Chiedi all’utente un solo carattere e verifica se si tratta di una vocale.

---

## 5. Somma degli elementi

Data una lista di numeri, calcola la somma totale dei suoi elementi senza usare `sum()`.

---

## 6. Prodotto degli elementi

Data una lista di numeri, calcola il prodotto di tutti gli elementi.

---

## 7. Presenza in lista

Data una lista di elementi e un valore inserito dall’utente, controlla se quel valore è presente.

Se c’è, mostra anche la sua posizione nella lista.

---

## 8. Istogramma con asterischi

Scrivi una funzione che riceva una lista di numeri e stampi, per ogni numero, una riga composta da tanti asterischi quanto vale il numero.

Esempio:

- `3` → `***`
- `5` → `*****`

---

## 9. La tua versione di `len()`

Scrivi una funzione che restituisca la lunghezza di una stringa oppure di una lista senza usare `len()`.

---

## 10. Lunghezza delle parole

Data una lista di parole, costruisci una nuova lista che contenga la lunghezza di ciascuna parola.

Esempio:

```python
["ciao", "python", "sole"]
```

può diventare:

```python
[4, 6, 4]
```

---

## 11. Frequenza dei caratteri

Scrivi una funzione che riceva una stringa e costruisca un dizionario in cui:

- le chiavi sono i caratteri
- i valori indicano quante volte ogni carattere compare

---

## 12. Conversione da metri

Scrivi una funzione che riceva una misura espressa in metri e mostri l’equivalente in:

- miglia terrestri
- iarde
- piedi
- pollici

---

## 13. Da giorni, ore e minuti a secondi

Leggi da tastiera un numero di giorni, ore e minuti e calcola il totale corrispondente in secondi.

---

## 14. Calcolatore di aree

Realizza una funzione che, in base alla scelta dell’utente, calcoli l’area di una tra queste figure:

- quadrato
- rettangolo
- triangolo
- cerchio

---

## 15. Generatore di indirizzi MAC

Scrivi una funzione che generi un indirizzo MAC casuale nel formato:

```text
AA:BB:CC:DD:EE:FF
```

Puoi usare il modulo `random`.

---

## 16. Informazioni sul sistema

Scrivi una funzione che stampi il nome del sistema operativo in uso e la relativa release.

Suggerimento: cerca nel modulo `platform`.

---

## 17. Codice ASCII di un carattere

Leggi un carattere da tastiera e mostra il codice ASCII corrispondente.

---

## 18. Numero perfetto

Scrivi una funzione che controlli se un numero è perfetto.

Un numero è perfetto se è uguale alla somma dei suoi divisori positivi, escluso sé stesso.

---

## 19. Lista di colori filtrata per iniziale

Chiedi all’utente di inserire 10 colori in una lista.

Poi chiedi una lettera e mostra soltanto i colori che iniziano con quella lettera.

---

## 20. Stampa senza andare a capo

Leggi più stringhe da tastiera usando un ciclo `while`.

Continua finché l’utente inserisce qualcosa; quando preme invio senza scrivere nulla, il ciclo termina.

Tutte le stringhe inserite devono essere stampate sulla stessa riga.

---

## 21. Registro di segreteria

Scrivi una funzione che riceva una lista di dizionari, dove ogni dizionario rappresenta uno studente con:

- nome
- cognome
- classe
- lista dei voti

La funzione deve stampare gli studenti e calcolare la media dei voti di ciascuno.

---

## 22. Gestione utenti con CSV

Scrivi un programma che memorizzi i dati di alcuni utenti in un file CSV.

Per ogni utente salva:

- username
- password
- email
- data di registrazione

Il programma deve anche leggere il file e mostrarne il contenuto.

---

## 23. Salvataggio di un testo in file

Scrivi una funzione che chieda all’utente il titolo di una canzone e il suo testo, poi salvi il testo in un file chiamato con il titolo della canzone.

Esempio:

```text
titolo_canzone.txt
```

Suggerimento: usa `with` per gestire il file.

---

## 24. Il sistema solare

Crea una tupla contenente, per ogni pianeta del sistema solare:

- nome
- tipologia (roccioso o gassoso)
- numero di satelliti naturali conosciuti

Poi stampa il contenuto della tupla e calcola il numero totale di satelliti.

---

## 25. Sport di squadra o individuale

Scrivi una funzione che riceva lo sport preferito dell’utente e indichi se si tratta di uno sport di squadra oppure individuale.

Puoi usare due insiemi (`set`) distinti per classificare gli sport.

---

## 26. Il linguaggio dei furfanti

Nel cosiddetto *rövarspråket* ogni consonante viene raddoppiata e tra le due viene inserita una `o`.

Ad esempio:

```text
mangiare -> momanongogiarore
```

Scrivi una funzione che traduca una parola o una frase in questo linguaggio e poi chieda all’utente se desidera tradurre un altro testo.

---

## 27. Stringa al contrario

Scrivi una funzione che riceva una stringa e la stampi al contrario.

Esempio:

```text
abcd -> dcba
```

---

## 28. Palindromo

Scrivi una funzione che riceva una parola e controlli se è un palindromo, cioè se si legge allo stesso modo da sinistra a destra e da destra a sinistra.

---

## 29. Generatore di password

Scrivi una funzione che generi password casuali.

Il programma deve poter creare:

- una password semplice di 8 caratteri alfanumerici
- una password complessa di 20 caratteri, includendo anche simboli ASCII

---

## 30. Rimario

Scrivi una funzione che riceva una lista di parole e poi chieda all’utente una parola.

La funzione deve cercare le rime, intese come parole che hanno uguali le ultime 3 lettere.

Le parole trovate devono essere mostrate in output in una sola stringa, ad esempio usando `join()`.

---

## 31. Gestione di una libreria

Scrivi una funzione `vendi_libri()` che aiuti nella gestione di una piccola libreria.

La funzione deve:

- controllare se il libro richiesto è disponibile
- se presente, diminuire di 1 il numero di copie
- se le copie arrivano a 0, rimuovere il titolo dal catalogo
- se il libro non è disponibile, aggiungerlo a una lista di libri da ordinare

La funzione deve restituire `True` o `False` in base all’esito della vendita.

---

## 32. Crittografia ROT13

Il cifrario ROT13 sostituisce ogni lettera con quella che si trova 13 posizioni più avanti nell’alfabeto.

Scrivi una funzione in grado di cifrare una stringa con ROT13 e anche di decifrarla.

---

## 33. Peso totale di una cartella

Scrivi una funzione che calcoli la somma, espressa in MB, delle dimensioni dei file presenti nella cartella di lavoro.

Puoi usare il modulo `os`.

---

## 34. Invio di email

Scrivi una funzione che invii una email tramite Gmail.

Il programma deve chiedere:

- username
- password
- destinatario
- oggetto
- messaggio

Suggerimento: puoi usare `smtplib`.

---

## 35. Ricerca di file PDF

Scrivi una funzione che esplori un percorso di sistema alla ricerca di file PDF.

La funzione deve:

- verificare che il percorso indicato esista davvero
- mostrare i PDF trovati durante la scansione
- stampare il numero totale di file `.pdf` individuati

---

## 36. Backup di file per estensione

Scrivi una funzione `file_backup()` che effettui copie di backup di file di un certo tipo.

La funzione deve:

- chiedere all’utente il percorso da scansionare
- chiedere il percorso della cartella di backup
- chiedere l’estensione dei file da copiare
- verificare che il percorso da scansionare esista
- creare la cartella di backup se non è presente
- copiare i file trovati

Suggerimento: puoi usare `os` e `shutil`.

---

## 37. Fattoriale ricorsivo

Scrivi una funzione ricorsiva che calcoli il fattoriale di un numero.

---

## 38. Successione di Fibonacci

Scrivi una funzione ricorsiva che generi i numeri della successione di Fibonacci fino a una soglia scelta dall’utente.

Esempio iniziale della successione:

```text
1, 1, 2, 3, 5, 8, 13, ...
```

---

## 39. Cifrario di Cesare

Il Cifrario di Cesare sposta ogni lettera di un certo numero di posizioni nell’alfabeto.

Scrivi una funzione che riceva:

- una stringa
- una chiave numerica

La funzione deve restituire la stringa cifrata applicando lo spostamento indicato dalla chiave.

---
