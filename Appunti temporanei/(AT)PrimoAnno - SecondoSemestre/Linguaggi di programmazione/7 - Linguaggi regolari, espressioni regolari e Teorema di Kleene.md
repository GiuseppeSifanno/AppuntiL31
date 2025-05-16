## Linguaggi regolari ed espressioni regolari
**Definizione di linguaggio regolare**
Sia $X$ un alfabeto finito, un linguaggio $L$ è regolare se è finito oppure se può essere ottenuto grazie alle operazioni di unione,concatenazione e iterazione:
1. $L=L_{1} \cup L_{2}$ con $L_{1},L_{2}$ regolari
2. $L=L_{1} \cdot L_{2}$ con $L_{1},L_{2}$ regolari
3. $L=L_{1}^*$ con $L_{1}$ regolare
Si noti che  $\varnothing$ e $\{\lambda\}$ sono linguaggi regolari, per denotarli usiamo il simbolo $\mathcal{L}_{REG}$ 
### Espressioni regolari
Un espressione regolare non è nient'altro che una stringa fatta da simboli
**Definizione**
Sia $X$ un alfabeto finito, una stringa $R$ di alfabeto $X \cup \{\lambda,+,*,\cdot,\varnothing,(,)\}$ (con $X \cap \{\lambda,+,*,\cdot,\varnothing,(,)\} = \varnothing$) è una **espressione regolare** di alfabeto $X$ se e solo se vale una delle seguenti condizioni:
1. $R=\varnothing$
2. $R=\lambda$
3. $R=a$, per ogni $a \in X$ (tutti i simboli)
4. $R=(R_{1}+R_{2})$ con $R_{1},R_{2}$ espressioni regolari di alfabeto $X$
5. $R=(R_{1} \cdot R_{2})$ con $R_{1},R_{2}$ espressioni regolari di alfabeto $X$
6. $R=(R_{1})^*$ con $R_{1},R_{2}$ espressioni regolari di alfabeto $X$
#### Espressioni regolari e linguaggi regolari
Ad ogni espressione regolare $R$ si denota un linguaggio regolare $S(R)$ definito nel modo seguente:
 <table>
        <thead>
            <tr>
                <th>Espressione regolare</th>
                <th>Linguaggio regolare corrispondente</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td><code>∅</code></td>
                <td><code>∅</code> (linguaggio vuoto)</td>
            </tr>
            <tr>
                <td><code>λ</code></td>
                <td><code>{λ}</code> (linguaggio contenente solo la stringa vuota)</td>
            </tr>
            <tr>
                <td><code>a</code> (dove <code>a ∈ X</code>)</td>
                <td><code>{a}</code> (linguaggio contenente il simbolo <code>a</code>)</td>
            </tr>
            <tr>
                <td><code>(R₁ + R₂)</code></td>
                <td><span class="math">S(R₁) ∪ S(R₂)</span> (unione dei linguaggi)</td>
            </tr>
            <tr>
                <td><code>(R₁ · R₂)</code></td>
                <td><span class="math">S(R₁) · S(R₂)</span> (concatenazione)</td>
            </tr>
            <tr>
                <td><code>(R₁)*</code></td>
                <td><span class="math">(S(R₁))*</span> (chiusura di Kleene)</td>
            </tr>
        </tbody>
    </table>

