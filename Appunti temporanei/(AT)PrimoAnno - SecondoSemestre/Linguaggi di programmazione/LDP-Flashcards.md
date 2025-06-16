**ATTENZIONE:**
Alcune card potrebbero sembrare "mancanti", questo è perchè le domande che ho fatto formulare da un AI erano abbastanza ridondanti. Ho lasciato quelle che ritenevo abbastanza importanti, le risposte ovviamente sono fatte da me

---
## Flashcards - Linguaggi Formali e Grammatiche

**Card 1:** Che cos'è un alfabeto in teoria dei linguaggi formali?
L'alfabeto  è un insieme finito e non vuoto di simboli primitivi con cui si formano le parole

**Card 2:** Come si definisce una parola (o stringa) su un alfabeto X?
Una parola è la concatenazione di simboli primitivi presi su alfabeto $X$

**Card 3:** Come si denota la lunghezza di una stringa w e qual è la lunghezza della stringa vuota?
La lunghezza di una stringa $w$ si denota con $|w|$, una stringa vuota (chiamata lambda, $\lambda$) ha lunghezza 0

**Card 4:** Che cosa rappresenta la notazione X*?
Rappresenta l'insieme di tutte le stringhe possibili su un alfabeto $X$ compresa la parola vuota

**Card 5:** Qual è la differenza tra $X^*$ e $X^+$?
La differenza è che il primo insieme contiene la parola vuota mentre il secondo contiene tutte le parole di almeno lunghezza 1

**Card 6:** Che cos'è la concatenazione di stringhe e quali sono le sue proprietà principali?
La concatenazione è l'operazione che permette di unire due (o più) stringhe 

Le proprietà sono:
- Associtività: l'ordine in cui si associano non è rilevante, il risultato sarà sempre lo stesso
- Non commutatività: Cambiando l'ordine di posizione per gli elementi, la parola formata dalla concatenazione non sarà la stessa

**Card 7:** Qual è l'elemento neutro per l'operazione di concatenazione?
È lambda ($\lambda$)

**Card 8:** La concatenazione è commutativa? Fornisci un esempio.
No, per esempio $\alpha\beta \neq \beta\alpha$ (con $\alpha=\text{ciao}$ e $\beta=\text{mondo}$)

**Card 9:** Come si definisce la potenza h-esima di una stringa α?
Si definisce induttivamente come:
$$\alpha^h=\begin{cases} \lambda & \text{se } h = 0 \\ \alpha \cdot \alpha^{h-1} & \text{altrimenti}\end{cases}$$

**Card 10:** Che cosa rappresenta Xi (la potenza i-esima di un alfabeto X)?
Rappresenta tutte le possibili stringhe formate dalla concatenazione di simboli alla i-esima su un alfabeto $X$

