(Forniti gentilmente dal pasticcino alla crema di Pice)
## Gerarchia di Chomsky
Sia $G=(X,V,S,P)$ una grammatica, dalla sua definizione si ha:
$$P=\{v \rightarrow w | v \in (X \cup V)^{+} \text{ e v contiene almeno un NT}, w \in  (X \cup V)^{*}\}$$
Definita anche come la produzione di una coppia di stringe (dove $v$ appartiene all'insieme di tutti i simboli con almeno un simbolo terminale e $w$ l'unione dei simboli terminali e non terminali)
### Classificazione
A seconda delle restrizioni imposte sulle regole di produzione, si distinguono le varie classi di grammatiche:
- **Tipo 0**: quando le stringhe che appaiono nella produzione non sono soggette ad alcuna limitazione
- **Tipo 1 - Dipendenti da contesto**: quando le produzioni sono limitate alla forma
  1. $yAz \rightarrow ywz$ con $A \in V, \space y,z \in (X \cup V)^{*}, \space w \in (X \cup V)^{*}$
  2. $S \rightarrow \lambda$, purchè $S$ non compaia nella parte destra di alcuna produzione
- **Tipo 2 - Libera da contesto**: quando le produzioni sono limitate alla forma $v \to w \text{ con } v \in V$
- **Tipo 3 - Lineare destra**: quando le produzioni sono limitate alla forma
  1. $A \to bC \text{ con } A,C \in V \text{ e } b \in X$ ($A \text{ e } C$ producono terminale, $b$ produce non terminale)
  2. $A \to b \text{ con } A \in V \text{ e } b \in X \cup \{\lambda\}$ ($A$ produce terminale e $b$ produce nulla)

Una grammatica di tipo ‘3’ è detta **lineare destra** perché il simbolo $NT$, se c’è, compare a destra (nella parte destra della produzione).
**Un linguaggio generato da una tale grammatica è detto di tipo ‘3’ o lineare a destro**
### Teorema della gerarchia
Il **Teorema della Gerarchia di Chomsky** dimostra che le quattro classi di linguaggi formali (classificate come tipo 0, 1, 2 e 3) formano una gerarchia strettamente inclusiva, dove ogni classe è un sottoinsieme proprio della precedente.
Denotiamo con $\mathcal{L}_i$ (insieme dei linguaggi di tipo $i$) il seguente insieme:
$$\mathcal{L}_i=\{L \subset X^{*}|L=L(G), G \text{ di tipo i}\}$$
La gerarchia di Chomsky è una gerarchia in senso stretto di classi di linguaggi:
$$\mathcal{L_{3}} \underset{\neq}{\subset} \mathcal{L_{2}} \underset{\neq}{\subset} \mathcal{L_{1}} \underset{\neq}{\subset} \mathcal{L_{0}} $$
### Dimostrazione
#### $\mathcal{L_{3}} \underset{\neq}{\subset} \mathcal{L_{2}}$
- **Inclusione**: Ogni grammatica di tipo 3 (lineare destra) è anche di tipo 2 (libera da contesto), poiché le produzioni $A \to bC$ o $A \to b$ soddisfano la definizione di grammatica libera da contesto.
- **Inclusione stretta**: Esiste almeno un linguaggio di tipo 2 che non è di tipo 3.  
    **Esempio**:  
    $L = {a^n b^n \mid n > 0}$  
    Questo linguaggio è generato da una grammatica libera da contesto ma non può essere generato da una grammatica lineare destra.
- $\mathcal{L}_{3} \underline{\subset} \mathcal{L}_{2}$ discende dalle definizioni di linguaggio di tipo 3 e di grammatica di tipo 2. Infatti, si osserva facilmente che ogni grammatica di tipo 3 è anche una grammatica di tipo 2
#### $\mathcal{L_{2}} \underset{\neq}{\subset} \mathcal{L_{1}}$
- **Inclusione**: Ogni grammatica libera da contesto è anche dipendente da contesto, con l'eccezione delle produzioni $A \to \lambda$ (dove $A \neq S$).
  Lo definiamo come: 
   $$\forall L:L \in \mathcal{L}_{2} \Leftrightarrow \exists G, \text{G è C.F.}: L=LG$$
  Tuttavia, il **Lemma della stringa vuota** permette di eliminare queste produzioni senza alterare il linguaggio generato, rendendo la grammatica di tipo 1 
 
