# struttura del file
```c
#include <stdio.h>

int somma(int [], int );
int *somme_parziali(int [], int);

int N = 12;  // variabile globale, qualsiasi funzione all'interno di questo file puo' usarla
             // invece una funzione definita dentro main(), non puo' essere usata in somma

int main(){
    ...
}
```

# main
```c
int main(){
	int n;
	int a[12]; // array di 12 interi, vanno dalla posizione 0 fino alla posizione 11
	int b[] = {50, 1, 4, 9, 61}; // array di 5 interi
	int c[10] = {3, 2, 10}; // array di 10 interi, i primi 3 sono {3, 2, 10}
	int m[1000] = {0};
	// int x[n]; dove n e' una variabile. questo e' un errore perche' il compilatore deve sapere precisamente quanta memoria deve allocare per un array, non si puo' usare una variabile per definire la lunghezza di un array, bisogna usare un valore costante nel tempo (per esempio i numeri)
	int i; // quando una variabile viene inizializzata, le viene assegnato un valore randomico (che dipende dall'indirizzo di memoria in cui si trova la variabile)
	int na = sizeof(a)/sizeof(int); // questo e' un modo per ottenere il numero di elementi in un array, dividiamo la grandezza in byte di 'a' per la grandezza di ogni singolo intero (ovvero ogni elemento di a)
	
	printf("size(a) = %d\n", sizeof(a));
	
    // possiamo usare il ciclo for per scorrere tutti gli elementi di una lista
	// assegna per ogni valore di a il valore: i*i+1
    for(i = 0; i < na; i++){
		a[i] = i*i+1;
	}
	
	printf("a\n");

	// stampa ogni valore di a
	for(i = 0; i < na; i++){
		printf("%d\n", a[i]);
	}
	
	printf("b\n");
	
	for(i = 0; i < 5; i++){
		printf("%d\n", b[i]);
	}
	
	printf("c\n");
	
	for(i = 0; i < 10; i++){
		printf("%d\n", c[i]);
	}
	
    // richiama la funzione somma
	printf("somma(a) = %d\n", somma(a, na));


	int *somme = somme_parziali(a, nx\a);
	
	for(i = 0; i < na; i++){
		printf("%d\n", somme[i]);
	}
	
}
```

# funzioni somma
```c
int somma(int x[], int n){
    // int somma(int x[], int n)
    // x: int[] -> array di elementi da sommare
    // n: int -> numero di elementi di x

    // n = sizeof(x)/sizeof(int); non da il risultato giusto
    // il compilatore non sa quanti elementi ci sono in x, perche' il suo tipo e' incompleto in quanto manca la lunghezza dell'array
    // il tipo di x si dice incompleto perche' a int x[] manca la lunghezza dell'array

	int somma = 0;
	
    // sizeof(x) in questo caso e' equivalente a scrivere sizeof(int *x)
	printf("sizeof(x) = %d\n", sizeof(x));
	
	for(int  i = 0; i < n; i++){
		somma += x[i];
	}
	
	return somma;
}


// versione errata della funzione
int somma2(int x[]){
	int somma = 0;
	
	//int na = sizeof(x)/sizeof(int);
	
	printf("sizeof(x) = %d\n", sizeof(x));
	
	for(int  i = 0; i < N; i++){
		somma += x[i];
	}
	
	return somma;
}

int *somme_parziali(int x[], int n){
	/*
	 * ritorna un int s[n] tale che s[i] = x[0]+x[1]+...+x[i]
     * ritorna un array s dove ogni elemento s[i] e' la somma di di tutti gli elementi di x fino all'elemento numero i
     */
    // crea un array lungo come x
    int i, s[n], somme = 0;
    
    for( i = 0; i < n; i++){
        somme += x[i];
        s[i] = somme;
    }
    
    return s; // non va bene, ritorna l'indirizzo di una variabile locale
}
```