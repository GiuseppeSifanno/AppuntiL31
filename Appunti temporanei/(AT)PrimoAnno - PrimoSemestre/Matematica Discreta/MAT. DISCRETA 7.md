# INDUZIONE

# Cos’è l’induzione (in parole semplici)**
L’induzione è un modo per dimostrare che una proprietà P(n) è vera per tutti gli interi $n\ge n_0.$ Si fanno due cose:
1. **Base**: dimostrare che $P(n_0)$ è vera (di solito $n_0=1$).
2. **Passo induttivo**: assumere che $P(n)$ sia vera per un generico n (questa è l’**ipotesi induttiva**) e usare questa ipotesi per dimostrare $P(n+1)$.
    Se riesci, allora la proprietà vale per $n_0$, per $n_0+1$, per $n_0+2$, ecc. — cioè per tutti.

**Esercizio:** Dimostrare per induzione che per ogni $n\in\mathbb{N}, n\ge1,$
$\sum_{k=1}^n k^3 = \frac{1}{4} n^2 (n+1)^2.$

## **Approccio**

Si riconosce la nota identità $\sum k^3 = \big(\sum k\big)^2: infatti \sum_{k=1}^n k = \frac{n(n+1)}{2}$ e elevando al quadrato si ottiene la formula. Qui però chiedono _per induzione_ quindi si fa il classico passo base + passo induttivo.
  
Calcoliamo per piccoli n per vedere la relazione.
- n=1: sinistra =$1^3=1.$ Destra $\frac14\cdot1^2\cdot2^2=\frac14\cdot1\cdot4=1.$ OK.
- n=2: sinistra =$1^3+2^3=1+8=9.$ Destra $-\frac14\cdot2^2\cdot3^2=\frac14\cdot4\cdot9=9$ OK.
- n=3: sinistra =1+8+27=36. Destra $\frac14\cdot9\cdot16=\frac{144}{4}=36.$ OK.

## **Passo 1 — Base (n=1**)**
Per $n=1$:

$\sum_{k=1}^1 k^3 = 1^3 = 1, \qquad \frac{1}{4}\cdot 1^2\cdot(1+1)^2 = \frac{1}{4}\cdot1\cdot 2^2 = \frac{1}{4}\cdot4 = 1.$

Quindi $P(1)$ è vera.

## **Passo 2 — Ipotesi induttiva**
Supponiamo che per un generico $n\ge1$ valga

$\sum_{k=1}^n k^3 = \frac{1}{4} n^2 (n+1)^2.$
Questa è la nostra **ipotesi**: la usiamo per ricavare la formula per n+1.

## **Passo 3 — Dimostrare** P(n+1)
Scriviamo la somma fino a n+1 come somma fino a n più l’ultimo termine:
$\sum_{k=1}^{n+1} k^3 = \left(\sum_{k=1}^n k^3\right) + (n+1)^3.$

Scriviamo la somma fino a n+1 come somma fino a n più l’ultimo termine:
$\sum_{k=1}^{n+1} k^3 = \left(\sum_{k=1}^n k^3\right) + (n+1)^3.$

Ora sostituiamo l’ipotesi induttiva (la prima parte) con la sua espressione:
$\sum_{k=1}^{n+1} k^3 = \frac{1}{4} n^2 (n+1)^2 \;+\; (n+1)^3.$
  

Adesso dobbiamo trasformare questa espressione nella forma prevista con n+1:
$\text{desideriamo ottenere } \frac{1}{4}(n+1)^2(n+2)^2.$

Procediamo con i passaggi algebrici, **uno per volta**:
 Metti in evidenza il fattore comune $(n+1)^2$ (compare in entrambe le addendi, perché $(n+1)^3=(n+1)^2\cdot(n+1)):$
    
    $\frac{1}{4} n^2 (n+1)^2 + (n+1)^3 = (n+1)^2\left(\frac{1}{4}n^2 + (n+1)\right).$
    
Sommiamo dentro la parentesi i termini $\frac{1}{4}n^2 e n+1$. Per sommarli, portiamo n+1 allo stesso denominatore (4):
    $n+1 = \frac{4(n+1)}{4} = \frac{4n+4}{4}.$
    
Osserva che n^2+4n+4 è un quadrato perfetto:
    $n^2+4n+4 = (n+2)^2.$
    
Quindi
	$\frac{n^2 + 4n + 4}{4} = \frac{(n+2)^2}{4}.$
    
4. Sostituisci questo nella fattorizzazione:
	$\sum_{k=1}^{n+1} k^3 = (n+1)^2\cdot \frac{(n+2)^2}{4} = \frac{1}{4}\,(n+1)^2 (n+2)^2.$
    
Questo è esattamente la formula P(n+1). Quindi, a partire dall’ipotesi induttiva, abbiamo ottenuto la formula per n+1.
## **Conclusione**
Abbiamo verificato la base P(1), e abbiamo mostrato che $P(n)\Rightarrow P(n+1)$. Per il principio di induzione, la formula è vera per ogni $n\ge1.$



Esempio di traccia Fornito da dott. Milo: 
![[WhatsApp Image 2025-09-15 at 20.00.10.jpeg]]
![[WhatsApp Image 2025-09-15 at 20.00.15.jpeg]]