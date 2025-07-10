### 1. Definizioni
#### Concetti di base:
 **Grammatica**:
 Una grammatica generativa (o struttura di frase G) è una quadrupla
$$G=(X,V,S,P)$$
dove:
- $X$ è l'alfabeto terminale per la grammatica
- $V$ è l'alfabeto non terminale per la grammatica
- $S$ è il simbolo di partenza per la grammatica
- $P$ è l'insieme di produzioni della grammatica con le seguenti condizioni:$X \cap V = \oslash$ (non hanno elementi comuni tra loro) e $S \in V$ (esiste un simbolo di partenza nell'alfabeto non terminale)

**Regola di produzione / Produzione**:
Una produzione è una coppia di parole $(v,w)$,
dove $v \in (X \cup V)^+$ e dove $w \in (X \cup V)^*$
Un elemento $(v,w)$ di $P$ viene comunemente scritto nella forma
$$v \to w$$

**Derivazione diretta**:
Una produzione diretta avviene quando, dove data una grammatica $G=(X,V,S,P)$, abbiamo due stringhe $y$ e $z$ (composte da simboli terminali e non terminali con pezzi in comune) tali che:
$$y \Rightarrow z$$
**Linguaggio generato da una grammatica**:
Sia $G=(X,V,S,P)$ una grammatica, il **linguaggio generato da G**, denotato con $L(G)$, è l'insieme delle stringhe di terminali derivabili dal simbolo di partenza $S$
$$L(G)=(w \in X^{*} | S \Rightarrow w)$$
 **Albero di derivazione**:
 Data una grammatica C.F. e una parola $w$ derivabile da tale linguaggio, un albero $T$ rispetta le seguenti proprietà:
- la radice è etichettata con $S$
- ogni nodo interno è etichettato con un simbolo di $V$
- ogni nodo esterno (foglie) è etichettato con un simbolo di $X$ o $\lambda$
- se un nodo $N$ è etichettato con $A$, ed $N$$ ha $k$ discendenti diretti $N_{1},N_{2},\dots,N_{k}$ etichettati con i simboli $A_{1},A_{2},\dots,A_{k}$, allora la produzione $A \to A_{1},A_{2},\dots,A_{k}$  appartiene a $P$.
- la stringa $w$ è rappresentata dalla frontiera dell'albero.

**Grammatica context-sensitive:**
Una grammatica $G=(X,V,S,P)$ è **dipendente da contesto** se ogni produzione in $P$ è in una delle seguenti forme:

- **Produzione contestuale**:$$yAz \to ywz$$ con $A \in V$,$y, z \in (X \cup V)^*$ e $w \in (X \cup V)^+$.
- **Produzione speciale per la stringa vuota:**$$S \rightarrow \lambda$$
### 2. Algoritmi e Procedure
**Da grammatica a automa:**
Data una grammatica lineare destra $G = (X, V, S, P)$,l'automa accettore a stati finiti equivalente $M = (Q, \delta, q_0, F)$ viene costruito come segue:
1. $X$ come l'alfabeto di ingresso
2. $Q = V \cup \{q\}$, con $q \notin V$
3. $q_0 = S$
4. $F = \{q\} \cup \{B \mid B \rightarrow \lambda \in P\}$
5. La funzione di transizione $\delta:Q \times X \to 2^{Q}$ è definita nel modo seguente:
   - **(V.a)** $\forall B \to aC \in P, C \in \delta(B, a)$ 
   - **(V.b)** $\forall B \to a \in P, q \in \delta(B, a)$**

**Da Automa Non Deterministico a Deterministico**: 
![[Pasted image 20250710163336.png]]
### 3. Teoremi e Dimostrazioni
- **Proprietà degli Alberi di Derivazione**: Enunciare e dimostrare la relazione esistente tra l'altezza di un albero di derivazione e la lunghezza della sua frontiera nelle grammatiche libere da contesto.
### 4. Strutture Dati del Compilatore
- **Funzioni Generali**: Descrivere il contenuto e le funzioni principali della tabella dei simboli
- **Gestione nei Linguaggi a Blocchi**: Descrivere le operazioni di set e reset per la gestione delle tabelle dei simboli nei linguaggi a blocchi.
