# ALBERI

### **Che cos’è un albero (in teoria dei grafi)**
- Un **grafo** è un insieme di **vertici (o nodi)** collegati da **archi (o linee)*. 
- Un **albero** è un grafo che soddisfa due condizioni:
    1. **È connesso**: da ogni vertice puoi raggiungere qualunque altro seguendo gli archi.
    2. **Non ha cicli**: non puoi fare un giro chiuso tornando al punto di partenza senza ripassare da un arco.
Esempio visivo (un albero con 5 vertici):
    
```
    A
   / \
  B   C
     / \
    D   E
```
## **Proprietà fondamentali di un albero**
Ci sono due regole molto importanti che **valgono sempre**:
 **Numero di archi**
    Un albero con n vertici ha sempre **esattamente** n-1 **archi**.
    - Esempio: se hai 5 vertici, gli archi sono 4.
    - Se ne avessi di più, comparirebbe almeno un ciclo.
    - Se ne avessi di meno, non sarebbe connesso.

**Cos’è il grado di un vertice**
Il **grado** (o valenza) di un vertice è **quanti archi incidono su quel vertice**.
Non è “1 arco per vertice in generale”, ma dipende proprio da quanti collegamenti ha quel vertice.
Esempio: se un vertice è collegato ad altri 3, il suo grado è 3.
Se è una foglia (cioè tocca un solo arco), il suo grado è 1.

```
    A
   /
  B
   \
    C
     \
      D
       \
        E
```
 Contiamo i gradi:
- A ha **1 arco** (collegato solo a B) → grado 1
- B ha **2 archi** (uno verso A, uno verso C) → grado 2
- C ha **2 archi** (uno verso B, uno verso D) → grado 2
- D ha **2 archi** (uno verso C, uno verso E) → grado 2
- E ha **1 arco** (collegato solo a D) → grado 1

Quindi i gradi sono: 1,2,2,2,1.
La somma è:
		1+2+2+2+1 = 8



**Somma dei gradi dei vertici**
 - Il **grado (o valenza)** di un vertice è quanti archi partono da quel vertice.
        (es. nell’albero sopra: A ha grado 2, B grado 1, C grado 2, D grado 1, E grado 1).
 - C’è un teorema detto **stretta di mano**:        
        $\sum \text{gradi dei vertici} = 2 \cdot |E|$
        cioè la somma dei gradi è il doppio del numero di archi.
- Motivo: ogni arco tocca 2 vertici, quindi conta “2 gradi”.


Definizione: di **Isomorfo**
Due alberi sono detti isomorfi se sono essenzialmente lo stesso albero, ma con etichette diverse o disegnati in modo diverso. Più formalmente, sono isomorfi se esiste una corrispondenza uno-a-uno tra i loro nodi (vertici) che preserva le connessioni (archi) e la struttura dell'albero, ovvero i nodi adiacenti in un albero devono essere adiacenti anche nell'altro.

---

# **Algoritmo generale per verificare l’esistenza di un albero con gradi prefissati**

**Input:**
- n = numero di vertici
- Lista dei gradi dei vertici: $d_1, d_2, \dots, d_n$

**Output:**
- “L’albero esiste” / “L’albero non esiste”

### **Step 1: Controllo del numero di archi**

Formula:

$|E| = n - 1$
dove $|E|$ = numero di archi.
### **Step 2: Controllo della somma dei gradi (Handshake Lemma)**
Formula generale:

$\sum_{i=1}^{n} d_i = 2 \cdot |E| = 2 \cdot (n-1)$

**Se la somma dei gradi non è uguale a** $2(n-1)$ → l’albero **non può esistere**.
**Altrimenti** → continua.

### **Step 3: Controllo delle foglie e dei vertici interni**
- Definizioni:
    - **Foglie**: vertici di grado 1 → numero $L = |\{ i : d_i = 1 \}|$
    - **Vertici interni**: vertici di grado ≥ 2 → numero $I = |\{ i : d_i \ge 2 \}|$
        
- Controllo necessario:
    Ogni foglia deve essere collegata ad almeno un vertice interno.
    Formula minima di plausibilità:

    $I \ge 1 \quad \text{e} \quad \sum_{i \in \text{interni}} d_i \ge L + (I-1)$    
    - $\sum d_i$ degli interni ≥ numero di foglie + archi interni necessari per collegare i vertici interni fra loro (I-1).
    - Se non vale → albero **non esiste**.
		
### **Step 4: Check finale**
Se tutti i controlli sono soddisfatti:
- Numero archi corretto: $|E| = n-1$
- Somma dei gradi corretta: $\sum d_i = 2(n-1)$
- Foglie correttamente sostenute dai vertici interni: $\sum d_{\text{interni}} \ge L + (I-1)$

→ Allora **l’albero esiste**.
Altrimenti → **non esiste**.

### **Step 5: Preparazione al disegno**

Se l’albero esiste:
1. Ordina i vertici per grado decrescente.
2. Inizia dai vertici di grado massimo come “nodi principali”.
3. Distribuisci i vertici interni e poi le foglie, seguendo i gradi richiesti.
4. Alla fine controlla che:
    $\forall i: \text{grado}_i = d_i e numero archi = n-1.$


---

# Rappresentazione di un albero:
Quando ti chiedono di **rappresentare un albero con una certa distribuzione di gradi**, non esiste un “unico disegno preciso” da seguire. L’importante è che:

1. **Ordina i vertici**
    - Dividi i vertici in due gruppi:
        - **Vertici interni**: grado ≥ 2
        - **Foglie**: grado = 1
    
2. **Controllo preliminare**:
    - Verifica la somma dei gradi:
        $\sum \text{gradi} = 2 \cdot (n-1)$
        Se non è così, **l’albero non esiste**.
        
3. **Scegli il “vertice principale”**
    - Prendi uno dei vertici di grado massimo come radice provvisoria (puoi metterlo in alto).
        
4. **Attacca i vertici interni**
    - Collega i vertici interni fra loro in modo da distribuire i gradi:
        - Un vertice di grado 4 deve avere 4 archi in totale.
        - Ogni arco può andare verso un altro vertice interno o verso una foglia.
                
5. **Attacca le foglie**
    - Collega ciascuna foglia a un vertice interno che **ha ancora “posti liberi”** (cioè il grado attuale è minore del grado richiesto).
    - Evita di collegare foglia a foglia → altrimenti il grado cambia e non saranno più foglie.
        
6. **Verifica i gradi**
    - Dopo aver collegato tutto, conta i gradi di ogni vertice.
    - Devono coincidere **esattamente** con quelli richiesti.
        
7. **Assicurati che sia un albero**
    - Controlla che:
        - Non ci siano cicli (non chiudere mai un giro completo),
        - Tutti i vertici siano collegati (nessun vertice isolato),
        - Numero di archi = n−1
                
8. **Variante per non isomorfi**
    - Per creare un secondo albero diverso: cambia **l’ordine dei collegamenti** tra i vertici interni, oppure cambia quali foglie si collegano a quale vertice interno.

---

Esercizi d'esempio fornito da Dott. Sblendorio:
![[WhatsApp Image 2025-09-15 at 17.39.20.jpeg]]