---
title: Cominciare a programmare
layout: default
nav_order: 0
parent: Coding in C++
has_children: true
---

# Introduzione a C++

C++ è un linguaggio di programmazione derivato dal C, sviluppato nei primi anni '80 da Bjarne Stroustrup. Ha avuto un ruolo fondamentale nello sviluppo di software complesso e infatti, nel corso di questi anni è stato utilizzato per sviluppare:

- **Sistemi operativi**, ad esempio parti di Windows e Linux sono scritte in C++/C.
- **Motori di videogiochi**, ad esempio **Unreal Engine** e **CryEngine**. Un game engine è un software molto complesso e avanzato che gestisce grafica, fisica, suoni e logiche di gioco. Permette agli sviluppatori di creare giochi senza riscrivere tutto da zero. 
- **Giochi famosi**, ad esempio **The Witcher 3**, **Assassin’s Creed**, **World of Warcraft** (lista infinita)
- **Applicazioni desktop** come Adobe Photoshop e molti software di grafica professionale.
- **Browser web** come parti di Chrome e Firefox.
- **Software scientifico e ingegneristico**, software di simulazione e CAD.

## Alte prestazioni

Come visto, C++ viene spesso utilizzato per programmi e compiti molto complessi e dispendiosi, in quanto linguaggio ad alte prestazioni, efficiente e veloce. Per "prestazioni" intendiamo la capacità di un programma di utilizzare al meglio le risorse del computer, come la CPU e la memoria, per eseguire operazioni rapidamente e con poco spreco.

Questo è possibile perché C++ è un linguaggio compilato: il codice sorgente (programma scritto in linguaggio C++) viene tradotto direttamente in linguaggio macchina (codice binario), che il computer può eseguire direttamente senza passaggi intermedi. Inoltre, C++ offre un controllo molto fine sulle risorse hardware, permettendo agli sviluppatori di ottimizzare il codice per ottenere le migliori prestazioni possibili.


### Linguaggio compilato vs linguaggio interpretato

- C++ è un linguaggio **compilato**.  
- Il codice sorgente scritto in `.cpp` viene trasformato in **file eseguibili** tramite un **compilatore** (es. GCC, Clang, MSVC).  
- Questo significa che prima di eseguire il programma, il codice deve essere tradotto in linguaggio macchina.

In contrasto, un linguaggio **interpretato** (es. Python, JavaScript) viene eseguito da un interprete (un altro programma) linea per linea senza generare un file eseguibile standalone.

---

## Cosa serve per programmare

### IDE e editor consigliati

Per scrivere e testare codice C++, puoi usare:

- **Code::Blocks**: IDE completo, gratuito, facile da installare e usare.
- **Visual Studio Code**: editor leggero, con plugin C++ (es. C/C++ di Microsoft) per compilazione, debug e evidenziazione sintassi.

### IDE online

Se non vuoi installare nulla, puoi provare IDE online:

- **[GDB Online](https://www.onlinegdb.com/online_c++_compiler)**: compilatore e debugger online, molto utile per provare piccoli programmi velocemente.

---

[Ok, cominciamo!](0-primo-programma)
