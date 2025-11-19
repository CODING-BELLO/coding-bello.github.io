---
title: Software
layout: default
nav_order: 3
parent: Introduzione all'informatica 
---
# Introduzione al Software

### 1. Introduzione al software

Quando parliamo di **software**, stiamo parlando di tutto ciò che in un computer non si vede e non si tocca, ma che determina il comportamento della macchina. Il software è fatto di istruzioni e dati, rappresentati alla fine come sequenze di bit, che dicono all’hardware come reagire. Senza software, un computer acceso rimarrebbe fermo; senza hardware, il software sarebbe solo un insieme di simboli senza un “corpo” in cui vivere.

### 2. Programma e processo

La distinzione tra **programma** e **processo** è fondamentale per capire cosa succede dentro un sistema. Un programma è il testo delle istruzioni, salvato in un file sulla memoria di massa: per esempio, l’eseguibile di un browser o l’app di un videogioco. Quando facciamo doppio clic e avviamo il programma, il sistema operativo carica parte di quel contenuto in memoria centrale e fa sì che la CPU inizi a eseguirne le istruzioni: in quel momento nasce un **processo**. Il processo è quindi il programma “vivo”, in azione, con i suoi dati in RAM, il suo stato interno, i suoi file aperti. Molti studenti tendono a confondere le due cose, ma la differenza è simile a quella tra la partitura di un brano musicale (programma) e l’esecuzione dal vivo di quel brano da parte di un’orchestra (processo).

### 3. Software di base e software applicativo

Un’altra distinzione importante è tra **software di base** e **software applicativo**. Il software di base comprende il sistema operativo e i componenti essenziali che permettono al computer di funzionare. È il livello che si occupa di gestire l’hardware, organizzare la memoria, gestire i file, controllare la rete, proteggere gli utenti. Sopra questo strato si appoggiano i software applicativi, che sono quelli che usiamo ogni giorno: editor di testo, browser, giochi, editor di immagini, ecc. Ogni volta che salviamo un documento, guardiamo un video o inviamo un messaggio, in realtà il programma applicativo sta chiedendo servizi al sistema operativo, che a sua volta parla con l’hardware.

### 4. Astrazione e macchina a strati  

L’idea di astrazione è centrale nell’informatica. Le slide mostrano come ogni livello di un computer nasconda dettagli del livello sottostante e offra un linguaggio più semplice e potente per descrivere operazioni complesse.

**Cos’è un’astrazione?**  
È il processo di nascondere dettagli complessi per offrire un modello più semplice.  
- Nel software: i file nascondono blocchi e settori del disco.  
- Nel sistema operativo: i processi nascondono l’effettiva sequenza di istruzioni sulla CPU.  
- Nell’hardware: i bit nascondono segnali elettrici.

**Perché serve?**  
- Riduce la complessità.  
- Permette di progettare sistemi modulari.  
- Permette di scrivere lo stesso programma su hardware diversi (portabilità).  

Le slide mostrano tre grandi strati:
- **Hardware** → segnali elettrici, bit, CPU, RAM  
- **Sistema operativo** → processi, file system, memoria virtuale, permessi, rete  
- **Applicazioni** → ciò che l’utente usa (browser, giochi, editor)

Ogni app funziona solo perché sotto di essa ci sono livelli che parlano un linguaggio comprensibile e più semplice rispetto ai dettagli fisici reali.

Per mettere ordine in questa complessità, spesso si rappresenta un sistema informatico come una **struttura a strati**. Alla base c’è l’hardware: CPU, memoria, dischi, schede di rete, periferiche. Sopra troviamo il sistema operativo, che fornisce un insieme di astrazioni: file invece di settori di disco, processi invece di cicli di CPU, socket di rete invece di pacchetti individuali. Ancora sopra si trovano le applicazioni, che sfruttano queste astrazioni per risolvere problemi vicini all’utente. Ogni strato nasconde dettagli di quello sottostante e offre un linguaggio più comodo per descrivere ciò che vogliamo fare.

