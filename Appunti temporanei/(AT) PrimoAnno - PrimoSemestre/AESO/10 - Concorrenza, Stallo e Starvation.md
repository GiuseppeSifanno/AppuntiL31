## Stallo
Lo stallo può essere definito come una situazione in cui ciascun processo, in un insieme di processi, attende un evento che può essere causato solo da un altro processo dell’insieme.
Per il verificarsi di uno stallo quindi servono almeno 2 o più processi e generalmente i processi vanno in stallo per l'evento di attesa del rilascio di una risorsa.
Nessun processo nello stallo può:
- Passare in esecuzione
- Rilasciare risorse
- Essere riattivato
### Condizioni per lo stallo
Per poter succedere, uno stallo ha bisogno di 4 condizioni, che si suddividono in due macro categorie:
1. **Condizione necessarie ma non sufficienti (potrebbe verificarsi ma non è certo)**:
	- Mutua esclusione: un solo processo può usare una risorsa (o sezione critica)
	- Hold&Wait (possesso e attesa): un processo può mantenere il possesso delle risorse allocate mentre attende di averne altre
	- Assenza di pre-rilascio: i processi non possono essere forzati a rilasciare in anticipo le risorse acquisite
2. **Condizioni necessarie e sufficienti (sicuramente si verifica)**
	- Attesa Circolare: due o più processi sono mutualmente in attesa uno dell'altro, cioè ogni processo aspetta una risorsa occupata da un altro processo in attesa circolare![[Pasted image 20250219170700.png]]

Se manca una delle condizioni necessarie, lo stallo **non** si verifica

**NB**:
- Le prime tre condizioni derivano direttamente dalla progettazione (in molti casi sono auspicabili)
- La quarta è un evento che si può verificare e dipende dalla particolare sequenza di richieste e rilasci
### Strategie per affrontare lo stallo
Esistono diverse strategie come:
1. **Ignorare il problema (o algoritmo dello struzzo)**: Si ignora completamente il problema, fingendo che nel sistema non succeda mai. È una soluzione adottata dalla maggior parte dei sistemi operativi come Windows e Unix, è ragionevole quando lo stallo capita raramente o risulterebbe molto costoso evitarlo. Questa soluzione presenta comunque un degrado delle prestazioni, ma è un compromesso tra convenienza e correttezza. 
2. **Prevenirlo**: progettare il SO in modo che venga esclusa una delle 4 condizioni precedenti tramite la negazione 
3. **Esclusione**: le tre condizioni necessarie sono permesse ma si nega unicamente la quarta
4. **Consentire il verificarsi dello stallo, rilevarlo e risolverlo**
#### Prevenzione dello stallo
La prevenzione dello stallo, come detto precedentemente, si basa sul rimuovere la possibilità di uno stallo escludendo una delle 4 condizioni con la negazione.
Esistono due tipi di classi per la prevenzione dello stallo:
- **Metodi indiretti**: prevengono il verificarsi di una delle tre condizioni necessarie
- **Metodi diretti**: prevengono l'attesa circolare 

È possibile negare queste condizioni:
1. **Mutua esclusione**: Un processo non deve mai attendere una risorsa condivisibile, rendendo possibile gli accessi multipli alle risorse condivise (si pensi ai file in sola lettura, in questo caso l'accesso contemporaneo è possibile).
   Alcune risorse non sono comunque condivisibili (come le stampanti), rendendo quindi la negazione della mutua esclusione non applicabile per un SO.
2. **Hold&Wait**: Ogni processo richiede all'inizio della sua esecuzione tutte le risorse (non negando quindi la condizione di Hold ma quella di Wait), se il processo non ha disponibili tutte le risorse in quel preciso istante rimarrà in blocked fin quando le richieste non verranno sodisfatte contemporaneamente (quindi che le risorse siano libere).
   Questo approccio è molto inefficiente:
   - Un processo potrebbe pure andare in run utilizzando unicamente una parte di risorse, sprecando di fatto quelle che richiedeva sin dall'inizio
   - Le risorse assegnate al processo potrebbero rimanere poi bloccate per molto tempo, tenendo gli altri processi in attesa indefinita
   - Non è detto che per il processo vengano liberate tutte le risorse contemporaneamente
3. **Assenza di prerilascio**:
   Esistono due possibilità nell'assenza di pre rilascio:
   - Un processo che non riesce ad ottenere la/le risorsa/e di cui necessita rilascia quelle che ha già e si aggiungono a quelle che sta attendendo, per poi richiederle in un momento successivo (ritornando in run)
   [da finire]