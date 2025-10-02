# STRUTTURA ALGEBRICA BINARIE

![[Pasted image 20250915200403.png]]

(Interpretazione: il secondo componente è $\frac{2}{7}yv$; questa è la lettura coerente con la traccia stampata.)

Determinare: 1) associatività; 2) commutatività; 3) elemento neutro (se esiste); 4) inverso esplicito di $\big(\tfrac12,\tfrac12\big)$ (se esiste).

  

### **1) Associatività**

Calcoliamo ($(x,y)\star(u,v))\star(s,t) e (x,y)\star((u,v)\star(s,t)$) e confrontiamoli.

- Primo:
    $(x,y)\star(u,v) = (2+x+u,\;\tfrac{2}{7}yv)$.
    
    Quindi
    $((x,y)\star(u,v))\star(s,t) = \big(2 + (2+x+u) + s,\; \tfrac{2}{7}\cdot (\tfrac{2}{7}yv)\cdot t\big) = \big(4+x+u+s,\; (\tfrac{2}{7})^2\ y v t\big)$.
    
- Secondo:
    $(u,v)\star(s,t)=(2+u+s,\; \tfrac{2}{7} v t)$,
    quindi
    
    $(x,y)\star((u,v)\star(s,t)) = \big(2 + x + (2+u+s),\; \tfrac{2}{7}\cdot y\cdot (\tfrac{2}{7}vt)\big) = \big(4+x+u+s,\; (\tfrac{2}{7})^2\ y v t\big).$
    
Le due quantità coincidono per ogni (x,y),(u,v),(s,t). Quindi \star **è associativa** (grazie alla associatività dell’addizione e della moltiplicazione e ai fattori costanti).

### **2) Commutatività**

Verifichiamo:
$(x,y)\star(u,v)=(2+x+u,\;\tfrac{2}{7}yv)$

e

$(u,v)\star(x,y)=(2+u+x,\;\tfrac{2}{7}vy).$

Poiché $x+u=u+x$ e $yv=vy$, si ha $(x,y)\star(u,v)=(u,v)\star(x,y).$ Quindi $\star$ **è commutativa**.

### **3) Elemento neutro**
Cerchiamo $e=(e_1,e_2)\in A$ tale che per ogni $(x,y)$
$(x,y)\star(e_1,e_2)=(x,y).$

Calcolando:
$(x,y)\star(e_1,e_2) = (2+x+e_1,\; \tfrac{2}{7} y e_2) \overset{!}{=} (x,y).$

Quindi per tutti gli x serve $2+x+e_1=x\Rightarrow e_1=-2$. Per tutti i y serve $\tfrac{2}{7} e_2 = 1 \Rightarrow e_2=\tfrac{7}{2}.$


Quindi l’elemento neutro è
$\boxed{ e = \big(-2,\;\tfrac{7}{2}\big).}$

### **4) Inverso di** $\big(\tfrac12,\tfrac12\big)$
Sia$ a=(\tfrac12,\tfrac12)$. Cerchiamo $b=(u,v)$ con $a\star b = e$. Scriviamo le condizioni:

- Prima componente: $2 + \tfrac12 + u = -2 \Rightarrow u = -2 - \tfrac12 - 2 = -\tfrac{9}{2}.$ (Più chiaramente: 2 + 1/2 + u = $-2 \Rightarrow u = -2 -2 -1/2 = -9/2.)$
    
- Seconda componente: $\tfrac{2}{7}\cdot \tfrac12 \cdot v = \tfrac{7}{2}\Rightarrow \tfrac{1}{7}v = \tfrac{7}{2}\Rightarrow v = \tfrac{49}{2}.$
    
Quindi l’inverso esiste ed è

$\boxed{ \Big(\tfrac12,\tfrac12\Big)^{-1} = \Big(-\tfrac{9}{2},\; \tfrac{49}{2}\Big).}$
  
