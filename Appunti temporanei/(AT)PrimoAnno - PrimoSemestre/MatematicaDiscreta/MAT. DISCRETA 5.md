# PERMUTAZIONI
# **Che cos’è una permutazione (basi)**

## **Che cos’è una permutazione**
- Una **permutazione** è un **riordinamento** di un insieme di n elementi.
- Formalmente: è una **funzione biiettiva** $\sigma : \{1,2,\dots,n\} \to \{1,2,\dots,n\}$.
Significa che ogni elemento va in uno e un solo posto, e nessuno si ripete o sparisce.
Esempio: su $\{1,2,3\},$ la permutazione

$\sigma(1)=2,\;\sigma(2)=3,\;\sigma(3)=1$
è il ciclo $(1\;2\;3)$.


# **Notazione a cicli**
- Un ciclo ($a\ b\ c)$ significa $a\mapsto b,\ b\mapsto c,\ c\mapsto a$.
- Cicli disgiunti (che non condividono elementi) si possono scrivere uno accanto all’altro: si applicano indipendentemente.
- **Convenzione di composizione**: quando scrivi un prodotto di cicli $(\alpha\ \beta\ \gamma)(\delta\ \dots)$ si applica **prima** il ciclo più a destra, poi quello a sinistra (cioè si legge _right-to-left_). Questo è lo standard in teoria delle permutazioni.

Un ciclo è solo una regola che dice “questo numero va in quell’altro”.
$\begin{pmatrix} q & b & c \\ 1 & 4 & 8 \end{pmatrix}$
- $a,b,c$ (guarda le colonne sotto, e segui : $a\mapsto b,\ b\mapsto c,\ c\mapsto a$)
- $(1\;5\;8)$ vuol dire: $1\mapsto5,\; 5\mapsto8,\; 8\mapsto1$.
- $(2\;3\;8)$ vuol dire: $2\mapsto3,\; 3\mapsto8,\; 8\mapsto2$.
- $(4\;5)$ vuol dire: $4\mapsto5,\; 5\mapsto4$.

Tutti gli altri numeri rimangono invariati.

---

# Esempio di traccia:
Si consideri la seguente permutazione di $S_8$

 $g =(158)(238)(45)$
 1. Determinare la decomposizione in cicli disgiunti di g. 
 2. Determinare una permutazione $h$ $2 S_8$ tale che $h\circ g = g\circ h$, con $h\neq id$.

---

# Traccia: calcolo di g
Hai $g=(1\ 5\ 8)(2\ 3\ 8)(4\ 5)$. Seguiamo la regola: applichiamo prima $(4\ 5)$, poi $(2\ 3\ 8)$, poi $(1\ 5\ 8)$.
Per trovare la decomposizione in cicli disgiunti è comodo calcolare l’immagine di ogni elemento $1,2,\dots,8$.

Per scrivere una permutazione come **prodotto di cicli disgiunti**. 
1. Parti da un elemento, segui dove va, poi dove va il successivo, finché torni all’inizio → hai un ciclo.
2. Ripeti con gli elementi che non hai ancora toccato.
3. Metti tutto insieme.

##### **Premessa:** 
- **Il simbolo “**$\mapsto$**” (oppure** $|\to$**)**:
Si legge **“va in”** o **“è mandato in”**.
Serve per descrivere come una funzione trasforma un elemento.
**Descrive l’insieme di partenza e arrivo della funzione** (dominio → codominio). 

Esempi:
- Se ho una funzione $f(x)=x^2$, posso scriverla anche così:
    $f:\; x \mapsto x^2$.
    Si legge: “$f$ manda $x$ in $x^2$”.
- Per una permutazione $g=(1\ 2\ 3)$:
    $1 \mapsto 2,\quad 2 \mapsto 3,\quad 3 \mapsto 1$.


-  **Il simbolo “**$\to$**”**:
Si legge **“da … a …”** e serve per indicare **il dominio e il codominio** di una funzione.
**Descrive come un singolo elemento viene trasformato**. 

Esempi:
- La scrittura
    $f:\mathbb R \to \mathbb R,\quad x \mapsto x^2$
    significa:
    - “f è una funzione che prende input da $\mathbb R$ e restituisce output in $\mathbb R$”;
    - e precisamente manda $x$ in $x^2$.

### **Esempio con** $x=1$
Calcoliamo $g(1)$
- Applica $(4\;5)$: questo ciclo tocca solo 4 e 5, quindi lascia 1 invariato ⇒ 1.
- Poi $(2\;3\;8)$: tocca solo $2,3,8,$ quindi lascia 1 invariato ⇒ 1.
- Poi £: qui invece 1 va in 5 ⇒ 5.
    Quindi $g(1)=5$.
    
