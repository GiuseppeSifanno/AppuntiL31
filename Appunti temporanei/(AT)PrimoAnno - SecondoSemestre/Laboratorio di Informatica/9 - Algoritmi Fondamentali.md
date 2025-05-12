Gli algoritmi fondamentali aiutano un utente a risolvere problemi comuni tramite soluzioni standard, riconosciute come corrette e ottimali.

I più diffusi risolvono task di ordinamento e ricerca dei dati.

Precisiamo una cosa, **non esiste un'unica soluzione che risolve un determinato problema**, ma come si fa a dire quale tra le soluzioni è ottimale? Tramite il criterio della **complessità computazionale**.
Ogni algoritmo ha una complessità ad essere eseguito, di solito gli algoritmi più efficienti sono quelli più difficili da implementare (complessità **implementativa**), mentre quelli più semplici sono i meno efficienti
## Complessità di un algoritmo
La complessità computazionale è la **misura di quanto è complesso per un elaboratore eseguire un algoritmo** (ovvero la quantità di risorse usate da quel determinato algoritmo).

Le risorse che si sfruttano per un calcolatore sono:
- **Spazio**: quantità di memoria occupata durante l'esecuzione
- **Tempo**: quantità di tempo impiegata per ottenere la soluzione
Minori quindi saranno le risorse utilizzate dall'algoritmo, minore sarà la sua complessità computazionale
### Complessità temporale
Ma come si misura il tempo necessario per un algoritmo? Per convenzione si calcola il numero di volte in cui viene ripetuta l'operazione principale

Un codice del genere:
```c
for(int i = 0; i < n; i++) {
    // operazioni
}
```
ha complessità $n$. 
Quando effettuiamo calcoli di complessità in realtà calcoliamo delle approssimazioni, supponendo che il valore di $n$ sia "grande", la differenza tra $n$ e $n+1$ non è significativa, quindi l'istruzione di complessità $1$ si può ignorare.

Tipicamente quando si calcola la complessità si cercano le istruzioni "dominanti", cioè
quelle che vengono eseguite più volte. Spesso (non sempre!) la complessità degli algoritmi è data dal numero di operazioni che vengono effettuate nei cicli.
### Livelli di complessità di un algoritmo
La complessità di un algoritmo è crescente:
![[Pasted image 20250512115409.png]]
Un algoritmo è ottimale quando la sua complessità è costante (complessità ottimale).
Le operazioni collegate agli operatori presenti nel linguaggio (es. assegnazione, confronto, etc.) hanno tutti complessità costante, perché basta 1 operazione (1 istruzione) per risolvere il problema.

La notazione $O(n)$ serve appunto a dire che la complessità è «approssimata» ad $n$
Gli algoritmi più comuni hanno una complessità polinomiale o lineare. Gli algoritmi più efficienti hanno una complessità logaritmica o $nlog O(nlog n)$ che sono vicine
alla complessità lineare, mentre gli algoritmi esponenziali non sono trattabili in modo efficiente da un elaboratore
![[Pasted image 20250512122124.png]]

Quando parliamo di complessità computazionale dobbiamo distinguere diversi casi:
- **Migliore**: Corrispondente alla configurazione iniziale che comporta il **minimo** numero di esecuzioni dell’operazione principale
- **Peggiore**: Corrispondente alla configurazione iniziale che comporta il **massimo** numero di esecuzioni
- Medio