
# struttura del file 
```c
#include <stdio.h> // include la libreria standard, contiene le funzioni piu comuni

float abs_val( float );     // prototipo di funzione: vengono definiti solo i tipi delle variabili
float radice2( float x );   // non e' un prototipo, e' stato definito il nome del tipo float ma deve ancora essere implementata
                            // ricorda: le funzioni prima di essere chiamate devono essere almeno definite!

void main(){
  // punto di entrata per l'esecuzione del codice.
}
```

# main
## operazioni di assegnazione, divisione intera, e printf
```c
void main(){
	int n = 5;          // int -> integer, numeri interi
	float pi = 3.14;    // float -> numeri con la virgola
	
	// sintassi per commentare una singola riga 
	/*
        sintassi per un commento su piu righe
    */
	
	n = n/2;            // 5/2 = 2, divisione tra interi, ritorna un intero
	pi = (n+1)/2;       // 3/2=1 divisione tra interi, ritorna un intero
                      // 1 viene automaticamente convertito in float: 1.000000, perche' pi e' tipo float
  printf("n = %d, pi = %f\n", n, pi);	
```
`printf(format, ...)`: stampa del testo sul terminale
* `format` -> testo da stampare, formattato secondo gli specificatori
* `...` -> lista di oggetti da sostituire agli specificatori
* `%d` -> indica che verra' sostituito con un intero (int)
* `%f` -> indica che verra' sostituito con un numero con la virgola (float)
* `\n` -> carattere speciale, indica al terminale che bisogna andare a capo.

```c
	pi = (n+1)/2.0;         // divisione tra intero e float, non segue le regole della divisione tra interi!
                            // ritorna un float
	printf("n = %d, pi = %f\n", n, pi);
	
	pi = (1.0*(n+1))/2;     // viene calcolato prima n+1, che e' un intero
                            // viene calcolato poi 1.0*(n+1), che e' un float
                            // [1.0*(n+1)]/2 restituisce un float

  printf("n = %d, pi = %f\n", n, pi);
	 
  // la funzione: radice2 e' stata dichiarata prima del main(), quindi puo' essere chiamata
  // il compilatore pensera' a capire dove e' stata definita, in questo caso dopo il main()
	printf("La radice di %f = %f\n", 2.0, radice2(2));
	 
```

## cicli while e for
```c
  int i = 2;
  while ( i < 20 ){   // traduzione letterale: mentre i e' minore di 20 esegui: { ... }
      printf("La radice di %d = %f\n", i, radice2(i));
      i++;            // equivalente a i += 1
  }
                      // il ciclo viene eseguito finche' i < 20
                      // quando i = 20 l'esecuzione del ciclo viene interrotta
  
  
  for ( int j = 2; j < 20; j++ ){ 
                      // traduzione letterale: per j = 2, finche' j < 20 esegui { ... }, poi fai j++
      printf("La radice di %d = %f\n", j, radice2(j));
  }
                      // il ciclo viene eseguito 20-1 volte, quando j=19 viene eseguito il codice nelle parentesi 
                      // poi alla fine viene aggiornato il valore di j che rende falsa j<20
  
}
```

* operazioni relazionali: `==, <=, >=, !=`
* operatori logici: `&&` equivale a `and` in python, `!!` equivale a `or` in python.