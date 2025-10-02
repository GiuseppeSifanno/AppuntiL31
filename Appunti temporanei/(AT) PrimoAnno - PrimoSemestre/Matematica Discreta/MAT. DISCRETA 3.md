# FUNZIONI

Prima di parlare di esercizi su funzioni bisogna chiarire alcuni argomenti importanti:

## **Che cos’è una funzione?**
Una **funzione** $f: A \to B$ è una relazione che associa **a ogni elemento** x dell’insieme di partenza A (dominio) **uno ed un solo elemento** y dell’insieme di arrivo B (codominio).

Si scrive:
$y = f(x)$.
- A = **dominio**: insieme dei valori ammessi in input.
- B = **codominio**: insieme “previsto” dei valori di output.
- **Range** o immagine = sottoinsieme di B che contiene i valori che effettivamente escono dalla funzione.
Esempio: $f(x) = x^2$ con dominio $\mathbb R$ e codominio $\mathbb R$.

# **Che cos’è il** **dominio** **di una funzione?**
È **l’insieme di tutti i valori che posso dare in input** a una funzione, senza avere problemi (divisioni per zero, radici quadrate di numeri negativi, ecc.).

Esempio:
- $f(x)=\frac{1}{x}$. Qui **non posso** mettere x=0, perché non si può dividere per zero.
    Quindi il dominio è $\mathbb R\setminus\{0\}$ (tutti i reali tranne 0).
    
- $g(x)=\sqrt{x}$. Qui non posso mettere valori negativi (altrimenti non ho radici reali).
    Quindi il dominio è $[0,\infty)$.
    
- $h(x)=2x+3$. Qui non c’è nessun problema → il dominio è tutto $\mathbb R$.
    
# **Che cos’è il** **codominio** **?**
È **l’insieme in cui sono previsti i risultati** della funzione.

⚠️ ***Importante***: il codominio non è “deciso” dalla funzione, ma da **come definisco** la funzione.

Di solito nei problemi è scritto: $f:\mathbb R \to \mathbb R$. Vuol dire che:

- dominio = $\mathbb R$ (i valori di partenza)
- codominio = $\mathbb R$ (i valori “previsti in arrivo”).

Però non è detto che la funzione arrivi davvero a **tutti** i numeri del codominio.
E qui entra in gioco il **range**.

# **Che cos’è il** **range** **(o immagine)?**
È **l’insieme di tutti i valori effettivamente ottenuti dalla funzione**, cioè i risultati reali che la funzione produce quando varia il dominio.

Esempi:
- Funzione $f(x)=x^2$, con $f:\mathbb R\to\mathbb R$.
    - dominio = $\mathbb R$ (posso dare qualsiasi numero reale in input).
    - codominio = $\mathbb R$ (per definizione).
    - range = $[0,\infty)$, perché i quadrati non possono essere negativi.
        ⚠️ ***Vedi la differenza***: il codominio era $\mathbb R$, ma il range effettivo è solo la parte positiva.
        
    
- Funzione $g(x)=|x|+1$, con $g:\mathbb R\to\mathbb R$.
    - dominio = $\mathbb R$ (posso mettere qualunque numero).
    - codominio = $\mathbb R$.
    - range = $[1,\infty)$, perché $|x|\ge0$, quindi $|x|+1\ge1$.
        In pratica, i valori minori di 1 non possono uscire.
        
# **Come li trovo?**
1. **Dominio**: guarda la formula della funzione e chiediti: ci sono restrizioni?
    - Divisione per 0 
    - Radici quadrate di negativi 
    - Logaritmi di numeri ≤0 
        Se non c’è nulla di problematico, il dominio è tutto $\mathbb R$.

2. **Codominio**: di solito è scritto nel testo (es. $f:\mathbb R\to\mathbb R$). È un “contenitore” scelto dal prof. Se non è specificato, si prende di solito $\mathbb R$.

3. **Range**: guarda cosa esce davvero:
    - Analizza la funzione (es. quadrati ≥0, valori assoluti ≥0, ecc.).
    - Oppure calcola il minimo e massimo (se esistono).

# **Perché sono importanti?**
- Per sapere se la funzione è **suriettiva**: serve che range = codominio.
- Per sapere se è **invertibile**: serve anche iniettività, ma range e codominio giocano un ruolo chiave.


# **Funzione** iniettiva
Una funzione è iniettiva se **due input diversi danno sempre output diversi**.
Formalmente: se $f(x_1)=f(x_2)$ allora $x_1=x_2$.
**Immagine mentale**: “Non schiaccia mai due frecce in un unico punto”.

 Esempi:
