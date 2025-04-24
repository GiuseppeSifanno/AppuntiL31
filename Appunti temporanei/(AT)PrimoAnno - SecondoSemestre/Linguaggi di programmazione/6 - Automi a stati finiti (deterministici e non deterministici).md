## Definizione
Sia $X$ un alfabeto (di tipo terminale), un automa (accettore) a stati finiti è una quadrupla definita con:
$$M=(Q,\delta,q_{0},F)$$
dove:
- $X$ è detto alfabeto di ingresso
- $Q$ è un insieme finito e non vuoto di **stati**, chiamati anche memoria dell'automa e, come i simboli NT, permettono di effettuare transizioni nella fase di riconoscimento
- $\delta$ è una funzione da in $Q$, detta **funzione di transizione**:$$\delta: Q \times X \to Q$$
- $q_{0}$ è lo stato iniziale (dove comincia il processo di riconoscimento)
- $F \subseteq Q$ è l'insieme degli stati di accettazione o finali

[da riprendere fino a slide 22]
### Classe dei linguaggi riconosciuti da automi a stati finiti non deterministici