**Nota:** tutto è in $\mathbb Q\times\mathbb Q$: le coordinate trovate sono razionali, quindi inverse valide.

---

## **PASSO 1 — Chiusura (controllo rapido)**

1. Prendi $x,u,y,v\in\mathbb{Q}$.
2. Prima coordinata: $2+x+u$ è somma di razionali ⇒ è razionale.
3. Seconda coordinata: $\dfrac{2}{7}yv$ è prodotto di razionali ⇒ è razionale.
4. Conclusione: $(x,y)\ast(u,v)\in A.$ (Scrivilo in una riga.)
    



## **PASSO 2 — Associatività (dimostrazione completa, LHS = RHS)**

  

Obiettivo: mostrare che per ogni $(x,y),(u,v),(s,t)\in A$

$\bigl((x,y)\ast(u,v)\bigr)\ast(s,t) \;=\; (x,y)\ast\bigl((u,v)\ast(s,t)\bigr).$

  

### **LHS — calcolo esplicito**

1. Calcola $A:=(x,y)\ast(u,v).$
    $A = \bigl(2+x+u,\; \tfrac{2}{7}yv\bigr).$
    
2. Calcola A\ast (s,t):
    $A\ast(s,t) = \Bigl(2 + (2+x+u) + s,\; \tfrac{2}{7}\cdot\bigl(\tfrac{2}{7}yv\bigr)\cdot t\Bigr).$
    
3. Semplifica coordinate singolarmente:
    - Prima coordinata: $2 + (2+x+u) + s = (2+2) + x + u + s = 4 + x + u + s.$
    - Seconda coordinata:
        
        $\tfrac{2}{7}\cdot\bigl(\tfrac{2}{7}yv\bigr)\cdot t = \left(\tfrac{2}{7}\cdot\tfrac{2}{7}\right)\cdot y \cdot v \cdot t = \tfrac{4}{49}\,y v t.$
        
1. Quindi
    $\text{LHS} = \bigl(4 + x + u + s,\; \tfrac{4}{49}\,y v t\bigr).$
    

### **RHS — calcolo esplicito**

1. Calcola $B:=(u,v)\ast(s,t).$
    $B = \bigl(2+u+s,\; \tfrac{2}{7} v t\bigr).$
    
2. Calcola $(x,y)\ast B:$
    $(x,y)\ast B = \Bigl(2 + x + (2+u+s),\; \tfrac{2}{7}\cdot y \cdot\bigl(\tfrac{2}{7} v t\bigr)\Bigr).$
    
3. Semplifica:
    - Prima coordinata: $2 + x + (2+u+s) = 2+2 + x + u + s = 4 + x + u + s.$
    - Seconda: $\tfrac{2}{7}\cdot y \cdot\bigl(\tfrac{2}{7} v t\bigr) = \tfrac{4}{49}\, y v t.$

4. Quindi
    $\text{RHS} = \bigl(4 + x + u + s,\; \tfrac{4}{49}\,y v t\bigr).$

  

### **Confronto**
LHS = RHS (coordinata per coordinata). Quindi \ast **è associativa**.

(Scrivi la riga finale: “Perciò $((x,y)\ast(u,v))\ast(s,t)=(x,y)\ast((u,v)\ast(s,t))$ per ogni scelta.”)



## **PASSO 3 — Commutatività (dimostrazione completa)**

Mostra che $(x,y)\ast(u,v)=(u,v)\ast(x,y).$

1. Calcola:
    $(x,y)\ast(u,v) = \bigl(2+x+u,\; \tfrac{2}{7} y v\bigr).$
    $(u,v)\ast(x,y) = \bigl(2+u+x,\; \tfrac{2}{7} v y\bigr).$
    
2. Confronta le coordinate:
    - $2+x+u = 2+u+x$ perché l’addizione è commutativa.
    - $\tfrac{2}{7} y v = \tfrac{2}{7} v y$ perché la moltiplicazione è commutativa.
        
    
3. Conclusione: \ast **è commutativa**.
    

## **PASSO 4 — Elemento neutro (trovare** e=(e_1,e_2)**)**

Vogliamo $e\in A$ tale che per ogni $(x,y)\in A$,

$(x,y)\ast e = (x,y)$.

1. Scrivi l’equazione generica:
    $(x,y)\ast(e_1,e_2) = \bigl(2 + x + e_1,\; \tfrac{2}{7} y e_2\bigr) \stackrel{!}{=} (x,y)$.
    Quindi dobbiamo avere, per ogni x,y,
     $2 + x + e_1 = x \qquad\text{e}\qquad \tfrac{2}{7}y e_2 = y.$
    
2. Risolvi la prima equazione:
    - $2 + x + e_1 = x.$
    - Sottrai x ambo i membri: $2 + e_1 = 0.$
    - Quindi $e_1 = -2$.
        
    
3. Risolvi la seconda equazione (caso generale):
    - $\tfrac{2}{7} y e_2 = y.$
    - Se $y\neq 0$, possiamo dividere per $y: \tfrac{2}{7} e_2 = 1$.
    - Risolvi per $e_2: e_2 = \dfrac{1}{2/7} = 1\cdot \dfrac{7}{2} = \dfrac{7}{2}.$
        (Dettaglio aritmetico: $\frac{1}{2/7} = 1\cdot\frac{7}{2}=7/2.$)
    - Se $y=0$, l’equazione è $0=0$ e quindi non impone nulla, ma l’identità deve funzionare per TUTTI i y. Dunque deve valere lo stesso valore $e_2$ che funziona quando $y\neq 0: e_2=\tfrac{7}{2}.$
        
    
4. Conclusione:
    $\boxed{e = \Bigl(-2,\;\tfrac{7}{2}\Bigr).}$
    
5. Verifica rapida (sostituzione):
    - Prima coord.: $2 + x + (-2) = x$.
    - Seconda coord.: $\dfrac{2}{7} y \cdot \dfrac{7}{2} = \dfrac{2\cdot 7}{7\cdot 2} y = 1\cdot y = y.$
        (Mostra i passaggi di moltiplicazione: numeratore $2\cdot7=14$, denominatore $7\cdot2=14, 14/14=1.$)
        
## **PASSO 5 — Inverso generale e condizione di invertibilità**

Vogliamo per un generico $(x,y)\in A$ trovare (a,b) tale che

$(x,y)\ast(a,b) = e = \Bigl(-2,\tfrac{7}{2}\Bigr).$

1. Scrivi le equazioni coordinate:
    $2 + x + a = -2, \qquad \tfrac{2}{7} y b = \tfrac{7}{2}.$
    
2. Risolvi la prima:
    - $2 + x + a = -2.$
    - Sottrai $2+x$ da entrambi i membri:
        $a = -2 - (2 + x) = -2 -2 - x = -4 - x.$
        
3. Risolvi la seconda:
    - $\tfrac{2}{7} y b = \tfrac{7}{2}.$
    - Se $y=0: LHS = \tfrac{2}{7}\cdot 0 \cdot b = 0. RHS = \tfrac{7}{2}\neq 0$. Contraddizione ⇒ **se** $y=0$ **non esiste inverso**.
    - Se $y\neq 0$: dividi entrambi i membri per \$tfrac{2}{7}y$:
        $b = \dfrac{\tfrac{7}{2}}{\tfrac{2}{7}y}.$
        
        Esegui la divisione di frazioni:
        $b = \dfrac{7}{2}\cdot \dfrac{7}{2y} = \dfrac{7\cdot 7}{2\cdot 2y} = \dfrac{49}{4y}.$
        
4. Conclusione generale:
    - Per $(x,y)$ con $y\neq 0$ l’inverso esiste ed è
        $(x,y)^{-1} = \Bigl(-4-x,\; \dfrac{49}{4y}\Bigr).$
    - Per (x,0) **non esiste** inverso.
        
