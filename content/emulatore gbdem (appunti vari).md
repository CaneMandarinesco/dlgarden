https://gbdev.io/pandocs/Power_Up_Sequence

## memory map
* 8000 - 9FFF: VRAM (Video RAM)
* C000 - CFFF: 4Kib WRAM (Work RAM)
* D000 - DFFF: 4Kib WRAM
* E000 - FDFF: **echo**(duplicata) ram (C000-CFFF)
* FE00 - FE9F: object attribute memory
* FF80-FFFE: high ram

la VRAM puo' essere usata come normale RAM.

## grafica
manipolare la grafica pixel per pixel sarebbe costoso, invece la cpu gestisce gruppi di pixel chiamati tiles (8x8). e un tile e' in grado di assegnare dei colori ai sui pixel (4 colori).  
una palette consiste in un array di colori (4 nel gameboy)  
il gameboy ha 3 layer: background, window e objects con la possibilità di andare oltre questa astrazione.  
il background e' composto da una tilemap (griglia di riferimenti ai tiles), si puo' scrollare il background usando due registri.  
il window e' simile al background ma piu' limitato.

ogni tile ha 2 bit di color depth: quindi 4 possibili valori che identificano 4 diverse tonalita' di grigio. il colore `0` e' trasparente!

nella VRAM esistono 3 blocchi di ram di 128 oggetti:
* 8000 - 87FF blocco 1
* 8800 - 8FFF blocco 2
* 9000 - 97FF (inutilizabile)
ci sono 2 modi per indirizzare i blocchi in base all'indirizzo di riferimento (8000/9000). varia in base al valore di `LCDC bit 4`.
ogni tileset occupa 16 bytes e una linea e' formata da 2 bytes
## programmazione!
### boot rom e header
controlla che il logo nintendo nella rom sia uguale a quello immagazzinato dentro la console (misura antipirata che pero' e' stata deprecata). viene calcolata una checksum dell'header per controllare che non sia corrotta. 
l'header contiene la grandezza della rom. tutte queste informazioni devono essere calcolate correttamente altrimenti la rom non funziona, per farlo si usa `rgbfix` per trasformare la rom compilata in una rom usabile.

inoltre contiene:
* nome programma
* compatibilita' con game boy color
* grandezza rom
* checksum
* nintendo logo

anche se alcune di queste informazioni, anche se errate non invalidano la rom stranamente, dato che queste erano usate da Nintendo dato che l'header descrive l'hardware della cartuccia.  
ed e' proprio per questo motivo che per un emulatore e' importante analizzare l'header.

nella versione hardware del gameboy, dentro alla cpu troviamo la boot ROM che contiene le istruzioni eseguite all'accensione (compreso il logo nintendo) e controlla che le checksum e il logo nintendo nella cartuccia siano corretti.

## operazioni e flags
* inc
* dec

flags:

| nome | desc       |
| ---- | ---------- |
| Z    | zero flag  |
| N    | add/sub    |
| H    | half-carry |
| C    | carry      |
### compare
cp sottrae il suo operatore `x` da `a` e aggiorna le flag di conseguenza, quindi possiamo per esempio sapere quando `a >= x` o `a < x`!  

## jumps
* jump
* jump relative
* call
* return

jump semplicemente imposta `PC` al suo argomento. guardiamo l'esempio:
```rgbasm
    ld de, Tiles; Tiles corrisponde al primo byte dei dati sui tilesets
    ld hl, $9000; iniziamo a copiare in questo indirizzo
    ld bc, TilesEnd - Tiles; quanti dati dobbiamo copiare
CopyTiles:
    ld a, [de] ; copia de in a
    ld [hli], a 
    inc de ; vai al prossimo byte
    dec bc ; i byte da leggere decrementano di 1, dobbiamo sapere se arriviamo a 0
		    ; la flag non viene aggiornata nel caso dec bc quindi lo facciamo manualmente
    ld a, b 
    or a, c
    jp nz, CopyTiles ; se flag z e' non zero vai a CopyTiles
```
