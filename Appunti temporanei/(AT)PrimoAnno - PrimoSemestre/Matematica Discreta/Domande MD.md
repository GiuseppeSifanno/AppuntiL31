# Suriettività
Una funzione $f: A \to B$ si dice **suriettiva** (o _sovraiettiva_) se **ogni elemento del codominio** B **è immagine di almeno un elemento del dominio** A.
In simboli:
$f \text{ è suriettiva } \iff \forall b \in B, \ \exists a \in A \text{ tale che } f(a) = b$
Equivalentemente, l’**immagine di** f coincide con il codominio:
$\mathrm{Im}(f) = B$

**Esempi:**
1. $f: \mathbb{R} \to \mathbb{R}, \ f(x) = 2x + 1$
    - Per ogni $y \in \mathbb{R}$, possiamo trovare $x = \frac{y-1}{2} tale che f(x) = y$.
    - Quindi f è suriettiva.
2. $g: \mathbb{R} \to \mathbb{R}_{\ge 0}, \ g(x) = x^2$
    - Non è suriettiva perché non esistono $x \in \mathbb{R}$ tali che $g(x) < 0$.
    - L’insieme immagine è $\mathrm{Im}(g) = \mathbb{R}{\ge 0}$, quindi se il codominio fosse $\mathbb{R}{\ge 0}$ allora g sarebbe suriettiva, ma non lo è rispetto a tutto $\mathbb{R}$.


# Iniettività 
Una funzione $f$ da $A$ ad $A'$ si dice *iniettiva* se elementi distinti di $A$ hanno immagini distinte in $A'$, ossia se:
- $\forall a,b \in A, \ a \neq b \implies f(a) \neq f(b)$
o in forma equivalente:
- $\forall a,b \in A, \ f(a) = f(b) \implies a = b$

Esempio se richiesto:
1. $f: \mathbb{R} \to \mathbb{R}, \ f(x) = 2x + 1$
    - Se $f(a) = f(b) \Rightarrow 2a+1 = 2b+1 \Rightarrow a=b$
    - Quindi f è iniettiva.
2. $g: \mathbb{R} \to \mathbb{R}, \ g(x) = x^2$
    - Non è iniettiva perché $g(1) = g(-1) = 1, ma 1 \neq -1.$

# Biettività
Una funzione $f$ da $A$ ad $A'$ è detta biettivase contemporaneamente suriettiva e iniettiva. 

# Funzione composta
Date due funzioni $f:A \to B$ e $g:B \to C$, si definisce *funzione composta* di $f$ con $g$, e si indica con $g \circ f$, la funzione:
			$g \circ f: A \to C$
data con:
			$(g \circ f)(a) := g(f(a))$  $\forall a \in A$

Esempio in caso lo chieda: 

Siano:
- $f: \mathbb{R} \to \mathbb{R}, \quad f(x) = 2x + 1$
- $g: \mathbb{R} \to \mathbb{R}, \quad g(y) = y^2$

Allora la composizione $g \circ f$ è:
- $(g \circ f)(x) = g(f(x)) = g(2x+1) = (2x+1)^2$
- **Dominio**: $\mathbb{R}$
- **Codominio**: $\mathbb{R}$

# Grafo
Un **grafo** è una coppia ordinata $G = (V, E)$ dove:
- $V$ è un insieme finito e non vuoto i cui elementi si chiamano **vertici** o **nodi** o **puntatori**;
- E un insieme $E\subseteq V \times V$ di coppie ordinate di elementi di $V$ che si chiamano *archi* o *lati*.

# Monoide e Elemento invertibile del monoide
Sia ($M, \ast)$ un **monoide**, cioè:
- $M$ è un insieme,
- $\ast : M \times M \to M$ è un’operazione binaria **associativa**,
- esiste un elemento neutro $e\in M$ t. c. $\forall a \in M \quad a \ast e = e \ast a = a .$
    
Un elemento $a \in M$ si dice **invertibile** se esiste un elemento $b \in M$ tale che:
$a \ast b = b \ast a = e$
dove $e$ è l’elemento neutro del monoide. 
L’elemento $b$ si chiama **inverso** di $a$.

# Definizione di funzione da un insieme A ad un insieme B
Siano A e B due insiemi.
Una **funzione** da $A$ a $B$ è una relazione $f \subseteq A \times B$ tale che:
$\forall a \in A \; \exists! \; b \in B \; : \; (a,b) \in f .$

