# struttura del file
```c
union item {
    int val_i;
    float val_f;
    char *val_s;
}
typedef union item item;
// dentro a item, la stessa regione di memoria e' condivisa tra val_i, val_f e val_s

struct object {
    char type; // 'I' -> Intero, 'F' -> Float, 'S' -> *char
    item u;
}
typedef struct object object;

/* converti l'oggetto al tipo giusto per rappresentarlo */
object parse(char*);

/*controlla il tipo dell'item dentro a object e stampa il valore */
void print(object);

/* controlla se la stringa s contiene dei punti, in modo da capire se e' un float */
int cercapunto(char* s);

int main(int argc, char** argv){
    /*...*/
}
```

```c
// implementazione
```