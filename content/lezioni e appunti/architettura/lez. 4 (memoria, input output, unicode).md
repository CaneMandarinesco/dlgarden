# dispositivi interni al computer
## scheda madre
* CPU
* connettori RAM
* bus comunicazione
* connettori per I/O
* connettori IDE/SATA
* batteria per tenere l'orario e altre info
* interfacce di rete

## bus interno (DMA, ISR)
e' il sistema di comunicazione usato per collegare CPU, memoria e I/O.  ogni dispositivo I/O ha un **controller** che lo interfaccia al bus.  i bus possono essere **seriali o paralleli**.  
il bus interno e' tipicamente parallelo: si possono trasmettere piu bit contemporaneamente, al contrario quelli seriali hanno pochi cavi ma trasmettono i bit in serie.  
* problema semantico: chi e' che coordina il transito di informazioni (chi e' il master, chi e' lo slave)?  
* problema tecnico: come gestisco due segnali che vanno sulla stessa uscita
* 
oltre al dispositivo **fisico** (es. hard disk che hanno dei movimenti meccanici) abbiamo quindi un **controller**:
* pilota l'hardware (per esempio la testina del drive)
* logica di controllo per il dialogo
* tipicamente si utilizzava 1 bit per filo

si e' passati alla comunicazione seriale per diminuire il numero di fili.  
e' utile abbassare anche la tensione di funzionamento:
* meno consumo (+ batteria)
* meno riscaldamento (col riscaldamento si creano imperfezioni/cambiamenti di stati nel silicio, dove passa la corrente)

tre tipi di bus:
* bus dati: per il passaggio delle informazioni. dove chiunque puo' immettere e leggere dati
* bus di controllo: per assicurare il sincronismo sul bus

### esempio di lettura!
consideriamo di voler leggere da un hard disk magnetico (tempi di lettura molto lenti). esiste una tecnica che si chiama **DMA** (Accesso Diretto in Memoria), i dati vengono trasferiti sul bus dati senza che la CPU piloti l'operazione. 

come fa la CPU a sapere che il trasferimento e' stato terminato? grazie ad un segnale fisico/software viene chiamata la routine: **ISR** (Interrupt Service Routine / Interruzione). la cpu deve interrompere quello che sta facendo (ed poi riprendere l'esecuzione) *salvando lo stato dei registri* e viene eseguita la routine ISR (gia programmata).  una volta terminata la cpu riprende l'esecuzione.

> tutto cio' viene fatto per ridurre i tempi di attesa! (-tempo di attesa = meno consumi inutili)

> l'interruzione e' un evento asincrono imprevisto (non so quando avverra' ma so cosa devo fare quando avviene)!

### DMA
poiche' il bus e' condiviso, nessun'altro deve immettere dati nel bus. per questo scopo esiste un **arbitro del bus**.
* **cycle stealing**: rischio di perdere cicli in memoria.

### BUS ISA


### computer due bus
architettura che gestisce periferiche **IESA** e PCI


### BUS PCI 
utilizza una rete punto-punto con varie linee seriali con linee seriali di bit a commutazione di pacchetto (PCIe 3.0 ha una larghezza di banda 17GB/sec)

# dispositivi Input Output
sono dispositivi inseriscono o mostrano dispositivi dal/al mondo esterno.  
* tastiera: quando viene premuto un tasto viene generato un interrupt che viene catturato dal sistema operativo
* monitor: uno schermo piatto LCD e' fatto di molecole organiche viscose che si possono muovere come in un liquido. la variazione di un campo elettrico cambia l'allineamento delle molecole e delle proprieta' ottiche.

# RAM nella scheda video (VRAM)
la maggior parte degli schermi ha un refresh di 60/100 Hz (cicli al secondo) e accedono a una memoria speciale (VRAM) che si trova nel controller video.  
la vram contiene una **bitmap** che rappresenta l'immagine sullo schermo (tal volta ne troviamo 2).  
il colore di ogni pixel e' identificato da 3 byte, ciascuno per uno dei colori primari.  poiche' la manda minima per rappresentare dati video e' piu alta dello standard EISA  o PCI per connettere la scheda video alla CPU.

* dispositii di puntamento (tackball e trackpad fanno meno male alla mano sul lungo termine)
# mouse
diversi tipi:
*  inizialmente meccanico, avevamo una rotella che agiva su due potenziometri che calcolavano la distanza percorsa
* **ottico**, rileva il movimento grazie ad una "fotocamera"
* opto-meccanico, rileva il movimento grazie a dei rotori con dei forellini che calcolano la distanza di movimento

# stampanti
tecnologie:
* a matrice
* getto d'inchiostro
* laser
...
## impatto a matrice
usano una matrice di punzoni elettromagnetici che scorre longitudinalmente mentre il foglio scorre sotto. 
* monocromatiche
* lente
* rumorose
* bassa qualita'

## inkjet (getto d'inchiostro)
similmente all'impatto a matrice un foglio scorre sotto la matrice che puo' scorrere in orizzontale.

## laser
producono dei fumi tossici ma:
* alta qualita
* veloci
* silenziosi
* costi bassi
tamburo (**drum**) di precisione rotante, abbiamo bisogno di alta temperatura (generato da alta tensione 1000V).

# apparati per telecomunicazioni
inizialmente si usava il doppino telefonico (progettato per inviare audio). grazie ad un segnale sinusoidale (**portante**) che ha una frequenza compresa tra 1kHz e 2Khz. variando l'ampiezza/fase/frequenza di questo segnale e' possibile tasmettere i bit.

## modem
* modulazione di frequenza: ampiezza costante mentre varia la frequenza della portante in corrispondenza dei valori 0 e 1.  
* modulazione di fase: varia la fase

> nota: qualsiasi mezzo e' dispersivo (ovvero le onde elttriche/sonore ecc... possono incontrare degli ostacoli)

nasce la **DSL** (Digital Subscriber Line) e' una tecnologia che permette di superare le limitazioni dei modem (56 kbp), l'offerta piu popolare e' l'ADSL
...

### asymmetric digital subscriber line (ADSL)
* il canale 0 trasmette il servizio telefonico tradizionale (Plain Old Telephone service)
* i canali 1-5 non sono usati
* due canali sono usati per il traffico in upstream e downstream
* 248 canali (???) ....

## codifica dei caratteri!!!!
* ASCI (standard americano)
* UNICODE
* UTF-8
per la codifica si usano i numeri naturali

### ASCII
codice molto semplice che usa 7 bit: $2^7 = 128$ combinazioni.  i caratteri (per le stampanti a matrice) stampabili sono quelli che fanno da 00 a 4F (???).  questo sistema funziona bene per le lettere anglosassone *ma male per altre lingue* che usano caratteri non presenti sulla mappa ASCII (come rappresento simboli come $\Omega \, \, \Gamma$ ecc...).  
da un consorzio nasce: **UNICODE**.  

### UNICODE
ogni carattere e' codificato con 16-bit (65 mila e passa combinazioni).  risolve vari problemi ma manca:
* ordinamento degli ideogrammi (alcune lingue si basano sull'ordine degli ideogrammi)
* nascita di nuovi ideogrammi
* usa la stessa codifica per caratteri che sembrano uguali ma che in realta' hanno differenti significati.

* per esempio un dizionario giapponese ha 50k simboli kanjj
* unicode spreca 16 bit per codificare anche ASCII
### UTF-8
...
indica quanti byte la sequenza codifica.  