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