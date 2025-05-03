(Si ringrazia Giada per una parte di appunti scritti a mano)
## Automa deterministico
Un automa a stati finiti deterministico, noto anche come accettore a stati finiti deterministico, è un modello matematico utilizzato nell'informatica teorica per riconoscere linguaggi formali.
Un automa a stati finiti è vantaggioso per avere una memoria limitata più facile da gestire, ma comunque con vincoli molto importanti.
### Definizione (stati deterministici)
Sia $X$ un alfabeto (di tipo terminale), un automa a stati finiti(**FSA**) è una quadrupla definita con:
$$M=(Q,\delta,q_{0},F)$$
dove:
- $X$ è detto **alfabeto di ingresso**
- $Q$ è un insieme finito e non vuoto di **stati**, chiamati anche memoria dell'automa e, come i simboli NT, permettono di effettuare transizioni nella fase di riconoscimento
- $\delta$ è una funzione da in $Q$, detta **funzione di transizione**:$$\delta: Q \times X \to Q$$
- $q_{0}$ è lo stato iniziale (dove comincia il processo di riconoscimento)
- $F \subseteq Q$ è l'insieme degli stati di accettazione o finali, dove, se l'automa termina le transizioni in quello stato, la parola viene accettata.

Talora i valori della funzione di transizione $\delta$ non sono definiti per tutte le coppie (stato-simbolo di ingresso) $(q,x)$, si dice che $\delta$ è una **funzione parziale** o definita parzialmente. Questo significa che la lettura di $x$ dà luogo in $q$ ad un comportamento dell’automa che non si ritiene utile descrivere ai fini del riconoscimento (nel senso che produrrebbe stringhe non accettate).
Evidentemente questo fatto può essere descritto in modo equivalente, seguendo la definizione data di automa a stati finiti, passando da $q$, per effetto di $x$, in uno stato dal quale non si possa mai raggiungere uno stato finale (chiamato anche **stato pozza**).
Lo stato pozza non è altro che uno stato generato **a seguito di input su uno stato non definito nel dominio**
### Rappresentazione di un FSA
#### Grafo degli stati/Diagramma di Transizione/ Diagramma di stato
È una rappresentazione grafica in cui:
- Ogni stato $q \in Q$ è rappresentato da un cerchio, o nodo, con etichetta q
- Lo stato iniziale (nodo $q_{0}$) ha un arco orientato entrante libero (ossia che non proviene da nessun altro nodo)
- per ogni stato $q \in Q$ e per ogni simbolo $x$ dell'alfabeto di ingresso, $x \in X$, se $\delta(q,x)=q'$, esiste un arco orientato etichettato con $x$ uscente dal nodo $q$ ed entrante nel nodo
![[Pasted image 20250424165857.png]]
![[Pasted image 20250424165926.png]]
#### Tavola di Transizione
È una tabella in cui sono riportati gli stati sulle righe e i simboli dell'alfabeto di ingresso sulle colonne.
Per ogni coppia (stato-ingresso) si legge nella tavola lo stato successivo:
![[Pasted image 20250424175818.png]]
dove l’alfabeto di ingresso e l’insieme degli stati sono rispettivamente:$X=\{x_{1},x_{2},\dots,x_{n}\}$ e $Q=\{q_{0},q_{1},\dots,q_{m}\}$

Quindi si ha che:
$\delta(q_{i}​,x_{j}​)=q_{i}^j \quad ​\text{con} \quad q_{i}​, q_{i}^j \in Q,​x_{j}​ \in X$,
Ovvero **Se l’automa è nello stato $q^i$ e legge il simbolo $x^j$​, allora passa nello stato $q^i_j$​.**

In altre parole:
- Ogni cella della tavola di transizione contiene $q_{i}^j$​, che è lo stato raggiunto quando l’automa è in $q_{i​}$​ e legge $x_{j}$.
- Poiché è un **DFA**, per ogni coppia $(q_{i​},x_{j}​)$ esiste **esattamente un unico stato $q_{i}^j$​** (determinismo).
#### Estensione della funzione di transizione
L'**estensione della funzione di transizione** $\delta^*$ è un concetto fondamentale negli automi a stati finiti (DFA e NFA) che generalizza la funzione di transizione base $\delta$ per lavorare con **intere stringhe** (sequenze di simboli) invece di singoli caratteri.

