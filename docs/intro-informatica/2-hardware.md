---
title: Hardware
layout: default
nav_order: 2
parent: Introduzione all'informatica 
---

# Introduzione all’hardware

### Introduzione all'hardware

Quando parliamo di **hardware**, stiamo parlando di tutto ciò che, in un computer, si può toccare: dai chip minuscoli all’interno della scheda madre fino al monitor, alla tastiera, ai cavi. È la parte fisica della macchina, quella fatta di materiali, componenti elettronici e meccanici. Da solo però l’hardware non basta: senza il software che gli dice cosa fare, rimane un insieme di circuiti inattivo. Allo stesso tempo, il software non può esistere “nel vuoto”: ha bisogno di un supporto fisico su cui essere memorizzato ed eseguito. Le due cose sono intimamente legate.

### Capitolo 2 — Vista generale del computer

Per orientarsi nella complessità dell’hardware, è utile immaginare un computer come composto da alcuni **blocchi principali**. Al centro c’è la **CPU**, spesso descritta come il “cervello” del sistema: è il componente che esegue le istruzioni dei programmi, elabora i dati e produce risultati. Accanto alla CPU troviamo la **memoria centrale**, la più importante delle quali è la **RAM**. La RAM è la zona in cui vengono caricati i programmi e i dati mentre sono in esecuzione: possiamo pensarla come il **piano di lavoro** della cucina, dove appoggiamo gli ingredienti che ci servono per preparare una ricetta.

I dati che non stiamo usando in quel momento, ma che vogliamo conservare nel tempo (documenti, foto, programmi, sistema operativo), vengono memorizzati nella **memoria secondaria**, come gli **HDD** o gli **SSD**. Se la RAM è il piano di lavoro, la memoria secondaria è la **dispensa**: contiene tutto, ma per usare qualcosa dobbiamo andarla a prendere e portarla sul piano. Gli SSD moderni hanno reso questa operazione molto più veloce rispetto ai vecchi dischi rigidi meccanici, riducendo i tempi di avvio del sistema e di apertura dei programmi.

### Capitolo 3 — Scheda madre e bus

Tutti questi componenti sono montati sulla **scheda madre**, una grande piastra di circuito stampato piena di piste di rame e connettori. La scheda madre svolge un ruolo fondamentale: è il luogo in cui tutti i componenti si incontrano e comunicano. Per farlo usano i **bus**, insiemi di linee elettriche che trasportano dati, indirizzi e segnali di controllo. Possiamo immaginare i bus come una rete di strade interne al computer: grazie a queste “corsie” la CPU può leggere dalla memoria, scrivere su un disco, inviare informazioni alla scheda video, e così via.

### Capitolo 4 — CPU e funzionamento interno

Entrando un po’ di più nel dettaglio della **CPU**, troviamo alcuni blocchi concettuali importanti. L’**unità di controllo** coordina il flusso delle operazioni: preleva un’istruzione dalla memoria (fase di *fetch*), la decodifica per capire cosa deve fare (*decode*), e poi la esegue (*execute*). L’**ALU** (Arithmetic Logic Unit) è la parte che effettivamente esegue operazioni aritmetiche (somme, sottrazioni…) e logiche (AND, OR, confronti). I **registri**, infine, sono piccole memorie interne alla CPU, molto più veloci anche della RAM, usate per conservare temporaneamente dati e indirizzi durante i calcoli.

### Capitolo 5 — Memoria centrale e cache

Sopra alla RAM esiste un ulteriore livello di memoria, ancora più vicino alla CPU: la **cache**. È una memoria di dimensioni ridotte ma con tempi di accesso estremamente bassi. La cache conserva copie dei dati e delle istruzioni usati più di frequente, in modo che la CPU non debba continuamente tornare alla RAM, che è più lenta. Questa struttura “a livelli” (cache, RAM, memoria secondaria) è un esempio di come l’hardware sia progettato per bilanciare velocità, costo e capacità.

### Capitolo 6 — Periferiche

Oltre ai componenti interni, un computer è circondato da una serie di **periferiche**, che si dividono in input, output e input/output. Le periferiche di input (tastiera, mouse, microfono, sensori…) permettono all’utente o all’ambiente esterno di inviare dati al sistema. Le periferiche di output (monitor, stampante, casse…) mostrano il risultato dell’elaborazione. Alcune periferiche, come lo schermo touch, le chiavette USB o le schede di rete, svolgono entrambe le funzioni: ricevono e inviano informazioni.

### Capitolo 7 — Architettura di Von Neumann

Dal punto di vista logico, molti computer moderni seguono ancora il modello dell’**architettura di Von Neumann**. In questo schema, la CPU, la memoria centrale e i dispositivi di input/output sono collegati da bus, e sia i dati sia i programmi sono memorizzati nella stessa memoria, sotto forma di sequenze di bit. La CPU esegue continuamente un ciclo in cui preleva un’istruzione dalla memoria, la interpreta e la esegue, eventualmente leggendo o scrivendo dati. Questa idea, nata a metà del Novecento, è ancora alla base del funzionamento di gran parte dei computer attuali, dai PC ai server, fino a molti dispositivi “nascosti” dentro oggetti quotidiani.

### Capitolo 8 — Hardware visto dal software

Per chi programma, però, molti dettagli dell’hardware restano nascosti dietro ad **astrazioni** fornite dal sistema operativo: invece di pensare a settori magnetici su un disco, parliamo di file; invece di gestire direttamente i segnali della CPU, parliamo di processi e thread; invece di ragionare sugli indirizzi fisici della memoria, utilizziamo indirizzi virtuali. Queste astrazioni non cancellano la complessità dell’hardware, ma la organizzano in modo che possiamo lavorare su livelli più alti, senza perdere di vista il fatto che, in fondo, tutto si riduce a circuiti che manipolano bit.

Comprendere l’hardware, almeno a livello concettuale, aiuta a dare senso a molti fenomeni che incontriamo ogni giorno: perché un computer “rallenta” quando la RAM è piena, perché un SSD è più reattivo di un HDD, perché una CPU con più core può gestire meglio molte applicazioni aperte, o perché una scheda video dedicata fa la differenza nei videogiochi e nel rendering grafico. Dietro queste esperienze quotidiane ci sono scelte progettuali precise, e vederle con un po’ di chiarezza rende meno misterioso il mondo delle macchine.

<!--
## Contenuti

### 1. Cos’è l’hardware e perché è importante
- **Hardware** = tutte le parti fisiche e tangibili di un sistema di calcolo.
- Comprende: componenti interni, periferiche, cavi, connettori, ecc.
- Senza hardware il software non può essere eseguito.
- Senza software, l’hardware è solo “ferro”: ha bisogno di istruzioni per fare qualcosa di utile.

---

### 2. Vista d’insieme di un computer
- Possiamo immaginare un computer come formato da alcuni **blocchi principali**:
  - **CPU** (cervello, elabora i dati).
  - **Memoria centrale (RAM)** (piano di lavoro, dati e istruzioni in uso).
  - **Memoria secondaria** (magazzino dei dati: SSD, HDD).
  - **Scheda madre** (collega tutti i componenti).
  - **Periferiche di input/output** (tastiera, mouse, monitor, stampante, rete…).
- Tutti questi blocchi comunicano tra loro tramite **bus** (canali di comunicazione interni).

---

### 3. Case e alimentazione
- **Case**
  - Contiene e protegge i componenti interni.
  - Permette l’accesso alle **porte** (USB, HDMI, audio, ecc.).
  - Nei portatili e smartphone: scocca/cover.
- **Alimentazione**
  - **Alimentatore** (nei fissi) o **batteria** (nei portatili/smartphone).
  - Converte la corrente dalla presa nei voltaggi adatti ai componenti interni.
  - Elemento fondamentale per la stabilità del sistema.

---

### 4. Scheda madre e bus
- **Scheda madre (motherboard)**
  - Grande circuito stampato che collega fisicamente tutti i componenti.
  - Ospita: CPU, RAM, slot per schede video, schede di rete, connettori per dischi, ecc.
  - Le piste di rame sulla scheda trasportano i segnali elettrici.
- **Bus**
  - Insieme di linee elettriche che trasportano:
    - **Dati** (bus dati).
    - **Indirizzi** di memoria (bus indirizzi).
    - **Segnali di controllo** (bus di controllo).
  - Permettono a CPU, memoria e periferiche di comunicare.

---

### 5. CPU: il “cervello” del sistema
- **CPU (Central Processing Unit)**
  - Esegue le istruzioni dei programmi.
  - Elabora i dati e produce risultati.
- Struttura interna (a livello concettuale):
  - **Unità di controllo**: coordina il ciclo di esecuzione (fetch–decode–execute).
  - **ALU (Arithmetic Logic Unit)**: esegue operazioni aritmetiche e logiche.
  - **Registri**: piccole memorie interne velocissime.
- Caratteristiche:
  - **Frequenza di clock** (Hz, GHz): quante operazioni elementari al secondo.
  - **Numero di core**: più core = possibilità di gestire più flussi di lavoro in parallelo.
  - **Cache interna**: memoria molto veloce a pochi passi dalla CPU.

---

### 6. Memoria centrale: RAM, cache, ROM
- **RAM (Random Access Memory)**
  - Memoria principale del sistema.
  - **Veloce** ma **volatile** (si svuota quando si spegne il computer).
  - Contiene i programmi e i dati in uso in quel momento.
  - Metafora: è il **piano di lavoro** su cui appoggiamo gli “ingredienti” mentre cuciniamo.
- **Cache**
  - Memoria ancora più vicina alla CPU e più veloce della RAM.
  - Dimensione ridotta.
  - Conserva dati e istruzioni usati di frequente per evitare accessi lenti alla RAM.
- **ROM (Read Only Memory)**
  - Memoria non volatile in sola lettura (in condizioni normali).
  - Contiene informazioni fondamentali, ad esempio il programma di avvio (BIOS/UEFI).

---

### 7. Memoria secondaria: HDD e SSD
- Funzione: conservare dati, programmi e sistema operativo in modo **persistente** (anche a computer spento).
- **HDD (Hard Disk Drive)**
  - Usa dischi magnetici rotanti e testine meccaniche.
  - Più lento nell’accesso casuale ai dati.
  - Grande capacità a costi bassi.
  - Più sensibile a urti e vibrazioni.
- **SSD (Solid State Drive)**
  - Non ha parti meccaniche in movimento.
  - Molto più veloce nell’accesso ai dati.
  - Più resistente e silenzioso.
  - Oggi spesso è lo standard nei computer moderni.
- **Metafora della cucina**
  - Memoria secondaria = **dispensa/magazzino** (conserviamo tutto).
  - RAM = **piano di lavoro** (solo ciò che serve al momento).
  - CPU = **cuoco** (esegue la ricetta con gli ingredienti sul piano).

---

### 8. Periferiche di input/output
- **Periferiche di input**
  - Tastiera, mouse, touchpad, microfono, scanner, sensori, webcam.
  - Permettono all’utente o all’ambiente di **inviare dati** al computer.
- **Periferiche di output**
  - Monitor, stampante, casse, proiettore, cuffie.
  - Permettono al computer di **mostrare o riprodurre** il risultato dell’elaborazione.
- **Periferiche di input/output**
  - Schermo touch, dischi esterni, chiavette USB, schede di rete.
  - Possono sia inviare sia ricevere dati.
- Tutte queste periferiche sono collegate tramite porte e interfacce standard (USB, HDMI, Ethernet, Bluetooth, Wi-Fi, ecc.).

---

### 9. Architettura di Von Neumann (schema logico)
- Modello logico usato dalla maggior parte dei computer moderni.
- Componenti principali:
  - **CPU** (unità di controllo, ALU, registri).
  - **Memoria centrale** (dati + istruzioni).
  - **Dispositivi di input/output**.
  - **Bus** che collegano i blocchi tra loro.
- Caratteristiche fondamentali:
  - Dati e programmi sono entrambi rappresentati in **forma binaria**.
  - Dati e istruzioni risiedono nella **stessa memoria**.
  - La CPU esegue il ciclo:
    - **Fetch**: preleva l’istruzione dalla memoria.
    - **Decode**: la decodifica.
    - **Execute**: la esegue, eventualmente leggendo/scrivendo dati.

---

### 10. Hardware visto dal software
- Per il programmatore, l’hardware è visto tramite **astrazioni** fornite dal sistema operativo:
  - File invece di settori fisici sul disco.
  - Processi invece di dettagli della CPU.
  - Indirizzi di memoria “logici” invece di indirizzi fisici.
- Questo permette di:
  - Scrivere programmi senza conoscere ogni dettaglio dell’hardware.
  - Rendere il software più portabile tra macchine diverse.

-->