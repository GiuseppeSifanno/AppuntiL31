## Sistema organizzativo
Un **sistema organizzativo** è un insieme di risorse e regole che consentono il funzionamento di una qualunque struttura sociale per il raggiungimento dei suoi obbiettivi (alcuni esempi di questi sono una biblioteca, studio medico, università etc...). 
In merito all'università: le risorse possono essere materiali o non materiali, ad esempio il personale è materiale; sempre nell'ambito universitario, le regole stabiliscono il funzionamento della struttura.
## Sistema informativo
Ogni sistema organizzativo è dotato di **sistema informativo** che organizza e gestisce le informazioni necessarie per perseguire gli scopi dell’organizzazione stessa.
Il sistema informativo **assicura**:
1. *Raccolta*
2. *Acquisizione*
3. *Archiviazione*

**organizza**:
* Elaborazione
* Trasformazione
* Produzione
* Circolazione
* *Memorizzazione*

e **gestisce** delle informazioni

Un sistema informativo è molte volte indipendente dalle automatizzazioni che conosciamo, si basti ricordare l'era pre-calcolatori, come gli archivi delle banche o servizi anagrafici che esistono da vari secoli.

Un esempio di sistema informativo può essere una biblioteca:
![[Pasted image 20250930163113.png]]

La parte che quindi conosciamo di un sistema informativo per adesso è quella **non automatizzata**
### Sistema Informatico
Andiamo a definire un **sistema informatico** come la parte automatizzata di un sistema informativo. L'automazione può essere fatta su tutto il sistema o solo su una parte del sistema informativo, tutto ciò che di un sistema informativo viene automatizzato fa parte del sistema informatico.

Un esempio di sistema informatico potrebbe essere quello di una banca:
![[Pasted image 20250930163620.png]]

Andando a riformulare quindi un **sistema informativo** è un sistema software orientato alla
gestione dei dati, dove l’aspetto prevalente è rappresentato dai dati stessi (memorizzati, ricercati, modificati) che costituiscono il patrimonio informativo di un’organizzazione

Si distingue da:
- **Software orientato alla realizzazione di funzioni** quindi la complessità riguarda le funzioni da realizzare 
- **Software orientato al controllo** per la gestione e il controllo di attività che si sincronizzano e cooperano durante l'evoluzione del sistema, ad esempio i sensori.
#### Componenti
Per fornire i servizi attesi dagli utenti, il sistema informatico prevede **quattro componenti**:
- *I programmi applicativi* che forniscono i servizi agli utenti eseguendo insiemi di operazioni sulla base informativa.
- Uno *schema* che descrive la struttura della base informativa, le operazioni per agire su di essa, le restrizioni sui valori memorizzabili e sui modi in cui essi possono evolvere nel tempo (*vincoli d’integrità*);
- La *base informativa* (o base di dati) che contiene una rappresentazione delle informazioni memorizzate;
- *HW e SW di base*.

![[Pasted image 20251002170252.png]]

Nei sistemi orientati ai dati le informazioni sono strutturate con un formato predeterminato rispetto ai linguaggi di programmazione classici.

Ricapitolando la struttura di un'organizzazione può essere rappresentata come segue:
![[Pasted image 20251002173147.png]]
### Dato e informazioni
Nei sistemi informatici le informazioni sono rappresentate in modo essenziale attraverso i dati.
Ma qual è la differenza tra un dato e un informazione?

- Il **dato** è un elemento di informazione costituito da simboli non ancora elaborati (in parole povere, sono fatti noti che possono essere registrati su un qualche supporto in una forma simbolica.)
- L'**informazione** è un processo di elaborazione e interpretazione che consente di attribuire un significato ad un dato.

I dati da soli quindi non hanno un significato, lo acquisiscono soltanto diventano informazioni. *L’informazione deriva da un processo di interpretazione e correlazione dei dati che viene simulato anche nelle macchin,* dunque si crea l'informazione che si riferisce ad un contesto. 

Tutto ciò che produce variazione nel patrimonio conoscitivo di un soggetto è informazione.

$$
\text{dato} \rightarrow \text{informazione}
$$

### Evoluzione dei sistemi informatici
Un sistema organizzativo è composto da **settori** tra loro coordinati tramite la struttura organizzativa:
![[Pasted image 20250930172053.png]]

