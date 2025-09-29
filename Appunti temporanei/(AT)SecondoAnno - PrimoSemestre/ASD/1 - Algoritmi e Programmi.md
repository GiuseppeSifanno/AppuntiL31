## Algoritmo
Un algoritmo è una sequenza di azioni che un esecutore deve compiere per giungere alla soluzione di un qualsiasi problema computazionale, prende in input dei dati e li trasforma per produrre dei dati in output.
Di solito viene rappresentato in una scatola di questo tipo:
![[Pasted image 20250929100040.png]]

L'algoritmo e i dati sono strettamente legati, poichè le operazioni che esegue un algoritmo è condizionato dai dati che riceve
### Algoritmi e problemi
Il problema computazionale e l'algoritmo son due concetti distinti:

- Il problema computazionale specifica il risultato che si vuole ottenere, ovvero la relazione che lega i dati di input con i dati di output
- L'algoritmo definisce la serie di passi da eseguire per risolvere un problema

Un problema deve essere sempre definito;
Le definizioni di un problema devono essere complete, definire tutti i casi e sopratutto non essere **ambigua**.

Un possibile esempio è quello del minimo:
Il minimo di un insieme A è l'elemento di A che è minore o uguale ad ogni elemento di A, definito matematicamente in: $$min(A)=a\in A \Leftrightarrow \forall b \in A :a \leq b$$
La soluzione per questo problema è il confronto di ogni elemento con tutti gli altri, quello minore di tutti è il minimo
### Descrizione di algoritmi
La descrizione di un algoritmo è composta da azioni elementari 
- L'effetto di un’azione su un dato è certo, unico e ripetibile (non dipende da fattori casuali) 
- Le azioni devono essere comprensibili e non ambigue

### Valutazioni di algoritmi
Ogni algoritmo deve essere valutato in modo che produca il risultato atteso (correttezza), la correttezza di un algoritmo richiede una dimostrazione matematica, in genere **per induzione**

Un algoritmo poi deve essere **efficiente**, sia in termini di spazio (velocità) e spazio (occupazione di memoria)

Oltre a queste principali ci sono altre proprietà importanti
- Robustezza e sicurezza (gestione dei casi limite)
- Semplicità (possibilità di lettura semplificata e di espansione)
- Modularità
[da completare]
### Progettare un algoritmo
Per poter progettare un algoritmo bisogna:
- **Saper comprendere ed identificare un problema** (nel caso ci sia una soluzione robusta già presente saperla riutilizzare)
- **Saper utilizzare le principali tecniche algoritmiche**

## Ciclo di sviluppo del Software
In uno sviluppo del software avvengono diverse operazioni:
- **Studio di fattibilità**: valutare costi e benefici del sistema da costruire 
- **Raccolta e analisi dei requisiti**: definire il problema e specificare l'ambiente di sviluppo (sia software che hardware) per creare un **documento di analisi**
- **Progettazione**: Individuare 