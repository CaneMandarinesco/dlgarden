[materiale tauraso](https://www.mat.uniroma2.it/~tauraso/aa2324/an1-lezione27.pdf)
[video](https://www.youtube.com/watch?v=dF_hyMKu_tA)
definzione: 
$$
\sum_{k=k_0}^{\infty} a_{k} = \lim_{ n \to \infty } \sum_{k=k_{0}}^{n} a_{k} 
$$
> la serie di $a_{k}$ (**termine generico della serie**) e' definita come il limite della **somma parziale** per $n\to\infty$

dove il risultato può:
* divergere
* convergere
* essere indeterminato

## esempi

* la serie di $a_{n}=0$ converge a $0$ 
* la serie di $a_{n} = 2$ diverge a $+\infty$
*  la serie di $a_{n} = 2^n$ diverge a $+\infty$
* la serie di $a_{n} = (-1)^n$ e' **indeterminata**: la somma di infiniti 1 e -1 non e' detto che sia 0
	* le somme oscillano tra 1 e 0
		* 1 se n e' pari
		* 0 se n dispari
* la serie di $\sum_{n=0}^{\infty} \left( \frac{1}{2} \right)^n$ corrisponde al calcolo dell'area di un rettangolo (h=1, l=2) tramite la sua scomposizione in triangoli sempre più piccoli. i termini della somma sono: $1 + \frac{1}{2} + \frac{1}{4} + \frac{1}{8} \dots$ 
	* l'area del rettangolo (h=1, l=2) e' 2. quindi la serie converge a 2
	* **SERIE GEOMETRICA**
## operazioni tra serie
$$
\sum_{n=0}^{\infty}\alpha a_{n} + \beta b_{n}
$$
 il risultato:
* **converge** se $a_{n}$ e $b_{n}$ convergono entrambi
* **diverge** se una delle due diverge
* se $a_{n} = +\infty$ e $b_{n} = -\infty$ allora abbiamo una forma indeterminata

riprendendo il caso della serie geometrica:
$$
\sum_{n=0}^{\infty} 2^n = (2-1)\sum_{n=0}^{\infty} 2^n = 2\sum_{n=0}^{\infty} 2^n - 1\sum_{n=0}^{\infty} 2^n = -1
$$
> il risultato non vale perche e' una **forma indeterminata** e inoltre ad intuito e' un assurdo

con $\sum_{n=n_0}^{\infty} a_{n} = \lim_{ n \to \infty } S_{n} = L$ convergente
$$
S_{n+1} - S_{n} = \sum_{n=n_0}^{n+1} a_{k} - \sum_{n=n_0}^{n} a_{k} = a_{n+1}
$$
> per citare il maestro: sopravvive solo l'ultimo elemento

Il limite di questa differenza per $n\to\infty$ vale 0 perche entrambi convergono a $L$
## tipi di  serie
### serie geometrica
e' la potenza di un numero fissato
$$
\sum_{x=x_0}^{+\infty} x^n
$$
> $a$ e' la **ragione**

$$
S_{N} = \sum_{n}^{N} x^n = 1 + n^1 + \dots + n^N
$$
vale $n+1$ se $x=1$
altrimenti per $x \neq 1$
* N = 1: $1+x$ -> moltiplico per $1-x$ -> $1-x^2$
* N = 2: con lo stesso procedimento -> $1-x^3$
* e cosi via...
	* quindi $S_{N} = \frac{(1-x)^{N+1}}{1-x}$
### telescopica 

Esempio di serie telescopica:
$$
S_{n} = \sum_{k=2}^{\infty} \frac{1}{k(k-1)} = \lim_{ n \to \infty } S_{n} = \lim_{ n \to \infty } \left( 1-\frac{1}{n} \right) = 1
$$
Piu' generalmente: 
$$
S_{n} = \sum_{n=1}^{+\infty}(a_{n} - a_{n+k})
$$
e la sua somma vale:  $a_{1} + a_{2} + \dots + a_{k}$