- $f(x)=2x+1$ (una retta inclinata): ogni valore di x produce un valore unico, mai ripetuto.
- $f(x)=x^3$: anche qui, ogni input diverso dà output diverso.

 Non iniettive:
- $f(x)=x^2$: sia $x=2$ che $x=-2$ danno lo stesso valore 4.
- $g(x)=|x|: g(3)=g(-3)=3.$

- *Consiglio pratico:* Portare nella maggior parte delle volte la x a 1 o -1 dovrebbe verificare la sua iniettività. 


# **Funzione** suriettiiva
Una funzione è suriettiva se **copre tutto il codominio**: per ogni valore y nel codominio, esiste almeno un x nel dominio che ci arriva.
**Immagine mentale**: “Nessun buco rimane vuoto nel codominio”.

Esempi:
- $f:\mathbb R\to\mathbb R,\ f(x)=2x+1$. È suriettiva perché qualsiasi $y\in\mathbb R$ si ottiene risolvendo $y=2x+1$.
    
- $f:\mathbb R\to 0,\infty),\ f(x)=x^2$. È suriettiva su $[{0,\infty})$ perché ogni numero positivo è il quadrato di qualcosa.

Non suriettive:
- $f:\mathbb R\to\mathbb R,\ f(x)=x^2$. Qui il codominio è $\mathbb R$, ma la funzione produce solo numeri ≥0. Quindi i negativi non sono coperti → non è suriettiva.

# **Funzione** biettiva
Una funzione è biettiva se è **sia iniettiva che suriettiva**.
Quindi:
- Non schiaccia due input nello stesso output (iniettiva).
- Copre tutto il codominio (suriettiva).
**Immagine mentale**: “È una corrispondenza perfetta, tipo coppie uno-a-uno”.
  
Esempi:
- $f:\mathbb R\to\mathbb R,\ f(x)=2x+1$.
Iniettiva (retta inclinata, mai valori ripetuti) + suriettiva (copre tutto $\mathbb R)$ = biettiva.    
Non biettive:
- $f(x)=x^2:\mathbb R\to\mathbb R$. Non iniettiva e non suriettiva → quindi non biettiva.

# **Funzione** invertibile
Una funzione è invertibile se esiste un’altra funzione f^{-1} che “annulla” f, cioè:
f$^{-1}(f(x))=x \quad\text{e}\quad f(f^{-1}(y))=y$
Una funzione è **invertibile se e solo se è biettiva**.

Esempi:
- $f(x)=2x+1$. Inversa: $f^{-1}(y)=\frac{y-1}{2}$.
- $f(x)=x^3$. Inversa: $f^{-1}(y)=\sqrt[3]{y}$.

Non invertibili:
- $f(x)=x^2:\mathbb R\to\mathbb R$. Non è iniettiva (sia 2 che -2 vanno su 4) → non invertibile.
- Però se restringo il dominio a $[0,\infty)$, diventa invertibile con inversa $f^{-1}(y)=\sqrt{y}$.

---

# ESERCIZIO D'ESEMPIO da traccia d'esame

### **Soluzione passo-passo e spiegazioni (Esercizio 3)**

Riprendo l’enunciato:
$f:\mathbb R\to\mathbb R,\; f(x)=2-\dfrac{x}{5}.$
$g:\mathbb R\to\mathbb R,\; g(x)=|x|+1.$

Richiesto: calcolare $f\circ g$ e $g\circ f$; determinare se f e g sono invertibili e, se sì, trovare le inverse.
Ti mostro ogni passaggio e ti spiego **perché** faccio quella scelta.

## **1) Dominio / codominio / range (per orientarsi)**
- **Dominio**: l’enunciato dice $f:\mathbb R\to\mathbb R$, $g:\mathbb R\to\mathbb R$ → dominio e codominio dichiarati sono $\mathbb R$ per entrambe.
    _(Se la funzione avesse avuto una radice o una divisione per espressione che può essere 0, il dominio sarebbe stato diverso.)_
    
- **Range** (immagine effettiva):
    - Per f: essendo una retta inclinata (affine) con coefficiente$-\tfrac{1}{5}$ non nullo, f assume **tutti** i reali → range di $f = \mathbb R$.
    - Per $g: g(x)=|x|+1$. Poiché $|x|\ge0$ per ogni x, $g(x)\ge1$. Quindi range di $g = [1,\infty)$.
        
