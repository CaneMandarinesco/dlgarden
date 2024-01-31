# lez 1
* introduzione con gli scacchi

# lez 2: radice quadrata 
```python
x = input('Immetti un numero')
x = float(x)
g = x
# print(type(g)) mostra il tipo di g

while abs(g*g - x) > 0.00001: 
	print(g)
	g = 0.5*(g+x/g)

messaggio = "la radice quadrata di x e': "
print(messaggio, x)
```

codice per approssimare un numero x alla sua radice
non e' importante capire come funziona perche' non lo so manco io. 
`g = 0.5*(g+x/g)` dovrebbe essere un modo per fare la media pesata o qualcosa del genere

# lez 3
```python
x = input('Digita un intero: ')
x = int(x)

if x%2 == 0:
    print(x, 'è pari e', x,  '= 2*', x//2)
else:
    print(x, 'è dispari e', x,'= 2*', x//2, '+ 1')
```
* `%` -> resto della divisione tra due numeri
* `//` -> divisione intera, senza virgola

# lez 4: confronto tra stringhe e funzioni
```python

```