**Card 11:** Come si definiscono prefisso, suffisso e sottostringa di una parola?
Considerando una stringa $w=\alpha\beta$, $\alpha$ sarà il suo prefisso, $\beta$ il suo suffisso e $\delta$ la sottostringa (che contiene tutte le possibili combinazioni tra prefisso e suffisso all'interno della stringa)


**Card 13:** Che cos'è un monoide libero e come si collega al concetto di X*?
Un monoide libero è un insieme con singola operazione binaria che permette la formazione di tutte le possibili stringhe, su alfabeto X, tramite l'operazione di concatenazione 


**Card 14:** Come si definisce un linguaggio formale L su un alfabeto X?
Un linguaggio formale $L$ può essere definito come il sottoinsieme di $X^*$ (con il linguaggio definito su alfabeto $X$)


**Card 16:** Quali sono i due punti di vista principali per studiare i linguaggi formali?
Descrittivo/Generativo: tramite la descrizione delle regole di produzione per un linguaggio formale infinito (visto che l'elencazione dei suoi elementi è impossibile)
Riconoscitivo: tramite la costruzione di una "macchinetta" che permette il riconoscimento di una parola e conseguentemente se appartiene a quel linguaggio o no.

**Card 18:** Quali sono i quattro componenti di una grammatica $G = (X, V, S, P)$?
$X$: alfabeto terminale (composto dai simboli)
$V$: alfabeto non terminale (chiamati anche assiomi o variabili)
$S$: simbolo speciale di partenza
$P$: produzioni della grammatica 

**Card 19:** Che cos'è una produzione in una grammatica e come si scrive?
Una produzione in una grammatica è il processo di riscrittura di un simbolo non terminale in terminale o non terminale, viene rappresentata con $v \to w$

**Card 20:** Che differenza c'è tra produzione diretta e derivazione?
La produzione diretta è una regola di riscrittura, mentre la derivazione è la sua diretta applicazione per formare una stringa

**Card 21:** Come si definisce il linguaggio L(G) generato da una grammatica G?
È l'insieme di stringhe terminali derivabili dal simbolo di partenza $S$
$$L(G)=(w \in X^{*} | S \Rightarrow w)$$

**Card 22:** Che cos'è una forma di frase in una grammatica?
È la derivazione partendo da un simbolo speciale ($S \Rightarrow w$), considerando che si parte da una grammatica $G = (X, V, S, P)$ su alfabeto $X$ (e $w \in X^*$)

**Card 23:** Quando due grammatiche si dicono equivalenti?
Due grammatiche $G = (X, V, S, P)$ e $G' = (X, V, S, P)$ si dicono equivalenti quando producono lo stesso linguaggio tramite produzioni diverse 

## Flashcards - Linguaggi Liberi e Dipendenti da Contesto

**Card 1:** Come si definisce formalmente una grammatica libera da contesto?
Una grammatica libera da contesto $G$ è tale quando le produzioni sono di natura $v\to w$, con $v \in (X \cup V)^+$ e $w \in (X \cup V)^*$

**Card 2:** Che cosa significa che un linguaggio $L$ è libero da contesto?
Un linguaggio è libero da contesto quando è generato da una grammatica libera da contesto

**Card 4:** Se una grammatica non è context-free, cosa possiamo concludere sul linguaggio che genera? 
Che il linguaggio che genererà a sua volta sarà Context Sensitive

**Card 5:** Perché la maggior parte dei linguaggi di programmazione ricade nella classe dei context-free?
Perchè, pur avendo grammatiche context sensitive, ci potrebbero essere grammatiche C.F. che lo generano

**Card 6:** Quali sono le due forme di produzione ammesse in una grammatica dipendente da contesto?
$yAz\to ywz$ e $S\to \lambda$

**Card 7:** Nella produzione contestuale $yAz \to ywz$, che cosa rappresentano $y$, $z$, $A$ e $w$?
Rappresentano rispettivamente:
- Contesto destro
- Contesto sinistro
- Simbolo non terminale da sostituire
- Simbolo terminale

**Card 8:** Quando è ammessa la produzione $S \to \lambda$ in una grammatica dipendente da contesto?
È ammessa come eccezione per la stringa vuota nel caso $S$ non appaia come produzione destra di una grammatica context sensitive

**Card 9:** Che cosa significa che un linguaggio $L$ è dipendente da contesto?
Un linguaggio $L$ è dipendente da contesto quando la grammatica che lo genera è a sua volta C.S. con le produzioni descritte prima

**Card 11:** Come si definisce una grammatica monotona e quale condizione devono soddisfare le sue produzioni?
Una grammatica monotona si definisce induttivamente nel seguente modo:

$|v|\leq|w|$

con produzioni $v\to w$

**Card 12:** Che cos'è un linguaggio monotono?
Un linguaggio monotono è un linguaggio generato da una grammatica monotona

**Card 13:** Qual è la relazione tra linguaggi monotoni e linguaggi dipendenti da contesto?
I linguaggi monotoni e i linguaggi liberi da contesto sono eguali tra loro, le loro due classi coincidono

**Card 14:** Quale è l'unica eccezione alla regola di non contrazione nelle grammatiche monotone?
È ammessa come eccezione per la stringa vuota nel caso $S$ non appaia come produzione destra di una grammatica monotona, in questo caso però va bene se n

**Card 15:** Quali sono le due caratteristiche principali di una grammatica monotona?

**Card 16:** Qual è la relazione di inclusione tra linguaggi liberi da contesto e linguaggi dipendenti da contesto?

**Card 17:** Perché ogni grammatica libera da contesto può essere vista come un caso speciale di grammatica dipendente da contesto?
Perchè le produzioni C.F. possono essere viste come delle produzioni C.S. in questa maniera:
$$\lambda A\lambda \to \lambda w\lambda$$

**Card 25:** È sempre possibile trasformare una grammatica monotona in una equivalente dipendente da contesto? 
Sì, per ogni grammatica monotona ne esiste sempre una equivalente context sensitive,definita anche come:
$$L \text{ è C.S.} \Longleftrightarrow \exists G \text{ C.S.} : L=L(G)$$

## Flashcards - Linguaggi Liberi da Contesto

### Albero di Derivazione

**1.** Cos'è un albero di derivazione?
L'albero di derivazione è un grafo per descrivere le possibili produzioni di una grammatica C.F. 

**2.** Cosa si intende per "struttura di w" in una grammatica libera da contesto?
La sequenza di regole per produrre la forma w

**3.** Cos'è la frontiera di un albero di derivazione?
La stringa finale generata dall'albero

**4.** Elenca le proprietà che deve rispettare un albero T per una parola w derivabile da una grammatica C.F.
- Radice (etichettata con $S$)
- Nodi interni etichettati con $V$
- Nodi esterni (foglie) etichettati con simboli come $X$ o $\lambda$
- Le produzioni 
- La stringa $w$ è la frontiera

**5.** Come si definisce la lunghezza di un cammino in un albero di derivazione?
Il numero di non terminali dalla radice alla foglia

**6.** Come si definisce l'altezza (o profondità) di un albero di derivazione?
Come il cammino più lungo dalla radice alla frontiera

**7.** Qual è la relazione tra derivazioni e alberi di derivazione?
Le derivazioni possiedono un unica rappresentazione possibile sull'albero di derivazione, mentre quest'ultimo può rappresentare più derivazioni possibili

### Derivazioni Destre e Sinistre

**8.** Cosa si intende per derivazione destra?
La derivazione più a destra di un albero che va a riscrivere un simbolo terminale

**9.** Cosa si intende per derivazione sinistra?
La derivazione più a sinistra di un albero che va a riscrivere un simbolo terminale


### Principio di Sostituzione di Sotto-alberi

**11.** Cosa succede quando si sostituisce un sottoalbero con un altro sottoalbero avente la stessa radice etichettata?
Si crea un albero complementare con le stesse derivazioni

**12.** Qual è la proprietà fondamentale dei linguaggi liberi riguardo alla crescita delle parole?
Un linguaggio libero deve avere sempre una crescita di parole costanti

**13.** Se un linguaggio genera parole la cui lunghezza cresce in maniera esponenziale, cosa si può concludere?
Che quest'ultimo non appartenga alla classe dei context free

**14.** Cosa si ottiene quando si hanno due nodi con la stessa etichetta su uno stesso cammino in un albero di derivazione?

### Pumping Lemma

**18.** Enuncia il Pumping Lemma per i linguaggi liberi da contesto.
Sia $L$ un linguaggio libero, esiste una costante $p$, definita dal linguaggio $L$, tale che se $z$ è una parola del linguaggio, la sua lunghezza è maggiore di p  e può essere riscritta come $z=uvwxy$

**19.** Quali sono le tre proprietà che devono essere soddisfatte nel Pumping Lemma?
- $|vwx| \leq p$
- $vx \neq \lambda$
- $\forall i \geq 0, uv^iwx^iy \in L$

**20.** Come si usa il Pumping Lemma per dimostrare che un linguaggio non è libero?
Si studia il linguaggio in modo da dimostrare che la crescita delle parole non sia costante, rendendolo uno non libero. 


**21.** Quale proprietà del Pumping Lemma viene solitamente utilizzata per dimostrare che un linguaggio non è C.F.?
Viene utilizzata la terza proprietà, in modo da rompere una regola possibile del linguaggio

**22.** Cosa si può concludere se un linguaggio infinito non obbedisce al Pumping Lemma?
Che quest'ultimo non sia libero poiché non generato da una grammatica C.F.
### Grammatiche Ambigue

**23.** Quando una grammatica G libera da contesto è considerata ambigua?
Una grammatica è considerata ambigua quando, data una stringa, esistono due alberi di derivazione differenti

**24.** Perché l'ambiguità è una proprietà negativa nei linguaggi di programmazione?



**25.** Qual è l'unico vantaggio delle grammatiche ambigue?

---

**26.** Cosa si intende per linguaggio inerentemente ambiguo?
