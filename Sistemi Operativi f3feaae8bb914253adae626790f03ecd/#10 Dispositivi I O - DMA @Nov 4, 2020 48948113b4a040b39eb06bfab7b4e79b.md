# #10. Dispositivi I/O - DMA @Nov 4, 2020

# Dispositivi I/O

Dispositivi di input e output: sono lenti sono tutti diversi tra loro, il sistema operativo non può gestirli tutti.

Di diverso tipo (leggibili):

- utente: HD, stampanti, controller
- macchina: storage, USB, sensori, controllori
- navigazione: modem, rete, WiFi

Un qualsiasi dispositivo invia un segnale a seguito di un evento fisico. Il sistema operativo può scrivere su una periferica e la parte del kernel che gestisce un dispositivo di I/O si chiama driver.

Una delle tecniche più utilizzate per effettuare input-output: (che può essere con o senza interrupt, CPU o MEM) è il DMA.

---

# DMA

Acronimo di DIRECT MEMORY ACCESS:

- cpu delega al DMA;
- trasferisce dati da o verso RAM;
- quando azione completata genera un interrupt;

Obiettivi:

- **efficienza**: ridurre tempi lettura scrittura a zero
- **generalità**: gestire input output in maniera uniforme, nascondere i dettagli in codice assembly, progettare funzionalità
- **programmazione gerarchica**: ogni livello fornisce servizi a livello superiore

Bisogna evitare la situazione di deadlock: due o più processi o azioni si bloccano a vicenda, aspettando che uno esegua una certa azione (es. rilasciare il controllo su una risorsa come un file, una porta input/output ecc.) che serve all'altro e viceversa.