
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
$yAz\to ywz $

**Card 7:** Nella produzione contestuale $yAz \to ywz$, che cosa rappresentano $y$, $z$, $A$ e $w$?

**Card 8:** Quando è ammessa la produzione $S \to \lambda$ in una grammatica dipendente da contesto?

**Card 9:** Che cosa significa che un linguaggio $L$ è dipendente da contesto?

**Card 10:** Come si può leggere/interpretare una produzione contestuale $yAz \to ywz$?

**Card 11:** Come si definisce una grammatica monotona e quale condizione devono soddisfare le sue produzioni?

**Card 12:** Che cos'è un linguaggio monotono?

**Card 13:** Qual è la relazione tra linguaggi monotoni e linguaggi dipendenti da contesto?

**Card 14:** Quale è l'unica eccezione alla regola di non contrazione nelle grammatiche monotone?

**Card 15:** Quali sono le due caratteristiche principali di una grammatica monotona?

**Card 16:** Qual è la relazione di inclusione tra linguaggi liberi da contesto e linguaggi dipendenti da contesto?

**Card 17:** Perché ogni grammatica libera da contesto può essere vista come un caso speciale di grammatica dipendente da contesto?

**Card 18:** Come si può rappresentare una produzione C.F. $A \to w$ come produzione C.S.?

**Card 19:** Fornisci un esempio di linguaggio che è context-free e monotono.

**Card 20:** Fornisci un esempio di linguaggio che è monotono ma non context-free.

**Card 21:** Qual è il teorema principale che mette in relazione grammatiche monotone e grammatiche dipendenti da contesto?

**Card 22:** Come si può riformulare la condizione per un linguaggio dipendente da contesto in termini di lunghezza delle produzioni?

**Card 23:** Qual è la proposizione fondamentale sui linguaggi C.S. e monotoni?

**Card 24:** Che tipo di condizione sulla lunghezza caratterizza le produzioni nelle grammatiche monotone?

**Card 25:** È sempre possibile trasformare una grammatica monotona in una equivalente dipendente da contesto?

**Card 27:** In una trasformazione da grammatica monotona a C.S., quali sono le due fasi principali del processo?

**Card 28:** Perché è necessario introdurre nuovi simboli non terminali nella trasformazione monotona → C.S.?