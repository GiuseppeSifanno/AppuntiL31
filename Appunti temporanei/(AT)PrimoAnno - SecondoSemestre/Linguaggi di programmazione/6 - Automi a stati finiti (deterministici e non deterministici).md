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
Sia M = $(Q, \delta, q_{0}, F)$ un FSA con alfabeto di ingresso $X$, **il linguaggio accettato o riconosciuto** da $M$ è il seguente sottoinsieme di $X^*$:$$T(M)=\{w \in X^*| \delta (q_{0},w \in F)\}$$
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
Dato in ingresso un alfabeto $X$Un automa a stati finiti non deterministico(**FSA**) è una quadrupla definita con:
$$M=(Q,\delta,q_{0},F)$$