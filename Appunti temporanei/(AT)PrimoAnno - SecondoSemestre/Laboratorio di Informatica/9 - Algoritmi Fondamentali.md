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
- **Medio** 

Ad esempio, in un algoritmo di ricerca la complessità computazionale è diversa se l’elemento da trovare è il primo del vettore (caso migliore), l’ultimo del vettore (caso peggiore) o è al centro del vettore (caso medio)
Allo stesso modo, in un algoritmo di ordinamento la complessità computazionale è diversa se il vettore è già ordinato (caso migliore), oppure ordinato in modo opposto (caso peggiore) rispetto a quello che vogliamo.
## Algoritmi di ricerca
Poniamo un problema:
Si ricerca un elemento $x$ in un insieme di $n$ dati (come un array), e se è effettivamente presente, si restituisce la posizione. 
Se l’elemento non viene trovato, si può restituire un valore speciale (ad esempio, `0` o `-1`). 
### Ricerca Lineare Esaustiva
Questa tecnica consiste nel **scandire ogni elemento** dell’insieme, memorizzando eventualmente la posizione in cui si trova l’elemento cercato, è utilizzabile anche su insiemi **non ordinati** e non richiede particolari condizioni.

L’algoritmo restituisce **l’ultima occorrenza** dell’elemento, il che è utile quando ci sono duplicati, sopratutto continua comunque a esaminare tutti gli elementi anche dopo aver trovato una corrispondenza.

La complessità di questo metodo è sempre $O(n)$ nel caso migliore, peggiore e medio, poiché scandisce sempre tutti gli elementi.  

*Esempio*
```c
int ricercaLineareEsaustiva(int a[], int n, int x) {
    int j = 0;
    int posizione = -1; // -1 indica elemento non trovato

    while (j < n) {
        if (a[j] == x) {
            posizione = j; // aggiorna la posizione ogni volta che trova x
        }
        j++;
    }

    return posizione; // restituisce l’ultima occorrenza o -1
}

```
### Ricerca Lineare con Sentinella
Questa variante si interrompe **alla prima occorrenza** trovata, migliorando le prestazioni in casi favorevoli. È particolarmente utile quando si sa che l’elemento, se presente, è **unico**, oppure quando si è interessati **solo alla sua presenza**.
La complessità risulta:
- $O(1)$ nel caso migliore (elemento in prima posizione),
- $O(n)$ nel caso peggiore o se l’elemento è assente,
- $\frac{n+1}{2} \to O(n)$$in media, considerando una distribuzione casuale.

*Esempio*
```c
int ricercaLineareConSentinella(int a[], int n, int x) {
    int j = 0;
    int posizione = -1; // -1 indica elemento non trovato

    while (j < n && posizione < 0) {
        if (a[j] == x) {
            posizione = j; // interrompe al primo match
        }
        j++;
    }

    return posizione; // restituisce la prima occorrenza o -1
}

```

### Ricerca Binaria
La ricerca binaria è l’algoritmo di ricerca **più efficiente** in termini di complessità, ma può essere applicato **solo su insiemi ordinati**. Richiede dunque che i dati siano preordinati, eventualmente tramite un algoritmo di ordinamento.

L’idea è quella di confrontare l’elemento cercato con quello al centro dell’intervallo considerato e, in base al confronto, **escludere metà dei dati**: se è maggiore, si analizza la metà destra; se è minore, la metà sinistra. Si ripete finché:
- l’elemento viene trovato, oppure
- l’intervallo si riduce a zero.

La **complessità è O(log n)** in tutti i casi:
- **O(1)** nel migliore, quando l’elemento è già al centro.
- **O(log n)** nel peggiore e medio, poiché si dimezza ogni volta il numero di elementi da analizzare.
Ad esempio, in un array di 128 elementi si impiegano al massimo **8 cicli**, dato che `log2(128) = 7` e si aggiunge 1 per il conteggio iniziale.
(infatti nel primo ciclo abbiamo 128 elementi da esaminare, al termine elementi da esaminare dimezzati, al secondo ciclo diventano 64 elementi da esaminare e via dicendo fino al settimo ciclo dove sono 2 e all'ottavo ciclo 1)


Il codice tipico segue questi passaggi:
1. Inizializza `first = 0` e `last = n - 1`.
2. Calcola il valore mediano `j = (first + last) / 2`.
3. Confronta `x` con `a[j]`:
	- Se uguali, restituisce `j`.
    - Se `x > a[j]`, aggiorna `first = j + 1`.
    - Se `x < a[j]`, aggiorna `last = j - 1`.
*Esempio*
```c
int ricercaBinaria(int a[], int n, int x) {
    int posizione = -1; // -1 indica elemento non trovato
    int first = 0;
    int last = n - 1;

    while (first <= last && posizione == -1) {
        int mid = (first + last) / 2;

        if (a[mid] == x) {
            posizione = mid; // trovato
        } else if (x > a[mid]) {
            first = mid + 1; // cerca nella metà destra
        } else {
            last = mid - 1; // cerca nella metà sinistra
        }
    }

    return posizione; // indice dell'elemento o -1
}

```

Vediamo ora qualche esempio con i numeri
![[Pasted image 20250512164006.png]]
![[Pasted image 20250512164020.png]]
