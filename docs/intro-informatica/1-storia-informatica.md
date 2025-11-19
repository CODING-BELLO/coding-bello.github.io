---
title: Storia dell'informatica
layout: default
nav_order: 1
has_toc: false
parent: Introduzione all'informatica 
---

# Storia dell’informatica

## 1. Dalle origini del calcolo agli strumenti primitivi

All’inizio troviamo strumenti molto semplici come l’abaco. Non è un computer, ma è già un primo passo verso l’idea di spostare il calcolo fuori dalla sola mente umana. L’abaco aiuta a ricordare i numeri e a eseguire più facilmente operazioni ripetitive. È un esempio di come un oggetto fisico possa supportare un’attività mentale.

## 2. I computer umani e i primi tentativi di automazione

Quando i problemi diventano più complessi, non basta più l’abaco. Nasce la figura dei **computer umani**: persone che, organizzate in gruppi, passano le giornate a fare conti a mano. L’obiettivo è produrre tabelle numeriche da usare in altri contesti: per esempio per calcolare la traiettoria di un proiettile, o per valutare interessi bancari, o per la navigazione. Questo sistema funziona, ma è lento, costoso e fragile: basta un errore in una riga perché tutta la tabella diventi inaffidabile.

## 3. Calcolatrici meccaniche e il sogno delle macchine programmabili

Con studiosi come Leibniz e Babbage si passa dall’idea di “affidare i calcoli a persone” a quella di **affidarli a macchine**. Leibniz costruisce una calcolatrice meccanica, la *Stepped Reckoner*, in grado di eseguire automaticamente le quattro operazioni. Babbage, qualche decennio dopo, si concentra sul problema delle tabelle matematiche: se una macchina potesse calcolare da sola tutti i valori, gli errori umani sparirebbero. Progetta così la **Difference Engine**.

Ma Babbage fa anche un passo in più, concettualmente gigantesco: immagina una macchina non limitata a un solo compito, ma **programmabile**. La chiama **Analytical Engine**. Nella sua idea, questa macchina ha un’unità di calcolo, una memoria, e usa schede perforate sia per i dati sia per le istruzioni. È, di fatto, uno schema molto simile a quello dei computer moderni. Il problema è che, al tempo, la tecnologia meccanica non è abbastanza matura, i costi sono altissimi e il progetto non verrà mai realizzato completamente. Rimane però un’idea potentissima, in anticipo sui tempi.

## 4. Hollerith e l’era delle schede perforate

Un altro grande problema storico è quello del censimento negli Stati Uniti. Alla fine dell’Ottocento, elaborare i dati raccolti sul territorio richiede talmente tanto tempo che, quando i risultati sono pronti, la situazione del Paese è già cambiata. Qui entra in gioco **Herman Hollerith**, che capisce che la chiave è rappresentare i dati in un formato che una macchina possa leggere facilmente. Nascono così le **schede perforate**, dove la presenza o l’assenza di un foro rappresenta una certa informazione. Macchine apposite possono leggere e contare automaticamente i fori. Il tempo di elaborazione del censimento si riduce drasticamente e si afferma l’idea di elaborazione meccanica dei dati.


## 5. L’era delle macchine specializzate

Nonostante questi progressi, per molto tempo le macchine restano **specializzate**: ogni problema richiede un dispositivo progettato apposta. Serviva calcolare interessi? Si costruiva una macchina contabile. Serviva fare moltiplicazioni? Una macchina per le moltiplicazioni. Serviva elaborare il censimento? Macchine per schede perforate. Era un mondo frammentato, dove ogni nuova esigenza richiedeva un nuovo dispositivo progettato da zero.

Eppure, alcuni pensatori iniziano a intuire un’idea diversa: **non creare una macchina per ogni problema, ma una macchina che possa risolvere qualsiasi problema** — se **istruita** nel modo giusto.

### Leibniz e il sogno di un linguaggio universale
Leibniz non costruisce solo strumenti meccanici: immagina qualcosa di molto più ambizioso. Nel suo progetto culturale più grande, cerca un **linguaggio formale universale**, capace di rappresentare tutti i ragionamenti umani — matematici, logici, filosofici.

L’idea, straordinariamente moderna, è che:
- se i ragionamenti dell'uomo possono essere trasformati in simboli,
- e se questi simboli seguono regole meccaniche,
- allora **una macchina potrebbe manipolarli** per risolvere problemi al posto nostro.

È un’anticipazione concettuale dei linguaggi di programmazione e degli algoritmi. Il suo sogno è che un giorno due filosofi che litigano possano dire: *«Calcoliamo!»*. Non discutere, ridurre il ragionamento a un procedimento e giungere a una conclusione certa.

