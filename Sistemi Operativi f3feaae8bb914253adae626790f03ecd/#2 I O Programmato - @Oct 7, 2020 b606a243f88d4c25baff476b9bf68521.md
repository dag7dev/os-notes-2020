# #2. I/O Programmato - @Oct 7, 2020

## I/O Programmato

- L'azione viene effettuata dal modulo I/O non dal processore;
- Niente interruzioni
- Setta i bit appropriati sul registro di I/O

Prima la lettura veniva effettuata per sempre, ora no.
C'è una fase aggiuntiva della CPU stessa che si deve preoccupare di gestire il mio dispositivo.

---

## DMA (Direct Memory Access)

- Metodo utilizzato attualmente
- trasf un blk di dati direttamente alla memoria
- quando viene completato il trasferimento viene inviato un interrupt

---

## Cache

- Memoria che sta a metà tra cpu e ram

Contiene copie di alcune parti della memoria centrale e l'idea è che il processore controlla se quel dato è prima presente sulla cache. Se non è presente prima viene salvato sulla cache e poi viene fatto l'accesso.

Politiche di reinserimento:

- LRU
- Hit or miss
- Blocco, set

Si hanno due politiche: write-through e write-back

Linux non può disabilitare il caching, sceglie sempre il WriteBack

---

## Servizi offerti

- accesso ai dispositivi di I/O (nel caso di dispositivi di memoria di massa → file system)
- accesso al sistema operativo (shell)
- sviluppo di programmi: gestione memoria RAM, system call, compilatori, debugger
- rilevamento gestione errori
- accounting raccolta di dati, performance, statistiche ecc

Obiettivi:

- convenienza
- efficienza: non deve fare complicazioni inutili
- capacità di evolvere: aggiornamenti

Oct 5, 2020