- **Inclusione stretta**: Esiste almeno un linguaggio di tipo 1 che non è di tipo 2.  
    **Esempio**:  
    $L = {a^n b^n c^n \mid n > 0}$  
    Questo linguaggio è dipendente da contesto ma non libero da contesto.
##### Lemma della stringa vuota
Sia $G = (X, V, S, P)$ una grammatica C.F. con
almeno una $\lambda$-produzione, allora esiste una
grammatica C.F. G’ tale che:
1. $L(G)=L(G')$ (con le due grammatiche che si equivalgono)
2. Se $\lambda \not\in L(G)$ allora in $G'$ non esistono produzioni del tipo $A \to \lambda$
3. Se $\lambda \in L(G)$ allora in $G'$ esiste un'unica produzione $S' \to \lambda$, ove $S’$ è il simbolo iniziale di $G’$ ed $S’$ non compare nella parte destra di alcuna produzione di $G'$

Se $G$ ha almeno una $\lambda$-produzione, utilizziamo il Lemma della stringa vuota per determinare una grammatica C.F. $G’$ equivalente a $G$, ma priva di $\lambda$-produzioni (al più, in $G’$ compare la produzione , ed $S’$ non compare nella parte destra di alcuna produzione di $G’$). G’ è di tipo 1, dimostrando che $\mathcal{L}_{2} \underline{\subset} \mathcal{L}_{1}$
#### $\mathcal{L}_1 \subset \mathcal{L}_0$
- **Inclusione**: Ogni grammatica di tipo 1 è anche di tipo 0, poiché le produzioni dipendenti da contesto sono un caso particolare delle produzioni non ristrette (tipo 0).
- **Inclusione stretta**: Esistono linguaggi ricorsivamente enumerabili (tipo 0) che non sono dipendenti da contesto. La dimostrazione formale richiede nozioni avanzate come le macchine di Turing.

## Operazioni sui linguaggi
Siano $L_{1}$ ed $L_{2}$ due linguaggi definiti su uno stesso alfabeto $X \quad ( L_{1}, L_{2}, \subseteq X^*)$, le operazioni attuabili su essi sono:
### Unione insiemistica 
L'unione di due linguaggi è l'insieme di tutte le stringhe che appartengono **almeno a uno** dei due linguaggi, anche se definiti su alfabeti diversi.
 $$L_{1} \cup L_{2} = \{ w | w\in L_{1} \lor w \in L_{2}\}$$
### Concatenazione 
La concatenazione genera tutte le possibili combinazioni prima una stringa di $L_{1}​$, poi una di $L_{2}$
$$L_{1} \cdot L_{2} = \{ w |w =w_{1}w_{2}, w\in L_{1} \lor w \in L_{2}\}$$
### Iterazione
L'iterazione è un operazione unaria, si parte da un linguaggio e si fa una generalizzazione dalle parole di uno stesso linguaggio. Si ottiene un linguaggio infinito, definito con la formula:
$$L_{1}^* = \{w|w=w_{1}w_{2}\dots w_{n}, n\geq 0 \text{ e } \forall i:w_{i}\in L_{1}\}$$
$L^{*}$ = potenza all'ennesimo di tutti i linguaggi
### Complemento
Il complemento è l'insieme di tutte le parole meno l'insieme di partenza, definito con la formula
$$\overline{L_{1}} = X^* - L_{1}$$
### Intersezione 
L'intersezione tra due linguaggi è l'operazione di prendere due elementi in comune tra due linguaggi, quindi stringhe presenti in entrambi.
$$L_{1} \cap L_{2} = \{w|w\in L_{1} \land w\in L_{2}\}$$
L'intersezione, la concatenazione e l'unione sono dette operazioni binarie, in quanto prevedono l'uso di due insiemi. Complemento e iterazione sono invece operazioni unarie.
#### Proprietà
L'operazione di concatenazione gode delle seguenti proprietà:
Dati $L_{1},L_{2},L_{3} \subseteq X^* \quad (\equiv L_{1},L_{2},L_{3} \in 2^{X^*})$, si possono avere:
- **Associatività**, l'ordine in cui concateni tre linguaggi non cambia il risultato: $(L_{1}\cdot L_{2})\cdot L_{3}=L_{1}\cdot(L_{2}\cdot L_{3})$
- **Non commutativa**,l'ordine dei linguaggi **influenza** il risultato: $L_{1}\cdot L_{2} \neq L_{2}\cdot L_{1}$
- **Elemento neutro**: $L_{1}\cdot \{\lambda\} = \{\lambda_{1}\} \cdot L_{1} = L_{1}$

$(2^{X^*},\cdot)$ è anch'esso un **monoide** (ovvero una struttura algebrica che ha elemento neutro e gode della proprietà commutativa) quindi, in quanto presenta:
- $L_{1}\cdot \emptyset = \emptyset \cdot L_{1}= \emptyset \quad$, $(\emptyset)$ è l'**elemento assorbente**
- Se un linguaggio contiene la stringa vuota ($\lambda \in L_{1}$ oppure $\lambda \in L_{2}$), valgono queste inclusioni: 
    - $L_{2} \subseteq L_{1}\cdot L_{2}$
    - $L_{2} \subseteq L_{2}\cdot L_{1}$
    - $L_{1} \subseteq L_{1}\cdot L_{2}$
    - $L_{1} \subseteq L_{2}\cdot L_{1}$
## Potenza di un linguaggio
Sia $L$ un linguaggio definito su un alfabeto $X$, dicesi **potenza n-esima** di $L$, e si denota con $L^n$ , $n\geq0$, il seguente linguaggio:

$L^n = \begin{cases} \{\lambda\} \text{ se n=0} \\ L^{n-1} \cdot L \text{ altrimenti}\end{cases}$

Si ha dunque che: 
$L^+ = \bigcup_{\substack{i\geq i}}L^i$, (unione di tutte le potenze maggiori di 1, quindi deve avere almeno una concatenazione)

Si può definire l'unione di tutte le potenze anche con la stringa vuota: $L^* = \{\lambda\}\cup L^+ = \bigcup_{\substack{i\geq 0}} L^*$
## Proprietà di chiusura delle classi di linguaggi
Un linguaggio definito su un alfabeto è un insieme di parole, una classe di linguaggi è un insieme di linguaggi.
### Definizione di chiusura
Si suppone di avere un operazione binaria, definita su una coppia di linguaggi ()
### Teorema di chiusura
La classe dei linguaggi di tipo $i, i = 0, 1, 2, 3$ è chiusa rispetto alle operazioni di unione, concatenazione ed iterazione. 
Dati quindi due linguaggi quindi, dopo aver effettuato una di queste operazioni tra i due linguaggi, si ottiene sempre un linguaggio della stessa classe.
#### Dimostrazione del teorema
Lo schema generale della dimostrazione è il seguente:
- consideriamo una certa operazione, denotata con $a$;
- date $G_{1}$ e $G_{2}$, costruiamo una nuova grammatica $G$:$$G=(X,V,S,P)$$
  Per la quale si dimostra che:
  - se $G_1$ e $G_2$ sono di tipo i, allora $G$ è di tipo $i$; 
  - $L(G)=\alpha(L_{1},L_{2})$

Assumendo che non abbiano non terminali in comune.
Poniamo che: $V = V_{1} \cup V_{2} \cup \{S\}$
Lo schema generale della dimostrazione è il seguente: 
- consideriamo una certa operazione, denotata con $\alpha$
- costruiamo una nuova grammatica $G$ per cui dimostriamo che
	- se $G_1$ e $G_2$ sono di tipo i, allora $G$ è di tipo i;
	- $L(G)=\alpha(L_{1},L_{2})$
##### Unione (per $\mathcal{L_{2}}$ ):
Costruiamo la grammatica $G_{3} = (X,V,S,P_{3})$ ove:
	$P_{3} = \{S \to S_{1}, S \to S_{2}\} \cup P_{1} \cup P_{2}$
Osserviamo che, se $G_1$ e $G_2$ sono entrambe di tipo 2, lo è anche $G_3$ in quanto abbiamo aggiunto due produzioni libere da contesto:
- $S \to S_{1}$
- $S \to S_{2}$
Nel primo caso si avrà la derivazione: $S \Rightarrow S_{1} \xRightarrow{*} w_{1} \in L_{1}$
Nel secondo caso si avrà la derivazione: $S \Rightarrow S_{2} \xRightarrow{*} w_{2} \in L_{2}$

E' pertanto dimostrato che $\ell_{2}$ è chiusa rispetto all'unione.
##### Unione (per $\mathcal{L_{3}}$ ):
Se $G_1$ e $G_2$ sono di tipo ‘3’, $G_3$ non è lineare destra, perché le produzioni che abbiamo introdotto non sono lineari destre: $S \to S_{1} \quad S \to S_{2}$
Per risolvere il problema dobbiamo introdurre produzioni lineari destre che simulino i passi iniziali delle derivazioni in $G_1$ ed in $G_{2}$.
Costruiamo la grammatica $G_{4} = (X,V,S,P_{4})$ ove $P_4$:
- per ogni regola $S_{1} \to w \in P_{1}$ aggiungiamo a $P_4$ la regola: $S \to w$
- per ogni regola $S_{2} \to w \in P_{2}$ aggiungiamo a $P_4$ la regola: $S \to w$

$P_{4} = \{S \to w | S_{1} \to w \in P_{1}\} \cup \{S \to w | S_{2} \to w \in P_{2}\}\cup P_{1} \cup P_{2}$.

Tutte le regole di $P_4$ sono lineari destre in quanto abbiamo aggiunto regole la cui parte destra rispetta il vincolo delle grammatiche di tipo ‘3’: $G_4$ è di tipo ‘3’.
##### Concatenazione (per $\mathcal{L_{2}}$ ):
Costruiamo la grammatica $G_{5} = (X,V,S,P_{5})$, nella quale $P_{5} = \{S \to S_{1}S_{2}\} \cup P_{1} \cup P_{2}$.

Osservazione:
- se $G_1$ e $G_2$ sono di tipo ‘2’, anche $G_5$ è di tipo '2' 
-  $L(G_{5}) = L_{1} \cdot L_{2}$, poiché tutte le derivazioni sono del tipo: $S \Rightarrow S_{1}S_{2} \xRightarrow{*} w_{1}S_{2} \xRightarrow{*} w_{1}w_{2} \in L_{1}\cdot L_{2}$
È pertanto dimostrato che $\ell_{2}$ è chiusa rispetto alla concatenazione.
##### Concatenazione (per$\mathcal{L_{3}}$ ):
Osservazione:
Data una grammatica di tipo ‘3’, ogni forma di frase derivata dal suo simbolo iniziale ha due peculiarità: 
1. in essa compare al più un NT 
2. se in essa compare un NT, questo è il simbolo più a destra

Quindi, se $G_1$ e $G_2$ sono di tipo ‘3’, $G_5$ non è di tipo ‘3’, per la presenza della produzione: $S \to S_{1}S_{2}$. C'è pertanto bisogno di una nuova grammatica in grado di simulare l'effetto di tale produzione.

Osserviamo che per generare una parola del linguaggio $L_{1} \cdot L_{2}$ senza usare la produzione $S \to S_{1}S_{2}$, dovremmo "chiudere" (ovvero sostituire l'ultimo non terminale della forma di frase, ottenendo dunque una stringa terminale) la derivazione di una parola di $L_{1}$ (ovvero derivare $S_{1}$ fino ad ottenere solo caratteri terminali) per poi generare l'assioma di $L_1$. 

Studiando una generica derivazione di una parola di $L_{1}$ notiamo che:
$S_{1} \Rightarrow x_{1}A \Rightarrow x_{1}x_{2}A \xRightarrow{*} x_{1}x_{2}\dots x_{n-1}N \Rightarrow x_{1}x_{2}\dots x_{n}$

Avremmo quindi due possibili derivazioni del nonterminale N:
1. $N \to \alpha$
2. $N \to \lambda$

###### Caso 1:
Le regole del tipo $N \to \alpha$ vengono modificate in: $N \to \alpha S_{2}$, e quindi:
$S_{1} \Rightarrow x_{1}A \Rightarrow x_{1}x_{2}A \xRightarrow{*} x_{1}x_{2}\dots x_{n-1}N \Rightarrow x_{1}x_{2}\dots x_{n-1}\alpha$ diventa:
$S_{1} \Rightarrow x_{1}A \Rightarrow x_{1}x_{2}A \xRightarrow{*} x_{1}x_{2}\dots x_{n-1}N \Rightarrow x_{1}x_{2}\dots x_{n-1}\alpha S_{2}$

Dall'assioma di $S_{2}$ si potrà successivamente generare una parola $w_{2}\in L_{2}$, ottenendo una parola $\in L_{1}\cdot L_{2}$

###### Caso 2:
Le regole del tipo $N \to \lambda$ non possono essere trasformate in $N \to S_{2}$ in quanto non sarebbe lineare destra.
Per tale regola dobbiamo risalire al non terminale che ha generato $N$ ovvero alle regole del tipo: $M \to \alpha N$, con poi $N \to \lambda$, chiudendo quindi la derivazione di una parola di $L_1$.

In pratica si deve intervenire su ogni $\lambda$-produzione e relative regole che generano il non terminale presente nella parte sinistra della $\lambda$-produzione.
Costruiamo quindi la grammatica $G_{6} = (X,V - \{S\},S_{1},P_{6})$. Le sue produzioni sono del tipo:
$P_{6} = \{A \to bB | A \to bB \in P_{1}\} \cup \{A \to bS_{2}|A \to b \in P_{1} b \neq \lambda\} \cup \{A \to bS_{2}|B \to \lambda \in P_{1}, A \to bB \in P_{1}\} \cup P_{2}$
Questa grammatica tuttavia ha un problema, in quanto non è possibile derivare solo le parole di $L_2$. (Dovremmo dunque implementare una sorta di $S_{1} \to \lambda$, non implementabile in quanto non sarebbe lineare destra.)
Per risolvere tale problema non dovremmo fare altro che innescare anche da $S_1$ la derivazione di parole di $S_2$. Aggiungiamo quindi una nuova regola alle produzioni:

$P_{6} = \{A \to bB | A \to bB \in P_{1}\} \cup \{A \to bS_{2}|A \to b \in P_{1} b \neq \lambda\} \cup \{A \to bS_{2}|B \to \lambda \in P_{1}, A \to bB \in P_{1}\} \cup P_{2} \cup \{S_{1} \to w | S_{2} \to w \in P_{2}, \text{ se } S_{1} \to \lambda \in P_{1}\}$
Con l'ultima regola non andiamo a fare altro che a trascrivere $S_{1}$ con i non terminali di $L_2$ qualora ci sia una $\lambda$-produzione.
È pertanto dimostrato che $L_3$ è chiusa rispetto alla concatenazione
##### Iterazione (per $\mathcal{L_{2}}$ )
Costruiamo la grammatica $G_7$ partendo da $G_1$ : $G_{7} = (X,V_{1} \cup \{S\},S,P_{7})$
dove $P_{7} = \{S \to \lambda, S \to S_{1}S\} \cup P_{1}$.
Osserviamo che se $G_{1}$ è di tipo 2, lo è anche $G_{3}$ in quanto abbiamo aggiunto due produzioni libere da contesto
##### Iterazione (per $\mathcal{L_{3}}$ )
Anche qui nasce il problema che $S \to S_1S$ non è lineare destra.  
Dobbiamo costruire una nuova grammatica $G_8$ il cui assioma $S$ produca $\lambda$ e tutte le parti destre dell’assioma di $G_1$, in modo da garantire che ogni derivazione di $G_8$ inizi esattamente come una di $G$.
**Osservazione preliminare:**  
L'operatore $\mathcal{L_{3}}$  produce stringhe costituite da **concatenazioni di zero o più stringhe di $L(G_1)$**, quindi serve una grammatica che permetta sia di generare una singola stringa di $G_1$, sia di ripeterla quante volte si vuole, sia di fermarsi (producendo $\lambda$).

**Algoritmo per costruire $G_8 = (V_8, \Sigma, P_8, S)$ a partire da $G_1 = (V_1, \Sigma, P_1, S_1)$:**
1. Aggiungiamo una nuova variabile $S \notin V_1$ come nuovo assioma.  
2. Poniamo $V_8 = V_1 \cup \{S\}$  
3. Inizializziamo $P_8 = \{S \to \lambda\}$  
4. Per ogni produzione $S_1 \to w \in P_1$, aggiungiamo **due produzioni** a $P_8$:  
   - $S \to w$  
   - $S \to wS$  
In simboli:
- $P_8 = \{S \to \lambda\} \cup \{S \to w, S \to wS \mid S_1 \to w \in P_1\}$


**Verifica della correttezza: due casi**
1. **Caso 1: $G_1$ non produce $\lambda$**
   Allora $L(G_8) = L(G_1)^*$  
   Ogni stringa generata da $G_8$ è ottenuta concatenando zero o più stringhe generate da $G_1$.
2. **Caso 2: $G_1$ produce $\lambda$**
   Allora $\lambda$ è già incluso in $L(G_8)$ tramite la regola $S \to \lambda$,  
   ma attenzione: se $S_1 \to \lambda$ è una regola in $G_1$, allora:
   - $S \to \lambda$ (già presente)
   - $S \to \lambda S$ (aggiunta come $S_1 \to \lambda$ $\Rightarrow$ $S \to \lambda S$)
   Quindi bisogna notare che:
   - $S \Rightarrow \lambda$
   - $S \Rightarrow \lambda S \Rightarrow \lambda \lambda S \Rightarrow \dots$
Ovvero, si generano **infinite derivazioni** della parola vuota, ma l’insieme delle stringhe generate rimane **$L(G_1)^*$**, come desiderato.


### Altri teoremi di chiusura

1. La classe dei linguaggi lineari destri (tipo ‘3’) è chiusa rispetto al complemento ed all'intersezione  
2. La classe dei linguaggi liberi da contesto (tipo ‘2’) non è chiusa rispetto al complemento ed all’intersezione  
3. La classe dei linguaggi dipendenti da contesto (tipo ‘1’) è chiusa rispetto al complemento e all’intersezione  
4. La classe dei linguaggi di tipo ‘0’ non è chiusa rispetto al complemento  

Per $\ell_{1}$ e $\ell_{0}$ non lo dimostriamo
#### Dimostrazioni:
1. **Per la classe di tipo 3 (lineari destri):**
   Assumiamo dimostrata la chiusura di $\ell_3$ rispetto al complemento.  
   Secondo le Leggi di De Morgan:
   $$
   L_1 \cap L_2 = \overline{\overline{L_1} \cup \overline{L_2}}
   $$

   Allora, poiché i linguaggi regolari (tipo 3) sono chiusi per:
   - **complemento**: $\mathcal{L_{3}}$  è chiuso rispetto al complemento
   - **unione**: $\mathcal{L_{3}}$  è chiuso rispetto all’unione
   ne segue che anche l’intersezione è chiusa:
   $$
   L_1 \cap L_2 = \overline{\overline{L_1} \cup \overline{L_2}} \in \ell_3
   $$
   Poiché tutte le operazioni usate sono chiuse in $\mathcal{L_{3}}$ , anche $L_1 \cap L_2$ appartiene a $\mathcal{L_{3}}$ .
2. **Per la classe di tipo 2 (liberi da contesto):**
   Non vale la chiusura né per il **complemento** né per l’**intersezione**.  
   È possibile dimostrarlo con un controesempio:
   - Sia $L_1 = \{ a^n b^n c^m \mid n, m \geq 0 \}$  
     (libero da contesto)
   - Sia $L_2 = \{ a^m b^n c^n \mid m, n \geq 0 \}$  
     (libero da contesto)

   Allora:
   $$
   L_1 \cap L_2 = \{ a^n b^n c^n \mid n \geq 0 \}
   $$
   che **non è un linguaggio libero da contesto**.  
   Quindi la classe dei CFL (tipo 2) **non è chiusa** rispetto all’intersezione.
   Inoltre, se fosse chiusa rispetto al **complemento**, allora anche l’intersezione lo sarebbe (per De Morgan), il che porterebbe a una contraddizione.  
   Quindi anche **la chiusura per complemento fallisce**.

### Riflessione
#### Definizione di stringa riflessa
Sia $w$ una parola su un alfabeto $X=\{x_{1},x_{2}\dots,x_{k}\}$, con $w=x_{i_{1}},x_{i_{2}} \dots x_{i_{n-1}},x_{i_{n}}$, si dice **stringa riflessa** o **riflessione** di $w$ la stringa:$$w^R=x_{i_{n}},x_{i_{n-1}} \dots x_{i_{2}}, x_{i_{1}}$$
#### Operazione di riflessione
Sia $w$ una parola su un alfabeto $X=\{x_{1},x_{2}\dots,x_{k}\}$ e sia $w^R$ ;a
