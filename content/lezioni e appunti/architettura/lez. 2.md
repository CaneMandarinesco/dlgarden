## processore
e' il cervello del computer e contiene:
* unita' di controllo (**CU**)
* unita aritmetica e logica (**ALU**)
* registri (memorie piccolissime ad altissima velocita')
i registri più importanti sono:
* **program counter** (PC): dove si trova la prossima istruzione *da prelevare*
* **instruction register** (IR): mantiene l'istruzione corrente in fase di esecuzione
le componenti di un computer sono collegati grazie al **bus**: una collezione di cavi paralleli usati per trasferire indirizzi, dati e segnali di controllo

### organizzazione della CPU
una CPU di *von Neumann* contiene:
* il **datapath** (percorso dati) costituito da 1 a 32 registri
* ALU
* bus di collegamento (con immagine)

### esecuzione delle istruzioni 
il ciclo **fetch-decode-execute** e' fondamentale per l'esecuzione delle istruzioni, e' costituito dai seguenti passaggi:
1. **preleva** l'istruzione dalla memoria e mettila nell'IR.
2. **aggiorna** il program counter
3. decodifica l'istruzione in IR
4. se l'istruzione referenzia una parola in memoria, la ricerca (???)
5. (se necessario) preleva la parola dalla memoria e mettila nel registro
6. esegui
7. ritorna a 1.
### strategie di progettazione
#### architettura CISC
in **CISC** (Complex Instruction Set Computer) la CPU e' in grado di comprendere molte istruzioni complesse nativamente (livello di astrazione molto alto)
#### architettura RISC
in **RISC** (Reduced Instruction Set Computer), poche istruzioni, semplici e veloci. (e' necessario solo un ciclo nel datapath ???)
#### ibrido (CISC e RISC)
dal *x486* le CPU contengono un sottoinsieme delle istruzioni RISC piu' comuni che possono essere eseguite con un solo ciclo nel datapath, mentre quelle piu' complesse vengono interpretate dall'architettura CISC.
### principi di progettazione
* le istruzioni devono essere semplici da decodificare (regolari, lunghezza predefinita, numero ridotto di variabili e campi).  
* le istruzioni `LOAD` e `STORE` sono le uniche che devono fare riferimento alla **memoria** (tempi di accesso elevati), le altre devono operare sui **registri**
* le CPU dovrebbero contenere un *numero elevato di registri* (sempre a causa della lentezza della memoria), cosi dopo il fetch di una word, questa puo' essere tenuta in un registro
## parallelismo
dato che non si può aumentare il clock oltre un **certo limite** dovuto alle leggi della fisica, i progettisti guardano al **parallelismo** per incrementare le performance, con due tipi di parallelismo:
* al livello di istruzione (un processore gestisce piu flussi di lavoro contemporaneamente)
* a livello di processore (piu' processori insieme)
### pipelining (prefetched buffer)
l'operazione di `FETCH` (recupero dati dalla memoria) e' lenta, per ridurre questo problema sono stati introdotti i **prefetched buffer** precaricati con l'istruzione già pronta per l'esecuzione.  
grazie al pipeline l'esecuzione delle istruzioni e' divisa in **stage** o fasi in modo da eseguire queste fasi in parallelo su hardware dedicato.
esempio di pipelining a 5 stage:
1. fetch dalla memoria e memorizzazione nel buffer di prefetch
2. decodifica
3. rintraccia gli operandi
4. esegui
5. metti i risultati nei registri (compreso lo stato del processore)

### banda del processore
il pipelining permette di bilanciare la **latenza** (durata esecuzione di una istruzione) con la **banda del processore** (quanti MIPS la CPU emette).  

> una CPU senza pipeline che opera ad un clock $T \text{ ns}$ ed emette una istruzione per ciclo ha una banda di $10^3/ \text{T MIPS}$

ora supponendo di avere a disposizione di una CPU con:
* clock pari a $T \text{ ns}$
* una pipeline a **p** stadi in cui ogni stadio viene eseguito in un ciclo di clock
la ***latenza totale*** e':
$$
p \cdot T
$$
mentre la ***banda*** e':
$$
p \cdot 10^3 \text{/ MIPS}
$$
### piu pipeline insieme
se una pipeline funziona allora possiamo metterne di piu' (immagine), come nell' **intel x486** ma,tutta via:
* non tutte le istruzioni possono essere svolte in parallelo 
* e' necessario troppo hardware per le varie unita

### architetture superscalari
si adotta un approccio diverso: il processore dispone di una pipeline con piu' unita' funzionali in alcuni stadi di essa.  
esempio intel core (immagine)  
per far si che questo tipo di implementazione abbia senso, la velocità in emissione di `S3` deve essere piu' alta dello stadio `S4`. in `S4` possiamo trovare piu' ALU duplicate.

### parallelismo a livello di cpu
possiamo ottenere un fattore di miglioramento che va da 5 a 10. se vogliamo incrementare drasticamente la performance del sistema possiamo arrivare ad un incremento di 50, 100 o piu. abbiamo 3 differenti approcci:
* computer con parallelismo sui dati
* multiprocessori
* multicomputer

## classificazione flynn
| flusso di istruzioni | flusso di dati | nome | esempio                         |
| -------------------- | -------------- | ---- | ------------------------------- |
| Singolo              | Singolo        | SISD | modello Von Neumann             |
| Singolo              | Multiplo       | SIMD | Supercomputer vettoriali        |
| Multiplo             | Singolo        | MISD | non sono note                   |
| Multiplo             | Multiplo       | MIMD | multiprocessori e multicomputer |
### tassonomia dei calcolatori paralleli
...
### computer con parallelismo sui dati
#### processori SIMD (Single Instruction-stream Multiple Data-stream)
i processori SIMD sono costituiti da un vasto numero di processori identici, che eseguono la stessa sequenza di istruzioni su dati differenti, esempio: GPU.  
> vengono usati tanti sommatori quanti sono gli elementi del vettore
#### processori vettoriali
esegue la stessa sequenza di operazioni su coppie di dati ma le addizioni sono svolte da un unico sommatore nella pipeline.  
> viene usato un solo sommatore e un unico **registro vettoriale**

> entrambe le architetture lavorano su array di dati

### multiprocessori (memoria sincronizzata)
architettura costituita da piu' CPU che condividono una **memoria comune**.  
dato che ciascuna CPU puo' *leggere e scrivere in qualsiasi zona della memoria comune*, devo essere **sincronizzate** via software, quindi devono interagire in modo profondo: sistema ***fortemente accopiato***.

### multicomputer (memoria privata)
dato che multiprocessori con più di 256 CPU sono difficili da costruire si e' preferito abbandonare la memoria comune e usando CPU interconnesse con ognuna una **memoria privata**.  
quindi in un multi-computer le CPU:
* sono accoppiate in modo lasco (**loosely**)
* comunicano attraverso messaggi
anche se in architetture piu grandi la completa interconnessione non e' fattibile, quindi si usano metodi che sfruttano la **topologia** (griglia, anelli, albero)

## memoria principale
memorizza i programmi e i dati. l'unita piu' piccola di memoria e' il bit (BInary digiT).  

## sistemi di numerazione
e' un sistema linguistico fatto di numeri ed e' composto di alfabeto e grammatica.  
* romano
* posizionale: il numero di simboli usati indica la base, e il valore di ogni simbolo dipende dalla base
* basi importanti: `2,8,10,16`
in base `16` si usano le  lettere `A...F` perché la macchina da scrivere all'epoca disponeva di questi simboli (la scrittura in base 16 nasce prima del computer!).  
metodi per trasformare le basi:
* per trasformare la base si usa il metodo delle **divisioni successive**.  
* metodo semplificato: **base 10 -> base 2** (nel metodo basta chiederci: il numero e' pari o dispari?).  
* metodo semplificato: **basi potenza l'una dell'altra** (es. 2 e 8)

## indirizzi di memoria
e' organizzata in **celle**, dove ogni cella contiene lo stesso quantitativo di informazioni in byte, e rappresenta quindi l'unita' di memoria piu piccola indirizzabile, i byte possono essere raggruppati in **parole**.
ordinamento dei byte nelle parola:
* Big Endian: da sinistra a destra
* Little Endian: da destra a sinistra

## codici di correzione errore
sono dei codici che si usano per sapere dove e' avvenuto un errore:
* un parola di codice 
(???)
* codice di **hamming**
abbiamo dei bit di controllo (in una parola), che rappresentano delle posizioni
(da approfondire)

## memorie cache
memoria all'interno della cpu, velocita' prossima a quella dei registri.
il problema della memoria e' che essendo grande ha dei tempi di accesso elevati.
* esistono più livelli di cache (comune, istruzioni, dati)
possiamo costruire una gerarchia di memorie

## banco di memoria
* chip di memoria
* chip di controllo