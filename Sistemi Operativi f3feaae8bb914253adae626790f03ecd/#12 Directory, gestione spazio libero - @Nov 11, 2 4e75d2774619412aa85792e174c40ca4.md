# #12. Directory, gestione spazio libero - @Nov 11, 2020

# Directory

Sono dei file speciali che specificano Dove si trovano altri file e memorizzano diversi informazioni di essi.
operazioni fondamentali: Ricerca, modifica, lista di file, cancellazione
Informazioni di base: Nome, tipo, organizzazione, volume dove sono memorizzati, indicatore della partizione dove sul disco

- i nomi devono essere unici nella stessa Directory
- workspace: Directory di lavoro, ossia una directory dove si sta lavorando in quel momento.

Percorso assoluto: Tutto il Path
Percorso relativo: Relativo alla cartella nella quale ci si sta lavorando

# Preallocazione vs allocazione dinamica

Nella prima si specifica la dimensione massima del file, non è più utilizzata

**Porzioni**: Si alloca una porzione sufficientemente grande e sì alloca un blocco alla volta oppure si fanno porzioni grandi di dimensione variabile oppure si costruiscono tabelle piccole e compatte

Nella pre-allocazione i pezzi sono più grandi, non si usa la tabella di allocazione

Allocare i file

- **contiguo**: Insieme di blocchi con frammentazione esterna
- **concatenato**: Puntatore al prossimo blocco, niente frammentazione
- **indicizzato**: Viene utilizzata spesso come base di filesystem moderni. Anziché dove seguir man mano i vari link, viene memorizzato solo il blocco dov'è memorizzato il file che contiene tutti i blocchi dove sono memorizzati i pezzi di file;

# Gestione spazio libero

Occorre sapere dov'è lo spazio libero. È l'antagonista dell'altro.
Tabella di bit per ogni blocco occupato: 1 occupato, 0 libero

**Indicizzazione**: Tratta lo spazio libero come un file e quindi usa un indice proprio come si farebbe per un file. L'indice gestisce tutte le porzioni come se fossero variabili.

**Volumi**: È un disco logico, cioè un'area di memorizzazione di dati con un singolo file system -> partizionati, messi insieme e visti come uno unico (lvm)

**Journaling**: Anziché scrivere le informazioni nelle opportune porzioni del disco, scrive in una certa zona dedicata (log)
In caso di Reboot dopo un crash basta leggere il log: Si utilizza un bit di controllo per controllare che il sistema operativo abbia effettivamente spento tutto correttamente.

**Gestione file Linux**: Normale, directory, speciali, named pipe, hardlink, link simbolico

- **speciali:**  /dev/null esempio o i /mnt/ point
- **named pipe:** FIFO
- **hardlink**: è una vera e propria copia speculare di un file presente sul nostro sistema Linux e quindi conterrà al suo interno il contenuto del file originario
- **link simbolico**: un file, contenente all'interno un collegamento ad un altro file (o directory)

**Inode**: index node, contiene varie informazioni su uno specifico file o directory o qualunque altro oggetto del filesystem.