## Documentare un prodotto
Un prodotto viene documentato tramite due manuali solitamente:
- **Manuale Tecnico**: descrive **come è fatto** un prodotto
- **Manuale d'uso**: descrive **cosa fa** un prodotto

Un prodotto quindi non è altro che un insieme di <u>attributi</u> tangibili e intangibili di un bene o un <u>servizio</u> volti a procurare un beneficio a un <u>utilizzatore</u>, ottenuto tipicamente attraverso un processo di <u>produzione</u>

Alcune delle parole evidenziate possono essere associate al software, che anche lui è un **prodotto**:
- **Attributi** = Funzionalità del software
- **Servizio** = Scopo del software
- **Utilizzatore** = Utente del software
- **Produzione** = Sviluppo del software

Anche una **libreria** è un modulo di software più grande e può essere vista come un prodotto:
- **Attributi** = Cosa implementa (funzioni, procedure, tipi di dati, costanti...)
- **Servizio** = Scopo della libreria
- **Utilizzatore** = Sviluppatore che usa la libreria
- **Produzione** = Programmazione della libreria

Ogni prodotto che si rispetti ha un **interfaccia** e un **implementazione**:
- L'interfaccia è come il prodotto viene mostrato al pubblico
- L'implementazione invece è la struttura interna
Nel nostro caso l'interfaccia sono le **funzioni implementate in una libreria**, mentre l'implementazione è **il codice sorgente che le realizza**, e tutte e due possono essere documentate in modo generativo.
La documentazione dell'interfaccia spiega come può il software o la libreria può essere **utilizzata da un utente finale**, mentre la documentazione sull'implementazione fornisce dettagli **sul processo alla realizzazione del prodotto** 
### Documentazione di una libreria
L'interfaccia di una libreria software rappresenta **la descrizione degli attributi pubblici**, cioè le funzionalità utilizzabili dall'utilizzatore, in questo caso il file header