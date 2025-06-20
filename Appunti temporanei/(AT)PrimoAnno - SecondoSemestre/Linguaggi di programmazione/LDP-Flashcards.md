# Flashcards - Linguaggi di Programmazione

**ATTENZIONE:** Alcune card potrebbero sembrare "mancanti", questo è perché le domande che ho fatto formulare da un AI erano abbastanza ridondanti. Ho lasciato quelle che ritenevo abbastanza importanti, le risposte ovviamente sono fatte da me.

---

## Flashcards - Linguaggi Formali e Grammatiche

**Card 1:** Che cos'è un alfabeto in teoria dei linguaggi formali? **Risposta:** L'alfabeto è un insieme finito e non vuoto di simboli primitivi con cui si formano le parole.

**Card 2:** Come si definisce una parola (o stringa) su un alfabeto X? **Risposta:** Una parola è la concatenazione di simboli primitivi presi su alfabeto $X$.

**Card 3:** Come si denota la lunghezza di una stringa w e qual è la lunghezza della stringa vuota? **Risposta:** La lunghezza di una stringa $w$ si denota con $|w|$, una stringa vuota (chiamata lambda, $\lambda$) ha lunghezza 0.

**Card 4:** Che cosa rappresenta la notazione X*? **Risposta:** Rappresenta l'insieme di tutte le stringhe possibili su un alfabeto $X$ compresa la parola vuota.

**Card 5:** Qual è la differenza tra $X^*$ e $X^+$? **Risposta:** La differenza è che il primo insieme contiene la parola vuota mentre il secondo contiene tutte le parole di almeno lunghezza 1.

**Card 6:** Che cos'è la concatenazione di stringhe e quali sono le sue proprietà principali? **Risposta:** La concatenazione è l'operazione che permette di unire due (o più) stringhe. Le proprietà sono: **Associatività**: l'ordine in cui si associano non è rilevante, il risultato sarà sempre lo stesso; **Non commutatività**: Cambiando l'ordine di posizione per gli elementi, la parola formata dalla concatenazione non sarà la stessa.

**Card 7:** Qual è l'elemento neutro per l'operazione di concatenazione? **Risposta:** È lambda ($\lambda$).

**Card 8:** La concatenazione è commutativa? Fornisci un esempio. **Risposta:** No, per esempio $\alpha\beta \neq \beta\alpha$ (con $\alpha=\text{ciao}$ e $\beta=\text{mondo}$).

**Card 9:** Come si definisce la potenza h-esima di una stringa α? **Risposta:** Si definisce induttivamente come: $$\alpha^h=\begin{cases} \lambda & \text{se } h = 0 \ \alpha \cdot \alpha^{h-1} & \text{altrimenti}\end{cases}$$

**Card 10:** Che cosa rappresenta $X^i$ (la potenza i-esima di un alfabeto X)? **Risposta:** Rappresenta tutte le possibili stringhe formate dalla concatenazione di $i$ simboli su un alfabeto $X$.

