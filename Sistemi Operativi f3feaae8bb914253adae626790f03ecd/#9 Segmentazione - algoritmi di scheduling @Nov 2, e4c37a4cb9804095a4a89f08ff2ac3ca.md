# #9. Segmentazione - algoritmi di scheduling @Nov 2, 2020

# Segmentazione

La segmentazione permette al programmatore:

- di vedere la memoria come un insieme di spazi (segmenti) di indirizzi
- condividere, proteggere dati
- ogni processo ha una sua tabella di segmenti

La differenza tra paginazione e segmentazione: la prima è trasparente al programmatore, la seconda è visibile al programmatore e per ogni segmento si ha la divisione in pagine

Operazioni: 

- fetch: decide quando una pagina data debba essere in RAM
- placement policy: page Fault -> deve metterla in RAM, dove? nel primo spazio libero
- replacement: principio di località (palla di vetro)
- residence set:
    - management: quanti frame di RAM dò a un processo?

        fissa: decisa nel tempo di creazione

        variabile: il contrario

    - scope: quando si rimpiazza, stesso frame/processo o casuale?

        locale : frame stesso processo

        globale : qualsiasi Frame

- Frame locking: un frame è bloccato se viene utilizzato dal sistema operativo
- Cleaning (pulitura): Frame modificato: quando?

Algoritmi di sostituzione del Frame: ottima , lru, Fifo, Clock

In CLK, c'è uno use bit: ogni frame ha un mito che dice che la pagina è stata inserita in quel frame o no e sostituisce se non ha il bit a 1.

Buffering pagine: aggregato all'algoritmo delle pagine senza buttarle via. Quando la pagina deve essere rimpiazzata la si mette in questo buffer.

(seconda possibilità: cimitero)