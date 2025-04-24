## Automa deterministico
Un automa a stati finiti deterministico, noto anche come accettore a stati finiti deterministico, è un modello matematico utilizzato nell'informatica teorica per riconoscere linguaggi formali.
Un automa a stati finiti è vantaggioso per avere una memoria limitata più facile da gestire, ma comunque con vincoli molto importanti.
### Definizione (stati deterministici)
Sia $X$ un alfabeto (di tipo terminale), un automa a stati finiti(FSA) è una quadrupla definita con:
$$M=(Q,\delta,q_{0},F)$$
dove:
- $X$ è detto **alfabeto di ingresso**
- $Q$ è un insieme finito e non vuoto di **stati**, chiamati anche memoria dell'automa e, come i simboli NT, permettono di effettuare transizioni nella fase di riconoscimento
- $\delta$ è una funzione da in $Q$, detta **funzione di transizione**:$$\delta: Q \times X \to Q$$
- $q_{0}$ è lo stato iniziale (dove comincia il processo di riconoscimento)
- $F \subseteq Q$ è l'insieme degli stati di accettazione o finali, dove, se l'automa termina le transizioni in quello stato, la parola viene accettata.

Talora i valori della funzione di transizione $\delta$ non sono definiti per tutte le coppie (stato-simbolo di ingresso) $(q,x)$. In tal caso, si dice che $\delta$ è una **funzione parziale** o definita parzialmente. Questo significa che la lettura di $x$ dà luogo in $q$ ad un comportamento dell’automa che non si ritiene utile descrivere ai fini del riconoscimento (nel senso che produrrebbe stringhe non accettate).
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