Non esiste ancora una macchina universale, ma inizia a farsi strada **l’idea che il ragionamento umano possa essere formalizzato**.

### Babbage e la Analytical Engine: una macchina che può fare tutto
Babbage porta questo sogno su un piano più concreto. Con la **Analytical Engine**, immagina la prima macchina:
- con **unità di calcolo**,
- una **memoria**,
- un **meccanismo di controllo del flusso**,
- e soprattutto **programmabile** tramite schede perforate.

La Analytical Engine non è solo una calcolatrice avanzata: è progettata per eseguire **sequenze di istruzioni** generiche. Se fosse stata costruita, sarebbe stata la prima macchina a programmabilità generale della storia.

Ancora una volta, siamo vicini all’universalità, ma mancano:
- una teoria matematica del calcolo,
- una tecnologia in grado di costruire la macchina.

### Una strada tracciata, ma ancora incompleta
Leibniz fornisce la **visione astratta**: un linguaggio universale per esprimere qualsiasi pensiero.  
Babbage fornisce la **visione meccanica**: una macchina programmabile che può trasformarsi in qualsiasi altra macchina.

Manca però il tassello fondamentale: **dimostrare in modo rigoroso che un’unica macchina può, in linea di principio, eseguire qualunque procedura calcolabile**.

Quel tassello arriverà con **Alan Turing**, che formalizzerà finalmente il concetto di *calcolatore universale*.

## 6. Alan Turing e il concetto di macchina universale

Sul piano teorico, questo passo viene compiuto da **Alan Turing**. Turing si chiede che cosa significhi, in termini matematici, che un calcolo è “eseguibile”. Propone il modello della **Macchina di Turing**: un nastro potenzialmente infinito, una testina che legge e scrive simboli, un insieme finito di stati e regole che dicono alla macchina cosa fare. Non è importante costruire fisicamente una macchina del genere: ciò che conta è dimostrare che, con uno schema così semplice, si possono rappresentare tutti i procedimenti di calcolo che consideriamo “meccanici”.

L’idea ancora più rivoluzionaria di Turing è quella di **macchina universale**: invece di costruire una macchina diversa per ogni problema, possiamo costruirne una sola che, ricevendo in ingresso la descrizione di un programma, si comporta come la macchina specializzata per quel problema. Questa è l’essenza del computer moderno: un’unica macchina fisica che può diventare, di volta in volta, calcolatrice, editor di testo, browser, gioco, semplicemente caricando software diverso.

## 7. I primi calcolatori elettronici: Mark I, ENIAC, EDSAC

Negli anni ’40 e ’50 queste idee teoriche cominciano a essere realizzate in pratica. Il **Mark I** è un grande calcolatore elettromeccanico, basato su relè, usato anche per calcoli militari durante la Seconda Guerra Mondiale. È lento e enorme secondo i nostri standard, ma rappresenta un passo importante. Il **ENIAC** fa un salto di qualità passando ai componenti elettronici: usa valvole termoioniche, molto più veloci dei relè, al prezzo di consumi elevati e forte riscaldamento. Anche se potente, l’ENIAC è scomodo da programmare, perché ogni nuovo problema richiede di riconfigurare fisicamente cavi e pannelli.

Con l’**EDSAC** e altri calcolatori di fine anni ’40 si afferma l’architettura che oggi chiamiamo di **Von Neumann**: dati e istruzioni sono memorizzati insieme nella stessa memoria, rappresentati in binario, e la CPU li preleva uno dopo l’altro per eseguirli. È un passaggio cruciale: da questo momento programmare significa scrivere una sequenza di istruzioni che verrà caricata in memoria, non più spostare cavi o collegare plugboard.

## 8. Mainframe e rivoluzione del personal computer

Dopo l’EDSAC e i primi calcolatori elettronici, negli anni ’50 e ’60 i computer diventano strumenti potentissimi ma ancora enormi e costosi: sono i **mainframe**. Occupano intere stanze, richiedono impianti di raffreddamento e costano milioni di dollari. Vengono usati da governi, banche, università e grandi industrie.

### Perché erano così importanti?
- Permettevano di eseguire calcoli scientifici e militari impensabili a mano.
- Automatizzavano attività amministrative come censimenti, assicurazioni, finanza.
- Più utenti potevano accedervi tramite **terminali** collegati alla macchina centrale.

### Il limite: non erano per tutti
La maggior parte delle persone non aveva mai visto un computer. Erano strumenti altamente specializzati e riservati a pochi esperti.

### L’arrivo dei transistor e dei microchip cambia tutto
Con l’invenzione del transistor prima e del **microchip** poi:
- i computer diventano più piccoli,
- consumano meno energia,
- sono più economici e meno fragili.

