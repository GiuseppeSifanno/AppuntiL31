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

Ogni prodotto che si rispetti ha un **interfaccia** e un **implementazione**:
- L'interfaccia è come il prodotto viene mostrato al pubblico
- L'implementazione invece è la struttura interna

La documentazione dell'interfaccia spiega come può il software (o la libreria) essere **utilizzata da un utente finale**, mentre la documentazione sull'implementazione fornisce dettagli **sul processo alla realizzazione del prodotto** 
### Documentazione di una libreria
Anche una **libreria** è un modulo di software più grande e può essere vista come un prodotto:
- **Attributi** = Cosa implementa (funzioni, procedure, tipi di dati, costanti...)
- **Servizio** = Scopo della libreria
- **Utilizzatore** = Sviluppatore che usa la libreria
- **Produzione** = Programmazione della libreria

L'interfaccia viene rappresentata dalle **funzioni implementate in una libreria**, mentre l'implementazione è **il codice sorgente che le realizza**, e tutte e due possono essere documentate in modo generativo.

L'interfaccia di una libreria software rappresenta **la descrizione degli attributi pubblici**, cioè le funzionalità utilizzabili dall'utilizzatore, in questo caso per le librerie in C si definisce con un file header di un modulo.
Fornire comunque il codice dell'interfaccia non è **sufficiente a rendere utilizzabile una libreria**, ma è necessaria una **documentazione aggiuntiva**.

Cosa deve offrire questa documentazione aggiuntiva?:
- Descrivere il **significato dei tipi** e delle **costanti pubbliche**
- Descrivere **cosa fanno le funzioni e le procedure**
- **Non deve descrivere come le funzioni e le procedure svolgono il loro compito** (concetto di information hiding)
Documentare il codice equivale a scrivere un **manuale d'uso**, in questo caso l'interfaccia di una libreria
### Documentazione vs commento
C'è un importante differenza tra la documentazione di un prodotto sorgente e il commento del codice sorgente:
- La **documentazione** spiega il significato di una funzione **all'utilizzatore**
- Il **commento** spiega i punti più critici al **programmatore** della funzione
### Documentazione di una funzione
Quando si documenta una funzione cosa bisogna inserire?
1. **Cosa fa la funzione**:
   - Scenari tipici (comportamento normale della funzione)
   - Scenari eccezionali (cosa fa la funzione in caso di situazioni anomale)
2. **Significato e dominio dei parametri**
3. **Esempi d'uso** 
4. **Pre-condizioni**
5. **Post-condizioni**
6. Eventuali riferimenti (altre funzioni, link, test, standard...)
7. Eventuali note (funzioni deprecate, portabilità...)
#### Documentazione pre-condizione
La pre-condizione è **una condizione che deve essere vera prima della chiamata di una funzione**, solitamente è una condizione sui paramenti.
Se una pre-condizione è falsa, **il funzionamento non è garantito**.
*ES*. la funzione per il calcolo del BMI ha come pre-condizione che peso e altezza siano maggiori di 0 ed eventualmente minuri di una certa soglia.

Il chiamante di una procedura ha la responsabilità di garantire la verifica di tutte le condizioni (una pre-condizione falsa è sintomo di bug)

**IMPORTANTE:** la definizione delle pre-condizioni non implica il mancato uso della programmazione difensiva, infatti è bene specificare le precondizioni ma anche rendere il codice solido in modo tale da restituire risultati anche quando le pre-condizioni non sono verificate
Sapere a priori quali errori possono verificarsi è diverso dallo scrivere codice in grado di gestirli!
#### Documentazione post-condizione
La post-condizione è **una condizione che deve essere vera dopo l'esecuzione di una funzione**, solitamente è sui parametri di output.
La falsificazione di una post-condizione (se le pre-condizioni sono verificato) è un chiaro sintomo della presenza di un bug nella funzione. 
*ES*. riprendendo il BMI, se non corrisponde a quello corretto evidentemente c'è un problema nell'implementazione
### Documentazione in linea
Oltre a documentare le funzioni nel modo convenzionale, si può documentare una libreria nel **codice sorgente stesso**, ma è
