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