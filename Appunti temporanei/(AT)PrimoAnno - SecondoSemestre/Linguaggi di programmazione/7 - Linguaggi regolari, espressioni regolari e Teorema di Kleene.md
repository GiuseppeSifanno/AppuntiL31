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
4. $R=(R_{1}+R_{2})$ con $R_{1},R_{2}$ espressioni r