## Esercizi sulla generazione

Sia dato il linguaggio $L = \{ a^nb^{2n+1}|n\ge0\}$.
Determinare una grammatica generativa per L.
	Alcune parole:
		L={$b, ab^3,a^2b^5,a^3b^7,..$}
		
Parola più piccola possibile:
	S $\to$ b
Un esempio di produzione potrebbe essere:
- S $\to$ b | aSbb 
Esempio:
S $\implies$ aabbbbb 
S $\to$ aSbb
S $\to$ aaSbbbb
S $\to$ aabbbbb
Avendo quindi la grammatica:
	G = (X, V, S, P):
		X={a,b}
		V={S}
		S
		P = {S $\to$ b | aSbb}

---

Sia dato il linguaggio $L = \{ a^nb^{n+m}c^m|n, m\gt0\}$.
Determinare una grammatica generativa per L.
	Alcune parole
		L = {$ab^2c, ab^3c^2,a^2b^3c,a^2b^4c^2$}
Per facilitare la comprensione possiamo riscrivere il linguaggio:
	$L = \{ a^nb^nb^mc^m|n, m\gt0\}$
	Notiamo che vi è un legame tra a e b, ma anche tra b e c. Le coppie hanno infatti tra loro lo stesso esponente. Inoltre, siccome le due coppie hanno esponente diverso, possiamo generarle indipendentemente tra loro.
Possiamo pensare dunque ad una produzione:
		S $\to$ aAbbBc
			A $\to$ $\lambda$ | aAb
			B $\to$ $\lambda$ | bBc
Con la conseguente grammatica.
Un'altra possibile produzione sarebbe:
	S $\to$ AB
		A $\to$ ab | aAb
		B $\to$ bc | bBC
Avendo quindi la grammatica:
	G = (X, V, S, P):
		X={a,b,c}
		V={S, A, B}
		S
		P = {S $\to$ AB, A $\to$ ab | aAb, B $\to$ bc | bBc}

---

Sia dato il linguaggio $L = \{ a^nb^{2k+1}|n, k\ge0\}$.
Determinare una grammatica generativa per L.
...
Possibile produzione:
	S $\to$ ABb
		A $\to$ aA | $\lambda$
		B $\to$ bbB | $\lambda$
...

---
Sia dato il linguaggio $L = \{ a^nb^nc^n|n > 0\}$.
Determinare una grammatica generativa per L.
...
Possibile produzione
S $\Rightarrow$ aSBC $\Rightarrow$ aaSBCBC $\Rightarrow$ aaaSBCBCBC $\Rightarrow$ aaaaSBCBCBCBC $\Rightarrow$ aaaaaBCBCBCBCBC $\Rightarrow$ aaaaaBBCCBCBCBC $\Rightarrow$ aaaaaBBCBCCBCBC $\Rightarrow$ aaaaaBBBCCCBCBC $\Rightarrow$ aaaaaBBBCCBCCBC $\Rightarrow$ aaaaaBBBCBCCCBC $\Rightarrow$ aaaaaBBBBCCCCBC $\Rightarrow$ aaaaaBBBBCCCBCC $\Rightarrow$ aaaaaBBBBCCBCCC $\Rightarrow$ aaaaaBBBBCBCCCC $\Rightarrow$ aaaaaBBBBBCCCCC $\Rightarrow$ aaaaabBBBBCCCCC $\Rightarrow$ aaaaabbBBBCCCCC $\Rightarrow$ aaaaabbbBBCCCCC $\Rightarrow$ aaaaabbbbBCCCCC $\Rightarrow$ aaaaabbbbbCCCCC 

Regole di produzione:
S $\to$ aSBC|aBC
CB $\to$ BC
aB $\to$ ab
bB $\to$ bb
bC $\to$ bc
cC $\to$ cc

---

Sia dato il linguaggio $L = \{ a^nb^mc^n|n,m > 0\}$.
Determinare una grammatica generativa per L.
...
S $\to$ aSc | aBc
B $\to$ bB | b

---
![[Pasted image 20250606172108.png]]
	G = (X, V, S, P):
		X={0,1}
		V={S,A,B}
		S
		P = {S $\to$ A1B
			A $\to$ 0A|0
			B $\to$ 0B|0BB|0
			}


## Esercizi sul Pumping Lemma
### Caso di studio n.1
Sia dato il linguaggio $L = \{ a^nb^nc^n|n > 0\}$.
Dimostrare che L non è C.F..