### 5. Sistema operativo: funzioni principali


Più in profondità, il sistema operativo non si limita a offrire funzioni, ma **costruisce astrazioni**: invece di vedere cicli di CPU, vediamo *processi*; invece di vedere indirizzi fisici di memoria, vediamo uno *spazio di indirizzamento* comodo per ogni programma; invece di parlare con una scheda di rete a colpi di bit, vediamo una *connessione* o un *socket*. Queste astrazioni non esistono fisicamente: sono modi organizzati di interpretare ciò che realmente accade nell’hardware, per renderlo comprensibile e utilizzabile dai programmi e, indirettamente, dalle persone.

Un altro compito critico è la **gestione della memoria**. La RAM è una risorsa limitata: il sistema operativo deve decidere quanta memoria assegnare a ogni processo e impedire che un programma vada a leggere o scrivere nella parte di memoria di un altro. In caso di mancanza di RAM, può usare la memoria secondaria come “estensione” temporanea (memoria virtuale), spostando su disco i dati usati meno di frequente. Anche se questo rende il sistema più flessibile, si paga con tempi di accesso più lunghi.

### 6. Gestione della memoria

Un altro compito critico è la **gestione della memoria**. La RAM è una risorsa limitata: il sistema operativo deve decidere quanta memoria assegnare a ogni processo e impedire che un programma vada a leggere o scrivere nella parte di memoria di un altro. In caso di mancanza di RAM, può usare la memoria secondaria come “estensione” temporanea (memoria virtuale), spostando su disco i dati usati meno di frequente. Anche se questo rende il sistema più flessibile, si paga con tempi di accesso più lunghi.

### 7. File system e memoria secondaria

Per quanto riguarda i dati permanenti, il sistema operativo offre il **file system**, che per noi appare come un insieme di file e cartelle. Dal punto di vista dell’utente è naturale pensare a directory annidate ad albero, con nomi, estensioni e percorsi. Ma fisicamente i dischi (o gli SSD) sono solo grandi sequenze di blocchi numerati contenenti **0 e 1**.

Il file system è quindi una **astrazione forte**: una rappresentazione virtuale che mappa blocchi di bit in oggetti logici (file, cartelle) dotati di significato. 
- Quando chiediamo di aprire `relazione.docx`, il programma non va a cercare da solo i blocchi giusti sul disco: chiede al sistema operativo di interpretare la struttura del file system e restituire il contenuto di quel file.
- Quando creiamo una nuova cartella, in realtà il sistema operativo aggiorna delle strutture dati interne che descrivono come i blocchi fisici sono organizzati.

Questo livello di astrazione nasconde la complessità dell’organizzazione fisica e permette di lavorare con concetti semplici (nomi di file, estensioni, percorsi). È importante ricordare che **“file” e “cartella” non esistono davvero nel disco**: quello che esiste sono solo bit; è il sistema operativo che li interpreta come se fossero file e directory, rendendo possibile la nostra esperienza quotidiana con i dati.

### 8. Utenti, permessi e sicurezza

Il sistema operativo si occupa anche di **utenti e permessi**, cioè di “chi può fare cosa”. In un sistema multiutente, non ha senso che un qualsiasi utente possa cancellare i file di sistema o leggere senza limiti i documenti di altri. Per questo esistono meccanismi di autenticazione (password, PIN, impronta digitale, riconoscimento facciale) e di autorizzazione (permessi di lettura, scrittura ed esecuzione). In questo modo il sistema operativo agisce come un custode che controlla l’accesso alle risorse e contribuisce alla sicurezza complessiva del sistema.

### 9. Rete e comunicazione

