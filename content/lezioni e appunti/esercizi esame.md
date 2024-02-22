### es 1 - inversa moltiplicativa
Calcolare e esiste l'inversa moltiplicativa di: 
$$
[48]_{86}
$$
per verificare l'inversa moltiplicativa bisogna costruire una basa sulla funzione **diofantea**:
$$
48x + 86y = 1
$$
cosi facendo, svolgendo A.E. su $48 \text{ e } 86$ bisogna ottenere come $M.C.D$ il valore 1

Algoritmo euclideo: si parte dal numero 86:

$$
86 = (1)48 + 38
$$
$$
48 = (1)38 + 10
 $$
$$
38 = (3)10 + 8
$$
$$
 10 = (1)8 + 2
$$
$$
 8 = (4)2 + 0
$$
$$
2 \neq 1
$$
quindi non esiste una classe di resto tra $[48]_{86}$

### es 2
$$
[129]_{144}
$$
$$
129x + 144y = 1
$$
faccio A.E.
$$
144 = (1)129 +15
$$
$$
129 = (8)15 + 9
$$
$$
15 = (1)9 + 6
$$
$$
9 = (1)6 + 3
$$
$$
6=(2)3 + 0
$$
quindi non esiste

### es 3
$$
[56]_{97}
$$

$$
56x + 97y = 0
$$
$$
97 = (1)(56) + 41
$$
$$
56 = (1)41 + 15
$$
$$
41 = (2)15 + 11
$$
$$
15 = (1)11 + 4
$$
$$
11 = (2)4 + 3
$$
$$
4 = (1)3 +1
$$
> dove: $+1$ e' il **massimo comune divisore**
$$
3 = 1(3) + 0
$$
ora si usa l'identita' di **bezut**, porto $+1$ a sinitra e il $4$ a destra:
$$
 1 = 4 - (1)3
$$
$$
M.C.D. = 1 = 4-(1)3
$$
ora sostituisco il 3:

$$
1 = 4 -(1)3 \to 1 =4 -(1)(11 - 2(4))$$
$$
1 = 4-(1)11 + 2(4) = (3)4-1(11)
$$
> raccolgo i 4, quindi

$$
1 = 4(1+2) - 1(11)
$$