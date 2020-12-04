# #1. Cosa viene insegnato in SO? - @Oct 5, 2020

## Cosa viene insegnato in SO?

- come fa un pc a funzionare?
- come è possibile che interagendo con le periferiche funzioni il pc?
- perchè se scrivo qualcosa di semplice essa funziona?
- devo usare la RAM?

## Nozioni di base

- CPU
- Memoria Centrale suddivisa in volatile e primaria
- I/O
- Bus di sistema [scheda madre]

## Registri

- Visibili:
    - usati da chi programma
    - obbligatori
    - facoltativi =
    - compilati / interpretati
- Di controllo e di stato:
    - CPU
    - Funzioni privilegiate
- Interni:
    - CPU microprogrammazione
    - Comunicazioni I/O

Registri ↔ RAM

- registri interni memoria (MAR, prossima operazione lettura / scrittura)
- registro di memoria temporanea:

Memory buffer service (MBR): contiene i dati da scrivere in memoria o fornisce lo spazio dove scrivere i dati in memoria

LW S1, 0(S2): concettualmente copia il contenuto di S2 in MAR e poi in MBR.

## Interrupt

è il modo principale col quale l'hardware si interfaccia col software. Dal nome appunto si interrompe l'esecuzione per eseguire le operazioni. Tutto questo avviene se il flag per gli interrupt è abilitato. Ci sono diverse interruzioni:

- asincrone: arrivano "quando vogliono" poichè dipendono da I/O Hw failure, errore parità memoria, timer interno al processore

Le asincrone riprendono dall'istruzione successiva a dove si è verificato l'interrupt.

- sincrone: overflow, divisore per 0, debug, illegal opcode, memoria interna non disponibile

Le sincrone:

- faults
- aborts
- trap and systems: esecuzione continua istruzione successiva

L'interrupt Handler è un programma di default: non usa librerie esterne, semplicemente sta lì per gestire qualcosa di inaspettato