Un altro aspetto fondamentale oggi è la **rete**. Quasi ogni software moderno, in un modo o nell’altro, comunica via Internet: scarica aggiornamenti, invia messaggi, recupera pagine web, sincronizza dati nel cloud. Anche qui il sistema operativo ha un ruolo di mediatore: le applicazioni non parlano direttamente con i cavi o con il Wi-Fi, ma usano interfacce di rete (socket) fornite dal sistema operativo. Quest’ultimo si occupa di incapsulare i dati nei protocolli corretti, inviarli, riceverli, e consegnarli all’applicazione giusta. In questo processo può anche filtrare il traffico e bloccare comunicazioni sospette, come fa un firewall.

### 10. System call: il ponte tra software e hardware

Il ponte concreto tra applicazioni e sistema operativo è rappresentato dalle **system call**. Quando un programma vuole salvare un file, creare un nuovo processo, mandare dati in rete o allocare memoria, non può semplicemente “toccare” l’hardware; deve invece invocare una system call, cioè una funzione speciale gestita dal sistema operativo. Questo meccanismo centralizza il controllo, aumentando la sicurezza (perché il sistema operativo può verificare che l’operazione sia lecita) e la portabilità (perché il programma non deve conoscere i dettagli di ogni dispositivo: li conosce il sistema operativo).

### 11. Software applicativo nella vita reale

Infine, guardando al **software applicativo** nella vita di tutti i giorni, ci accorgiamo che è ovunque: non solo sul PC o sul telefono, ma anche nei dispositivi che ci circondano (auto, elettrodomestici, wearable, sistemi di controllo industriale…). Ogni applicazione è costruita sopra una pila di altri software e, alla base di tutto, sull’hardware. Avere un’idea chiara di come si collegano programma, processo, sistema operativo e hardware aiuta a non vedere le “app” come scatole magiche, ma come parte di un sistema complesso e progettato.


<!--
## Contenuti

### 1. Cos’è il software
- **Software** = insieme di programmi e dati non fisici che danno uno scopo a una macchina.
- È la “parte invisibile” del computer: non si può toccare, ma decide **cosa fa** l’hardware.
- Senza software l’hardware è solo un insieme di circuiti inattivi.

---

### 2. Programma vs processo
- **Programma**
  - Insieme di istruzioni che implementano un algoritmo.
  - È conservato in un file (memoria secondaria).
  - È **statico**: descrive un comportamento possibile.
- **Processo**
  - È un programma in esecuzione.
  - Le istruzioni sono caricate in RAM e la CPU le esegue.
  - È **dinamico**: descrive cosa sta facendo il computer in quel momento.
- Esempio:
  - Il file di un browser salvato sul disco = programma.
  - Quando lo avvio, l’istanza che gira in RAM = processo.

---

### 3. Software di base vs software applicativo
- **Software di base**
  - Comprende il **sistema operativo** e i programmi fondamentali per il funzionamento del computer.
  - Gestisce risorse, file, utenti, rete, periferiche.
- **Software applicativo**
  - Programmi che usiamo per svolgere compiti specifici:
    - Videoscrittura, fogli di calcolo, browser, giochi, app di messaggistica, editor di immagini…
  - Si appoggiano al sistema operativo per usare l’hardware.
- Relazione:
  - Utente → software applicativo → sistema operativo → hardware.

---

### 4. Struttura a strati (layer)
- Possiamo vedere un sistema informatico come una **pila di livelli**:
  - **Hardware** (bit, circuiti, segnali elettrici).
  - **Sistema operativo** (gestione risorse, astrazioni).
  - **Applicazioni** (programmi usati dall’utente).
- Ogni livello:
  - Nasconde i dettagli di quello sotto.
  - Offre funzioni più semplici e astratte a quello sopra.
- Vantaggi:
  - Complessità gestita meglio.
  - Maggiore portabilità e riuso del software.

---

### 5. Sistema operativo: ruolo generale
- Il **sistema operativo (SO)** è il software che:
  - Controlla e coordina le risorse hardware.
  - Offre **servizi** ai programmi applicativi.
- Obiettivi principali:
  - Far sì che il sistema sia **usabile** (per l’utente).
  - Far sì che sia **efficiente** (uso delle risorse).
  - Far sì che sia **sicuro** (controllo accessi, isolamento dei processi).

