https://www.youtube.com/watch?v=h63XAsLEOtk
* $O(n)$: limite superiore della complessita' dell'algoritmo (caso **peggiore**)
* $\Omega(n)$: limite inferiore della complessita' dell'algoritmo (caso migliore)
* $\Theta(n)$: limite superiore e inferiore della complessita (caso medio)

### es. ricerca sequenziale
con un ciclo controllo tutti gli elementi di una lista (`a`) finche' non trovo il valore che cerco (`x`):
```python
for i=1 to n:
	if a[i] = x:
		return i
```
* $T(n) = \Omega(1)$ (caso migliore)
* $T(n) = O(n)$ (caso peggiore)
* $T(n) = \Theta\left( \frac{n+1}{2} \right)$ dove $\frac{n+1}{2}$ e' stato trovato scomponendo la somma delle varie possibilita' delle posizioni di x: $\frac{1+2+3+4+\dots+n}{n}$ si ricava la sommatoria e si trova il risultato

### logaritmico
la complessità e' logaritmica quando la dimensione dell'input diminuisce di un fattore multiplo costante, esempio: ricerca binaria (gli elementi devono essere ordinati!).
```python
def ricerca_binaria(elementi, target):
	primo = 0
	ultimo = len(elementi) - 1
	trovato = False
	while primo <= ultimo and not trovato:
		intermedio = (primo + ultimo) // 2
		if elementi[intermedio] == target:
			trovato = True
		else:
			if target < elementi[intermedio]:
				primo = intermedio + 1
			elif target > elementi[intermedio]:
				ultimo = intermedio - 1
	return trovato
```
in questo algoritmo a