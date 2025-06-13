
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

**Card 18:** Quali sono i quattro componenti di una grammatica G = (X, V, S, P)?
$X$: alfabeto terminale (composto dai simboli)
$V$: alfabeto non terminale (chiamati anche assiomi o variabili)
$S$: simbolo speciale di partenza
$P$: produzioni della grammatica 

**Card 19:** Che cos'è una produzione in una grammatica e come si scrive?
Una produzione in una grammatica è il processo di riscrittura di un simbolo non terminale in terminale o non terminale, viene rappresentata con $v \to w$

**Card 20:** Che differenza c'è tra produzione diretta e derivazione?
La produzione diretta è una regola di riscrittura, mentre la derivazione è la sua diretta applicazione per formare una parola

**Card 21:** Come si definisce il linguaggio L(G) generato da una grammatica G?
Si definisce nel seguente modo:


**Card 22:** Che cos'è una forma di frase in una grammatica?
**Card 23:** Quando due grammatiche si dicono equivalenti?
**Card 24:** Perché in generale non esiste un algoritmo che dimostri se una grammatica genera un determinato linguaggio?
**Card 25:** Che cos'è la grammatica libera da contesto (Context-free Grammar) secondo Chomsky?
