### tipi di dati numerici
sono supportati: interi, float e complessi
operazioni importanti da ricordare:
* `x//y`: divisione intera. tra interi ritorna intero e tra float ritorna float
* `x%y`: resto della divisione
* `x**y`: x elevato alla y

### float(x)
`float(x)` restituisce un float a partire da un numero o da una stringa.
se l'input e' una stringa può anche essere *NaN* (Not A Number), in quel caso si ottiene un errore di tipo `ValueError`
* per infinito: `float('inf') = inf`
* se il numero e' troppo grande per essere gestito da python abbiamo un `OverflowError`

### es 1. x e' pari o dispari?
```python
if x%2 == 0:
	print(x, ' e\' pari e: ', x, '= 2*', x//2 )
else:
	print(x, ' e\' dispari e: ', x, '= 2*', x//2, '+ 1')
```

### es 2. x e' una vocale?
```python
while i < len(x):
	if x[i] in 'aeiouAEIOU':
		numero_vocali = numero_vocali + 1
```


### es 3. puo' x essere convertito in float?
```python
i = 0
while i < len(x) and ( (x[i] in '0123456789') or (x[i] == "." and numero_punti == 0)):
	if x[i] == ".":
		numero_punti += 1
	i+=1

if i == len(x):
	x = float(x)
else:
	x=0

```

### es 4. sostituire spazi con `_`
```python
x = 'programmazione python e c'
y = ''
n = len(x)

for c in x:
	if c == ' ':
		y = y+'_'
	else:
		y = y+c
```
questo codice viene seguito in tempo **quadratico**, perche' ad ogni iterazione di `c in x`, quando scriviamo `y+carattere` viene creata una copia di y, operazione che in base alla lunghezza di n, puo' essere molto costosa.

### es 5. palindromo
```python
b = ''
for c in a:
	b = c+b

return a == b
```
come nell'esercizio sopra, anche questa e' **quadratica**: $o(n^2)$ 