**Definizione:**
Dato un automa a stati finiti(FSA) $M=(Q,\delta,q_0,F)$ con alfabeto di ingresso $X$ definiamo la funzione:$$\delta^*:Q\times X^*\to Q$$tale che $\delta^*(q,w)$, per $q \in Q$ e $w \in X^*$, sia lo stato in cui $M$ si porta avendo in ingresso la parola $w$ su $X$ e partendo dallo stato $q$
**Definizione ricorsiva**
![[Pasted image 20250428101154.png]]La prima parte è il caso base, dove con una stringa vuota si rimane nello stato corrente, nel passo induttivo si calcola prima lo stato processando $w$ e applicando la transizione per l'ultimo simbolo $w$
![[Pasted image 20250428102336.png]]
### Parola accettata o riconosciuta da un FSA
Sia M = $(Q, \delta, q_{0}, F)$ un FSA con alfabeto di ingresso $X$. Una parola $w \in X^*$ è **accettata** (o **riconosciuta**) da $M$ se, partendo dallo stato iniziale $q_{0}$, lo stato $q$ in cui l’automa si porta alla fine della sequenza di ingresso $w$ è uno stato finale.
$$w \text{ accetata }\xLeftrightarrow{def} \delta (q_{0},w) \in F$$
Questa definizione coincide con il concetto di parola generata da una grammatica
### Linguaggio accettato o riconosciuto da un FSA 
Sia $M = (Q, \delta, q_{0}, F)$ un FSA con alfabeto di ingresso $X$, **il linguaggio accettato o riconosciuto** da $M$ è il seguente sottoinsieme di $X^*$:$$T(M)=\{w \in X^*| \delta (q_{0},w \in F)\}$$
$T(M)$ è il linguaggio generato dall'automa $M$,ovvero l'insieme di tutte le stringhe che, quando processate da MM, portano a uno stato finale.
Questa definizione coincide con il concetto di grammatiche equivalenti
### FSA equivalenti
Sia $M_{1}=(Q_{1},\delta_{1},q_{1},F_{1})$ ed $M_{2}=(Q_{2},\delta_{2},q_{2},F_{2})$ due FSA di alfabeto di ingresso $X$, $M_{1}$ e $M_{2}$
si dicono equivalenti se:$$T(M_{1})=T(M_{2})$$
### Linguaggi a stati finiti
**Definizione di una nuova classe di lunguaggi**
Dato un alfabeto $X$, un linguaggio L su $X$ è un **linguaggio a stati finiti** (o FSL - Finite State Language) se esiste un automa che lo accetta FSA $M$ con alfabeto di ingresso $X$ tale che $L=T(M)$
#### Classe dei linguaggi a stati finiti
La **classe dei linguaggi a stati finiti** (indicata come $\mathcal{L}_{FSL}$) è l'insieme di tutti i linguaggi formali che possono essere **riconosciuti da un automa a stati finiti deterministico (FSA)** o non deterministico (NDA). 
Questi linguaggi sono strettamente legati alle **grammatiche regolari** e costituiscono la classe più semplice nella gerarchia di Chomsky.
**Definizione:**
Dato un alfabeto $X$, la classe $\mathcal{L}_{FSL}$ è definita come:
$$
\mathcal{L}_{FSL} = \left\{ L \subseteq X^* \,\middle|\, \exists \text{ FSA } M \text{ tale che } L = L(M) \right\}
$$
dove $T(M)$ è il linguaggio accettato dall'automa $M$.
## Automa non deterministico
Dato in ingresso un alfabeto $X$,un automa a stati finiti non deterministico(**FSA**) è una quadrupla definita con:
$$M=(Q,\delta,q_{0},F)$$dove:
- Per $Q,q_{0},F$ valgono le definizioni date per gli FSA
- $\delta:Q\times X \to 2^{Q}$ è la funzione di transizione che assegna ad ogni coppia (stato-simbolo di ingresso) $(q,x)$ un insieme $\delta(q,x)\subseteq Q$ di possibili stati successivi

