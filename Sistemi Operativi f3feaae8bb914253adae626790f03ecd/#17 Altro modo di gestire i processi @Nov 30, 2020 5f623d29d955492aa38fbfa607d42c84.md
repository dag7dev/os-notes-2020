# #17. Altro modo di gestire i processi  @Nov 30, 2020

Algoritmo di Dekker VS algoritmo di Peterson

Dekker:
- acquisisce risorsa
- aspetta se l'altro processo sta usando la risorsa
— se sta aspettando la risorsa aspetta anche il turno
—- rilascia la risorsa mentre aspetta

Peterson:
- acquisisce risorsa
- passa il turno
- aspetta mentre altro processo sta usando la risorsa E ha il turno

L'altro modo per gestire la sync tra processi: possiamo avere quindi delle istruzioni speciali che permettono ai processi dai gestire sincronizzazione e comunicazione. Le istruzioni sono:
- send
- receive
- test_ricezione

Receive rendezvous: un modo per scambiarsi i messaggi. Sia mittente che destinatario sono blocked finchè il messaggio non viene completamente ricevuto.

Send-non-bloccante: (nbsend): il mittente continua a inviare messaggi, il destinatario è bloccato finchè non li riceve

Sono entrambe operazioni atomiche e tipicamente vengono usate a coppia: o sono entrambe nb o no.