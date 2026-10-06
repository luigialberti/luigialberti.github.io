---
title: "Fasatura di una phased array di trasduttori piezoelettrici mediante un sistema di controllo a catena chiusa"
collection: thesis
type: "BSc"
---

## Descrizione

Nelle **phased array** due o più trasmettitori inviano energia sonora a un ricevitore. La fase delle onde sonore viene opportunamente aggiustata in modo che sul ricevitore il loro effetto si sommi risultando massimo.
Questo progetto prevede lo studio e la realizzazione di uno script Matlab che esegue la fasatura di due o più trasmettitori al fine di massimizzare la tensione ottenuta sul ricevitore. Questa operazione è effettuata mediante lo scambio di dati con una  scheda elettronica che alimenta dei trasduttori piezoelettrici e con un oscilloscopio che misura l'ampiezza della tensione ai capi del ricevitore.  

Lo scambio di informazioni con la scheda avviene mediante un insieme di funzioni scritte in linguaggio Matlab, già disponibili, che sfruttano la **comunicazione seriale** tra PC e scheda. Lo scambio di dati con l'oscilloscopio avviene mediante un protocollo di comunicazione seriale di cui sono disponibili le specifiche.


## Attività previste

- presa di conoscenza delle modalità operative della scheda di alimentazione della phased array
- presa di conoscenza delle funzioni Matlab per il controllo della scheda di alimentazione
- presa di conoscenza del protocollo di comunicazione dell'oscilloscopio
- implementazione delle funzioni di comunicazione con l'oscilloscopio
- progettazione dell'algoritmo di fasatura della phased array
- implementazione dell'algoritmo di fasatura 
- test e sperimentazione dell'algoritmo di fasatura