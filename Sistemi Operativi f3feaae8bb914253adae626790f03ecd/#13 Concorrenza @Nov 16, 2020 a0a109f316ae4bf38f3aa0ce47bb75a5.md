# #13. Concorrenza @Nov 16, 2020

Gestione file system Windows

- ntfs
- fat: Per ciascun blocco contiene il blocco successivo o si è finito
settore di avvio: 36 byte
I blocchi si chiamano cluster e la dimensione di ognuno di essi è decisa da 1 a 128 al momento della formattazione
Ogni record della fat è composto da 5 settori, cluster libero valore riservato cluster dati valore riservato cluster danneggiato ultimo

Concorrenza
App multiple, esecuzione multipla
Operazione atomica: Non scomponibile, sequenze indivisibile di comandi
Sezione critica: Accesso ad una pozione di memoria condivisa
Mutua esclusione: Se c'è quella risulta condivisa bisogna che è un processo unico vi acceda. Non possono usare due processi quella risorsa nello stesso istante.
Corsa critica: Accedere alla mutua esclusione e Quando ciò viene violata errore.
Deadlock, livelock, starvation

I problemi: Nessuna assunzione sui processi, gestione locazione delle risorse condivise, difficile tracciare gli errori di programmazione.
Competizione: Ogni processo credi di essere da solo. Non c'è nessuna comunicazione.
Cooperazione: Sanno che ci sono altri processi, che sono e che fanno. Comunicano tra loro.