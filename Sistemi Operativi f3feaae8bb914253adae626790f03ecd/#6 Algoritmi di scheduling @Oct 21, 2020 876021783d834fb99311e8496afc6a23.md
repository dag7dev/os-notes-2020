# #6. Algoritmi di scheduling @Oct 21, 2020

# Algoritmi di scheduling

- Round Robin un po' ciascuno quando finisce il quarto di tempo viene preso il processo è sospeso la misura del quarto di tempo della preemption deve essere poco più lungo del Tipico tempo di iterazione per un processo ma non troppo altrimenti si degenera in fcfs.

    Favorisce i CPU Based Ma non gli i/o based poiché si impiega più tempo. Per ovviare a questo problema usa un round Robin virtuale

- SPN: shortest Process Next: non preemptive esegue il processo più breve a parità di arrivo.
Si possono soffrire di starvation possono essere non eseguiti Perché continuano ad arrivare i processi.
- SRT: spazio Come spn preventivo. Non round Robin, un processo può essere interrotto quando Ne arriva uno nuovo.
- HRRN: highest Response ratio Next: processo seguente a quello che ha il tempo di risposta più alta. non preemptive.

Scheduling Linux: round Robin un secondo , sfrutta le cose con priorità. priorità in base: processi utente basso , swapper alta, sistema operativo

Assegnamento :

- statico da quando nasce e muore sul processo
- dinamico: può essere trasferito da un processo all'altro a seconda di quanto è pieno

Run queue: STS

Wait queue: code nelle quali i processi sono messi in attesa