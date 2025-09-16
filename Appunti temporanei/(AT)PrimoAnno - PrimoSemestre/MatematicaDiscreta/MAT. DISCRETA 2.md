# INSIEMI

Un insieme è una semplice collezione di oggetti. 
Pe esempio, sono i seguenti insiemi:
- L'insieme di tutti gli abitanti di Parigi
- L'insieme di tutti i bambini nati nel 2001
- L'insieme dei numeri naturali. 
- L'insieme di tutte le rette su un piano. 

Si è soliti indicare un insieme con la lettere maiuscola. Gli oggetti composti da un insieme A prendono il nome di *elementi* di A, e si indicano con la lettera minuscola. 

Per indicare che un elemento appartiene ad un insieme utilizziamo il simbolo $\in$ per esempio: $a \in A$ e quando non appartiene $a \notin A$. 
L'insieme vuoto si indica con il simbolo: $\emptyset$, cioè l'insieme che non ha nessun elemento. 

Un insieme A si può definire o elencare tra parentesi graffe i suoi elementi, oppure sempre tra parentesi graffe, specificando una sua proprietà caratteristica. 
Per esempio:
		$A=\{5,6,7,8,9,10,11,12,13,14,15,16,17,18,19\}$
oppure:
		$A = \{ n \in \mathbb{N}|5< n<20 \}$
dove il simbolo | si legge *tale che*.
L'ordine in cui gli elementi sono posizionati non è importante.

### SOTTOINSIEME
Un sottoinsieme di A è un sottoinsieme di B tale ce ogni elemento b di B è anche elemento di A. 
Si scrive: $A \subseteq B$

Per indicare la inclusione propria, ossia che esiste un elemento di A che non appartiene a B. 
Si scrive: $A \subset B$.

Per indicare che un insieme B non è un sottoinsieme di A. 
Si scrive: $B \not\subseteq A$

L'insieme vuoto è un sottoinsieme di ogni insieme. 

### **INTERSEZIONE**
Dati due insiemi A e B, si definisce loro *intersezione*, e si indica con $A\cap B$, l'insieme di tutti gli elementi che appartengono sia ad A sia a B. 
In simboli:
$A \cap B = \{\, x \mid x \in A \ \land \ x \in B\}$

### **UNIONE DI DUE INSIEMI**
L'*unione* di due insiemi A e B, che si indica con $A\cup B$, è l'insieme degli elementi che appartengono ad A o a B. 
In simboli:
$A \cup B = \{\, x \mid x \in A \ \lor \ x \in B \,\}$

Esempio:
Siano:
	A={1,2,3,5,8,9,10}         B={2,4,6,8}
Allora:
	$A\cap B={2,8}$
	$A\cup B={1,2,3,4,5,6,7,8,9,10}$

L'unione è costituita dagli elementi che appartengono ad *almeno* uno dei due insiemi A e B. 
Nel nostro esempio 1,3,5,9,10 appartengono solamente ad A, 4 e 6 appartengono *solamente* a B, mentre 2 e 8 appartengono sia ad A sia a B. 

### **INTERSEZIONE E UNIONE DI UNA FAMIGLiA DI INSIEMI**
Le definizioni di unione e di intersezione di due insiemi si possono generalizzare al caso si una famiglia non vuota, anche infinita ${A_{a}}|a\in I$, di insiemi:

$\bigcap_{a \in I} A_a \; =_{\text{def}} \; \{\, x \in A_a \mid \forall a \in I \,\}$

$\bigcup_{a \in I} A_a \; =_{\text{def}} \; \{\, x \in A_a \mid \exists a \in I \,\}$

### **IL COMPLEMENTO DI UN INSIEME**
Sia ora *U* un *fissato universo*, ossia un insieme che contiene tutti gli oggetti che ci possono interessare. 

def: Si definisce *complemento* o *complementare* di un insieme A l'insieme di tutti gli elementi di $U$ che appartengono ad A. 
Esso si indica con $\complement A$

Quindi:
$\complement A\; =_{\text{def}} \; \{\, x \in U \mid x \notin A \,\}$