Non stiamo facendo operazioni numeriche (tipo somme o prodotti), stiamo solo **seguendo le regole dei cicli**: controlliamo se il numero è citato dentro al ciclo.
- Se sì, lo spostiamo in quello successivo del ciclo.
- Se no, resta uguale.
### **Esempio con** x=5
Calcoliamo $g(5)$.
- Applica $(4\;5)$: questo ciclo dice $5\mapsto4$.
- Poi $(2\;3\;8)$: non tocca il 4, quindi resta 4.
- Poi $(1\;5\;8)$: non tocca il 4, quindi resta 4.
    Quindi $g(5)=4$.


### **Calcolo immagine per immagine (passo-passo)**

Applichiamo i tre cicli in ordine (destra→sinistra) a ciascun elemento.
- **Per** 1:
    1. $(4\ 5)$ lascia 1 invariato → 1.
    2. $(2\ 3\ 8)$ lascia 1 invariato → 1.
    3. $(1\ 5\ 8)$ manda $1\mapsto5$.
        $⇒ g(1)=5$.
        
- **Per** 5:
    1. ($4\ 5): 5\mapsto4$.
    2. $(2\ 3\ 8): 4\mapsto4$.
    3. $(1\ 5\ 8): 4\mapsto4$.
        $⇒ g(5)=4.$
	    
- **Per** 4:
    1. $(4\ 5): 4\mapsto5$.
    2. $(2\ 3\ 8): 5\mapsto5$.
    3. ($1\ 5\ 8): 5\mapsto8$.
        $⇒ g(4)=8$.
        
- **Per** 8:
    1. $(4\ 5): 8\mapsto8$.
    2. $(2\ 3\ 8): 8\mapsto2$.
    3. $(1\ 5\ 8): 2\mapsto2$.
        $⇒ g(8)=2$.
        
- **Per** 2:
    1. $(4\ 5): 2\mapsto2$.
    2. $(2\ 3\ 8): 2\mapsto3$.
    3. ($1\ 5\ 8): 3\mapsto1$.
        $⇒ g(2)=3$.
        
- **Per** 3:
	1. $(4\ 5): 3\mapsto3$.
    2. ($2\ 3\ 8): 3\mapsto8$.
    3. $(1\ 5\ 8): 8\mapsto2$.
        $⇒ g(3)=1$.
        
- **Per** 6 e 7: nessun ciclo li tocca ⇒ sono fissi: $g(6)=6,\ g(7)=7$.

Riepilogo (mappa):
$1\mapsto5,\;5\mapsto4,\;4\mapsto8,\;8\mapsto2,\;2\mapsto3,\;3\mapsto1,\;6\mapsto6,\;7\mapsto7.$

### **Costruzione dei cicli disgiunti**
Parto da 1 e seguo le immagini fino a tornare a 1:

$1 \to 5 \to 4 \to 8 \to 2 \to 3 \to 1.$

Quindi c’è un ciclo di lunghezza 6:
$(1\;5\;4\;8\;2\;3).$

Gli elementi 6 e 7 sono fissi (cicli di lunghezza 1, di solito si omettono).

**Risposta (punto 1):**
$\boxed{g = (1\;5\;4\;8\;2\;3)}\qquad(\text{6 e 7 fissi}).$     $di \ lughezza \ 6$



# **2) Trovare** $h\in S_8$ **non banale con** $h\circ g = g\circ h$

## **Premessa: cosa significa “commutare”?**

Due permutazioni $g, h \in S_n$ **commutano** se l’ordine in cui le applichi non cambia il risultato:

			$h \circ g = g \circ h$
- Dove “$\circ$” indica la **composizione**: applicare prima una permutazione e poi l’altra.
- In altre parole: se applichi h prima e $g$ dopo, ottieni lo stesso risultato che se applichi $g$ prima e h dopo.
    

**Esempio intuitivo:**
- Immagina 6 carte numerate $1,2,3,4,5,6$.
- Sia g la permutazione che le ruota di 1 posizione: $(1\;2\;3\;4\;5\;6)$.
- Se applichi g due volte ($g^2$), è come ruotarle di 2 posizioni.
- Adesso, $g^2 \circ g = g \circ g^2 = g^3$, cioè ruotare di 3 posizioni.
- Quindi $g$ e $g^2$ **commutano**, perché l’ordine non cambia il risultato finale.

**Idea chiave:** quando due permutazioni commutano, puoi scambiarne l’ordine senza modificare l’effetto finale.


#### **Perché considerare le potenze di** g?

Una proprietà fondamentale dei **cicli**:
- Ogni potenza $g^k$di un ciclo g **commuta con** $g$:    g$^k \circ g = g \circ g^k = g^{k+1}$.
- Qui, “centralizzatore” significa l’insieme di tutte le permutazioni che commutano con $g$.
- Se $g$ è un ciclo di lunghezza 6, allora: $g^6 = \text{id} \quad\text{(l’identità)}$ e nessuna potenza minore di 6 fa tornare tutti gli elementi al punto di partenza.
- Quindi basta scegliere una potenza $g^k$ con $1 \le k \le 5$ per ottenere una permutazione **non banale** che commuta con g.