Un NDA è un FSA con l'unica eccezione che, in corrispondenza di una coppia (stato simbolo di ingresso) $(q,x)$, vi è un insieme di stati in cui l'automa può transitare (stati successivi possibili)
### Estensione della funzione di transizione per un NDA
Come per gli FSA si può definire un'estensione della funzione di transizione $\delta$ come segue:
**Definizione $\delta^{*}$ per NDA**
Dato un NDA $M=(Q,\delta,q_{0},F)$ con alfabeto di ingresso X, definiamo per induzione la funzione: $$\delta^{*}:2^{Q} \times X^{*} \to 2^{Q}$$
La definizione è induttiva:

Si parte dal **caso base** (con parola vuota $\lambda$):
$$M = (Q, \delta, q_0, F)$$
Per arrivare al passo **induttivo**:
$$\delta^*(q, xw') = \bigcup_{p \in \delta(q, x)} \delta^*(p, w')$$
Se leggo una parola composta da un simbolo iniziale $x$ seguito da una parola $w$, allora:
- prima vedo dove posso andare da $q$ leggendo $x$: $\delta(q, x)$ è un insieme di stati.
- poi, per ciascuno di questi stati $p$, calcolo $\delta^*(p, w)$, ossia dove posso arrivare leggendo $w$ da $p$.
- l’unione di tutti questi insiemi è il risultato finale.

Analogamente a quanto fatto per gli FSA, si dovrebbero riformulare le definizioni di parola accettata e di linguaggio accettato da un NDA. La complicazione, rinveniente dalla computazione non deterministica dello stato successivo in cui un
NDA transita, comporta che una stessa parola può indurre cammini multipli attraverso un NDA, alcuni che terminano in stati di accettazione, altri che terminano in stati di non accettazione.
```
(Guardare Esempio Esercizio 6_1)
```
### Parola accettata o riconosciuta da un NDA
Sia M = $(Q, \delta, q_{0}, F)$ un NDA con alfabeto di ingresso $X$. Una parola $w \in X^*$ è **accettata** (o **riconosciuta**) da $M$ se, partendo dallo stato iniziale $q_{0}$, se esiste almeno un modo per M di portarsi in uno stato di accettazione alla fine della sequenza di ingresso $w$
$$w \text{ accettata } \iff \exists p \in \delta^*(\{q_0\}, w) \cap F \iff \delta^*(\{q_0\}, w) \cap F \neq \emptyset

