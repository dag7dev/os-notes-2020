# #7. Scheduling in Linux - Gestione della memoria - Partizionamento @Oct 26, 2020

# Scheduling in Linux

Tipi di processi:
- interattivi: shell, gui
- non interattivi: compilazioni, computazioni
- real time: quelli usati dai klt di sistema klt vuol dire kernel Linux thread

Tipi di scheduling:
- sched_fifo da 1 a 99
- sched_rr da 1 a 99
- sched_other da 100 139
Un processo sched_fifo viene non solo Pre-empted ma anche rimesso in coda solo se

- si blocca per input output
- un altro processo va da blocked a running con priorità più alta

sched_rr: quarti di tempo
sched_rt: mai,
sched_other: simile a unix tradizionale

## Gestione della memoria

Le moderne applicazioni richiedono il quantitativo di memoria sempre maggiore. si potrebbero imporre dei limiti ma ciò impatterebbe molto sul programmatore.
Il sistema operativo gestisce la memoria, e ai processi dà l'illusione che abbiano tutti la stessa quantità di memoria disponibile. In realtà non è vero, perché la gestisce il sistema operativo (il programmatore non sa come viene gestita).

### Requisiti: rilocazione, protezione, condivisione, organizzazione fisica, organizzazione logica

- rilocazione: il programmatore non sa e non deve sapere In quale zona della memoria il programma viene caricato. i riferimenti alla memoria devono essere tradotti indirizzo fisico vero

    Gli indirizzi possono essere:
    - logici: il riferimento memoria e indipendente dell'attuale posizionamento del programma in memoria
    - relativi: uno spiazzamento rispetto ad un qualche punto noto
    - fisici o assoluti due punti di riferimento effettivo alla memoria

    Registri usati:
    - base: partenza del processo
    - bound: fine
    I valori per questi registri vengono settati nel momento in cui il processo viene posizionato in memoria e quindi serve aiuto Hardware

- protezione: i processi non devono poter accedere allocazione di memoria. a causa di una rilocazione non si può fare a livello di compilazione ma di Runtime e quindi serve una mano a livello Hardware
- condivisione: possibilità dei processi di condividere la stessa zona di memoria esempio fork
- organizzazione logica: a livello hardware organizzati in modo lineare sequenziale a livello software organizzato in moduli
- organizzazione fisica: il sistema operativo deve fare da Ponte tra queste due organizzazioni gestione da RAM a memoria secondaria e viceversa

## PARTIZIONAMENTO

uno dei primi metodi per gestire la memoria

Ci sono più tipi di partizionamento:

- fisso: partizioni di uguale lunghezza; se il processo è minore o uguale Della dimensione del blocco Allora può essere caricato; deciso aa tempo di Boot
problema: Il programma non entrava nella partizione e ogni programma anche piccolo veniva assegnata una partizione più grande
- variabile: partizione specializzata ossia la memoria Viene divisa in Celle più grandi o più piccole.
problema: gestione inefficiente della memoria , assegnazione blocco

    Ci sono delle differenze tra best fit e First fit:

    - best: sceglie il migliore tra quelli adatti, lascia frammenti molto piccoli
    - first: riempie solo la prima parte di memoria, viene scelto il primo blocco sufficientemente grande
- paginazione semplice: la memoria viene divisa in pezzi di grandezza uguale e piccola
i pezzi di processi sono chiamati pagine, i pezzi di memoria sono chiamati Frame; ogni pagina deve essere collocata in un frame

Il sistema operativo ha una tabella per ogni processo punto per ogni pagina la tabella dice in quale frame si trova.