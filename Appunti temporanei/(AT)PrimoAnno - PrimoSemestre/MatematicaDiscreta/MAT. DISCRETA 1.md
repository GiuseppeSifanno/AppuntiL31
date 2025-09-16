# Simboli e significato 

# DEFINIZIONI

### **PROPOSIZIONE**
Una proposizione è una affermazione che è o vera o falsa, ma non può essere contemporaneamente vera e falsa. 

Per esempio:
- Londra si trova in Europa. 
- Madrid è la capitale d'italia. 
- 3+3=8
- 8-4=4

Le affermazioni che non sono proposizioni sono:
- Che ore sono?
- Mostrami quello che hai scritto. 
- Che bella musica. 
- x + 6 = 1 (non è nè vera nè falsa, perchè non sappiamo il valore di x). 
- Tutti i giorni in estate piove almeno due ore. (Non possiamo dire se questa affermazioni sia vera o falsa. Perchè è possibile che in certe parti della terra in estate piove almeno 2 ore)
	- per esempio se trasformassimo la frase in: *in qualche parte della terra piove alemeno 2 ore* la proposizione risulta vera. 
	- oppure: *a Roma tutti i giorni in estate piove almeno due ore*, allora diventerebbe una proposizione falsa. 

Le proposizioni si indicano generalmente con le lettere dell'alfabeto: p, q, r, s, t, ecc. 

### **Negazione di una proposizione**
Se abbiamo una proposizione p, possiamo costruire una nuova proposizione chiamata **negazione di** p e si indica con:
		$\neg p$
- Si legge: **“non** p”
- Significa: **non è vero che** p.

Sia p la proposizione:
	*Ieri abbiamo battuto gli avversari.*
La sua negazione è la proposizione:
	$\neg p$: Non è vero che ieri abbiamo battuto gli avversari. 
Cioè la proposizione:
	*Ieri non abbiamo battuto gli avversari.*
	
### **Quantificatore esistenziale**
- **Forma:** $\exists x \; P(x)$
- **Significato:** Esiste almeno un valore di x per cui P(x) è vero.
- **Esempio:**
    - $P(x):\; x^2 = 4$
    - $\exists x \; (x^2 = 4)$ significa “esiste almeno un numero il cui quadrato è 4”.
    - È **vero**, perché x = 2 e x = -2 soddisfano la proprietà.
    
### **Quantificatore universale**
- **Forma:** $\forall x \; P(x)$
- **Significato:** Per ogni valore di x, P(x) è vero.
- **Esempio:**
    - $P(x):\; x^2 \geq 0$
    - $\forall x \; (x^2 \geq 0)$ significa “per ogni numero reale, il suo quadrato è maggiore o uguale a zero”.
    - È **vero**, perché qualunque numero prendi, il quadrato non è mai negativo.

### **OPERATORE DI CONGIUNZIONE**
Siano p e q due proposizioni. 
La proposizione "p e q" si denota con p $\vee$ q ed è vera quando entrambe p e q sono vere, falsa altrimenti, ossia quando una almeno delle due proposizioni è falsa. 

È **vera solo se entrambe** le proposizioni sono vere; è **falsa** se almeno una delle due è falsa.
**Esempio:**
- p: “Oggi piove”
- q: “Porto l’ombrello”
- p $\wedge$ q: “Oggi piove **e** porto l’ombrello”.
    - Se piove e porto l’ombrello → **vero**
    - Se piove ma non porto l’ombrello → **falso**
    - Se non piove ma porto l’ombrello → **falso**
    - Se non piove e non porto l’ombrello → **falso**

### **OPERATORE DI DISGIUNZIONE**
Siano p e q due proposizioni. 
La proposizione "p o q" si denota con p $\wedge$ q ed è falsa quando entrambe p e q sono false, vera altrimenti, ossia quando almeno una delle due proposizioni è vera. 

È **falsa solo se entrambe** le proposizioni sono false; è **vera** se almeno una delle due è vera.
**Esempio:**
- p: “Oggi piove”
- q: “Porto l’ombrello”
- p $\vee$ q: “Oggi piove **oppure** porto l’ombrello”.
    - Se piove e porto l’ombrello → **vero**
    - Se piove ma non porto l’ombrello → **vero**
    - Se non piove ma porto l’ombrello → **vero**
    - Se non piove e non porto l’ombrello → **falso**

### **IMPLICAZIONE LOGICA**
Siano p e q due proposizioni. 
L'implicazione si scrive
			p $\Rightarrow$ q
Si legge: **“se** p, allora q”. 
- **Ipotesi**: p (la condizione di partenza)
- **Conclusione/Tesi**: q (ciò che deve seguire)

È possibile anche pensarla in altri modi:
- p è condizione sufficiente di q. 
- q è condizione necessaria per p. 

