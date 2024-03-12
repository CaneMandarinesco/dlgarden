## gerarchie di memorie
alla base della piramide troviamo i **registri**.
nella piramide:
* dalla cima verso il basso, **il tempo di accesso e il costo decrementa**
* al contrario, **cresce la capacita'**

> la dimensione della memoria e' inversamente proporzionale al tempo di acceso e direttamente al costo.

> i nastri magnetici sono grandi ma lenti ( e economici )

### dischi magnetici
sono fatti da piatti di alluminio che attraverso la **isteresi magnetica** (???) possiamo modificare i bit incisi su di esso.  
poi abbiamo la **testina** che fa ruotare il disco e un **solenoide** rileva lo stato di magnetizzazione.  
le tracce del disco sono divisi in **settori** (di **grandezza fissa**), e tra ogni settore c'e' uno spazio (**gap**), ogni traccia contiene un preambolo e serve ad allineare le testine e contiene un **CCE** (puo' essere hamming).  
un controllore del disco (disk controller) collega il disco al bus.  
i dischi per definire la grandezza dei settori, i gap ecc... ha bisogno di essere formattato.

> il **floppy disk** e' un disco magnetico

#### hard disk 
l'hard disk magnetico ha 3 tempi:
* tempo medio di seek (per raggiungere la locazione desiderata): $5$ ai $10 ms$
* tempo rotazionale (il tempo del motore per muoversi/**inerzia**): $3$ a $6ms$
* tempo di trasferimento, dipende da:
	* densita' lineare
	* velocita' di rotazione
	* con una velocita di trasferimento di 150mb/s se il settore e' di 512 byte ci vogliono 3,5 micro secondi

#### IDE
i dischi IDE sono i primi dischi magnetici. i primi avevano una velocita' di trasferimento di $4MB /s$, poi si e' riusciti ad arrivare a $16MB /s$.

... EIDE ... ATAPI-4 / 5 / 6 / 7

#### SCSI Disks (Small Computer System Interface)
diventa standard ANSI per collegare dispositivi (HD, CD-ROM, Scanner, nastri)

### RAID
#### RAID livello 0
i dati sono suddivisi su `k` settori e memorizzati in dischi diversi con modalità **round-robin**. in questo modo un blocco di dati puo' essere letto con 4 letture parallele. questo schema funziona su grandi quantita' di dati al contrario su pochi dati non e' vantaggioso.
#### RAID livello 1
evoluzione del livello 0
#### RAID livello 2
usa le parole binarie o byte per decomporre le informazioni sui vari dischi .
* troughtput alto perche' ho molte operazioni in parallelo
#### RAID livello 3
versione semplificata del 2 che usa.
disco di parita' (contiene i bit di parita del codice di hamming)
#### RAID livello 4 e 5 (oppure S)
lavorano con strisce e non richiedono dischi sincronizzati

### dischi a stato solido (SSD)
basati su una memoria flash non volatile. si usurano nel tempo a causa dell'usura dei transistor e possono quindi perdere capacita' di memorizzazione. alte prestazioni fino a 3 volte un disco magnetico, più tolleranti alle vibrazioni in quanto non presentano parti meccaniche

### CD-ROM (Compat Disk Read Only Memory)
dischi fatti di policarbonato con uno strato di alluminio riflettente e ricoperto da una vernice resistente. questi materiali si possono degradare col calore. nel substrato di policarbonato si possono creare delle depressioni (**pit**) tra aree non incise (**land**). esiste un valore di variazione tra **pit** e **land**.

#### memorizzazione
sono memorizzate usando un preambolo, poi un settore e infine il CCE

#### settori
due modalità: 1 (*con errore*) e 2 (*senza errore*, potrebbe non avere senso correggerlo, come formati audio/video).  

#### CD-R (registrabili)
contengono uno *strato di pigmento* che permette di **scrivere i pit**. contengono una scalanatura che permette di guidare il laser in fase di scrittura. durante la scrittura il raggio laser colpisce il pigmento rompendo un **legame** molecolare che **non si puo' ripristinare**

#### CD-RW (riscrivibili)
al posto del pigmento troviamo una lega che ha due stati stabili: cristallino e amorfo, dove il laser puo' avere 3 diverse intensita:
* alta potenza, la lega


#### DVD (Digital Versatile Disk)
sono progettati in modo simile ai CD, ma possono contenere piu' dati, e puo' essere inciso su entrambi i lati ...

#### dispositivi interni al  computer...


