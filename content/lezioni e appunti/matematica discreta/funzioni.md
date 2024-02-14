# 1.3 applicazioni tra insiemi
siano $A,B$ due insiemi, una **applicazione** da A in B e' una legge che associa ad un elemento un **unico elemento** di B.

> [!note] DEF.
> una applicazione (o funzione o mappa) e' un sottoinsieme $f \subseteq A \times B$ quindi e' un sottoinsieme che per ogni $a \in A$ esiste un unico $b \in B$ tale che: $(a,b) \in f$ che scrive: $f(a)=b$

>[!note] SURIETTIVA
>se $\forall b \in B$ esiste $a \in A$ tale che: $f(a) = b$

> [!note] INIETTIVA
> se $\forall x, y  \in A $ allora se $x\neq y$ allora $f(x) \neq f(y)$]

> [!note] BIUNIVOCA
> se valgono sia la **suriettiva** e **iniettiva**

>[!note] DEF.
> **composizione**: 
> $(g \circ f)(a) = g(f(a))$

## prop 1.3.1
siano $A,B,C$ insiemi, e $f: A\to B$ e $g: B\to C$ allora:
* $f \text{ e } g$ **iniettive** allora $g \circ f$ e' **iniettiva** 
* $f \text{ e } g$ **suriettive** allora $g \circ f$ e' **suriettiva**
* $f \text{ e } g$ **biunivoche** allora $g \circ f$ e' **biunivoca**

> [!note] DIM. INIETTIVA
siano $x,y \in A$, poiche' $f(x) \neq f(y)$ allora dato che vale anche per g (e' **iniettiva**), abbiamo che: $g(f(x)) \neq g(f(y))$

> [!note] DIM. SURIETTIVA 
> sia $c \in C$, poiché $g$ e' **suriettiva** allora $\exists b \in B$ tale che $f(b) = c$, la stessa cosa vale per $f$ quindi $g(f(a)) = g(b) = c$
