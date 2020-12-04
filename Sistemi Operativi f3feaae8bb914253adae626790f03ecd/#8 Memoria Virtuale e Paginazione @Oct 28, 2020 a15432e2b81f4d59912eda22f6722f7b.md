# #8. Memoria Virtuale e Paginazione @Oct 28, 2020

# Memoria Virtuale

La memoria virtuale è uno schema di allocazione di memoria in cui la secondaria viene usata come quella principale.
La dimensione della memoria virtuale è limitata dalle dimensioni della secondaria.

La memoria principale non influisce sulla memoria virtuale durante l'esecuzione e questo perché un processo può essere trasferito da una memoria all'altra (da principale a secondaria e viceversa).

Il servizio di traduzione automatica a far sì che non tutte le pagine debbano essere caricate in memoria principale

Il vantaggio di usare una memoria virtuale è che il processore non è idle: infatti più processi possono essere caricati in memoria contemporaneamente garantendo che il processore lavori in continuazione

Residence set: insieme dei pezzi del programma che si trovano in memoria principale

## THRASHING

Un processo usa talmente tanta memoria che avviene sempre un page fault (esempio di overhead inaccettabile).
Per ovviare a questo problema sistema operativo cerca di indovinare quali pagine servono basandosi sul principio di località -> i riferimenti al processo tendono ad essere sempre vicini

---

# Paginazione

Tecnica attraverso la quale il sistema operativo, usando gli algoritmi di paging, suddivide la memoria in parti di dimensioni minori, e la alloca al programma da eseguire usando pagine come blocco minimo di lavoro.

Ogni processo ha una sua tabella: il pcb punta a questa tabella

Più piccola è una pagina, minore sarà la frammentazione e quindi parte delle tabelle finisce memoria secondaria.

Le moderne architetture possono supportare diverse dimensioni delle pagine

Possono esserci più tabelle delle pagine: occupo meno spazio

Per migliorare ulteriormente la cosa esiste la TLB, memoria temporanea per le traduzioni future punto.
Ogni riferimento alla memoria virtuale può generare due accessi

- elemento tabelle delle pagine
- dato

La TLB contiene proprio quegli elementi delle pagine e si basa sulla logica LRU (Last Recent Used)

Hit or miss -> pagina presente -> indirizzo reale

Mapping associativo: la tlb ha solo alcuni elementi, motivo per cui non posso usarla come indice. Il numero di pagina va cercato quindi