#### **Applicazione al nostro caso concreto**
Abbiamo la permutazione $g \in S_8$:
			$g = (1\;5\;4\;8\;2\;3)$

- Questo è un **6-ciclo**: ruota sei elementi e lascia fissi 6,7.     
- Significa:
    - $g^1 = g →$ ruota di 1 posizione
    - $g^2 →$ ruota di 2 posizioni
    - $g^3$ → ruota di 3 posizioni
    - …
    - $g^6 = \text{id}$

**Osservazione:** Qualsiasi g^k commuta con g.

## **Costruire** $h = g^2$ **e decomporlo in cicli disgiunti**
Applichiamo g **due volte** ($g^2$) su ogni elemento:

- Consideriamo la sequenza degli elementi:
    - $1 \mapsto 5 \mapsto 4 → 1 \mapsto 4$
    - $4 \mapsto 8 \mapsto 2 → 4 \mapsto 2$
    - $2 \mapsto 3 \mapsto 1 → 2 \mapsto 1$
        $⇒ ciclo (1\;4\;2)$
        
- Altri elementi nel 6-ciclo:
    - $3 \mapsto 1 \mapsto 5 → 3 \mapsto 5$
    - $5 \mapsto 4 \mapsto 8 → 5 \mapsto 8$
    - $8 \mapsto 2 \mapsto 3 → 8 \mapsto 3$
        $⇒ ciclo (3\;5\;8)$
        
- Gli elementi 6 e 7 restano fissi.
    
Quindi la decomposizione di $g^2$ in cicli disgiunti è:
$h = g^2 = (1\;4\;2)(3\;5\;8)$

- $h \neq \text{id} →$ è **non banale**
- $h \circ g = g \circ h →$ **commuta con** g
    
### Conclusione
- **Risposta finale:**
    $\boxed{h = g^2 = (1\;4\;2)(3\;5\;8)} \quad (\text{commuta con } g,\, h \neq \text{id})$
    
- **Perché funziona sempre questo metodo:**
    - Le potenze di un ciclo rimangono all’interno del ciclo stesso, non mischiano elementi di cicli diversi.
    - Quindi $g^k $commuta sempre con g.
    - In generale, se ci sono più cicli disgiunti, le potenze combinano in modo naturale con ogni ciclo.


--- 

# Per esercizi sulle Parole

**Quanti anagrammi si possono formare con la parola** COCCODRILLO? **Quanti di questi anagrammi iniziano per L?**


Scrivi la parola e conta quante volte appare ciascuna lettera.

COCCODRILLO → lettere e loro frequenze:
- C : 3
- O : 3
- L : 2
- D : 1
- R : 1
- I : 1

Totale lettere = 3+3+2+1+1+1 = 11.

  
**2) Formula generale (permutazioni con ripetizioni)**
Se hai n oggetti in totale e, tra loro, gruppi indistinguibili di dimensioni $n_1,n_2,\dots$, il numero di permutazioni distinte è

$\frac{n!}{n_1!\,n_2!\,\cdots}$

Qui $n=11$ e i denominatori sono $3!,3!,2!,1!,1!,1!$. Quindi

$\#\text{anagrammi}=\frac{11!}{3!\,3!\,2!}$.

  

**3) Calcolo numerico (passo passo)**

- $11! = 11\cdot10\cdot9\cdot8\cdot7\cdot6\cdot5\cdot4\cdot3\cdot2\cdot1 = 39\,916\,800.$ 
- $3! = 6.$ Quindi denominatore $=6\cdot6\cdot2 = 72.$
    
    Ora dividi:
    $\frac{39\,916\,800}{72} \;=\; \frac{39\,916\,800}{6} \div 6 \div 2 =6\,652\,800 \div 6 \div 2 =1\,108\,800 \div 2 =554\,400.$
    
Quindi **ci sono** 554\,400 **anagrammi distinti**.

**4) Quanti iniziano per**  **L** **?**

Mettiamo la prima lettera fissata a L. Poiché le L sono 2 identiche, fissare la prima posizione come L significa semplicemente **rimuovere una L**..

Rimangono 11-1=10 lettere con frequenze:

- $C: 3, O: 3, L: 1, D:1, R:1, I:1.$

Numero di permutazioni delle rimanenti:

$\frac{10!}{3!\,3!} .$

Calcolo:
- $10! = 3\,628\,800.$
- $3!\cdot3!=6\cdot6=36.$
    $\frac{3\,628\,800}{36} = \frac{3\,628\,800}{6}\div 6 = 604\,800\div 6 = 100\,800.$
    
Quindi 100\,800 anagrammi iniziano per L.

**Risposte parte 1**

- Totale anagrammi: $\boxed{554\,400}.$
- Di questi, quelli che iniziano per $L: \boxed{100\,800}.$