def: Il *complemento relativo* di un insieme A in un insieme B è costituito da tutti gli elementi di B che non stanno in A. 
Si indica con $B \setminus A$ e prende anche il nome di *insieme differenza* di B ed A: 

$B \setminus A \; =_{\text{def}} \; \{\, x \in B \mid x \notin A \,\}$

Le definizioni vengono illustrate con il *diagramma di Venn*
![[Pasted image 20250908130455.png]]

### **IL PRODOTTO CARTESIANO DI INSIEMI**
def: SI definisce *prodotto cartesiano* di due insiemi A e B, e si indica con $A\times B$, l'insieme costituito da tutte le *coppie ordinate* (a, b), dove il primo elemento varia in A e il secondo elemento in B 

Per esempio, se A={3,4} e B={1,5}, allora

$A \times B = \{\ (3,1),(3,5),(4,1),(4,5)\}$ 

Gli elementi del prodotto cartesiano di due insiemi A e B non sono quindi elementi di A o di B, ma solo elementi di altra natura: sono *coppie* di elementi di A e B. 
	È possibile definire il prodotto cartesiano di più insiemi. 

def:
Si definisce *prodotto cartesiano* di *n* insiemi $A_{1}, A_{2}, \dots, A_{n}$, e si indica con $A_{1} \times A_{2} \times \dots \times A_{n}$, l'insieme costituito da tutte n-ple *ordinate* $(a_{1}, a_{2}, \dots, a_{n})$ dove il primo elemento varia in $A_{1}$, se il secondo varia in $A_{1}$, il secondo varia in $A_{2}$, l'*n*-esimo varia in $A_{n}$:

$A_{1} \times A_{2} \times \dots \times A_{n} =_{\text{def}} \{\ a_{1}, a_{2}, \dots, a_{n}| a_{i} \in A, i= 1,2,\dots,n \}$

### **L'INSIME DELLE PARTI DI UN INSIME**
def: Dato un insieme A, l'*insieme delle parti* (o sottoinsiemi) di , che si indica con P(A), è dato da:

$P(A) =_{\text{def}} \{\ B|B \subseteq A\}$

Possiamo notare che gli elementi di P(A) sono sottoinsiemi di A. 
Ricordo quanto detto a proposito della differenza tra *essere elemento di* e *essere contenuto in*, se A={a,b}, allora $a\in A$, ma $a\not\in P(A)$. 
Invece, $\{a\}\in P(A)$,e $\{a\}\subseteq P(A)$. 
Per esempio, se A={a,b}, sarà:
	$P(A) = \{\ \emptyset, \{a\},\{b\}, \{a,b\}\}$

### **RELAZIONI**

Immagina di avere due insiemi, A e B.
Se vogliamo collegare un elemento a che sta in A con un elemento $b$ che sta in B, la cosa più naturale è pensare alla **coppia ordinata** ($a, b$), dove il primo posto è riservato a $a$ e il secondo a $b$.

Tutte le coppie possibili ($a, b$) formano quello che chiamiamo **prodotto cartesiano** A $\times$ B.

Quindi, quando parliamo di una **relazione**, in realtà stiamo scegliendo alcune di queste coppie dal prodotto cartesiano: è proprio da lì che nasce il concetto di relazione.

def: Una **relazione** da un insieme A a un insieme B è un **sottoinsieme** del prodotto cartesiano.  A $\times$ B.
- Se A = B, si parla di **relazione su** A.
- L’insieme A si chiama **dominio** della relazione.
- L’insieme B si chiama **codominio** della relazione. 
  
Una relazione collega un elemento $a \in A$ con un elemento $b \in B$. Per indicarlo si usa la freccia:
			$a \;\longrightarrow\; b$
che significa che ($a, b$) fa parte della relazione.

Esempio:
Prendiamo:
$A = \{1, 2, 3\}, \quad B = \{x, y\}.$

Il prodotto cartesiano è:
$A \times B = \{(1,x), (1,y), (2,x), (2,y), (3,x), (3,y)\}.$

Ora definiamo una relazione R scegliendo solo alcune coppie, ad esempio:
$R = \{(1,x), (2,y), (3,x)\}.$

Questo significa:
- $1 \to x$
- $2 \to y$
- $3 \to x$

