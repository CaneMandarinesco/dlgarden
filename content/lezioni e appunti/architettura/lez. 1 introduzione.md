due tipi di grandezze:
* analogica: varia in modo infinitesimo
* digitale: le informazioni sono codificate con una sequenza di **valori discreti**, può essere trattato da un calcolatore.

### teorema del campionamento
il teorema garantisce che un campionamento di un segnale analogico e' senza perdita di informazione se la frequenza di campionamento e' pari al doppio della frequenza massima camionabile.

* ADC -> Analog To Digital Converter 
* DAC -> Digital To Analog Converter

### il calcolatore
* usa il sistema di numerazione binario
* puo' sommare numeri, controllare se una cifra e' zero, copiare dati ecc...
* contiene una CPU, che riconosce un unico linguaggio: il **linguaggio macchina**.

### problema della distanza concettuale 
* tra il linguaggio naturale e il linguaggio del computer esiste una distanza concettuale
* al livello 0 esiste una macchina quindi che interpreta il linguaggio usando il linguaggio L0 (questo livello e' costituito dal computer)
* possiamo creare una **macchina virtuale** (M1) che utilizza un linguaggio L1 che si interfaccia con il livello L0
* questi livelli di stratificazione servono a colmare la distanza tra linguaggio macchina e linguaggio naturale.

### creare una macchina virtuale
si puo' creare in due modi.
#### 1. traduzione
il programma in $L_{1}$ e' convertito da un programma $L_{0}$ chiamato **traduttore** in programma $L_{0}$ **equivalente**.
* il programma e' composto di istruzioni in $L_{0}$
* e' ottimizzato per $M_{0}$ e non può essere usato in nessun'altra macchina.

#### 2. interpretazione
un programma scritto in $L_{0}$ chiamato **interprete** 

### interazione
l'utente puo' interagire con la macchina virtuale più astratta. ogni livello interagisce con quello a lui sottostante, **non può accadere diversamente**.

> [!note] OSS.
> questo e' un concetto base che vale anche per la programmazione (programmazione ad oggetti)

### hardware e software
* hardware: oggetto tangibile
* software: idee astratti, algoritmi o istruzioni
* oggi, hardware e software ***sono logicamente equivalenti***, perché ogni istruzione hardware può essere simulata dal software

### evoluzione dele architetture multilivello
#### invenzione microprogrammazione
nel 1951 nasce la prima macchina con interprete, che eseguiva a livello ISA
#### invenzione sistema operativo
nel 1960 nasce un computere con un softare sempre attivo che gestisce l'hardware
#### migrazione verso il microcodice
nel 1970 il microcodice si arricchisce con istruzioni e tecniche

#### eliminazione della microprogrammazione
...

### pietre miliari (generazioni di computer)
#### generazione zero
* macchina **pascalina** (1600-xxxx): fa somme e sottrazioni
* macchina **Leibniz**: fa operazioni algebriche usando una scheda perforata, un fotodiodo riconosceva la presenza di un foro o meno.
* primi computer a relè (mark 1 e mark 2)

#### prima generazione
* valvole termoioniche,  computer usato per decifrare i messaggi durante la seconda guerra mondiale

* macchina di **von neumann**, architettura alla base di oggi, costituita da 5 componenti fondamentali:
	* memoria
	* ALU (Airthmetic Logic Unit)
	* Control Unit
	* Input
	* Output

...

#### seconda generazione
* **transistor**: utilizzano i transistor e implementa il concetto di **bus**
grazie al bus, ogni componente può dialogare con gli altri, utilizzando una linea comune. questo porta vari vantaggi:
* se dobbiamo aggiungere un dispositivo di I/O, possiamo aggiungerlo semplicemente collegandolo sulla linea comune
ciò introduce il **problema del cortocircuito**: come posso collegare vari elementi insieme e **riconoscere chi sta mandando i segnali**? chi e' che ascolta e che parla? se due oggetti parlano allo stesso momento avviene un cortocircuito. (problema del sincronismo)
#### terza generazione
circuiti integrati
#### quarta generazione
very large scale integration (VLSI), si possono inserire milioni di transistor in un singolo chip.
nascono le prime cpu intel (8080/8088/80386)

#### quinta generazione
computer integrati in elettrodomestici, orologi, carte di credito ecc...

### legge di Moore
il numero di transistor raddoppia ogni 18 mesi ($60\% \text{ annuo}$), in modo costante. a un certo punto ci si e' arrestati per problemi di natura energetica e dissipazione del calore.

### server e clusters
* server: gest
...

### mainframe
...

### storia di intel
i processori nuovi sono in grado di emulare le funzioni dei vecchi processori, o le integrano.
la velocità di clock di un processore non e' indice della velocità del processore! apparentemente potrebbe essere cosi' ma e' errato.
esistono architetture che hanno un basso clock ma emettono dati alla stessa velocità di un'altra architettura che ha un alto clock.
a cosa serve la memoria dentro al chip? ci si riferisce alla **cache**

#### memoria cache
principio di località spaziale e località temporale.

### unita' metriche
le principali unita' metriche sono multipli e potenze di 10, quando ci si riferisce ai dati si utilizza la base 2.