Ogni **settore** ha le proprie informazioni dove alcune sono comuni ad altri mentre altre sono di esclusiva competenza di alcuni sotto-settori.

Ad esempio un docente che va in pensione è un informazione necessaria per più sottosettori: *stipendi*, *incarichi insegnamento docenti* e *personale*, invece lo stipendio del personale non deve interessare il settore *Incarichi insegnamento docenti* oppure *ufficio web*

Sempre nell'esempio dell'università troviamo:

| Settore                        | Evento                                              | Dati generati                                                                    |
| ------------------------------ | --------------------------------------------------- | -------------------------------------------------------------------------------- |
| Incarichi Insegnamento Docenti | Assegnazione di un nuovo insegnamento ad un docente | Codice Insegnamento, Nome Insegnamento, a.a. di attivazione, Docente affidatario |
| Personale                      | Assunzione nuovo Docente                            | Matr. Docente, CF, Nome Cognome, Indirizzo, posizione accademica                 |
| Amministrazione Sito Web       | Pubblicazione insegnamenti per il nuovo a.a.        | Nome insegnamento, Programma, Nome Docente, Numero Stanza                        |
Tipicamente gli eventi posso determinare una nuova informazione o la morte di un dato.

Questa suddivisione in sottosettori la possiamo trovare in ogni organizzazione che sviluppa un proprio sistema organizzativo, spesso i settori interessati sono medesimi o ce ne sono di nuovi a seconda del dominio in cui ci troviamo.
### Sistemi Informatici Settoriali
Si stabiliscono tra i settori flussi di informazioni che permettono ad ogni settore di procurarsi i dati di interesse dal settore originante, di conseguenza accade:
- **Una proliferazioni dell'informazioni**, ossia informazioni soggette a frequenti aggiornamenti con richiesta di definire regole organizzative per garantire una consistenza delle informazioni
- **Una relazione gerarchica** che si instaura fra i settori coinvolti nello scambio informativo (ll settore che cede l'informazione controlla quantità e qualità dell’informazione fornita)

Nella fase iniziale del processo di automazione dei vari settori aziendali, le procedure tendono ad essere prodotte separatamente per ogni settore:
![[Pasted image 20250930173237.png]]
Questa procedura è più economica e permette maggiore produttività, ma:
- Si ha un alta ridondanza dei dati
- Per uno stesso dato ci possono essere diversi cicli di vita (in base al settore)
- Ogni settore sceglie il supporto di memorizzazione, la struttura di memorizzazione, la chiave di accesso, ecc. secondo criteri di ottimizzazione locali
- Le proprietà che il dato deve rispettare possono variare da settore a settore.

Questo tipo di approccio non va bene per un **sistema informatico complesso**.
### Requisiti di un sistema informatico complesso
1. **Integrazione dei dati**: disporre di un’unica raccolta dati comuni e tanti programmi che realizzano le applicazioni operano solo sui dati di loro interesse, eliminando praticamente le ridondanze
2. **Flessibilità di realizzazione**: possibilità di partire da un nucleo di funzioni essenziali e poter espandere il sistema (scoprendo possibili modalità d'impiego)
### Sistemi di gestione di basi di dati (PT.1)
I **sistemi di gestioni di basi di dati** (chiamato Data Base Management System, DBMS) è un sistema software in grado di gestire collezioni di dati che siano grandi, condivise e persistenti, garantendo affidabilità, privatezza, efficienza ed efficacia.

I DBMS mettono a disposizione strumenti avanzati di archiviazione e reperimento di informazioni, soddisfacendo i requisiti di un sistema informatico complesso
#### Proprietà delle basi di dati
Le **basi di dati** sono:
- **Grandi**, possono avere dimensioni enormi e in generale molto maggiori della della memoria centrale disponibile, di conseguenza i DBMS devono prevedere una gestione articolata dei dati in memoria secondaria
- **Condivise**, diverse applicazioni, settori e sottosistemi devono potervi accedere secondo le opportune modalità. In questa maniera è possibile ridurre la ridondanza di dati e, di conseguenza, inconsistenze.
  Nel caso un DBMS gestisca più operazioni in contemporanea vi è necessario un controllo di concorrenza. 
- **Persistenti**, hanno un tempo di vita indipendente dalle singole esecuzioni dei programmi che lo utilizzano
#### Garanzie di un DBMS
Un DBMS deve garantire:
- **Affidabilità**, quindi una resistenza a malfunzionamenti HW e SW in modo da mantenere intatto il contenuto o permetterne la ricostruzione (backup e recovery).
  Una tecnica fondamentale è la gestione delle transazioni, cioè delle unità di lavoro atomiche che non possono avere effetti parziali.![[Pasted image 20251001091657.png]]
- **Privatezza dei dati**, un sistema deve poter definire dei meccanismi di autorizzazione per utente (opportunamente riconosciuto)![[Pasted image 20251001091836.png]]
##### Affidabilità
Un DBMS prevede che le interazioni con la base di dati avvengano per mezzo di **transazioni**.
Una **transazione** è una sequenza di azioni di lettura e scrittura del DB e di elaborazioni di dati in memoria temporanea, che il DBMS esegue garantendo le seguenti proprietà (ACID properties):

- **Atomicity**: è eseguita nella sua interezza oppure non è eseguita affatto (Le transazioni che terminano prematuramente sono abortite)
- **Consistency preservation**: un'esecuzione corretta della transazione porta il DB da uno stato consistente all’altro (i vincoli di integrità devono essere rispettati).
- **Isolation**: una transazione non deve rendere gli aggiornamenti visibili ad altre transazioni finché non termina normalmente.
- **Durability** : le modifiche su DB di una transazione terminata normalmente sono permanenti, cioè non sono alterabili da malfunzionamenti successivi alla terminazione

L'interruzione di transazione causa l'attivazione di procedure ripristino o recovery (riportano il DB allo stato corretto precedente al malfunzionamento)
##### Integrità
I DBMS prevedono anche meccanismi per controllare che i dati inseriti, o modificati, siano conformi alle definizioni nello schema per garantire sempre la consistenza del DB

I linguaggi per la definizione dello schema logico consentono di definire le condizioni cui i dati devono sottostare per essere significativi (vincoli d’integrità), e cosa fare in caso di violazioni.
![[Pasted image 20251001093300.png]]
### Sistemi di gestione di basi di dati (PT.2)
I dati di DB, gestiti da un elaboratore, si distinguono in:
- **Metadati**, ovvero lo schema di DB (*database schema*) 
	  **Def.** raccolta di definizioni che descrivono la struttura dei dati, le restrizioni sui valori ammissibili (vincoli  d’integrità), relazioni tra gli insiemi
- **Dati**: rappresentazione di fatti conformi alle definizioni dello schema

Un DBMS consente di
- Definire schemi di basi di dati e vincoli di integrità;
-  Scegliere le strutture dati per la memorizzazione e l’accesso ai dati;
-  Memorizzare, interrogare e modificare i dati interattivamente da utenti o programmi autorizzati

![[Pasted image 20251001102155.png]]

Alcuni DBMS sul mercato sono:
- MySQL
- Access
- DB2
- Oracle
- SQLServer
- PostgresSQL

## Utenti dietro le quinte

1. **Progettisti di DBMS e implementatori**: un DBMS è un sistema software complesso che consiste di molti moduli per: linguaggio di interrogazione, processori di interfaccia, accesso ai dati, memorizzazione e sicurezza. 

Il DBMS deve interfacciarsi con altri sistemi software complessi, come i sistemi operativi e i traduttori di vari linguaggi di programmazione.

2. **Sviluppatori di tool**: i *tool* sono pacchetti software che facilitano il progetto di un DB e aiutano a migliorarne le prestazioni. 
Esempi di tool sono quelli che consentono:
* il monitoraggio delle risorse
* la prototipazione rapida
* la generazione di dati di test
* la generazione di report

## Modelli di dati
I dati di un DB si organizzano in insiemi omogenei; sia la struttura dei dati che le relazioni dipendono dal *modello (logico)* dei dati utilizzato. 

***Un modello di dati (o modello logico dei dati) è un insieme di costrutti utilizzati per organizzare i dati di interesse e descriverne la struttura in modo comprensibile ad un elaboratore.*** 

Ogni modello di dati fornisce meccanismi di astrazione per definire nuovi tipi sulla base di tipi (elementari) predefiniti e costruttori di tipo.

Il **modello relazione** dei dati (più diffuso tra tutti) permette di definire tipi per mezzo del costrutto della **relazione**, che consente di organizzare i dati in insiemi di record a struttura fissa ovvero record omogenei tra loro.

Un buon modello di dati è caratterizzato da:
- Espressività: rappresentazione in modo naturale e diretto del significato di ciò che si sta modellando.
- Semplicità d’uso: pochi meccanismi, semplici da usare e da comprendere.
- Efficienza di realizzabilità

Oltre al modello relazionale possiamo trovare altri modelli:
<table>
  <thead>
    <tr>
      <th>Modello</th>
      <th>Struttura usata</th>
      <th>Anni</th>
      <th>DBMS</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Modello gerarchico</td>
      <td>basato sull'uso di strutture ad albero</td>
      <td>'60</td>
      <td>IMS<br>System 2000</td>
    </tr>
    <tr>
      <td>Modello reticolare</td>
      <td>basato sull'uso di strutture a grafo</td>
      <td>Inizio '70</td>
      <td>IDMS, IDS II, DM IV</td>
    </tr>
    <tr>
      <td>Modello relazionale</td>
      <td>basato sull'uso di relazioni: insiemi di record a struttura fissa con campi di tipo primitivo</td>
      <td>'80</td>
      <td>System R, Ingres, Oracle, DB2</td>
    </tr>
    <tr>
      <td>Modello ad oggetti</td>
      <td>basato sull'uso di classi di oggetti e istanze</td>
      <td>Fine '80 - '90</td>
      <td>O2<br>ObjectStore</td>
    </tr>
    <tr>
      <td>Modello XML</td>
      <td>rivisitazione del modello gerarchico: dati presentati insieme alla loro descrizione e non devono sottostare rigidamente ad un'unica struttura logica</td>
      <td>'90</td>
      <td>BaseX</td>
    </tr>
    <tr>
      <td>Modelli semi-strutturati e flessibili</td>
      <td>non hanno rigidità nell'organizzazione dei dati ed hanno alte prestazioni</td>
      <td>'00</td>
      <td>Sistemi NoSQL</td>
    </tr>
  </tbody>
</table>

Il primo modello adottato è quello gerarchico, basato sull’uso di strutture ad albero ovvero una struttura dati che contiene i dati tramite radici, rami e foglie che si ripetono fino ad una 
certa profondità. 
Il modello gerarchico e reticolare basate su grafi e albero gestivano i puntatori a basso livello con i dati che si trovano ad alto livello creando un problema nella gestione tra alto livello e basso livello. Ciò ha portato alla realizzazione del **modello relazionale** basato sull’uso di relazioni, insiemi di record a struttura fissa con campi di tipo primitivo.

Il modello a oggetti invece si ispira alla programmazione ad oggetti basato sull’uso di classi di oggetti e istanze. 

Negli anni 90 data la crescente necessità di dover scambiare dati tra diversi sistemi in rete per via della crescente evoluzione di Internet si è cercato di rendere il più leggero possibile lo scambio delle informazioni permettendo alle applicazioni di comunicare senza conoscere come i dati fossero organizzati negli altri sistemi, dunque il modello XML, una rivisitazione del modello gerarchico: dati presentati insieme alla loro descrizione e non devono sottostare rigidamente ad un'unica struttura logica.
Gli ultimi modelli sono quelli semi-strutturati e flessibili, non hanno rigidità nell'organizzazione dei dati ed hanno alte prestazioni. 
### Modello relazionale
Una **relazione** rappresenta l'organizzazione dei dati in insiemi omogenei
Le **istanze di una relazione** rappresentano i dati veri e propri
[guardare pag 6-7]

#### Modelli dei dati vs concettuali
I modelli dei dati precedentemente elencati sono detti
- Logici: le strutture usate da questi modelli, pur essendo astratte, riflettono una particolare organizzazione (alberi, grafi, a tabelle, oggetti etc).
	- Sono adottati nei DBMS esistenti per  l’organizzazione dei dati e indipendenti dalle strutture fisiche

- Concettuali: utilizzati per descrivere i dati in modo completamente indipendente dalla scelta del modello logico. Descrivono concetti del mondo reale, piuttosto che i dati utili a rappresentarli.
	- Sono utilizzati nella fase preliminare di  progettazione di un DB, per modellare la realtà indipendentemente da aspetti realizzativi.
	  Un esempio è il modello Entità-Relazioni.

I modelli concettuali, a differenza di quelli logici, non sono generalmente disponibili nei DBMS.
### Livelli di astrazione nei DBMS

Nei DBMS l'architettura di un DB è articolato in **tre livelli distinti** di descrizione dei dati, (*architettura ANSI/SPARC*) per ciascuno dei quali esiste uno schema.

*Avere uno standard significa che tutti parlano la stessa lingua e si può comunicare più facilmente. Per avere uno standard bisogna avere un organismo di standardizzazione situati in Europa o America o altrove nel mondo*

* **Livello fisico**: definisce l'organizzazione fisica dei dati nelle memorie permanenti e le strutture dati ausiliarie per facilitarne l'uso quindi a basso livello.
La descrizione di questi aspetti è detta **schema fisico** o **interno** (*physical o internal schema*).

![[Pasted image 20251003162330.png]]

* **Livello logico**: descrive la struttura degli insiemi di dati e delle relazioni fra loro, *secondo un modello logico dei dati*, senza nessun riferimento alla loro organizzazione fisica nella memoria permanente. Quindi una descrizione a seconda del modello scelto (gerarchico, ad oggetti, relazione, ecc...), è necessario farlo a monte per determinare anche quale DMBS adottare.

La descrizione della struttura del DB è detta **schema logico** (*logical schema*)

![[Pasted image 20251003162457.png]]

* **Livello di vista logica**: definisce come deve apparire la struttura del DB ad una certa applicazione. Questa descrizione è spesso chiamata **schema esterno** o **vista** (*external schema o user view*) e si riferisce a ciò che un utente/applicazione vede come DB.

Lo schema logico è unico ,ma possono esistere più schemi esterni, uno per ogni applicazione (o gruppo di applicazioni correlate).

![[Pasted image 20251003162643.png]]

Quindi il livello fisico viene descritto da uno schema fisico, necessario per il livello logico che sarà a sua volta definito da uno schema logico, infine abbiamo il livello di vista logico che può avere più schemi esterni a seconda dell'applicazione.

Questa architettura garantisce l’**indipendenza dei dati**, proprietà fondamentale dei DBMS

* **Indipendenza fisica**: è possibile modificare le strutture fisiche (e.s., organizzazione dei file gestiti dal DBMS o l'allocazione fisica dei file) senza influire sulle descrizioni dei dati ad alto livello e quindi sui programmi che utilizzano i dati. Tramite quest'architettura è possibile modificare la struttura dei dati che non impatterà mai il modo in cui verrà mostrati verso l'esterno;
* **Indipendenza logica**: consente di interagire con il livello esterno del DB in modo indipendente dal livello logico
	* es: aggiungere un nuovo schema esterno senza modificare lo schema logico.


Esempio: 
  Si consideri un DB per le attività di
  * dell’ufficio stipendi e 
  * biblioteca 
  
  per gestire informazioni sul **personale (docenti e non)** di un’università. 
  
  Schemi esterni (Livello di vista logica): 
  * Ufficio stipendi: nome, cognome, CF, stipendio. 
  * Biblioteca: nome e cognome, recapito telefonico

*Livello logico*
Dati personale descritti da un unico insieme di registrazioni (record) 

Schema logico di DB relazionale dichiarato come segue:

```
CREATE TABLE Personale ( 
	Nome CHAR(30), 
	Cognome CHAR(30), 
	CodiceFiscaleCHAR(15), 
	Stipendio INTEGER, 
	Recapito CHAR(8) 
)
```

Per creare le due viste logiche si scriverà:
```
CREATE VIEW PersonalePerUfficioStipendi AS SELECT Nome, Cognome, CodiceFiscale, Stipendio FROM Personale 

CREATE VIEW PersonalePerLaBiblioteca AS SELECT Nome, Cognome, Recapito FROM Personale
```


*Livello fisico* 
Il progettista del DB può memorizzare l’insieme
* in modo sequenziale, oppure
* con tecnica hash usando il cognome come chiave


```
MODIFY Personale TO HASH ON Cognome
```

Esempio (cont.): Successivamente si decide di cambiare l’organizzazione logica dei dati sul personale, memorizzandoli in due relazioni, *TecniciAmministrativi* e *Docenti*. 
Per rendere le applicazioni che usano la relazione *Personale* indipendenti dalla modifica, il DB si ridefinisce come: 

```
CREATE TABLE Docenti (
	Nome CHAR(30), 
	CodiceFiscale CHAR(15),
	Stipendio INTEGER,
	Recapito CHAR(8)
)
CREATE TABLE TecniciAmministr ( 
	Nome CHAR(30),  
	CodiceFiscale CHAR(15), 
	Stipendio INTEGER, 
	RecapitoCHAR(8)
)

CREATE VIEW Personale AS SELECT FROM Docenti UNION SELECT FROM TecniciAmministrativi
```
## Linguaggi per Database

Negli usuali linguaggi di programmazione, le istruzioni dichiarative e quelle eseguibili coesistono. 
Nel caso di DB, funzioni *dichiarative* e di *elaborazione* vengono separate in due diversi linguaggi poichè in un DB i dati persistono quindi dopo averli definiti, è possibile inserirli anche in momenti diversi cosa che non accade con un programma normale dove i dati creati (le variabili) scompaiono non appena il programma termina.

Il linguaggio si distingue tra: 
 * **Linguaggi di definizione dei dati** o *data definition language (DDL)*
	 * usati per definire gli schemi logici, esterni e fisici e le autorizzazioni per l’accesso
* **Linguaggi di manipolazione dei dati** o *data manipulation language (DML)*
	* usati per interrogazione e aggiornamento delle istanze di DB

Il termine *query language* viene spesso usato come sinonimo di DML. 

Le istruzioni di un DML definite iterrogazioni sono quelle che non modificano il database. 
Originariamente la distinzione fra DDL, DML e query language era netta.
Successivamente, proposti linguaggi che integrano le funzionalità suddette, come SQL.

## Classificazione dei DBMS

Il criterio principale utilizzato per classificare è il **modello dei dati** sul quale si fonda il DBMS, distinguendo le basi di dati gerarchiche da quelle reticolari, relazionali, orientate a oggetti, ecc. 

Altri criteri sono: 
* **Il numero di utenti**, sistemi **single-user** supportano solo un utente per volta e sono per lo più usati con personal computer. La maggior parte dei DBMS sono **multi-user**.

* **Il numero di centri (site) in cui è distribuito il DB**. 
  DBMS *centralizzati* → i dati sono memorizzati in un unico centro.
	* Un DBMS centralizzato può supportare più utenti, eventualmente remoti. 
  
  DBMS *distribuito* → può avere dati e software distribuiti in più centri connessi da una rete locale o geografica. Tipicamente i database distribuiti hanno un’architettura client-server cioè i singoli dati possono trovarsi su più centri quindi è necessario sapere anche quale centro iterrogare per recuperare un dato.

![[Pasted image 20251003164204.png]]

I DBMS distribuiti **omogenei** $\leftrightarrow$ usano lo stesso software (cioè DBMS).
Sviluppati software per accedere a diversi DB autonomi pre-esistenti memorizzati in DBMS eterogenei 
$$\downarrow$$
DBMS **federato (multidatabase)** I DBMS partecipanti sono accoppiati in modo lasco e hanno un alto grado di autonomia. Ad esempio due banche, università o aziende decidono di unirsi e per non creare un nuovo sistema si decide di rendere possibile una comunicazione continua tra i due DB.

## Vantaggi e svantaggi dei DBMS

Oltre ai vantaggi di **integrazione dei dati** e di **flessibilità** del DB, la tecnologia delle basi di dati consente anche:
1. stabilire degli **standard** circa la strutturazione e nomenclatura dei dati in una organizzazione;
2. **ridurre i tempi di sviluppo** delle applicazioni rispetto a quelli richiesti usando la tecnologia degli archivi. 

Tuttavia si hanno anche degli svantaggi: 
1. I DBMS richiedono impegno hardware e software per messa a punto e funzionamento, di conseguenza anche costi più elevati e personale con competenze per lo specifico DBMS 
2. Impatto sulla struttura organizzativa 
3. Progetto di DB ed applicazioni richiedono personale qualificato e strumenti opportuni, l’impiego di DB richiede ristrutturazione dei dati in archivi esistenti e riscrittura degli applicativi 
4. Non consigliati per applicazioni con uno o pochi utenti, senza necessità di accessi concorrenti e relativamente stabili nel tempo
