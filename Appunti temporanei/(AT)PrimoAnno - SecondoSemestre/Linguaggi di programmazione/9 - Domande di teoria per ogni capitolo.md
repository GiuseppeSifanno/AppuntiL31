Un piccolo documento con delle domande che per ogni capitolo dovrebbero essere importanti, in modo da aiutare con la teoria
# Capitolo 1
1. **Qual è la differenza principale tra un linguaggio di programmazione (LDP) e la programmazione stessa?**  
   - _Suggerimento: Pensa alla comprensione delle fondamenta vs. l'apprendimento di molti linguaggi._

2. **Quali sono i quattro livelli di descrizione necessari per definire un linguaggio?**  
   - _Suggerimento: Include grammatica, semantica, pragmatica e un quarto livello specifico per i linguaggi di programmazione._

3. **Cosa compone una grammatica in termini di alfabeto, lessico e sintassi?**  
   - _Suggerimento: Definisci ciascuno di questi tre componenti._

4. **Perché nei linguaggi di programmazione è essenziale una sintassi rigorosa rispetto ai linguaggi naturali?**  
   - _Suggerimento: Considera la precisione richiesta dai computer._

5. **Cos'è la BNF (Backus Naur Form) e a cosa serve?**  
   - _Suggerimento: Pensa a un metalinguaggio per definire regole sintattiche._

6. **Descrivi l'albero di derivazione per la frase "The man hits the dog" usando le regole BNF fornite.**  
   - _Suggerimento: Usa le regole come `<frase semplice> ::= <parte nominale> <parte verbale> <parte nominale>`._

7. **Cosa sono le grammatiche libere da contesto (Context-free Grammars) e perché sono importanti?**  
   - _Suggerimento: Pensa alla sintassi dei linguaggi di programmazione e alla classificazione di Chomsky._

8. **Definisci il linguaggio delle parentesi ben formate e fornisci un esempio di regole di produzione per generarlo.**  
   - _Suggerimento: Usa regole come $S \rightarrow ()$ o $S \rightarrow (S)$._

9. **Qual è il ruolo dell'analisi sintattica nel processo di compilazione?**  
   - _Suggerimento: Considera il passaggio dalla sintassi alla semantica._

10. **Spiega il concetto di "derivazione" nelle grammatiche formali con un esempio.**  
- _Suggerimento: Usa la notazione $\alpha \Rightarrow \beta$ per mostrare un passo di derivazione._
# Capitolo 2
1. **Cos'è un alfabeto $X$ nella teoria dei linguaggi formali?**  
   - _Suggerimento: Pensa alla definizione di base e alle proprietà._

2. **Definisci una "parola" (o stringa) su un alfabeto $X$ e fornisci un esempio.**  
   - _Suggerimento: Considera la lunghezza e la composizione._

3. **Cosa rappresenta $X^*$ e qual è il ruolo della stringa vuota $\lambda$ in questo insieme?**  
   - _Suggerimento: Pensa all'insieme di tutte le possibili combinazioni._

4. **Spiega l'operazione di concatenazione tra due stringhe $\alpha$ e $\beta$ e fornisci un esempio.**  
   - _Suggerimento: Considera la lunghezza risultante e l'ordine._

5. **Quali sono le tre proprietà principali della concatenazione? Descrivile con esempi.**  
   - _Suggerimento: Associatività, elemento neutro, non commutatività._

6. **Cosa sono prefisso, suffisso e sottostringa di una stringa $y$? Fornisci un esempio per ciascuno.**  
   - _Suggerimento: Usa $y = 00110$ come caso di studio._

7. **Definisci la potenza $h$-esima di una stringa $\alpha$ ($\alpha^h$) e mostra come funziona con $\alpha = ab$ e $h = 3$.**  
   - _Suggerimento: Pensa alla concatenazione ripetuta._

8. **Cos'è la potenza $i$-esima di un alfabeto $X$ ($X^i$)? Fornisci un esempio con $X = \{a, b\}$ e $i = 2$.**  
   - _Suggerimento: Elenca tutte le combinazioni possibili._

9. **Qual è la differenza tra $X^+$ e $X^*$?**  
   - _Suggerimento: Considera la presenza o assenza della stringa vuota._

10. **Definisci un linguaggio formale $L$ su un alfabeto $X$ e fai un esempio concreto (es. parentesi bilanciate).**  
- _Suggerimento: Pensa a un sottoinsieme di $X^*$ con una proprietà specifica._

11. **Spiega la differenza tra il punto di vista generativo e quello riconoscitivo per i linguaggi formali.**  
    - _Suggerimento: Generazione vs. verifica._

12. **Descrivi la struttura di una grammatica generativa $G = (X, V, S, P)$ e il ruolo di ciascun componente.**  
    - _Suggerimento: Terminali, non terminali, assioma, produzioni._

13. **Cosa sono le produzioni in una grammatica? Fornisci un esempio in BNF per generare numeri interi relativi.**  
    - _Suggerimento: Regole di riscrittura con simboli non terminali._

14. **Definisci "derivazione diretta" ($\Rightarrow$) e "derivazione" in una grammatica, con un esempio.**  
    - _Suggerimento: Passaggi successivi per ottenere una stringa terminale._

15. **Cos'è un albero di derivazione? Mostra l'albero per la stringa $-375$ usando le produzioni dell'esempio 2.11.**  
    - _Suggerimento: Struttura ad albero con simboli non terminali e terminali._

16. **Quando due grammatiche $G$ e $G'$ si dicono equivalenti?**  
    - _Suggerimento: Pensa al linguaggio generato._

17. **Dimostra che il linguaggio generato da $G$ con produzioni $S \rightarrow aSb \mid ab$ è $L(G) = \{a^nb^n \mid n > 0\}$.**  
    - _Suggerimento: Usa l'induzione sul numero di derivazioni._

18. **Perché non esiste un algoritmo generale per verificare se $L(G) = L$ per una grammatica $G$ e un linguaggio $L$?**  
    - _Suggerimento: Pensa alla complessità e ai casi indecidibili._

19. **Come si applica il principio di induzione per dimostrare proprietà sui linguaggi formali?**  
    - _Suggerimento: Caso base e passo induttivo._

20. **Spiega il concetto di "forma di frase" in una grammatica e come si relaziona alle derivazioni.**  
    - _Suggerimento: Stringhe intermedie durante la derivazione._
