> [!info] DEF.
>  Una successione reale: $\{a_{n}\}_{n\geq n_{0}}$ e' una funzione che per ogni $n \in N: n \geq n_{0}$ esiste un corrispettivo **reale**: $a_{n}$
# limite di una successione
$$
\lim_{  n \to \infty } a_n = 
$$
* $+\infty$ se $\forall M \in R \text{, } \exists N\geq n_{0}: \forall n > N\text{, }$ $a_{n} > M$$
	* **divergenza**
	* ovvero: per ogni M (un numero grande), esiste almeno un $a_{n}$ più  grande di M
* $-\infty$ se $\forall M \in R\text{, } \exists N\geq n_{0}: \forall n>N, a_{n} < M$
	* **divergenza**
* $\exists l \in R$ se $\forall \epsilon > 0 \text{, } \exists N\geq n_{0}: \forall n>N, |a_{n}-l| < \epsilon$ oppure $l-\epsilon < a_{n} < l+\epsilon$
	* **convergenza**
	* ovvero la **distanza tra $a_{n} \text{ e } l$ e' minore del valore di $\epsilon$** (per un certo $n>N$, quindi non sempre)
* $\nexists$ se altrimenti 
> se $l=0$ abbiamo un infinitesimo

> [!info] OSS.
> il limite di una successione $\{a_{n}\}_{n\geq n_{0}}$ non dipende dal valore di $n_{0}$

# proprietà dei limiti
## 1. unicità
L'operazione del limiti e' un operazione che ha un risultato unico (come 2+2=4 fa sempre 4)
> [!note] DIM.
>  Se per assurdo:  $\lim_{ n \to \infty } a_{n} = L_{1}$ e allo stesso tempo $\lim_{ n \to \infty } a_{n} = L_{2}$
>  Vuole dire che per la definizione di limite convergente valgono:
> - $|a_{n}-L_{1}| < \epsilon$
> - $|a_{n}-L_{2}| < \epsilon$
> 
> Quindi se le unisco insieme (facendo una somma tra i termini a sinistra e i termini a destra) ho che:
> - $|a_{n}-L_{1}| + |a_{n} - L_{2}| < 2\epsilon$
> - e sapendo che: $|a_{n} - L_{1}| = |L_{1} - a_{n}|$
> 	- dato che, per esempio: $|5 - 2| = |2-5| \to 3=|-3|$
> 	- e ancora: $|7-20| = |20-7| \to |-13| = 13$
> 
> usando la **disuguaglianza triangolare** so che: 
> - $|L_{1} - L_{2}| = |L_{1} -a_{n} + a_{n} -L_{2} | < |L_{1}-a_{n}| + |a_{n} - L_{2}| < 2\epsilon$
> - quindi: $|L_{1}-L_{2}| < 2\epsilon \to  \frac{|L_{1}-L_{2}|}{2} <\epsilon$
> 
> contraddizione: se $\epsilon = \frac{|L_{1}-L_{2}|}{2} \to \frac{|L_{1}-L_{2}|}{2} \not<\frac{|L_{1}-L_{2}|}{2}$
> dove: $\frac{|L_{1}-L_{2}|}{2}$ e' sempre un valore  > 0 che rispetta la definizione del limite finito ($\forall \epsilon > 0$)

## 2. successione limitata
Se  il limite di una successione e' limitato(/convergente) **allora** la successione sara limitata. Non vale il viceversa.

## 3. sotto successioni
Il limite di una successione $a_{n}$ esiste allora il limite di tutte le sue sotto successioni $a_{n_{k}}$ hanno lo stesso risultato e:
* $\lim_{ n \to \infty } a_{n}= \lim_{ n \to \infty } a_{n_{k}}$

## 4. permanenza del segno
se il limite diverge a $+\infty$ o converge a un valore > 0 allora: $\exists N: \forall n>N, a_{n} > 0$
> [!note] DIM.
> - supponiamo che: $\lim_{ n \to \infty }a_{n} = l > 0$
> - allora per la definizione abbiamo che:  $|a_{n} - l| > \epsilon$
> - ovvero: $(a_{n}-l < \epsilon < a_{n}+l) \to (l-\epsilon < a_{n} < l+\epsilon)$
> - possiamo dire che $\epsilon = \frac{l}{2} > 0$
> - quindi sostituendo e sommando abbiamo che: $\frac{1}{2}l < a_{n} < l+ \frac{1}{2}l$ 
> - $\frac{1}{2}l$ e' una quantità sicuramente > 0 quindi $a_{n}$ e' sempre compreso tra due numeri > 0

## 5. confronto 
siano $a_{n} \text{ e }b_{n}$ due successioni t.c.  $a_{n} \leq b_{n}$. allora se i limiti di $a_{n} \text{ e } b_{n}$ esistono e sono rispettivamente $l_{1} \text{ e } l_{2}$ **allora** possiamo affermare che $l_{1} \leq l_{2}$
dim. boh

## 6. doppio confronto (carabinieri)
facilissima

## 7. limite di successione limitata per successione infinitesima
sia $a_{n}$ una successione limitata, e $b_{n}$ una successione infinitesima (ovvero che $\lim_{ n \to \infty } b_{n} = 0$) allora l'operazione: $\lim_{ n \to \infty } a_{n} * b_{n} = 0$
> [!note] DIM.
> essendo $b_{n}$ limitata superiormente: $\exists M > 0: \forall n>n_{0}, b_{n} \leq M$: 
> - $|a_{n}|  |b_{n}| < M|a_{n}| < 0$
> - $0 \leq |a_{n} - b_{n}|$
> e per confronto $a_{n}*b_{n} \to 0$


## 8. algebra dei limiti
sono valide le seguenti operazioni: 
* con $\lim_{ n \to \infty } a_{n} =l_{1} \text{ e } \lim_{n \to \infty } b_{n} = l_{2}$
$$
\lim_{ n \to \infty } \frac{a_{n}}{b_{n}} = \frac{l_{1}}{l_{2}}
$$
$$
\lim_{ n \to \infty } a_{n} * b_{N} = l_{1}*l_{2}
$$
$$
\lim_{ n \to \infty } a_{n} + b_{n} = l_{1} + l_{2}
$$

## 9. funzione monotona:
...
## 10. funzioni continue
se una funzione e' continua **allora**:
$$
\lim_{ n \to \infty } f(a_{n}) = f(l)
$$

# numero di nepero
la successione: $\{\left( 1+\frac{1}{n} \right)^n\}_{n\geq 1}$ ed il suo limite a $+\infty$ converge ad $e$ (numero di nepero).  
per dimostrarlo bisogna far vedere 2 cose:
1. stretta crescenza
2. e' limitato superiormente

### 1. stretta crescenza
$$
\forall n \geq 1 
$$