Da un espressione regolare si possono eliminare le coppie di parentesi superflue, tenendo conto che le operazioni 4,5,6 sono ordinate in priorità crescente
#### Proposizione
Un linguaggio su $X$ è regolare se e solo se corrisponde ad una espressione regolare su $X$
Quindi, denotato con $\mathcal{R}$ l'insieme delle espressioni regolari di alfabeto $X$, definiamo la funzione:
$$S:\mathcal{R} \to 2^{X^{*}}$$
che ad ogni espressione regolare $\mathcal{R}$ associa il corrispondente linguaggio regolare $S(R)$
Si ha dunque:$$\mathcal{L}_{REG}=\{L \in 2^{X^*} | \exists R \in \mathcal{R: L}=S(R)\}$$
Un linguaggio regolare può essere descritto da più di una espressione regolare, quindi $S:\mathcal{R} \to 2^{X^{*}}$ non è una funzione iniettiva
(GUARDARE ESEMPI DALLE SLIDE)
#### Espressione regolari equivalenti
Due espressioni regolari $R_{1}$ e $R_{2}$ su $X$ sono equivalenti se e solo se $S(R_{1}) = S(R_{2})$
#### Proprietà delle espressioni regolari
##### Proprietà 1 – Associatività dell'operazione "+" (unione)
L’operazione di unione tra espressioni regolari è associativa, quindi si ha che:
$$(R_1 + R_2) + R_3 = R_1 + (R_2 + R_3) = R_1 + R_2 + R_3$$
##### Proprietà 2 – Commutatività dell’operazione “+”
L’ordine delle espressioni non influisce sull’unione:
$$R_1 + R_2 = R_2 + R_1$$
##### Proprietà 3 – $\emptyset$ è l’elemento neutro per “+”
L’unione di un’espressione con l’insieme vuoto restituisce l’espressione stessa:
$$\emptyset + R_1 = R_1 + \emptyset = R_1$$
##### Proprietà 4 – Idempotenza dell’operazione “+”
Unendo un’espressione con sé stessa si ottiene ancora l’espressione:
$$R_1 + R_1 = R_1$$
##### Proprietà 5 – Associatività della concatenazione
La concatenazione è associativa:
$$(R_1 \cdot R_2) \cdot R_3 = R_1 \cdot (R_2 \cdot R_3) = R_1 \cdot R_2 \cdot R_3$$
##### Proprietà 6 – Non commutatività della concatenazione
In generale, la concatenazione non è commutativa:
$$R_1 \cdot R_2 \neq R_2 \cdot R_1$$
##### Proprietà 7 – $\lambda$ è l’elemento neutro per la concatenazione
La concatenazione con la stringa vuota $\lambda$ lascia invariata l’espressione:
$$\lambda \cdot R_1 = R_1 \cdot \lambda = R_1$$
##### Proprietà 8 – $\emptyset$ è l’elemento assorbente per la concatenazione
Concatenando $\emptyset$ con qualsiasi espressione si ottiene $\emptyset$:
$$\emptyset \cdot R_1 = R_1 \cdot \emptyset = \emptyset$$
##### Proprietà 9 – Distributività sinistra della concatenazione rispetto a “+”
La concatenazione si distribuisce a sinistra sull’unione:
$$R_1 \cdot (R_2 + R_3) = R_1 \cdot R_2 + R_1 \cdot R_3$$
##### Proprietà 10 – Distributività destra della concatenazione rispetto a “+”
Anche a destra la concatenazione si distribuisce:
$$(R_2 + R_3) \cdot R_1 = R_2 \cdot R_1 + R_3 \cdot R_1$$
##### Proprietà 11 – Chiusura di Kleene su $R_1$ equivale a unione con sé stessa iterata
La chiusura di Kleene di un’espressione è equivalente a:
$$R_1^* = \lambda + R_1 + R_1 \cdot R_1 + R_1 \cdot R_1 \cdot R_1 + \ldots$$
##### Proprietà 12 – Chiusura di $\lambda$ e $\emptyset$
Le chiusure di Kleene sulle espressioni $\lambda$ e $\emptyset$ risultano:
$$\lambda^* = \{\lambda\}, \quad \emptyset^* = \{\lambda\}$$
##### Proprietà 13 – Chiusura su somma iterata
Una concatenazione di un numero arbitrario di ripetizioni di unione di espressioni è ancora esprimibile con la chiusura:
$$(R_1 + R_2 + \ldots + R_n)^* = R_1^* + R_2^* + \ldots + R_n^* + \ldots$$
##### Proprietà 14 – Variante della proprietà 11 con concatenazione
Anche in presenza di chiusure concatenate con $\lambda$, si ha:
$$\lambda + R_1^* = R_1^* = R_1^* + \lambda$$
##### Proprietà 15 – Non generalità della distribuzione di chiusura su somma
In generale non vale che:
$$(R_1 + R_2)^* = R_1^* + R_2^*$$
##### Proprietà 16 – Chiusura concatenata con se stessa
Concatenando una chiusura con sé stessa non cambia nulla:
$$R_1^* \cdot R_1^* = R_1^*$$
##### Proprietà 17 – Espressione equivalente con distribuzione delle chiusure
Si ha l’equivalenza:
$$(R_1 \cdot R_2)^* \cdot R_1 = R_1 \cdot (R_2 \cdot R_1)^*$$
##### Proprietà 18 – Equivalenza tra forme distribuite di chiusura con somma
Vale anche:
$$R_1^* \cdot (R_2 + R_1 \cdot R_1^* \cdot R_2)^* = (R_1 + R_1 \cdot R_1^* \cdot R_2)^*$$
##### Proprietà 19 – Equivalenza alternativa per la proprietà 18
Un'altra forma equivalente è:
$$(R_1 + R_1 \cdot R_2)^* \cdot R_1 = R_1 \cdot (R_2 \cdot R_1)^*$$
##### Proprietà 20 – Equivalenza condizionata con esclusione di $\lambda$
La seguente equivalenza è vera **se e solo se** $\lambda \notin S(R_2)$, ovvero se $\lambda$ **non appartiene** al linguaggio generato da $R_2$:
$$(R_1 \cdot R_2)^* \cdot R_1 = R_1 \cdot (R_2 \cdot R_1)^* \quad \text{se e solo se} \quad \lambda \notin S(R_2)$$
#### Dimostrazioni delle proprietà
Le proprietà da 1 a 5 e da 7 a 14 si possono dimostrare ricorrendo alla funzione $S$, che associa ad ogni espressione regolare il linguaggio corrispondente. Tuttavia, per la maggior parte delle proprietà da 1 a 20, si può usare una tecnica generale detta **dimostrazione mediante riparsificazione**, che consiste nel mostrare che ogni parola generata da un’espressione può essere riorganizzata in modo da soddisfare l’altra espressione, e viceversa, dimostrando quindi l’equivalenza dei linguaggi.
(GUARDARE ESEMPI DALLE SLIDE)

### Teorema di Kleene
Il **Teorema di Kleene** afferma l’equivalenza tra tre diverse definizioni di linguaggi regolari:

$$
\mathcal{L}_3 \equiv \mathcal{L}_{FSL} \equiv \mathcal{L}_{REG}
$$

Dove:

- $\mathcal{L}_3$ è l’insieme dei linguaggi generati da **grammatiche lineari destre** (cioè di tipo 3 secondo la classificazione di Chomsky).
- $\mathcal{L}_{FSL}$ è l’insieme dei linguaggi riconosciuti da **automi a stati finiti**.
- $\mathcal{L}_{REG}$ è l’insieme dei linguaggi descrivibili tramite **espressioni regolari**.
#### Dimostrazione teorema di Kleene
### Algoritmo: Costruzione di un automa a stati finiti non deterministico equivalente ad una grammatica lineare destra
[da finire]
