## Astrazione funzionale
**L'astrazione funzionale** è la tecnica che permette di potenziare il linguaggio disponibile introducendo nuovi operatori, definiti attraverso sotto-programmi in cui si fa uso degli operatori di base già disponibili

I linguaggi di programmazione ad alto livello permettono l'uso di astrazione funzionale, cioè consentono di:
- creare delle unità di programma dando un nome ad un gruppo di istruzioni e stabiliscono le modalità di comunicazione tra l’unità di programma creata ed il resto del programma in cui essa si inserisce
- al momento della attivazione (su chiamata) della unità di programma viene sospesa l’esecuzione del programma (o dell’unità) chiamante, passando il controllo all'unità attivata, terminando poi e tornando al programma chiamante

I costrutti linguistici per realizzare l’astrazione funzionale consentono di definire una **specifica** e una **realizzazione**:
- La **specifica** definisce “cosa” ci si aspetta dalla funzione quindi la relazione che caratterizza il legame tra dati di  ingresso e risultati
- La **realizzazione** definisce “come” il risultato viene ottenuto, ad una stessa specifica ci possono essere più realizzazioni
## Astrazione dati
L’**astrazione di dati** permette di ampliare i tipi di dati disponibili attraverso l'introduzione sia di nuovi tipi di dati che di nuovi **operatori**.

Un'astrazione di dati consente un'estensione dell'algebra dei dati disponibile in un linguaggio di programmazione. 
Ma cos'è un'algebra? È un sistema matematico costituito da un dominio, cioè un insieme di valori, e da un insieme di funzioni applicabili su tali valori, dove il numero, il tipo e le proprietà delle funzioni sono gli elementi essenziali di un'algebra. 
Esiste una corrispondenza diretta tra tipo astratto e algebra, specificamente tra gli insiemi di valori di un'algebra e i domini di definizione di un tipo astratto, e tra le funzioni di un'algebra e le operazioni associate ad un tipo astratto.

Per estendere l'algebra dei dati disponibile in un linguaggio di programmazione, molti linguaggi forniscono i mezzi per definire e creare nuovi tipi di dati, ma non tutti consentono di fare astrazione dati o creare tipi di dati astratti. Un tipo di dati si dice astratto se le operazioni applicabili sugli oggetti che li rappresentano sono isolate dai dettagli usati per realizzare il tipo.
### Requisiti dell'astrazione dati
## Specifica di realizzazione

## Struttura di dati
Tra i tipi di dato possiamo individuarne particolari, chiamate **strutture di dati**, che tendono a rappresentare una collezione di dati che la compongono dal tipo e dall'organizzazione degli elementi componenti.
Nei linguaggi si trovano solo tabelle monodimensionali (vettori o array) 

In generale si distinguono in:
- **Lineari**: i suoi elementi sono in una sequenza, con un certo ordine
- **Non lineari**: non esiste una sequenza 

- **A dimensione fissa**: il numero di elementi non varia nel tempo
- **A dimensione variabile**: il cui numero di elementi varia nel tempo

- **Omogenee**
- **Non omogenee**