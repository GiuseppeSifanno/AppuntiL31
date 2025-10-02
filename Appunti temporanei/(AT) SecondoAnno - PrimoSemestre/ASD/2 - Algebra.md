## **Astrazione funzionale**
Un **algoritmo** trasforma dati di input in dati di output. In questo modo definisce **nuovi operatori**.
Con l’astrazione funzionale si può **ampliare il repertorio di operatori** sui dati scrivendo nuovi sottoprogrammi.

**Esempio del coefficiente binomiale**:
- Formula matematica: $\binom{n}{k} = \frac{n!}{k!(n-k)!}.$
- Se esiste già un operatore **Fatt(i)** (fattoriale), il calcolo è immediato.
- Se Fatt non esiste, si deve implementare un sottoprogramma, questa è l’astrazione funzionale.

### **Come funziona nei linguaggi:**
I linguaggi ad alto livello permettono di creare **unità di programma** (funzioni o procedure). 
Quando una funzione viene chiamata:
    1. L’esecuzione del chiamante si sospende.
    2. Il controllo passa al sottoprogramma.
    3. Al termine, il controllo torna al programma chiamante.

  
### **Specifica e realizzazione:**
- **Specifica**: descrive _cosa fa_ la funzione.
    - Esempio: int Fatt(int k)
        - Input: numero intero k
        - Output: intero k!
        
- **Realizzazione**: descrive _come lo fa_.
    - Può esserci più di una realizzazione:
- **Iterativa**:
```c
Fatt(int k)
  f = 1
  for i = 2 to k do
      f = f * i
  return f
```

- **Ricorsiva**:
```c
Fatt(int k)
  if k = 1 then f = 1
  else f = k * Fatt(k-1)
  return f
```

## **Astrazione di dati**
L’astrazione di dati **estende il concetto di astrazione funzionale**.
**Differenze:**
- L’astrazione funzionale amplia i **modi di operare sui dati**, cioè aggiunge nuovi operatori.
- L’astrazione di dati amplia i **tipi di dati disponibili**, cioè introduce nuove strutture di dati e i relativi operatori.

 **Definizione:**
- Un’astrazione di dati consente di **estendere l’algebra dei dati** di un linguaggio di programmazione.

**Cos’è un’algebra**: è un sistema matematico formato da:
1. **Un dominio**: l’insieme di valori.
2. **Un insieme di funzioni**: operazioni applicabili su quei valori.
C’è una corrispondenza diretta:
- Dominio dell’algebra ↔ insieme di valori del tipo astratto.
- Funzioni dell’algebra ↔ operazioni del tipo astratto.

### **Tipi di dati astratti (ADT):**
Un tipo di dato è detto **astratto** quando le **operazioni disponibili sugli oggetti** che lo rappresentano sono **separate** dai dettagli di realizzazione.
In pratica:
- L’utente sa _cosa può fare_ con quel tipo (operazioni disponibili).
- L’utente non deve sapere _come_ il tipo è implementato.

Esempio intuitivo: con un “numero intero” in un linguaggio di programmazione, l’utente lo usa per sommare, sottrarre, moltiplicare ecc., senza dover sapere come il linguaggio rappresenta internamente quell’intero (binario, registri, ecc.).


# Esempi di astrazione

### **Numeri complessi**
- I numeri complessi hanno la forma:
    $c = r_1 + i r_2$
    dove:
    - $r_1$ = parte reale
    - $r_2$ = parte immaginaria
    - $i = \sqrt{-1}$
    
Matematicamente possono essere rappresentati come una **coppia ordinata ($r_1, r_2$)**.

### **Operatori necessari:**

- **Operatori di costruzione e selezione**:
    - conscx($r_1, r_2$) → costruisce un numero complesso a partire da due reali.
    - realpart(c) → estrae la parte reale.
    - immgpart(c) → estrae la parte immaginaria.
    
