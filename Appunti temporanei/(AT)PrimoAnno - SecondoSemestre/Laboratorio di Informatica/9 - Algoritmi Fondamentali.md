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
ha complessità $n$