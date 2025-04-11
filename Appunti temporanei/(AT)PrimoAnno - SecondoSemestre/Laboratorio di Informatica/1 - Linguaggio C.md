## Padding
Il padding è una tecnica utilizzata per allineare i dati in memoria, tramite l'inserimento di uno o più byte (indirizzi) vuoti, inseriti  (o lasciati vuoti) a loro volta tra gli indirizzi di memoria assegnati per gli altri membri della struttura durante l'allocazione della memoria. L'architettura di un processore del computer è tale da poter leggere 1 word (4 byte nel processore a 32 bit) dalla memoria alla volta.
Per sfruttare questo vantaggio del processore, i dati sono sempre allineati come un pacchetto da 4 byte che porta a inserire indirizzi  vuoti tra l'indirizzo di un altro membro, portando un occupazione diversa di byte a seconda dell'ordine di dichiarazione


In linguaggi come C il padding viene aggiunto automaticamente dal compilatore per allineare i dati in memoria. Ad esempio:
```c
struct Esempio {
    char a;      // 1 byte
    int b;       // 4 byte
    short c;     // 2 byte
};
```

Una struttura comunque ha un valore diverso di byte a seconda dell'ordine in cui viene dichiarata