5. Interpretazione strutturale:
    - A con $\ast$ è **un monoid commutativo** (associativo + elemento neutro) su tutto A.
    - L’insieme $G = \mathbb{Q}\times(\mathbb{Q}\setminus\{0\})$ è un **gruppo abeliano** rispetto a $\ast$ (tutti gli elementi hanno inverso come sopra).
    - Gli elementi con seconda coordinata 0 non sono invertibili → non è gruppo sull’intero A.
        

## **PASSO 6 — Inverso specifico di $\bigl(\tfrac12,\tfrac12\bigr)$ (tutti i passaggi aritmetici)

Vogliamo (a,b) con:
$\Bigl(\tfrac12,\tfrac12\Bigr)\ast(a,b) = \Bigl(-2,\tfrac{7}{2}\Bigr).$

### **Prima coordinata**
1. Scrivi l’equazione: $2 + \tfrac12 + a = -2$.
2. Calcola $2 + \tfrac12:$
    - Scrivi $2 = \dfrac{4}{2}$.
    - Quindi $2 + \tfrac12 = \dfrac{4}{2} + \dfrac{1}{2} = \dfrac{5}{2}$.
3. Quindi $\dfrac{5}{2} + a = -2.$
4. Risolvi per $a: a = -2 - \dfrac{5}{2}.$
    - Scrivi $-2 = -\dfrac{4}{2}.$
    - Quindi $-\dfrac{4}{2} - \dfrac{5}{2} = -\dfrac{9}{2}.$
5. Quindi $a = -\dfrac{9}{2}.$
    
### **Seconda coordinata**

1. Scrivi l’equazione: $\dfrac{2}{7}\cdot \dfrac{1}{2}\cdot b = \dfrac{7}{2}.$
2. Calcola il coefficiente davanti a b:
    - $\dfrac{2}{7}\cdot \dfrac{1}{2} = \dfrac{2\cdot 1}{7\cdot 2} = \dfrac{2}{14}.$
    - Semplifica $\dfrac{2}{14} = \dfrac{1}{7} (perché 2/14 = 1/7).$
3. Quindi $\dfrac{1}{7} b = \dfrac{7}{2}$.
4. Moltiplica entrambi i membri per 7:
    $b = 7\cdot \dfrac{7}{2} = \dfrac{49}{2}.$
    (Dettaglio: $7\cdot 7 = 49$, quindi $49/2.$)
    
### **Conclusione**
$\boxed{\Bigl(\tfrac12,\tfrac12\Bigr)^{-1} = \Bigl(-\tfrac{9}{2},\; \tfrac{49}{2}\Bigr).}$

  

### **Verifica (sostituisci e mostra passaggi)**

# **Calcola**

$\Bigl(\tfrac12,\tfrac12\Bigr)\ast\Bigl(-\tfrac{9}{2},\tfrac{49}{2}\Bigr) \Bigl(2+\tfrac12-\tfrac{9}{2},\; \tfrac{2}{7}\cdot\tfrac{1}{2}\cdot\tfrac{49}{2}\Bigr).$
- Prima coordinata:
    - $2 + \tfrac12 - \tfrac{9}{2} = \dfrac{4}{2} + \dfrac{1}{2} - \dfrac{9}{2} = \dfrac{4+1-9}{2} = \dfrac{-4}{2} = -2.$
        
- Seconda coordinata:
    
    - Calcola $\dfrac{2}{7}\cdot\tfrac{1}{2} = \tfrac{1}{7}$ (già fatto).
    - Quindi $\tfrac{1}{7}\cdot\tfrac{49}{2} = \dfrac{49}{14}$.
    - Semplifica $\dfrac{49}{14} = \dfrac{49\div 7}{14\div 7} = \dfrac{7}{2}$.
        
Risultato = $\bigl(-2,\tfrac{7}{2}\bigr)$ cioè l’identità: verifica completa.