Queste informazioni servono spesso per decidere se una funzione è suriettiva o se una composizione è ben definita.

## **2) Calcolo di** $f\circ g$ **(cioè** $f(g(x))$) — passo per passo
Definizione: ($f\circ g)(x) = f(g(x)$).
1. Calcoliamo $g(x): g(x)=|x|+1$.
2. Mettiamo g(x) dentro f:
    $f(g(x)) = 2 - \frac{g(x)}{5} = 2 - \frac{|x|+1}{5}$.
3. Svolgiamo l’algebra:
    $2 = \dfrac{10}{5}$, quindi
    $f(g(x)) = \frac{10}{5} - \frac{|x|+1}{5} = \frac{10 - (|x|+1)}{5} = \frac{9 - |x|}{5}$.

**Risultato:**
$\boxed{(f\circ g)(x) = \dfrac{9 - |x|}{5}.}$

  **Osservazioni utili:**
- Dominio: tutto $\mathbb R$ (nessuna restrizione).
- Range: massimo quando $|x|=0$ → valore $=9/5$. Per $|x|\to\infty$ la funzione $\to -\infty$. Quindi range $=(-\infty,\;9/5]$.
- **Iniettività**: non è iniettiva perché dipende da |x|. Per esempio x=2 e x=-2 danno lo stesso valore:
    ($f\circ g)(2)=\frac{9-2}{5}=\frac{7}{5}=(f\circ g)(-2)$.  

Quindi $f\circ g$ non è iniettiva e (dato che il range è solo ($-\infty,9/5]$) neanche suriettiva su $\mathbb R$.

## **3) Calcolo di** $g\circ f$ **(cioè** $g(f(x))$**) — passo per passo**
Definizione: $(g\circ f)(x) = g(f(x))$.

1. Calcoliamo $f(x)=2 - \dfrac{x}{5}$.
2. Mettiamo dentro g:
    $g(f(x)) = \big|\,f(x)\,\big| + 1 = \left|2 - \frac{x}{5}\right| + 1.$

**Risultato:**
$\boxed{(g\circ f)(x) = \left|2 - \frac{x}{5}\right| + 1.}$


**Osservazioni:**

- Dominio: tutto $\mathbb R$.
- Range: se poniamo $u=2-\dfrac{x}{5}$, allora u varia su tutto $\mathbb R$ (perché f è suriettiva), quindi $|u|+1$ varia su $[1,\infty)$. Quindi range di $g\circ f$ è $[1,\infty)$.
- **Iniettività**: non è iniettiva. 
Quindi $g\circ f$ non è iniettiva; inoltre il suo range $[1,\infty)$ non è tutto $\mathbb R$, quindi non è suriettiva su $\mathbb R$.

## **4) Verifica invertibilità di** f
**Strategia**: verificare iniettività e suriettività (bijettività).

- $f(x)=2-\dfrac{x}{5}$ è una funzione affine con coefficiente angolare $-\tfrac{1}{5}\neq 0$. Le funzioni affini con coefficiente diverso da zero sono **monotone** (qui monotona decrescente), quindi **iniettive**.
- Per la suriettività: dato un $y\in\mathbb R$, risolvo $y = 2 - \dfrac{x}{5}$ per x:
    $x = 5(2-y) = 10 - 5y$,
    che è sempre un reale: quindi per ogni y esiste x tale che f(x)=y. Quindi f è suriettiva.


Conclusione: f è **bijettiva** su $\mathbb R$ e quindi **invertibile**.

**Trovo** $f^{-1}$: risolvo $y = 2 - \dfrac{x}{5}$ per x e poi scambio ruolo delle variabili:
$x = 10 - 5y \quad\Longrightarrow\quad f^{-1}(y) = 10 - 5y$.

Usando x come argomento dell’inversa:
$\boxed{f^{-1}(x) = 10 - 5x.}$

## **5) Verifica invertibilità di** g

- $g(x)=|x|+1$. Per **iniettività** osserva subito che $g(x)=g(-x)$ per ogni x. Quindi esistono sempre coppie diverse $(x,-x)$ con la stessa immagine (a meno di $x=0$). Quindi **non iniettiva** su $\mathbb R$.
- Per **suriettività** su $\mathbb R$: poiché $g(x)\ge1$, non si ottengono valori <1. Quindi **non suriettiva** su $\mathbb R$.

Conclusione: g **non è invertibile** come funzione $\mathbb R\to\mathbb R$.

---

---
# Schema operativo — Verifica di Iniettività, Suriettività, Biiettività (e calcolo dell'inversa)

