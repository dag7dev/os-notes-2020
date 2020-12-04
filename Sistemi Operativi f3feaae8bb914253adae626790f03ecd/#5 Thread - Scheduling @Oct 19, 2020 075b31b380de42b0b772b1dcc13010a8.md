# #5. Thread - Scheduling @Oct 19, 2020

# Thread

Thread: processi eseguiti in ordine parallelo: diverse esecuzioni dello stesso processo che condividono tutte le risorse ad eccezione dello stack e del processo
Possono essere gestiti sia lato utente che sistema.

ULT: Pro efficiente lo switch, politiche di scheduling diverse, thread anche sui s.o. che non offrono thread nativamente CONTRO:  se un thread si blocca si bloccano tutti e se il s.o. non ha i KIT niente thread per le routine.

Gli stati in Linux:
- running: ready and running
- interruptible, uninterr stopped traced: blocked
- zombie, dead, exit

LA DIFFERENZA TRA ECCEZIONE E INTERRUPT: gli INTERRUPT sono fatti dagli HW, overflow e così via. Le eccezioni servono per lanciare le syscall.

---

# Scheduling

Il sistema operativo deve assegnare le risorse tra le quali il processore. questa operazione viene definita scheduling. Esso deve associare il processore ai processi secondo alcuni parametri.

Esistono 3 tipi di scheduling:
- STS: quale processo va eseguito: dispatcher; jdinvocato sulla base di eventi, interruzione I/O, interruzione clock, syscall, segnali
- MTS: l'aggiunta ai processi in memoria principale
- LTS: l'aggiunta ai processi da essere eseguite. Coda FIFO con priorità. Batch: ammassati ed eseguiti, mix tra i/o bound e cpu bound, interattivi fino a saturazione, se si usa i/o bilancia le richieste
- I/Os: quale processo deve essere assegnato il dispositivo di input / output

Le politiche di scheduling dipendono dai criteri diversi: utente, tempo di risposta e output tempo; sistema: uso efficiente ed attivo;

Turn around time tempo di vita del processo
Response tempo tra l'inizio di una richiesta e una risposta
Throughput quantità di lavoro effettuato

Se non ci sono indicazioni tutti i processi hanno pari priorità.

I principali algoritmi sono:

- pre-emptive il s.o. sospende il processo
- non pre-emptive finchè non finisce o arriva I/O il processo è in esecuzione

FCFS: FIFO
RR: un po' per ciascuno basandosi su un clock