$$
### Linguaggi accettati o riconosciuti da un NDA
Sia M = $(Q, \delta, q_{0}, F)$ un FSA con alfabeto di ingresso $X$, **il linguaggio accettato o riconosciuto** da $M$ è l'insieme delle parole su $X$ accettate da $M$
$$T(M)=\{ w \in X^* \mid \delta^*(\{q_0\}, w) \cap F \neq \emptyset \}$$
(è l’insieme delle parole $w$ per le quali esiste almeno un cammino, etichettato con lettere di $w$ nell'ordine da sinistra a destra, attraverso il diagramma degli stati che porta $M$ dallo stato iniziale ad uno degli stati di accettazione).
### NDA equivalenti
Sia $M_{1}=(Q_{1},\delta_{1},q_{1},F_{1})$ ed $M_{2}=(Q_{2},\delta_{2},q_{2},F_{2})$ due NDA di alfabeto di ingresso $X$, $M_{1}$ e $M_{2}$
si dicono equivalenti se:$$T(M_{1})=T(M_{2})$$
### Classe dei linguaggi riconosciuti da automi a stati finiti non deterministici
La classe dei linguaggi riconosciuti da automi a stati finiti non deterministici (NDA) è definita come l'insieme di tutti i linguaggi formali che possono essere accettati da almeno un automa a stati finiti non deterministico.

Data la notazione nel documento:

$\mathcal{L}_{NDL} = \{ L \in 2^{X^*} \, | \, \exists M, \, M \text{ è un NDA}: L = T(M) \}$

Dove:
- $(X)$ è un alfabeto finito
- $(2^{X^*})$ rappresenta l'insieme di tutti i linguaggi possibili sull'alfabeto $X$
- $(M)$ è un automa a stati finiti non deterministico (NDA)
- $(T(M))$ è il linguaggio accettato dall'automa $M$
##### Caratteristiche Principali
1. **Equivalenza con gli automi deterministici**: Un risultato fondamentale è che questa classe è esattamente equivalente alla classe dei linguaggi riconosciuti da automi a stati finiti deterministici (DFA). Questo significa che per ogni NDA esiste un DFA equivalente che riconosce lo stesso linguaggio, e viceversa.
2. **Metodo di riconoscimento**: Un NDA accetta una parola se esiste almeno un cammino computazionale (tra i molti possibili a causa del non determinismo) che porta da lo stato iniziale a uno stato finale.
3. **Potere espressivo**: Nonostante il non determinismo, gli NDA non possono riconoscere linguaggi più complessi di quelli riconoscibili da DFA. Il non determinismo offre spesso una rappresentazione più compatta o intuitiva degli stessi linguaggi.
#### Equivalenza dei linguaggi riconosciuti da automi a stati finiti non deterministici
Gli automi a stati finiti deterministici (DFA) e non deterministici (NFA) riconoscono la **stessa classe di linguaggi**, ovvero i **linguaggi regolari**. Questo significa che:
- **Ogni NFA può essere convertito in un DFA equivalente** (che riconosce lo stesso linguaggio).
- **Ogni DFA è già un caso particolare di NFA** (dove ogni transizione porta a un solo stato).
##### Teorema 
- 1a formulazione): Le classi dei linguaggi $( \mathcal{L}_{FSL} )$ e $( \mathcal{L}_{NDL} )$ sono equivalenti.
- 2a formulazione):Sia $L$ un linguaggio su $X$, $L$ è un linguaggio a stati finiti se e solo se $L = T(M)$  per qualche NDA $M$.
##### Dimostrazione
**Parte 1: Da FSA a NDA ($\Rightarrow$)**
- **Ipotesi**: $L \in \mathcal{L}_{FSL} $ (esiste un FSA $ M_1 $ che riconosce $L$)  
- **Costruzione**: Dato $ M_1 = (Q_1, \delta_1, q_1, F_1) $, definiamo un NDA $ M_2 $ tale che:  
  \[
  M_2 = (Q_2, \delta_2, q_2, F_2)
  \]
  dove:  
  - $ Q_2 = Q_1 $  
  - $ \delta_2(q, x) = \{\delta_1(q, x)\} $ (transizioni come insiemi singoli)  
  - $ q_2 = q_1 $  
  - $ F_2 = F_1 $  

- **Risultato**: $ T(M_2) = T(M_1) $.  
  Ogni FSA è un caso particolare di NDA con transizioni deterministiche "impacchettate" in insiemi.


- **Ipotesi**: $ L \in \mathcal{L}_{FSL} $ (esiste un FSA $ M_1 $ che riconosce $ L $)  
- **Costruzione**: Dato $ M_1 = (Q_1, \delta_1, q_1, F_1) $, definiamo un NDA $ M_2 $ tale che:  
  \[
  M_2 = (Q_2, \delta_2, q_2, F_2)
  \]
  dove:  
  - $ Q_2 = Q_1 $  
  - $ \delta_2(q, x) = \{\delta_1(q, x)\} $ (transizioni come insiemi singoli)  
  - $ q_2 = q_1 $  
  - $ F_2 = F_1 $  

- **Risultato**: $ T(M_2) = T(M_1) $.  
  Ogni FSA è un caso particolare di NDA con transizioni deterministiche "impacchettate" in insiemi.