**Scopo:** fornire uno schema chiaro e riutilizzabile per affrontare esercizi su iniettività, suriettività, biiettività e calcolo delle inverse, con tutti i controlli necessari e i metodi più usati.

## Regole preliminari (prima di iniziare)
1. **Scrivi esplicitamente dominio e codominio** richiesti dall'esercizio. Non darli per scontati.
2. **Semplifica** l'espressione della funzione (espandi, riscrivi valore assoluto, pezzi, etc.).
3. Se la funzione è _a tratti_, tratta ogni intervallo separatamente.
4. Se compaiono simboli particolari (valore assoluto, radici, log, trig), annota le proprietà utili.


## Procedura passo‑passo

Segui i punti nell'ordine indicato — ogni punto contiene i metodi principali da usare.

### 1 Verifica di iniettività
**Obiettivo:** dimostrare $f(x1)=f(x2)⇒x1=x2$ oppure fornire un controesempio.

Metodi utili:
- **Metodo algebrico (diretto):** scrivi $f(x1)=f(x2)$ e riduci fino a ottenere$ x1=x2$.
- **Derivata (per funzioni reali, differenziabili):** se $f′(x)>0$ per tutti $x∈D$ (o sempre <0) allora f è monotona e quindi iniettiva. ATTENZIONE: $f′(x)≥0$ non basta; devono esserci segni stretti o monotonia provata per altri metodi.
    
- **Controesempio (per mostrare non iniettività):** trova $x1≠x2$ con $f(x1)=f(x2)$ (es.: funzioni pari, valore assoluto, quadratica tipicamente falliscono).

Scrittura della risposta:
- Se dimostri iniettività: mostra i passaggi algebrici o argomento con derivata; concludi chiaramente.
- Se non è iniettiva: fornisci un controesempio numerico e spiega perché è sufficiente.

### 2 Verifica di suriettività
**Obiettivo:** dimostrare che per ogni $y∈C$ esiste x∈D con $f(x)=y$.

Metodi utili:
- **Risolvi $y=f(x)$ per x** in funzione di y. Se riesci a esprimere $x=ϕ(y)$ e $ϕ(y)∈D$ per ogni $y∈C$, allora f è suriettiva.
- **Studio dell'immagine (range):** determina l'insieme delle immagini tramite:
    - analisi dei limiti per $x→±∞$,
    - comportamento ai punti singolari (es. discontinuità, punti a pezzi).
        
- **Controesempio (per mostrare non suriettività):** trova $y0∈C$ tale che l'equazione $f(x)=y0$ non abbia soluzioni in D.

Scrittura della risposta:
- Se è suriettiva: mostra la soluzione $x=ϕ(y)$ con la verifica che $ϕ(y)∈D$ per ogni $y∈C$.
- Se non è suriettiva: fornisci $y0∈C$ (spesso un valore limite) e mostra che non esiste x con $f(x)=y0$.

### 3 Conclusione su biiettività
- Se **iniettiva** $E$ **suriettiva** su $D→C$ allora **biiettiva**.
- Se biiettiva ⇒ **esiste** f$−1:C→D$.

### 4. Calcolo dell'inversa (se biiettiva)
1. Scrivi $y=f(x)$.
2. Scambia i ruoli: considera $x=f(y)$.
3. Risolvi per y in funzione di $x: y=F(x)$. Allora $f−1(x)=F(x)$.
4. **Specifica dominio e codominio** dell'inversa: il dominio di $f−1$ è la **immagine** di f, il codominio è il dominio di f.
5. Verifica (controllo rapido): $f−1(f(x))=x$ per ogni $x∈D$ e $f(f−1(y))=y$ per ogni y nell'immagine.

### 5. Composizioni e proprietà d'invertibilità
- Se f e g sono invertibili allora $f∘g$ è invertibile e ($f∘g)−1=g−1∘f−1$.
- Se $f∘g$ è invertibile allora **g** deve essere iniettiva e **f** deve essere suriettiva (ma questo non garantisce che f e g siano entrambe invertibili separatamente).

### 6. Come rendere una funzione invertibile (restringendo il dominio)
- Se f non è iniettiva per simmetria (es. x2, (|x|)), scegli un ramo monotono (es. per x2 prendi x≥0).
- Se f non è suriettiva sul codominio scelto, o cambia il codominio all'immagine naturale di f.
- Documenta sempre la restrizione: scrivi la nuova funzione e i nuovi insiemi dominio/codominio.
