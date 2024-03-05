link utili:
* [freecodecamp.org](https://www.freecodecamp.org/news/big-o-cheat-sheet-time-complexity-chart/)
* [cs dojo yt video](https://www.youtube.com/watch?v=D6xkbGLQesk
* [complessita di array e liste](https://yourbasic.org/algorithms/time-complexity-arrays/)

sia, per esempio, `a = [1,4,3,2, ..., 10]` e definiamo una funzione che restituisca la somma di tutti gli elementi in `a`, utilizzando un generico linguaggio di programmazione:
```python
def find_sum(a):
	total=0
	for each i in a:
		total += 1
	return total
```

ci chiediamo: *quanto tempo ci vuole per eseguire questo codice?*  
la risposta a questa domanda dipende da moltissimi fattori.  
possiamo domandarci invece: *come cresce il carico di lavoro di questa funzione?*  

### big-o notation e time complexity (notazione o-grande e complessità temporale)
consideriamo la funzione di prima (da implementare in python):
```python
def find_sum(a):
	total=0
	for each i in a:
		total += 1
	return total
```

l'array in input potrebbe avere **grandezze diverse**, per esempio:
* `a = [5,7,9,7,8]`, a ha grandezza 5 (contiene 5 elementi)
* `a = [1,7,4,6,3,7,9,6,8,0]`, a ha grandezza 10 (contiene 10 elementi)

> sia quindi $n$ il numero di elementi nell'array della funzione.

se analizziamo il **tempo di esecuzione** (ordinata, asse y) al variare del **numero di elementi** (ascissa, asse x)
![[Pasted image 20240227215606.png]]
> notiamo che la funzione ha un andamento **lineare**. quindi diremo che la funzione ha **complessità temporale lineare** (ovvero complessità $n$)

non sempre e' cosi, per esempio la complessità temporale potrebbe essere di altri tipi, per esempio:
* **costante**, quando non dipende da $n$
* **quadratica**, quando cresce molto più velocemente di $n$.

cosa significa che **quadratica** cresce molto più velocemente di $n$? per rispondere andiamo ad introdurre la *notazione matematica* (big-o notation):
* **tempo lineare**, può' essere espresso come: $O(n)$ (o-grande di $n$, dove come prima, $n$ e' la grandezza dell'array)
* **tempo costante**: $O(1)$
* **tempo quadratico**: $O(n^2)$

in un espressione matematica, come possiamo individuare il termine che cresce più velocemente?  
prendiamo in considerazione:
$$
T = an+b
$$
dato che $n$ e' un termine che da molto piccolo, **può diventare molto** grande, abbiamo che $an$ cresce sicuramente più di $b$, che invece e' un **termine costante**. possiamo quindi trascurare $an$, ora possiamo anche trascurare il **coefficiente** di $n$, ovvero $a$. quindi ci rimane solo $n$.

> per una definizione più rigorosa di o-grande studia matematica discreta.

seguendo le stesse regole di prima possiamo analizzare:
$$
T = cn^2 + dn + e
$$
dove come prima possiamo trascurare la $e$, e i coefficienti delle $n$, abbiamo quindi:
$$
T = n^2 + n
$$
ora dobbiamo chiederci: *man mano che $n$ diventa sempre più grande, qual'e' il termine che cresce "più velocemente"?* ovviamente $n^2$ quindi possiamo trascurare tutti gli altri termini "più lenti", abbiamo infine che:
$$
T = n^2
$$
> non importano quali siano i valori dei coefficienti, in generale per qualsiasi coefficiente, $n^2 > n$ (basta confrontare i grafici delle due funzioni)

analizziamo un po' di funzioni:

```python
def stupid_function(array):
	total = 0
	return total
```
per qualsiasi valore noi diamo ad array, la funzione esegue sempre lo stesso numero di operazioni, *quindi la complessità temporale e':* $O(c)$, $c$ può essere visto come $c \cdot 1$, quindi togliendo $c$ abbiamo che: $O(c) = O(1)$
che vale in generale per qualsiasi numero $c$.

ipotizziamo ora di avere due funzioni che **facciano la stessa cosa**, ma che sono state implementate in modo tale che, una venga eseguita in tempo: $O(1)$, e l'altra in tempo: $O(n)$. la *funzione migliore e' quella che impiega meno tempo per essere eseguita*, e dato che $O(1)$ vuol dire che la funzione viene eseguita in tempo costante, possiamo facilmente rispondere alla domanda.

come decidiamo qual'e' il tempo di esecuzione di una funzione? prendiamo come esempio:
```python
def find_sum(array):
	total = 0 # -> O(1)
	for each i in array:
		total += i # -> O(1)
	return total # -> O(1)
```

poniamo che ogni singola operazione sia eseguita in tempo: $O(1)$.
ora pero' l'operazione `total += i`  si trova dentro un loop che viene reiterato $n$ volte ($n \cdot O(1) = O(n)$). quindi volendo riscrivere la complessità temporale di questa funzione come formula avremo che:
$$
T = O(1) + n\cdot O(1) + O(1)
$$
semplificando secondo l'algebra degli o-grandi:
$$
T = O(n)
$$

ora sia `array_2d` un array definito in questo modo:
```python
# n = 3
array_2d = [[1,4,3],
			[3,1,9],
			[0,5,2]]
# es n= 4
array_2d = [[1,4,3,1],
			[3,1,9,4],
			[0,5,2,6],
			[4,5,7,8]]
# ecc...
```
quindi `array_2d` contiene $n$ elementi e a sua volta ogni elemento di $n$ contiene altri $n$ elementi. prendiamo in considerazione la seguente funzione che faccia la somma di tutti gli elementi in `array_2d`

```python
def find_sum_2d(aray_2d):
	total = 0 # O(1)
	for each row in array_2d:
		for each i in row:
			total += i # O(1)
	return total # O(1)
```

dove similmente a prima abbiamo: $T = n \cdot n \cdot O(1)$ ovvero:
$$
 T= O(n^2)
$$
## operazioni sugli array
in generale in un array:
* posso scrivere e leggere dati in **tempo costante**
* ma *aggiungere, togliere e cercare dati può essere dispendioso*

### array dinamici
un array dinamico e' un tipo di array che e' in grado di *cambiare grandezza in base all'occorrenza*. all'inizio ha una grandezza fissata, se lo spazio dovesse poi risultare **insufficiente** viene creata automaticamente una copia con più spazio del nostro array.
quindi per riassumere possiamo avere:
* *tempo costante nel caso migliore*: abbiamo ancora spazio nell'array
* *tempo lineare nel caso peggiore*: non abbiamo spazio, dobbiamo ricreare l'array da 0 e copiare al suo interno ogni singolo elemento ($n$ elementi).
### operazioni dispendiose nelle liste
aggiungere e rimuovere elementi in un punto della lista può risultare più o meno dispendioso dato che, dopo un inserimento, tutti gli elementi dopo l'indice di inserimento devono essere spostati in avanti. similmente succede la stessa cosa quando scansioniamo una lista per cercare un elemento, ovvero controlliamo ogni singolo elemento della lista.

> [!note] SUM.
> quindi al caso **peggiore** la complessità temporale di un'operazione del tipo add/remove/search e' $O(n)$, ovvero:
> - se facciamo un add, può essere che dobbiamo spostare tutti gli elementi della lista in avanti di un posto
> - se facciamo un search, dobbiamo scorrere tutta la lista fino alla fine

sia quindi `a` una lista di $n$ elementi, e eseguiamo il seguente codice:
```python
while len(a)>0:
	foo = a.pop(0)
```
la complessità temporale e': $O(n^2)$, perche':
* il loop viene eseguito $n$ volte
* `a.pop(o)` viene eseguito al caso peggiore in tempo $O(n)$

lista di operazioni dispendiose:

| codice          | tempo al caso peggiore                     |
| --------------- | ------------------------------------------ |
| `a.insert(i,x)` | $n-i$ ovvero finché non trovo l'indice $i$ |
| `a.pop(i)`      | $n-i$ ovvero finché non trovo l'indice $i$ |
| `del a[i]`      | $n-i$ // // // // // $i$                   |
| `del [i:j]`     | $n-i$ // // // // // $i$                   |
| `a.remove(x)`   | $n$, ovvero finché non trovo x             |
| `a.index(x)`    | $n$, ovvero finché non trovo x             |