- **Operatori di calcolo**:
    - Somma:
        parteReale(c3) = parteReale(c1) + parteReale(c2) parteImmg(c3) = parteImmg(c1) + parteImmg(c2)
        
    - Prodotto:
        parteReale(c3) = $r1_1 \cdot r1_2 - r2_1 \cdot r2_2$ 
        parteImmg(c3) = $r1_1 \cdot r2_2 + r2_1 \cdot r1_2$


Dunque servono funzioni come:
- cxsum(c1, c2) = somma
- cxprod(c1, c2) = prodotto

### **Realizzazione nei linguaggi 
- **Fortran**:
    - Supporta **astrazione funzionale** (subroutine), ma **non astrazione di dati**.
    - I numeri complessi si possono rappresentare come vettori di 2 reali:
```c
dimension c1(2), c2(2), c3(2)
```

- Problema: qualunque vettore di 2 reali può essere passato agli operatori → **manca protezione**.
    
- **Pascal**:
    - Supporta tipi definiti dall’utente → quindi consente astrazione dati.
    - Possibili dichiarazioni:
```c
TYPE COMPLEX = ARRAY [1..2] OF REAL;
```
- oppure con record:
```c
TYPE COMPLEX = RECORD
    PARTE_REALE : REAL;
    PARTE_IMMAGINARIA : REAL;
END;
```


## **Astrazione di dati**
- Se abbiamo un linguaggio che supporta i **tipi**, possiamo:
    1. **Usare direttamente i nuovi dati** come se fossero primitivi (es. variabili di tipo COMPLEX).
    2. **Limitare l’accesso agli operatori** costruiti per quel tipo → cioè solo le variabili di quel tipo possono usare gli operatori.

 Queste caratteristiche rappresentano i **requisiti fondamentali** dell’astrazione di dati.

## **Requisito di astrazione**
- **Definizione**: il requisito di astrazione è rispettato se i programmi che usano un tipo astratto non dipendono dalla sua **realizzazione interna**.
    - L’utente usa le operazioni del tipo, senza preoccuparsi di come il tipo è implementato.

**Esempio**:
- In Pascal posso definire COMPLEX sia come ARRAY che come RECORD.
- Se il requisito di astrazione è rispettato, le intestazioni delle procedure (SOMMACOMPLESSI, PRODOTTOCOMPLESSI, ecc.) non cambiano.

**Se manca il requisito**:
- Non è possibile dichiarare direttamente variabili del nuovo tipo.
- Bisogna sempre “conoscere” la rappresentazione interna.
- Esempio: in Fortran, i numeri complessi come dimension c(2) non permettono vera astrazione → ogni volta bisogna sapere che il primo elemento è la parte reale e il secondo quella immaginaria.

## **Requisito di protezione**
- **Definizione**: il requisito di protezione è rispettato se i dati astratti possono essere usati **solo tramite gli operatori definiti** per essi.

**Esempio**:
- In Fortran, un sottoprogramma per la somma dei complessi accetta qualunque vettore di due reali, anche se non rappresenta un complesso.
    → Qui **manca la protezione**, perché non c’è distinzione tra un “vero numero complesso” e una coppia qualsiasi di reali.

Se il requisito è rispettato:
- Solo le variabili del tipo COMPLEX possono accedere agli operatori cxsum, cxprod, ecc.
- Non è possibile usare tali operatori su altri dati (es. vettori generici di due reali).

## **Importanza dei requisiti**
- **Requisito di astrazione**:
    - I programmi devono dipendere solo dalla **specifica del tipo**, non dalla realizzazione concreta.
    - In questo modo, se cambia l’implementazione interna, i programmi che usano il tipo astratto non devono essere modificati.
        
- **Requisito di protezione**:
    - Garantisce che ci sia coerenza tra dati e operatori.
    - Il controllo di consistenza (compatibilità tra tipo e operazioni) non deve valere solo per i **tipi primitivi**, ma anche per i **tipi astratti**.
    - Senza protezione si rischiano errori logici o accessi impropri.