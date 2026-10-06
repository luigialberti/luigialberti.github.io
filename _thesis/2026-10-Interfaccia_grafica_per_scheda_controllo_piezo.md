---
title: "Realizzazione di una interfaccia grafica per il controllo di una scheda di alimentazione per trasduttori piezoelettrici"
collection: thesis
type: "BSc"
---

## Descrizione

Questo progetto prevede lo studio e la realizzazione di una **interfaccia grafica** (GUI) per PC dedicata allo scambio di comandi e informazioni di stato con una scheda elettronica che alimenta dei trasduttori piezoelettrici.  

Attualmente lo scambio di informazioni con la scheda avviene mediante un insieme di funzioni scritte in linguaggio Matlab che sfruttano la **comunicazione seriale** tra PC e scheda. Sul lato scheda il protocollo è implementato in linguaggio C e fa parte del firmware di controllo.

La GUI dovrebbe sostituire o mascherare le funzioni Matlab mantenendo la compatibilità con il firmware della scheda già esistente. Lo scopo della GUI è rendere più semplice e intuitiva la gestione della scheda elettronica permettendo all'utente di usare pulsanti, interruttori, display virtuali piuttosto che richiedendogli di eseguire particolari funzioni Matlab. 

## Attività previste

- presa di conoscenza delle modalità operative della scheda
- presa di conoscenza delle funzioni di comunicazione/controllo già disponibili
- definizione delle funzionalità della GUI e del suo layout
- selezione del linguaggio/ambiente di sviluppo da utilizzare per la realizzazione della GUI
- implementazione della GUI
- test e sperimentazione della GUI