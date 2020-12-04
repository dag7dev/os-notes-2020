# #3. Struttura di un S.O. - I processi @Oct 12, 2020

## Struttura di un sistema operativo

- A livelli:
1. circuiti elettrici, celle di memoria, porte logiche
2. istruzioni macchina, add sub lw sw
3. procedure, chiamate e ritorno
4. interrupt
5. processo, programma in esecuzione, operazioni su un processo
6. trasferimento blocchi di dati
7. spazio logico, indirizzi virtuali
8. comunicazioni tra processi
9. salva file
10. dispositivi esterni accesso
11. id interni ed esterni
12. supporto di alto livello
13. shell

### Requisiti di un sistema operativo

- gestione dei processi: gestione diverse computazioni che si vuole eseguire su un sistema computerizzato
- il sistema operativo deve effettuare operazioni di: multithreading, interleaving: esecuzione alternata tra processi, sincronizzazione processi, scambio informazioni processi

---

## I processi

Un processo è un programma in esecuzione, è l'esecuzione di una sequenza di istruzioni
- è composto da codici, dati, attributi che descrivono lo stato di un processo

Stato di un processo

- creazione
- esecuzione
- terminazione
- prevista
- non prevista

Ha diverse informazioni:

- PCB Process Control Block
- elementi sistema operativo
- creato e gestito dal s.o.
- permette al s.o. di gestire più processi contemporaneamente
- informazioni per bloccare il programma e farlo riprendere (indirizzi)
- Traccia: segue istruzioni che vengono eseguite → trace
- Dispatcher: sospende un processo per farne iniziare un altro. è un programmino del s.o.

Modello dei processi:

- a 2 stati
- a 5 stati
- usando due code

---

Terminazione dei processi: 

- normale completamento (halt; exit)
- uccisione
- s.o: memoria non disponibile / errore di protezione
- utente: x sulla finestra
- processo creatore
- c'è sempre un processo master che amministra tutto

---

Tabelle:

- di memoria: gestiscono memoria principale e secondaria: allocazione, protezione informazioni vmem
- I/O:
- il s.o. deve sapere: dispositivo disponibile o no, stato i/O op, lock memoria sorgente o destinazione
- File: informazioni file: esistenza, modifica, locazione, stato, altri attr. mem su disco e ram
- dei processi: