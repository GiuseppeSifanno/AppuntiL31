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

Sia dato il linguaggio $L = \{ a^ib^kc^j|i > 0, j > 0, 0 \leq k \leq i+j\}$.
Determinare una grammatica generativa per L.

Esempi di parole: {ac, abc, abbc, aac, aacc, ...}

---
Sia dato il linguaggio $L = \{ a^nb^mc^n|n,m > 0\}$.
Determinare una grammatica generativa per L.
...
S $\to$ aSc | aBc
B bB | b

## Esercizi sul Pumping Lemma
Sia dato il linguaggio $L = \{ a^nb^nc^n|n > 0\}$.
Dimostrare che L non è C.F..

L libero $\implies\exists p\in N \ \forall z\in L |z|>p$
 1. $|vwx| \leq p$
 2. ($vx \neq \lambda$)
 3. $\forall i, \ i\geq 0: uv^iwx^iy \in L$

Studiamo una stringa z $\in$ L $|z|>p$ (scegliendo la stringa con lunghezza maggiore di p più comoda per i calcoli)
$z = a^pb^pc^p \implies |z| = 3p>p$ 
$$\underbrace{a\dots a}_{\text{p}} \underbrace{b\dots b}_{\text{p}} \underbrace{c\dots c}_{\text{p}}$$
In questa stringa abbiamo un p numero di a, un p numero di b ed un numero p di c.

Casi:
1. vwx formato solo da a
2. vwx formato solo da b
3. vwx formato solo da c
4. vwx formato a cavallo tra a e b
5. vwx formato a cavallo tra b e c
6. vwx non può contenere a b e c, poichè non sufficientemente lunga

Caso 1:
Prendiamo una stringa a caso (quella più semplice)
	$uv^2wx^2y$
Prendendo la stringa pompata, possiamo aggiungere solo delle a.
Ora, il numero di a aumenta: $p+1\leq \#(a) \leq p+p$. Tuttavia il numero di c e b rimane invariato, il che non rispecchia le regole  del linguaggio. Quindi $uv^2wx^2y \not\in L \text{ poichè } \#(a) \neq \#(b) \neq \#(c)$ 

Caso 2 e 3:
Stessa cosa del caso 1, ripetuto però con le b e con le c.

Caso 4:
il punto vwx è a cavallo tra a e b.
	Caso 4.1: $v\neq \lambda \ x=\lambda$
		$v \neq \lambda \implies \text{ v contiene solo delle a}$, il che vuol dire che $wx = ab\dots b$. Pompando andremmo ad aumentare solo il numero delle a (non delle b poichè dovrebbero essere contenute nelle x, il quale è però vuoto). Anche in questo caso quindi avremmo un numero di a pari a: $p+1\leq \#(a) \leq p + p -1$ (p-1 poichè almeno una a è contenuta nelle w). Quindi $uv^2wx^2y \not\in L \text{ poichè } \#(a) \neq \#(b) \neq \#(c)$ 
	Caso 4.2: $v = \lambda \ x \neq \lambda$
		$x \neq \lambda \implies \text{ x contiene solo delle b}$.  In questo caso quindi avremmo un numero di b pari a: $p+1\leq \#(b) \leq p + p -1$ (p-1 poichè almeno una b è contenuta nelle w). Quindi $uv^2wx^2y \not\in L \text{ poichè } \#(a) \neq \#(b) \neq \#(c)$
	Caso 4.3: $v \neq \lambda \ x \neq \lambda$
		$v \neq \lambda \quad x \neq \lambda \implies \text{ v contiene solo delle v e x contiene solo delle b}$.  In questo caso quindi avremmo un numero di b pari al numero a: $p+1\leq \#(b) = \#(a) \leq p + p -1$ (p-1 poichè almeno una b è contenuta nelle w). Quindi $uv^2wx^2y \not\in L \text{ poichè } \#(a) \wedge \#(b) \neq \#(c)$

Caso 5:
Analogo al caso 4.

---

Sia L il linguaggio $L = \{a^{n^2} \text{ con } n \geq 0\}$.
$L = \{ \lambda, a, a^4, a^9, a^{16}, \dots\}$

Per assurdo L libero $\implies$
- $\exists p \in \mathbb{N} \quad \forall z \in \quad L |a|>p \quad z = uvwxy$
1. $|vwx| \leq p$
2. $vx \neq \lambda$
3. $\forall i, \ i\geq 0: uv^iwx^iy \in L$

Prendiamo in considerazione la stringa: $z = a^{p^2} \implies |z| = p^2 > p$

Caso 1: $vwx$ formato solo da a
$uv^2wx^2y \in L \text{?} \quad p+1 \leq \#(a) \leq p + p$
$L = \{ \lambda, a, a^4, a^9, a^{16}, \dots\, a^{p^2}, a^{(p+1)^{2}}\}$

$|uvwxy| < |uv^2wx^2y| = |\underline{uv}v\underline{wx}x\underline{y}| = |uvwxy| + |vx| = ||$ [PORCODDIO CONTINUA]

---

Sia $L = \{a^ib^jc^k \quad i>j>k>0 \implies \#(a)>\#(b)>\#(c)>0\}$.

Parole del linguaggio $L = \{a^3b^2c,a^4b^3c^2,a^4b^2c,a^5b^4c^3,\dots\}$

Per assurdo L libero $\implies$
- $\exists p \in \mathbb{N} \quad \forall z \in \quad L |a|>p \quad z = uvwxy$
1. $|vwx| \leq p$
2. $vx \neq \lambda$
3. $\forall i, \ i\geq 0: uv^iwx^iy \in L$

Consideriamo la stringa: $z = a^{p+2}b^{p+1}c^{p} \quad |z| = 3p + p>p$

Caso 1: vwx formata solo da a
Caso 2: vwx formata solo da b
Caso 3: vwx formata solo da c
Caso 4: vwx formata a cavallo tra a e b
Caso 5: vwx formata a cavallo tra b e c

[GUARDA FOTO E COMPLETA]


Come fare il pumping lemma:

$p$ è la costante per la lunghezza della parola presa a caso, $p$ deve essere più piccola di $uvwxy$ e deve essere più grande o pari di $vwx$

Le casistiche le prendiamo al linguaggio formato