Negli anni ’70 e ’80 nasce finalmente il **personal computer (PC)**:
- un computer che può stare su una scrivania,
- accessibile a molte più persone,
- pensato per uso personale, lavorativo e scolastico.

### Il Macintosh del 1984
Un punto di svolta arriva con l’Apple Macintosh:
- introduce **interfaccia grafica (GUI)** fatta di finestre, icone, cestino, menu,
- adotta il **mouse** per interagire con il sistema,
- rende il computer intuitivo anche per chi non conosceva comandi testuali.

Il PC diventa così uno strumento quotidiano, non più solo tecnico.

## 9. Internet, il Web e il computer come spazio digitale

Negli anni ’60 nasce negli Stati Uniti **ARPANET**, un progetto del Dipartimento della Difesa che aveva un obiettivo semplice ma rivoluzionario: far comunicare più computer tra loro in modo affidabile. L’idea fondamentale era che, anche se un nodo della rete cadeva, gli altri avrebbero potuto continuare a comunicare.

Negli anni ’70 e ’80, ARPANET si espande nelle università e nei centri di ricerca, creando un primo ecosistema di computer connessi.

### La svolta: i protocolli
All’epoca esistevano molte reti diverse e incompatibili. La soluzione arriva con lo sviluppo dei **protocolli** di comunicazione condivisi — regole comuni che tutti i computer devono seguire per capirsi.  
È grazie ai protocolli (come TCP/IP) che nasce **Internet**, una rete globale e aperta.

### La nascita del Web
Internet permette ai computer di comunicare, ma è con **Tim Berners-Lee**, all’inizio degli anni ’90, che nasce il **World Wide Web (WWW)**:
- le informazioni vengono organizzate in **pagine web**, collegate tra loro tramite link,
- il browser diventa la porta di accesso a questo mondo (grafico, cliccabile, facile),
- il protocollo **HTTP** definisce come le pagine vengono richieste e trasmesse.

Da quel momento:
- Internet non è più solo tecnica, ma diventa uno spazio culturale e sociale,
- aziende, scuole, case iniziano a connettersi,
- nasce la comunicazione digitale moderna (email, siti, social, streaming, servizi cloud).

### Il computer come spazio digitale
Oggi non percepiamo più il computer soltanto come una macchina che esegue calcoli.  
È un luogo dove vivono:
- documenti, foto, messaggi,
- identità digitali,
- relazioni, comunità e interazioni.


L’informatica non è più solo hardware e software: è un ecosistema di persone, reti e rappresentazioni digitali.

### 10. Dalle macchine alle persone: l’informatica come progetto umano

L’informatica, sin dalle sue origini, non è mai stata solo una disciplina tecnica. Ogni macchina inventata, ogni linguaggio sviluppato, ogni rete costruita nasce sempre per **rispondere a un bisogno umano**: comunicare, collaborare, calcolare, comprendere il mondo, ridurre la fatica mentale, risolvere problemi complessi.

Se guardiamo all’evoluzione completa — dall’abaco ai computer quantistici — vediamo un filo rosso:  
**l’informatica è un’estensione delle nostre capacità**, non un sostituto dell’essere umano.

Oggi viviamo immersi in dispositivi digitali: smartphone, PC, tablet, social network, piattaforme di studio, mappe, chat, notifiche. Questi strumenti ci connettono, ci aiutano a lavorare, a imparare, a ricordare, a esplorare. Ma allo stesso tempo possono diventare strumenti che consumano attenzione, tempo, energie mentali.

Per questo è fondamentale sviluppare una **alfabetizzazione digitale consapevole**:  
- capire come funzionano i sistemi,  
- riconoscere che ogni interfaccia è progettata con un certo scopo,  
- scegliere come e quando usare la tecnologia,  
- ritrovare equilibrio tra ciò che è digitale e ciò che è umano.

