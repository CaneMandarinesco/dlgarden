## algoritmi di ricerca
si intende che cerchiamo elementi che hanno una qualche proprieta' dentro uno spazio di ricerca.  
in una lista generica abbiamo che:
* caso peggiore: $\Theta(n)$
* caso medio: $O(n)$
secondo la seguente implementazione:

```python
n = ... # valore che mi interessa
for x in a
	if x == n:
		# ho trovato il valore che voglio!
```

> [!warning] attenzion!
> questa sezione e' inaccurata

>[!note] indirezione.
> quando accediamo ad una lista fatta di tipi diversi, per accedere all'elemento che cerchia non facciamo altro che accedere ad un elemento che contiene un riferimento all'oggetto che cerchiamo (questa ricerca puo' ripetersi n volte, dipende da quanti oggetti e come sono disposti nella lista).
> esempio: nella lista voglio arrivare ad `a[3]`, ma magari per arrivare ad alla posizione in memoria di `a[3]` (dato che suppongo che gli elementi in a siano di tipi diversi) devo partire per esempio da `a[0]`, prendere il suo puntatore ad `a[1]`, che punta ad `a[2]` che infine punta ad `a[3]`

> [!note] puntatori
> in python ogni elemento di una lista contiene un puntatore all'elemento successivo!

se vogliamo cercare un elemento nella lista `n` l'unico modo che ho e' scorrere tutti gli elementi finche' non trovo quello che voglio (vedi prima).

### binaria
supponiamo ora che `n` sia una lista ordinata (dal piu piccolo al piu grande) di interi, possiamo migliorare l'algoritmo di prima  in questo modo:
```python
def search(L,e):
	for i in range(len(L)): 
		if L[i] == e:
			return True
		if L[i] > e:
			return false
	return False
```

questa implementazione migliora il tempo medio ma non quello peggiore che rimane comunque: $\Theta(n)$.  possiamo fare di meglio: posso chiedermi se `e` sia piu' grande o piu' piccolo di `L[i]` e a seconda del risultato dell'operazione mi sposto nell'array.

```python
def search(L, e):
	def bin_search(L, e, low, high):
		if high == low:
			return L[low] == e
		mid = (low + high)//2
		if L[mid] == e:
			return True
		elif L[mid] > e:
			if low == mid:
				return False
			else:
				return bin_search(L, e, mid+1, high)
		else:
			return bin_search(L, e, 0, len(L-1))
	if len(L) == 0:
		return False
	else:
		return bin_search(L,e,0,len(L) -1)
```

al caso peggiore la complessità e':
$$
\Theta(\log(n))
$$
il perché: non e' interessante.

## algoritmi di ordinamento
### per selezione

### per fusione