**Card 11:** Come si definiscono prefisso, suffisso e sottostringa di una parola? **Risposta:** Considerando una stringa $w=\alpha\beta$, $\alpha$ sarà il suo prefisso, $\beta$ il suo suffisso e $\delta$ la sottostringa (che contiene tutte le possibili combinazioni tra prefisso e suffisso all'interno della stringa).

**Card 12:** Che cos'è un monoide libero e come si collega al concetto di X*? **Risposta:** Un monoide libero è un insieme con singola operazione binaria che permette la formazione di tutte le possibili stringhe, su alfabeto X, tramite l'operazione di concatenazione.

**Card 13:** Come si definisce un linguaggio formale L su un alfabeto X? **Risposta:** Un linguaggio formale $L$ può essere definito come il sottoinsieme di $X^*$ (con il linguaggio definito su alfabeto $X$).

**Card 14:** Quali sono i due punti di vista principali per studiare i linguaggi formali? **Risposta:** **Descrittivo/Generativo**: tramite la descrizione delle regole di produzione per un linguaggio formale infinito (visto che l'elencazione dei suoi elementi è impossibile); **Riconoscitivo**: tramite la costruzione di una "macchina" che permette il riconoscimento di una parola e conseguentemente se appartiene a quel linguaggio o no.

**Card 15:** Quali sono i quattro componenti di una grammatica $G = (X, V, S, P)$? **Risposta:** $X$: alfabeto terminale (composto dai simboli); $V$: alfabeto non terminale (chiamati anche assiomi o variabili); $S$: simbolo speciale di partenza; $P$: produzioni della grammatica.

**Card 16:** Che cos'è una produzione in una grammatica e come si scrive? **Risposta:** Una produzione in una grammatica è il processo di riscrittura di un simbolo non terminale in terminale o non terminale, viene rappresentata con $v \to w$.

**Card 17:** Che differenza c'è tra produzione diretta e derivazione? **Risposta:** La produzione diretta è una regola di riscrittura, mentre la derivazione è la sua diretta applicazione per formare una stringa.

**Card 18:** Come si definisce il linguaggio L(G) generato da una grammatica G? **Risposta:** È l'insieme di stringhe terminali derivabili dal simbolo di partenza $S$: $$L(G) = \{w \in X^* \mid S \Rightarrow^* w\}$$

**Card 19:** Che cos'è una forma di frase in una grammatica? **Risposta:** È la derivazione partendo da un simbolo speciale ($S \Rightarrow^* w$), considerando che si parte da una grammatica $G = (X, V, S, P)$ su alfabeto $X$ (e $w \in (X \cup V)^*$).

**Card 20:** Quando due grammatiche si dicono equivalenti? **Risposta:** Due grammatiche $G = (X, V, S, P)$ e $G' = (X', V', S', P')$ si dicono equivalenti quando producono lo stesso linguaggio tramite produzioni diverse.

---

## Flashcards - Linguaggi Liberi e Dipendenti da Contesto

**Card 1:** Come si definisce formalmente una grammatica libera da contesto? **Risposta:** Una grammatica libera da contesto $G$ è tale quando le produzioni sono di natura $A \to w$, con $A \in V$ e $w \in (X \cup V)^*$.

**Card 2:** Che cosa significa che un linguaggio $L$ è libero da contesto? **Risposta:** Un linguaggio è libero da contesto quando è generato da una grammatica libera da contesto.

**Card 3:** Se una grammatica non è context-free, cosa possiamo concludere sul linguaggio che genera? **Risposta:** Che il linguaggio che genererà a sua volta sarà Context Sensitive.

**Card 4:** Perché la maggior parte dei linguaggi di programmazione ricade nella classe dei context-free? **Risposta:** Perché, pur avendo grammatiche context sensitive, ci potrebbero essere grammatiche C.F. che li generano.

**Card 5:** Quali sono le due forme di produzione ammesse in una grammatica dipendente da contesto? **Risposta:** $yAz\to ywz$ e $S\to \lambda$.

**Card 6:** Nella produzione contestuale $yAz \to ywz$, che cosa rappresentano $y$, $z$, $A$ e $w$? **Risposta:** Rappresentano rispettivamente: $y$: contesto sinistro; $z$: contesto destro; $A$: simbolo non terminale da sostituire; $w$: stringa di simboli terminali e/o non terminali.

**Card 7:** Quando è ammessa la produzione $S \to \lambda$ in una grammatica dipendente da contesto? **Risposta:** È ammessa come eccezione per la stringa vuota nel caso $S$ non appaia come parte destra di nessuna produzione di una grammatica context sensitive.

**Card 8:** Che cosa significa che un linguaggio $L$ è dipendente da contesto? **Risposta:** Un linguaggio $L$ è dipendente da contesto quando la grammatica che lo genera è a sua volta C.S. con le produzioni descritte prima.

**Card 9:** Come si definisce una grammatica monotona e quale condizione devono soddisfare le sue produzioni? **Risposta:** Una grammatica monotona si definisce come quella in cui ogni produzione $v\to w$ soddisfa: $$|v|\leq|w|$$

**Card 10:** Che cos'è un linguaggio monotono? **Risposta:** Un linguaggio monotono è un linguaggio generato da una grammatica monotona.

**Card 11:** Qual è la relazione tra linguaggi monotoni e linguaggi dipendenti da contesto? **Risposta:** I linguaggi monotoni e i linguaggi dipendenti da contesto sono uguali tra loro, le loro due classi coincidono.

**Card 12:** Quale è l'unica eccezione alla regola di non contrazione nelle grammatiche monotone? **Risposta:** È ammessa come eccezione la produzione $S \to \lambda$ nel caso $S$ non appaia come parte destra di nessuna produzione di una grammatica monotona.

**Card 13:** Qual è la relazione di inclusione tra linguaggi liberi da contesto e linguaggi dipendenti da contesto? **Risposta:** I linguaggi liberi da contesto sono contenuti propriamente nei linguaggi dipendenti da contesto: $\mathcal{L}_2 \subset \mathcal{L}_1$.

**Card 14:** Perché ogni grammatica libera da contesto può essere vista come un caso speciale di grammatica dipendente da contesto? **Risposta:** Perché le produzioni C.F. possono essere viste come delle produzioni C.S. in questa maniera: $$\lambda A\lambda \to \lambda w\lambda$$

**Card 15:** È sempre possibile trasformare una grammatica monotona in una equivalente dipendente da contesto? **Risposta:** Sì, per ogni grammatica monotona ne esiste sempre una equivalente context sensitive, definita anche come: $$L \text{ è C.S.} \Longleftrightarrow \exists G \text{ C.S.} : L=L(G)$$

---

## Flashcards - Linguaggi Liberi da Contesto

### Albero di Derivazione

**Card 1:** Cos'è un albero di derivazione? **Risposta:** L'albero di derivazione è un grafo per descrivere le possibili produzioni di una grammatica C.F.

**Card 2:** Cosa si intende per "struttura di w" in una grammatica libera da contesto? **Risposta:** La sequenza di regole per produrre la forma $w$.

**Card 3:** Cos'è la frontiera di un albero di derivazione? **Risposta:** La stringa finale generata dall'albero.

**Card 4:** Elenca le proprietà che deve rispettare un albero T per una parola w derivabile da una grammatica C.F. **Risposta:** Radice etichettata con $S$; Nodi interni etichettati con simboli di $V$; Nodi esterni (foglie) etichettati con simboli di $X$ o $\lambda$; Le produzioni rispettano le regole della grammatica; La stringa $w$ è la frontiera.

**Card 5:** Come si definisce la lunghezza di un cammino in un albero di derivazione? **Risposta:** Il numero di nodi dal nodo radice a una foglia.

**Card 6:** Come si definisce l'altezza (o profondità) di un albero di derivazione? **Risposta:** Come il cammino più lungo dalla radice alla frontiera.

**Card 7:** Qual è la relazione tra derivazioni e alberi di derivazione? **Risposta:** Le derivazioni possiedono un'unica rappresentazione possibile sull'albero di derivazione, mentre quest'ultimo può rappresentare più derivazioni possibili.

### Derivazioni Destre e Sinistre

**Card 8:** Cosa si intende per derivazione destra? **Risposta:** La derivazione che ad ogni passo riscrive il simbolo non terminale più a destra.

**Card 9:** Cosa si intende per derivazione sinistra? **Risposta:** La derivazione che ad ogni passo riscrive il simbolo non terminale più a sinistra.

### Principio di Sostituzione di Sotto-alberi

**Card 10:** Cosa succede quando si sostituisce un sottoalbero con un altro sottoalbero avente la stessa radice etichettata? **Risposta:** Si crea un albero complementare con le stesse proprietà di derivazione.

**Card 11:** Qual è la proprietà fondamentale dei linguaggi liberi riguardo alla crescita delle parole? **Risposta:** Un linguaggio libero deve avere sempre una crescita di parole controllata (al massimo esponenziale).

**Card 12:** Se un linguaggio genera parole la cui lunghezza cresce in maniera più che esponenziale, cosa si può concludere? **Risposta:** Che quest'ultimo non appartenga alla classe dei context free.

### Pumping Lemma

**Card 13:** Enuncia il Pumping Lemma per i linguaggi liberi da contesto. **Risposta:** Sia $L$ un linguaggio libero, esiste una costante $p$, definita dal linguaggio $L$, tale che se $z$ è una parola del linguaggio con $|z| \geq p$, allora $z$ può essere riscritta come $z=uvwxy$ soddisfacendo tre condizioni.

**Card 14:** Quali sono le tre proprietà che devono essere soddisfatte nel Pumping Lemma? **Risposta:** $|vwx| \leq p$; $vx \neq \lambda$; $\forall i \geq 0, uv^iwx^iy \in L$.

**Card 15:** Come si usa il Pumping Lemma per dimostrare che un linguaggio non è libero? **Risposta:** Si studia il linguaggio in modo da dimostrare che la crescita delle parole non sia costante, rendendolo uno non libero.

**Card 16:** Quale proprietà del Pumping Lemma viene solitamente utilizzata per dimostrare che un linguaggio non è C.F.? **Risposta:** Viene utilizzata la terza proprietà, in modo da rompere una regola possibile del linguaggio.

**Card 17:** Cosa si può concludere se un linguaggio infinito non obbedisce al Pumping Lemma? **Risposta:** Che quest'ultimo non sia libero poiché non generato da una grammatica C.F.

### Grammatiche Ambigue

**Card 18:** Quando una grammatica G libera da contesto è considerata ambigua? **Risposta:** Una grammatica è considerata ambigua quando, data una stringa, esistono due alberi di derivazione differenti.

**Card 19:** Perché l'ambiguità è una proprietà negativa nei linguaggi di programmazione? **Risposta:** Perché il significato di una frase può essere definito come il suo albero di derivazione.

**Card 20:** Qual è l'unico vantaggio delle grammatiche ambigue? **Risposta:** Potrebbero contenere meno regole rispetto ad una grammatica inerentemente non ambigua.

**Card 21:** Cosa si intende per linguaggio inerentemente ambiguo? **Risposta:** Un linguaggio per cui tutte le grammatiche che lo generano sono ambigue.

---

## Flashcard - Gerarchia di Chomsky, Teoremi e Operazioni sui Linguaggi

**Card 1:** Cos'è la Gerarchia di Chomsky? **Risposta:** La gerarchia di Chomsky è la classificazione dei linguaggi formali basata sui vincoli imposti alle regole di riscrittura delle grammatiche.

**Card 2:** Quali sono le caratteristiche delle grammatiche di tipo 0 nella gerarchia di Chomsky? **Risposta:** Non hanno nessun tipo di restrizione sulle produzioni.

**Card 3:** Quali vincoli impone una grammatica di tipo 1 (dipendente dal contesto)? **Risposta:** Impone le seguenti produzioni: $yAz\to ywz$ e $S\to\lambda$.

**Card 4:** Qual è la forma delle produzioni in una grammatica di tipo 2 (libera da contesto)? **Risposta:** $A \to w$ con $A \in V$ e $w \in (X \cup V)^*$.

**Card 5:** Come si presentano le produzioni di una grammatica di tipo 3 (lineare destra)? **Risposta:** $A\to aB$ e $A\to a$ (dove $A,B \in V$ e $a \in X$).

**Card 6:** Che relazione esiste tra le classi $\mathcal{L}_3$, $\mathcal{L}_2$, $\mathcal{L}_1$ e $\mathcal{L}_0$? **Risposta:** Ognuna di queste classi è un sottoinsieme della precedente: $\mathcal{L}_3 \subset \mathcal{L}_2 \subset \mathcal{L}_1 \subset \mathcal{L}_0$.

**Card 7:** Qual è la definizione formale della gerarchia stretta di Chomsky? **Risposta:** Si dimostra che, per tutte le 4 classi di linguaggi formali si forma una gerarchia strettamente inclusiva dove ogni linguaggio è il sottoinsieme proprio del precedente.

**Card 8:** Perché $\mathcal{L}_3 \subsetneq \mathcal{L}_2$? **Risposta:** Perché ogni produzione lineare destra soddisfa la definizione di una grammatica C.F.

**Card 9:** Che cos'è il Lemma della stringa vuota? **Risposta:** Una regola che permette di generare una grammatica $G'$ senza $\lambda$-produzioni.

**Card 10:** Quali condizioni soddisfa una grammatica $G'$ derivata tramite il Lemma della stringa vuota? **Risposta:** Le due grammatiche generano lo stesso linguaggio: $L(G)=L(G')$; Se non esistono lambda produzioni nella prima grammatica, non esisteranno nella seconda; Se esistono lambda produzioni nella prima grammatica, allora esiste una produzione lambda che non appare nel contesto destro di nessuna produzione: $S'\to\lambda$.

**Card 11:** Quali sono le operazioni fondamentali che si possono applicare ai linguaggi? **Risposta:** Concatenazione, unione, intersezione, iterazione e complemento.

**Card 12:** Come si definisce l'unione di due linguaggi $L_1$ e $L_2$? **Risposta:** $L_1 \cup L_2 = {w | w \in L_1 \text{ o } w \in L_2}$.

**Card 13:** Come si definisce la concatenazione di due linguaggi $L_1$ e $L_2$? **Risposta:** $L_1 \cdot L_2 = {w_1w_2 | w_1 \in L_1 \text{ e } w_2 \in L_2}$.

**Card 14:** Come si definisce l'iterazione di un linguaggio $L$? **Risposta:** Si definisce come la generalizzazione di un linguaggio per ottenerne uno infinito: $L^* = \bigcup_{i=0}^{\infty} L^i$.

**Card 15:** Che cosa rappresenta $L^*$ per un linguaggio $L$? **Risposta:** La chiusura di Kleene del linguaggio $L$, che include la stringa vuota e tutte le possibili concatenazioni di stringhe di $L$.

**Card 16:** Come si definisce il complemento di un linguaggio $L$? **Risposta:** $\overline{L} = X^* \setminus L$, dove $X$ è l'alfabeto di riferimento.

**Card 17:** Come si definisce l'intersezione tra due linguaggi $L_1$ e $L_2$? **Risposta:** $L_1 \cap L_2 = {w | w \in L_1 \text{ e } w \in L_2}$.

**Card 18:** Quali proprietà ha la concatenazione tra linguaggi? **Risposta:** **Associatività**: $(L_1 \cdot L_2) \cdot L_3 = L_1 \cdot (L_2 \cdot L_3)$; **Non commutatività**: $L_1 \cdot L_2 \neq L_2 \cdot L_1$ in generale; **Elemento neutro**: ${\lambda}$.
## Flashcard – Automi a Stati Finiti (Deterministici e Non Deterministici)

### Automi Deterministici (FSA)
- Cos'è un automa a stati finiti deterministico? **Risposta:** è un modello matematico atto a riconoscere dei linguaggi formali 
- Qual è la definizione formale di un FSA? **Risposta:** Un automa $$
- Cosa rappresentano gli insiemi $Q$, $F$ e l'elemento $q_0$ in un FSA?
- Come si definisce formalmente la funzione di transizione $\delta$?
- Cosa si intende per funzione di transizione parziale?
- Cos’è uno stato pozza e quando viene usato?
- Come si rappresenta graficamente un automa deterministico?
- Qual è la differenza tra grafo degli stati e tavola di transizione?
- Come funziona la tavola di transizione di un FSA?
- Cos'è l'estensione $\delta^*$ della funzione di transizione?
- Come si definisce $\delta^*$ in modo ricorsivo per i FSA?
- Quando una parola $w$ è accettata da un FSA?
- Cos’è il linguaggio accettato $T(M)$ da un FSA?

### FSA Equivalenti e Linguaggi a Stati Finiti
- Quando due automi si dicono equivalenti?
- Cos’è un linguaggio a stati finiti?
- Come si definisce formalmente la classe $\mathcal{L}_{FSL}$?
- Qual è la relazione tra $\mathcal{L}_{FSL}$ e i FSA?

### Automi Non Deterministici (NDA)
- Cos'è un automa a stati finiti non deterministico?
- Qual è la principale differenza tra $\delta$ nei FSA e nei NDA?
- Come si definisce l'estensione $\delta^*$ per un NDA?
- In cosa consiste il passo induttivo per $\delta^*$ negli NDA?
- Quando una parola è accettata da un NDA?
- Come si definisce il linguaggio accettato da un NDA?

### Linguaggi e Equivalenze degli NDA
- Come si definisce formalmente la classe $\mathcal{L}_{NDL}$?
- È vero che NDA e FSA riconoscono la stessa classe di linguaggi? Spiega.
- Qual è il vantaggio principale dell'uso di NDA rispetto ai FSA?
- Come si dimostra che $\mathcal{L}_{NDL} = \mathcal{L}_{FSL}$?
- Come si costruisce un NDA a partire da un FSA?
- Cos'è la costruzione dei sottoinsiemi (powerset construction)?
- Quali insiemi compongono gli stati e le transizioni nel FSA risultante dalla powerset construction?
- Perché ogni NDA può essere convertito in un FSA equivalente?

### Generale
- Qual è la relazione tra automi e grammatiche?
- Perché la classe dei linguaggi riconosciuti da automi a stati finiti è considerata la più semplice nella gerarchia di Chomsky?

## Flashcard – Linguaggi Regolari, Espressioni Regolari e Teorema di Kleene

### Linguaggi Regolari
- Quando un linguaggio si definisce regolare?
- Quali sono le tre operazioni fondamentali per costruire linguaggi regolari?
- Cosa rappresentano $\varnothing$ e $\{\lambda\}$ nell’ambito dei linguaggi regolari?

### Espressioni Regolari
- Che cos'è formalmente un'espressione regolare?
- Qual è l'insieme di simboli ammessi in un'espressione regolare?
- Come si definisce la funzione $S(R)$ associata a un'espressione regolare?
- Un linguaggio può essere descritto da più espressioni regolari diverse? Spiega perché.
- Cosa vuol dire che $S: \mathcal{R} \to 2^{X^*}$ non è iniettiva?
- Due espressioni regolari sono equivalenti quando?


### Teorema di Kleene
- Cosa afferma il Teorema di Kleene?
- Quali sono le tre definizioni equivalenti di linguaggi regolari?
- In cosa consiste la costruzione di un automa finito da una grammatica lineare destra?
- Perché è importante il Teorema di Kleene nell’ambito della teoria dei linguaggi?

### Pumping Lemma per Linguaggi Regolari
- Qual è l’enunciato del pumping lemma per i linguaggi regolari?
- Quali condizioni devono essere soddisfatte da $u, v, w$ nel pumping lemma?
- Come si dimostra il pumping lemma usando il principio dei cassetti?
- A cosa serve il pumping lemma nella teoria dei linguaggi?
