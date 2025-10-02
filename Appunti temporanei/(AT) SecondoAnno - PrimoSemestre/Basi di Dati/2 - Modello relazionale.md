[DA AGGIUSTARE, guardare foto A.M.]
Il **modello relazionale** è stato proposto da **Edgar Frank Codd** nel lavoro _“A Relational Model for Large Shared Data Banks”_.

Esso nasce per **superare le limitazioni** dei modelli **gerarchici** e **reticolari**, i quali:
- Includevano **espliciti riferimenti alla struttura realizzativa sottostante**, attraverso l’uso di **puntatori** e l’**ordinamento fisico dei dati**.
- Non permettevano di realizzare pienamente la **proprietà di indipendenza dei dati**, già riconosciuta come fondamentale.
    
Il modello relazionale si fonda su due concetti principali:
- **Relazione (formale):** il concetto matematico astratto.
- **Tabella (intuitivo):** la rappresentazione pratica e immediata utilizzata per la comprensione e la gestione dei dati.
  
**Definizione formale:**
Una **relazione matematica** sui domini $D_1, D_2, …, D_n$ è un **sottoinsieme del prodotto cartesiano** $D_1 \times D_2 \times … \times D_n$.
- $n$ è detto **grado** del prodotto cartesiano (e quindi della relazione).
- Il **numero di $n–uple$ presenti nella relazione è la sua** **cardinalità**.

Poiché una **relazione** è definita come un **insieme**, essa possiede alcune proprietà fondamentali:
1. **Non esiste un ordinamento tra le n–uple**: l’eventuale ordinamento delle righe in una tabella è puramente occasionale e non ha significato logico.
2. **Le n–uple sono tutte distinte**: in un insieme non possono esserci duplicati; di conseguenza, una tabella rappresenta correttamente una relazione solo se ciascuna riga è diversa dalle altre.
    
Tuttavia, all’interno di una relazione, ogni **n–upla è ordinata**: ciò significa che          l’**i-esimo valore** di ciascuna tupla proviene dal dominio $D_i$.

Le informazioni che vogliamo organizzare nei database seguono una struttura riconducibile a quella dei **record**:
- Una relazione può quindi essere rappresentata come un **insieme di record omogenei**.
- Attribuendo un **nome (attributo)** a ciascun dominio, l’**ordinamento dei domini** diventa irrilevante, poiché l’identificazione è data direttamente dagli attributi.


### **Attributi, domini e tuple**
La **corrispondenza** tra l’insieme degli **attributi** $X$ e l’insieme dei **domini** $D$ è stabilita tramite una funzione:
$\text{DOM}: X \rightarrow D$
che associa a ciascun attributo $A \in X un dominio \text{DOM}(A) \in D$.

**Definizione:**
Una **tupla** su un insieme di attributi $X$ è una funzione t che associa a ciascun $A \in X$ un valore appartenente al dominio $\text{DOM}(A)$.
- Il valore di t su A può essere indicato come **t[A]** o **t.A**.
- Il valore di t su un insieme di attributi, ad esempio A e B, si indica come **t[AB]**.

Una **relazione** su X è definita come un **insieme di tuple** su X ed è tipicamente rappresentata mediante **tabelle dotate di intestazione** (con gli attributi come colonne).

Una **base di dati relazionale** è costituita da **più relazioni**, ciascuna organizzata secondo lo schema degli attributi e dei domini corrispondenti.


# Modello relazionale: vantaggi
Rispetto al modello basto sui record e puntatori, il modello relazionale, **basato sui valori**, presenta diversi vantaggi:
1. **Astrazione:** richiede di rappresentare solo ciò che è rilevante dal punto di vista di applicazione/utente. 
2. **Portabilità:** essendo tutta l'informazione contenuta nei valori, è relativamente semplice trasferire i dati da un contesto ad un altro. (Al contrario, i puntatori hanno un significato locale al singolo sistema, che non è immediato).
3. **Indipendenza fisica dei dati**: la rappresentazione logica dei dati non fa riferimento a quella fisica. 

### **Schemi e istanze relazionali**
- **Schema di relazione**
    Uno **schema di relazione** è costituito da un simbolo R, detto **nome della relazione**, e da un insieme di **attributi**    
    $X = \{A_1, A_2, …, A_n\}$
    a ciascuno dei quali è associato un dominio.
    
- **Schema di base di dati**
    Uno **schema di base di dati** è un insieme di schemi di relazione con **nomi diversi**, indicato come:
    $R = \{ R_1(X_1), R_2(X_2), …, R_m(X_m) \}$
    
- **Istanza di relazione**
    Una **istanza di relazione** su uno schema R(X) è un insieme r di tuple su X.

- **Istanza di base di dati**
    Un’**istanza di base di dati** su uno schema
    $R = \{ R_1(X_1), R_2(X_2), …, R_m(X_m) \}$
    è un insieme di relazioni
    $r = \{ r_1, r_2, …, r_m \}$
    dove ogni $r_i$ è una relazione sullo schema $R_i(X_i)$.

### **Attributi senza valore**
Quando si aggiunge una tupla a una relazione, **può non essere possibile specificare il valore di un attributo**.
Secondo l’ANSI (American National Standards Institute), esistono vari motivi per cui un valore può essere mancante; tra i principali:
1. **Valore non applicabile** (_inapplicable attribute_). 
2. **Valore sconosciuto** (_unknown attribute_).  
3. **Valore senza informazione** (_no information_). 

# **Informazione incompleta e valori nulli**
In alcuni casi può rendersi necessario rappresentare l’**assenza di un valore** per un attributo.
Una prima soluzione consiste nell’utilizzare un valore del dominio (es. una stringa di 15 spazi).

Tuttavia questa soluzione non è soddisfacente, perché:
1. Richiede che nel dominio esista un valore **mai usato realmente** come valore significativo.
2. La distinzione tra valori “veri” e valori fittizi deve essere gestita direttamente nei **programmi applicativi**, aumentando la complessità.

Per ovviare a questo problema, il concetto di **relazione** è stato esteso:
- ogni tupla può assumere, per ciascun attributo, **un valore del dominio** oppure un **valore speciale** detto **valore nullo (NULL)**.
- **NULL** denota l’assenza di informazione, senza necessità di introdurre valori artificiali nei domini.
![[Pasted image 20251002163950.png]]
1. Il valore nullo sulla data di nascita è ammissibile.
2. Il valore nullo sul numero di matricola impedisce di stabilire correlazioni fra tuple di relazioni diverse.
3. La presenza di più valori nulli in una tupla può rendere inutilizzabili le altre informazione nella tupla.
4. La presenza di più valori nulli in una relazione può causare problemi sull’identità delle tuple.