Supponiamo per assurdo che il linguaggio L sia libero allora: 
$\exists p \in N ,\ \forall z \in L, |z|>p, z=uvwxy \quad \text{t.c}$
 1. $|vwx| \leq p$
 2. ($vx \neq \lambda$)
 3. $\forall i, \ i\geq 0: uv^iwx^iy \in L$

Studiamo una stringa $z$ $\in L$ t.c $|z|>p$ 
$z = a^pb^pc^p \implies |z| = 3p>p$ 
$$\underbrace{a\dots a}_{\text{p}} \underbrace{b\dots b}_{\text{p}} \underbrace{c\dots c}_{\text{p}}$$


Casi:
1. $vwx$ formato solo da $a$
2. $vwx$ formato solo da $b$
3. $vwx$ formato solo da $c$
4. $vwx$ formato a cavallo tra $a$ e $b$
5. $vwx$ formato a cavallo tra $b$ e $c$


Caso 1:
Prendiamo una stringa a caso (quella più semplice)
	$uv^2wx^2y$
Prendendo la stringa pompata, possiamo aggiungere solo delle $a$.
Ora, il numero di a aumenta: $p+1\leq \#(a) \leq p+p$. Tuttavia il numero di $c$ e $b$ rimane invariato, il che non rispecchia le regole  del linguaggio. Quindi $uv^2wx^2y \not\in L \text{ poichè } \#(a) \neq \#(b) \neq \#(c)$ 

Caso 2 e 3:
Stessa cosa del caso 1, ripetuto però con le $b$ e con le $c$.

Caso 4:
il punto vwx è a cavallo tra $a$ e $b$.
	Caso 4.1: $v\neq \lambda \ x=\lambda$
		$v \neq \lambda \implies \text{ v contiene solo delle a}$, il che vuol dire che $wx = ab\dots b$. Pompando andremmo ad aumentare solo il numero delle $a$ (non delle $b$ poichè dovrebbero essere contenute nelle $x$, il quale è però vuoto). Anche in questo caso quindi avremmo un numero di a pari a: $p+1\leq \#(a) \leq p + p -1$ (p-1 poichè almeno una $a$ è contenuta nelle $w$). Quindi $uv^2wx^2y \not\in L \text{ poichè } \#(a) \neq \#(b) \neq \#(c)$ 
	Caso 4.2: $v = \lambda \ x \neq \lambda$
		$x \neq \lambda \implies \text{ x contiene solo delle b}$.  In questo caso quindi avremmo un numero di $b$ pari a: $p+1\leq \#(b) \leq p + p -1$ (p-1 poichè almeno una $b$ è contenuta nelle $w$). Quindi $uv^2wx^2y \not\in L \text{ poichè } \#(a) \neq \#(b) \neq \#(c)$
	Caso 4.3: $v \neq \lambda \ x \neq \lambda$
		$v \neq \lambda \quad x \neq \lambda \implies \text{ v contiene solo delle a e x contiene solo delle b}$.  In questo caso quindi avremmo un numero di b pari al numero a: $p+1\leq \#(b) = \#(a) \leq p + p -1$ (p-1 poichè almeno una b è contenuta nelle w). Quindi $uv^2wx^2y \not\in L \text{ poichè } \#(a) \wedge \#(b) \neq \#(c)$

Caso 5:
Analogo al caso 4.
### Caso di studio n.2
Questo caso è diverso, lo si va a studiare in un altra maniera rispetto a quello precedente, ovvero studiando la lunghezza della stringa
Qui il linguaggio è assurdo per una motivazione

---

Dimostrare che $L=\{w \in X^{*}|w=a^{n}b^{2^{n^{2}}}\}$ è un linguaggio libero da contesto

Supponiamo per assurdo che il linguaggio L sia libero, allora: 
$\exists p \in N ,\ \forall z \in L, |z|>p, z=uvwxy \quad \text{t.c}$
 1. $|vwx| \leq p$
 2. $vx \neq \lambda$
 3. $\forall i, \ i\geq 0: uv^iwx^iy \in L$

Studiamo la parola: $a^{p}b^{2^{p^{2}}}$, $|z|=p+2^{p^{2}} >p$

Andiamo a considerare la stringa pompata e ne studiamo la lunghezza

$|z|<|uv^2wx^2y|=|uvwxy|+|vx|=|z|+|vwx|\leq |z|+p \leq p+2^{p^{2}} + p<(p+1)+2^{(p+1)^{2}}$
 

Dunque nella stringa pompata abbiamo una lunghezza compresa tra $p + 2^{p^2} < |uv^2wx^2y| \leq (p+1) + 2^{(p+1)^2}$
Si conclude che il linguaggio è assurdo
### Esercizi su automi stati finiti
![[Pasted image 20250605181830.png]]

