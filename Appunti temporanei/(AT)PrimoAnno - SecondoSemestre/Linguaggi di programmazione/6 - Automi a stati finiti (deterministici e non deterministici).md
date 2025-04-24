Un automa a stati finiti deterministico, noto anche come accettore a stati finiti deterministico, è un modello matematico utilizzato nell'informatica teorica per riconoscere linguaggi formali.
## Definizione (stati deterministici)
Sia $X$ un alfabeto (di tipo terminale), un automa a stati finiti(FSA) è una quadrupla definita con:
$$M=(Q,\delta,q_{0},F)$$
dove:
- $X$ è detto **alfabeto di ingresso**
- $Q$ è un insieme finito e non vuoto di **stati**, chiamati anche memoria dell'automa e, come i simboli NT, permettono di effettuare transizioni nella fase di riconoscimento
- $\delta$ è una funzione da in $Q$, detta **funzione di transizione**:$$\delta: Q \times X \to Q$$
- $q_{0}$ è lo stato iniziale (dove comincia il processo di riconoscimento)
- $F \subseteq Q$ è l'insieme degli stati di accettazione o finali, dove, se l'automa termina le transizioni in quello stato, la parola viene accettata.

Talora i valori della funzione di transizione $\delta$ non sono definiti per tutte le coppie (stato-simbolo di ingresso) $(q,x)$. In tal caso, si dice che $\delta$ è una funzione parziale o definita parzialmente. Questo significa che la lettura di $x$ dà luogo in $q$ ad un comportamento dell’automa che non si ritiene utile descrivere ai fini del riconoscimento (nel senso che produrrebbe stringhe non accettate).
Evidentemente questo fatto può essere descritto in modo equivalente, seguendo la definizione data di automa a stati finiti, passando da $q$, per effetto di $x$, in uno stato dal quale non si possa mai raggiungere uno stato finale (chiamato anche stato poz)


[da spostare]
Un automa a stati finiti è vantaggioso per avere una memoria limitata più facile da gestire, ma con vincoli molto importanti.
[da spostare]