È **falsa solo** se p è vera **e** q è falsa.
In tutti gli altri casi, è **vera**.
Esempio pratico
- p: “Piove”
- q: “Porto l’ombrello”
L’implicazione p $\Rightarrow$ q: “Se piove, allora porto l’ombrello”.
- Se piove e porto l’ombrello → **vero**
- Se piove e non porto l’ombrello → **falso** (qui l’implicazione crolla)
- Se non piove e porto l’ombrello → **vero**
- Se non piove e non porto l’ombrello → **vero**

### PROPOSIZIONE PRIMITIVA e COMPOSTA
Una proposizione si dice primitiva se non si può spezzare in proposizioni più semplici mediante connettivi logici. 
Una proposizione non primitiva si dice composta. 

Per esempio la proposizione: 
*"Giovanni è alto e ha vinto la gara"* non è una proposizione primitiva, perchè si può scrivere come congiunzione delle due proposizioni. 
p: *Giovanni è alto*
q: Giovanni ha vinto una gara 
Ossia:
			$p \wedge q$
Invece la proposizione: *"Giovanni ha studiato"* è primitiva. 

### TAUTOLOGIA E CONTRADDIZIONE
Una proposizione composta che è sempre vera, indipendentemente dal valore di verità delle proposizioni da cui è composta, prende il nome di *tautologia.*
Esempio: La $p \vee \neg p$ è un esempio di tautologia, dato che, qualunque sia $p$, o $p$ o $\neg p$ è sicuramente vera, quindi $p \vee \neg p$ è sempre vera. 

Una proposizione composta che è sempre falsa prende il nome di *contraddizione*.
Esempio: La $p \wedge \neg p$ è un esempio di contraddizione, dato che, qualunque sia $p$ e $\neg p$  non possono essere contemporaneamente vere, quindi la $p \wedge \neg p$ è sempre falsa. 

Due proposizioni $p$ e $q$ si dicono *logicamente equivalenti* se $p$ è vera (o falsa) se e solo se $q$ è vera (o falsa). 

Ad ogni proposizione possiamo associare un valore di verità rispettivamente attraverso dei simboli: T e F con T vera e F falsa. 

### TAVOLE DI VERITA'

Possiamo costruire le tavole di verità. 
Per esempio sappiamo che la negazione $\neg p$ di una proposizione $p$, sappiamo che essa è falsa quando $p$ è vera e viceversa. 
La sua tavola corrisponde:


| $p$ | $\neg p$ |
| --- | -------- |
| T   | F        |
| F   | T        |

La tavola di verità che corrisponde alla proposizione di congiunzione e disgiunzione è la seguente:

| $p$ | $q$ | $p \wedge q$ | $p \vee q$ |
| --- | --- | ------------ | ---------- |
| T   | T   | T            | T          |
| T   | F   | F            | T          |
| F   | T   | F            | T          |
| F   | F   | F            | F          |

Dalle tavole di verità è possibile controllare per esempio due proposizioni logicamente equivalenti. 
Per verificare prendiamo due proposizioni:
			$\neg (p \wedge q)$ e $\neg p \vee \neg q$
Queste due proposizioni solo logicamente equivalenti. 
Possiamo verificare attraverso la tavola di verità:

| $p$ | $q$ | $\neg p$ | $\neg q$ | $p \vee q$ | $\neg (p \wedge q)$ | $\neg p \vee \neg q$ |
| --- | --- | -------- | -------- | ---------- | ------------------- | -------------------- |
| T   | T   | F        | F        | T          | F                   | F                    |
| T   | F   | F        | T        | F          | T                   | T                    |
| F   | T   | T        | F        | F          | T                   | T                    |
| F   | F   | T        | T        | F          | T                   | T                    |


Un'altro esempio di proposizione logicamente equivalente è la seguente:
			$p \Rightarrow q$ e $(\neg p) \vee q$
La tavola si svolge come si segue:

| $p$ | $q$ | $\neg p$ | $p \Rightarrow q$ | $(\neg p) \vee q$ |
| --- | --- | -------- | ----------------- | ----------------- |
| T   | T   | F        | T                 | T                 |
| T   | F   | F        | F                 | F                 |
| F   | T   | T        | T                 | T                 |
| F   | F   | T        | T                 | T                 |

Esempio di traccia:
$\neg (P \wedge Q) \equiv \neg P \vee \neg Q$

| P   | Q   | P ∧ Q | ¬(P ∧ Q) | ¬P  | **¬Q** | **¬P ∨ ¬Q** |
| --- | --- | ----- | -------- | --- | ------ | ----------- |
| V   | V   | V     | F        | F   | F      | F           |
| V   | F   | F     | V        | F   | V      | V           |
| F   | V   | F     | V        | V   | F      | V           |
| F   | F   | F     | V        | V   | V      | V           |

