[DA AGGIUSTARE]
# Astrazione funzionale

Un algoritmo trasforma dati di input in dati di output (risultato)
* Si può dire che, poiché trasforma dati iniziali in risultati, definisce un nuovo operatore sui dati
* Il repertorio di operatori disponibili sui dati può essere ampliato scrivendo programmi

L'astrazione funzionale è la tecnica che permette di potenziare il linguaggio disponibile introducendo nuovi operatori 
* Questi sono definiti attraverso sotto-programmi in cui si fa uso degli operatori di base già disponibili
* L'intestazione del sotto-programma introduce il nome e gli argomenti dell'operatore, mentre il corpo ne descrive le regole di comportamento


Consideriamo la formula per il calcolo del coefficiente binomiale 
$$
inserire formula slide 3
$$
che fornisce il numero di possibili combinazioni di n oggetti presi a gruppi di k
* Il calcolo è immediato se si suppone di avere un operatore Fatt(*i*) che calcola il fattoriale per un generico valore di *i* 

```
int Binomial(int n, int k) 
	return Fatt(n)/(Fatt(k) * Fatt(n-k));
```


Se Fatt(*i*) non è disponibile è necessario scrivere un sottoprogramma per ampliare il repertorio degli operatori. L'astrazione funzionale ci consente questo.


I linguaggi di programmazione ad alto livello permettono l'uso di astrazione funzionale, cioè consentono di
* **creare delle unità di programma dando un nome ad un gruppo di istruzioni** e stabiliscono le modalità di comunicazione tra l’unità di programma creata ed il resto del programma in cui essa si inserisce
* al momento della attivazione (su chiamata) della unità di programma viene sospesa l’esecuzione del programma (o dell’unità) chiamante: il controllo passa alla unità attivata e, all’atto del completamento della sua esecuzione, l’attivazione termina e il controllo torna al programma chiamante

I costrutti linguistici per realizzare l’astrazione funzionale consentono di definire una specifica e una realizzazione
* La **specifica** definisce **“cosa”** ci si aspetta dalla funzione, cioè definirà
	* “la relazione che caratterizza il **legame tra dati di ingresso e risultati”** 
* Nel caso del fattoriale la specifica dirà che: 
	* L'intestazione è *int Fatt(int k);* l'ingresso k (argomento) è una variabile di tipo intero; il risultato è ancora di tipo intero
	* La funzione da calcolare è definita come Fatt(k)=k (k-1) … (2) (1)


La **realizzazione** definisce **“come”** il risultato viene ottenuto

* Alla stessa specifica, infatti, potranno corrispondere scelte di realizzazione diverse
* La funzione Fatt potrebbe essere realizzata con un programma iterativo 

```
Fatt(int k) 
	f = 1 
	for i = 2 to k do 
	f = f * i 
return f 
```

ma anche con un programma ricorsivo 

```
Fatt(int k) 
	if k = 1 then f = 1 
	else f = k * Fatt(k-1) 
return f
```


L’astrazione di dati ricalca ed estende il concetto di astrazione funzionale

* Così come l'astrazione funzionale permette di ampliare l'insieme dei modi di operare sui dati, cioè gli operatori sui tipi di dati già disponibili, l’**astrazione di dati** permette di ampliare i tipi di dati disponibili attraverso l'introduzione sia di nuovi tipi di dati che di nuovi operatori ● L'astrazione funzionale stimola gli sforzi per evidenziare operazioni ricorrenti o ben caratterizzate all'interno della soluzione di un problema ● L'astrazione di dati sollecita ad individuare le organizzazioni dei dati più adatte alla soluzione del problema
# Astrazione di dati

Un'astrazione di dati consente un’estensione dell'algebra dei dati disponibile in un linguaggio di programmazione

**Cosa è un'algebra?** è un sistema matematico costituito da un dominio, cioè un insieme di valori, e da un insieme di funzioni applicabili su tali valori 
* il numero, il tipo e le proprietà delle funzioni sono gli elementi essenziali di un algebra 

Corrispondenza tra tipo astratto e algebra
* **insiemi di valori** di un algebra e i **domini di definizione** di un tipo astratto
* tra le **funzioni** di un'algebra e le **operazioni** associate ad un tipo astratto

## Astrazione dati: Esempio

Un numero complesso è un insieme di numeri reali, r1, r2.

Come è noto i numeri complessi hanno forma: r1 + i r2 
* Dove r1 e r2 sono numeri reali e i è √(-1) 
Per denotarli matematicamente basta la coppia (r1, r2)
* dove r1 è il coefficiente della parte reale e r2 quello della parte immaginaria

E' necessario definire operatori di selezione e costruzione che operano su complessi e su reali, operatori di somma e prodotto che operano esclusivamente sui complessi

Il calcolo di somma e prodotto su numeri complessi non è difficile se ricordiamo che 
* la somma di due numeri complessi c1 e c2 dà luogo ad un nuovo numero complesso c3 la cui parte reale è la somma delle parti reali e la cui parte immaginaria è la somma delle parti immaginarie
	* $parteReale(c3) = parteReale(c1) + parteReale(c2)$
	* $parteImmg(c3) = parteImmg(c1) + parteImmg(c2)$
# Requisiti della astrazione dei dati

Lo scopo dell'astrazione è la robustezza, creare sistemi grandi robusti 

Il requisito di astrazione, in accordo con i principi della astrazione di dati, impone che i programmi siano sensibili solo a variazioni della specifica dei nuovi tipi

Il requisito di protezione è particolarmente importante, se vogliamo che l'esecutore del linguaggio assicuri i controlli di consistenza tra i tipi di dati e gli operatori, non solo ai dati primitivi, ma anche ai dati ottenuti per astrazione

Se soddisfo i requisiti precedenti qualsiasi variazione fatta non impatterà chi accede dall'esterno mentre se uso ad esempio una struct allora dovrò in alcuni casi modificare tutte le informazioni che utilizzando i moduli esterni per accedere ad una funzione/dato.

## Specifica e realizzazione

Si è detto che un'astrazione di dati è costituita da:
* una **specifica** e una **realizzazione**

Una specifica, che ha il compito di descrivere sinteticamente il tipo dei dati e gli operatori che li caratterizzano, si distingue in: 
* specifica sintattica che fornisce: l'elenco dei nomi dei tipi di dato utilizzati per definire la struttura, delle operazioni specifiche della struttura e delle costanti. Ovvero le regole sintattiche di un linguaggio. I domini di partenza e di arrivo, cioè i tipi degli operandi e del risultato per ogni nome di operatore
* **specifica semantica** che definisce il significato dei nomi introdotti con la specifica sintattica. Associa: 
	* un insieme ad ogni nome di tipo introdotto nella specifica sintattica
	* un valore ad ogni costante
	* una funzione ad ogni nome di operatore esplicitando le seguenti condizioni sui domini di partenza e di arrivo: 
		* **pre-condizione** che definisce quando l'operatore è applicabile. Le situazioni che consentono di applicare l'operatore.
		* **post-condizione** che stabilisce come il risultato sia vincolato agli argomenti dell'operatore

