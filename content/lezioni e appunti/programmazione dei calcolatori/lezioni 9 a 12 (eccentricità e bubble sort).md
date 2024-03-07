``` python
N = ['B', 'A', 'D', 'F', 'E', 'C'] # nomi dei punti
P =             [2, 0, 6, 9, 7, 3] # valori dei punti

n = len(N)

# eccentricita
E = []

# calcolo le eccentricita' per ogni punto
for x in P:
	ecc_x = 0
	for y in P: # mi calcolo tutti i valori dei punti medi
				# e mi tengo il piu grande
		if abs(x-y) > ecc_x:
			ecc_x = abs(x-y)
	# ho trovato il punto midio piu grande, lo metto in E
	E.append(ecc_x) # O(1) caso medio / al caso medio impiega meno di O(1)
# Theta(n*n)

C = []
m = None

i = 0
while i < len(E):
	e = E[i]
	if e == m:
		C.append(N[i])
	elif m == None or e < m: # m e' nullo si verifica alla
							 # prima iterazione
		m = e
		C = [ N[i] ]
	i += 1
# Theta(n)

# complessita temporale e' Theta(n + n*n) ovvero Theta(n*n)
# complessita spaziale: Theta(n), la dimensione di E
```

...