---

### 6. Gestione dei processi e multitasking
- Il SO si occupa di:
  - Avviare e terminare i processi.
  - Assegnare tempo di CPU a ciascun processo.
  - Dare l’illusione che più programmi girino **contemporaneamente**.
- **Multitasking**
  - La CPU esegue un processo alla volta, ma cambia molto velocemente.
  - All’utente sembra che i programmi lavorino in parallelo.
- Esempio:
  - Ascolto musica, scarico un file e scrivo un documento: per l’utente sono tre cose insieme, per la CPU sono tanti piccoli pezzi alternati.

---

### 7. Gestione della memoria
- Il SO gestisce:
  - Quanta **RAM** assegnare a ogni processo.
  - Quali dati tenere in RAM e quali spostare temporaneamente su disco (memoria virtuale).
- Obiettivi:
  - Evitare che un programma occupi tutta la memoria.
  - Impedire che un processo legga/modifichi la memoria di un altro (isolamento).
- Collegamento hardware:
  - Senza la gestione della memoria, i programmi potrebbero distruggersi a vicenda.

---

### 8. File system: organizzare i dati
- Il **file system** è il modo in cui il SO organizza i dati su memoria secondaria.
- Concetti chiave:
  - **File**: contenitore logico di dati (documento, foto, programma…).
  - **Cartelle (directory)**: raccolte di file e altre cartelle.
  - Struttura ad **albero**: cartella radice → sottocartelle → file.
- Importante:
  - Il file system è un’**astrazione**:
    - L’utente vede file e cartelle.
    - Il disco in realtà è organizzato in blocchi/settori fisici.
- Vantaggi:
  - Permette di gestire i dati in modo comprensibile (nomi, percorsi, estensioni).

---

### 9. Utenti, permessi e sicurezza
- Il SO gestisce **utenti** diversi:
  - Ogni utente ha un proprio account (login con password, PIN, FaceID, TouchID…).
  - Ogni utente ha una propria area di lavoro (cartelle personali, impostazioni).
- **Permessi**
  - Specificano cosa può fare chi:
    - Lettura/scrittura/esecuzione su file e cartelle.
    - Possibilità di installare programmi o modificare impostazioni di sistema.
- Ruolo nella sicurezza:
  - Il SO è il primo livello di difesa contro accessi non autorizzati e programmi malevoli.

---

### 10. Rete e comunicazione tra computer
- Il SO gestisce anche la **rete**:
  - Decide quali applicazioni possono usare la connessione.
  - Passa e riceve dati attraverso protocolli (TCP/IP, HTTP, ecc.).
- Esempi:
  - Browser che chiede una pagina web.
  - App di chat che invia un messaggio.
- Ruolo del SO:
  - Mediare tra le richieste delle applicazioni e l’hardware di rete.
  - Possibilità di filtrare il traffico (es. firewall).

---

### 11. System call: il ponte tra applicazioni e sistema operativo
- Le **system call** sono le “porte” attraverso cui i programmi chiedono servizi al SO.
- Esempi di system call:
  - Aprire/chiudere/leggere/scrivere file.
  - Allocare memoria.
  - Creare o terminare processi.
  - Inviare dati in rete.
- Vantaggi:
  - Maggiore **sicurezza**: il programma non tocca direttamente l’hardware.
  - Maggiore **portabilità**: il programma parla con il SO, non con ogni singolo dispositivo.

---

### 12. Software applicativo nella vita reale
- Esempi di software applicativo:
  - Suite da ufficio (editor di testo, foglio di calcolo, presentazioni).
  - Browser web.
  - Social, app di messaggistica.
  - Videogiochi.
  - Editor di foto/video/musica.
  - App di controllo per automobili, robot, dispositivi smart.
- Tutte queste applicazioni:
  - Si appoggiano al SO per usare file, rete, schermo, tastiera…
  - Sono spesso specifiche per un sistema (Windows, macOS, Android, iOS…).
-->
---