Lascio intervento di **Dino Ambrosi** a TEDx: [**“The Battle for Your Time”**](https://www.youtube.com/watch?v=4TMPXK9tw5U)

In conclusione, l’informatica è costruita da persone, per le persone.  
Ogni sistema digitale è una scelta progettuale: cosa rappresentare, come comunicarlo, quali limiti imporre, quali possibilità offrire.

Studiare la storia dell’informatica non serve solo a conoscere le macchine del passato, ma a capire:
- che la tecnologia porta con sé valori,  
- che possiamo migliorare il mondo progettando strumenti più equi e più utili,  
- che il futuro digitale dipende da noi e da come scegliamo di usare ciò che abbiamo costruito.

L’informatica non è solo “come funzionano i computer”:  **è progettare e scegliere il futuro della vita umana in questa era digitale.**

<!--
## Contenuti

### 1. Perché studiare la storia dell’informatica
- Il computer non è magia: è il risultato di tante scelte storiche e tecnologiche.
- Dietro ogni macchina c’è **un problema reale** da risolvere (censimenti, guerra, scienza, comunicazione…).
- Capire il passato aiuta a capire **perché oggi i computer sono fatti così**.

---

### 2. Dall’abaco ai "computer umani"
- **Abaco**
  - Strumento manuale per facilitare i calcoli.
  - Primo esempio di calcolo “esternalizzato” dalla mente umana.
- **Computer umani**
  - Persone organizzate per eseguire grandi quantità di calcoli a mano.
  - Usati per astronomia, balistica, finanza, navigazione.
  - Producono **tabelle** che altri possono consultare.
- **Limiti**
  - Lento, costoso, soggetto a errori.

---

### 3. Calcolatrici meccaniche e sogno di Babbage
- **Leibniz**
  - Costruisce la *Stepped Reckoner*.
  - Esegue automaticamente le quattro operazioni.
  - Idea: lasciare alle macchine i calcoli ripetitivi.
- **Babbage – Difference Engine**
  - Macchina per calcolare tabelle matematiche in modo automatico.
  - Obiettivo: eliminare gli errori umani nelle tabelle.
- **Babbage – Analytical Engine**
  - Progetto di macchina **programmabile** con memoria e unità di calcolo.
  - Usa schede perforate per dati e istruzioni.
  - È un antenato concettuale del computer moderno, ma non viene mai completato.

---

### 4. Il problema del censimento e Hollerith
- **Censimento USA**
  - Richiede quasi 10 anni per essere elaborato.
  - Quando i risultati sono pronti, la realtà è già cambiata.
- **Hollerith**
  - Introduce le **schede perforate** per rappresentare i dati.
  - Progetta macchine che leggono e contano automaticamente i fori.
- **Conseguenze**
  - Tempo di elaborazione ridotto drasticamente (circa 2 anni e mezzo).
  - Nascono aziende dedicate all’elaborazione meccanica dei dati (antenati di IBM).

---

### 5. Macchine specializzate
- Dopo Hollerith si diffondono macchine dedicate a compiti specifici:
  - Registratori di cassa.
  - Calcolatrici da ufficio.
  - Macchine contabili.
- Ogni problema ha la **sua macchina**.
- Manca ancora il **calcolatore universale**, in grado di cambiare comportamento solo cambiando il programma.

---

### 6. Alan Turing e la macchina universale
- **Domanda di Turing**: cosa significa, in modo preciso, “calcolare”? 
- **Macchina di Turing**
  - Nastro potenzialmente infinito.
  - Testina che legge/scrive simboli.
  - Insieme di stati e regole di transizione.
- **Idee chiave**
  - Algoritmo = procedura finita, eseguibile da una macchina.
  - Macchina universale: una sola macchina può simulare qualsiasi altra, se programmata nel modo giusto.

---

### 7. Mark I, ENIAC, EDSAC
- **Harvard Mark I (1944)**
  - Calcolatore elettromeccanico (relè).
  - Enorme e relativamente lento.
  - Usato per calcoli militari (Seconda Guerra Mondiale).
  - Grace Hopper e il primo “bug” letterale (insetto nel relè).
- **ENIAC (1946)**
  - Calcolatore elettronico (valvole termoioniche).
  - Molto più veloce dei relè.
  - Programmazione tramite cavi e pannelli (scomoda, poco flessibile).
- **EDSAC (1949)**
  - Usa il **sistema binario**.
  - Dati e istruzioni vengono caricati in **memoria**.
  - Realizza in pratica l’architettura di Von Neumann.

---

### 8. Mainframe e personal computer
- **Mainframe**
  - Grandi calcolatori centrali, molto costosi.
  - Usati da governi, banche, università.
  - Molti utenti collegati tramite terminali.
- **Personal computer (PC)**
  - Anni ’70–’80: il computer diventa uno strumento personale.
  - **Macintosh (1984)**
    - Interfaccia grafica (icone, finestre, cestino).
    - Uso del mouse.
    - Computer pensato anche per utenti non esperti.

---

### 9. Dall’hardware al mondo digitale
- Evoluzione **hardware**
  - Valvole → transistor → microchip.
  - Computer sempre più piccoli, veloci, economici.
- Evoluzione **software**
  - Linguaggio macchina → assembly → linguaggi di alto livello.
  - Nascita di sistemi operativi e interfacce grafiche.
- **Reti e Web**
  - ARPANET → Internet.
  - Tim Berners-Lee → World Wide Web (anni ’90).
- Oggi il computer è:
  - Non solo macchina di calcolo.
  - Ma spazio dove vivono dati, relazioni, identità digitali.
-->
---