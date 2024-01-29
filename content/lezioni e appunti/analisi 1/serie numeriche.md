[materiale tauraso](https://www.mat.uniroma2.it/~tauraso/aa2324/an1-lezione27.pdf)
[video](https://www.youtube.com/watch?v=dF_hyMKu_tA)
definzione: 
$$
\sum_{k=k_0}^{\infty} a_{k} = \lim_{ n \to \infty } \sum_{k=k_{0}}^{n} a_{k} 
$$
dove: 
* $a_k$ e' il termine generico
* $\sum_{k=k_{0}}^{n} a_{k}$ e' la somma parziale
il risultato puo:
* convergere
* divergere a $\pm \infty$
* essere indeterminato 

Esempi:
$$
\text{(1)  }\sum_{k=1}^{\infty} \frac{1}{10^k} = 0.\overline{1} = \frac{1}{9}
$$
$$
\text{(2)  }\sum_{k=1}^{\infty} 1 = \lim_{ n \to \infty } \sum_{k=1}^{n} 1 = \lim_{ n \to \infty } n = +\infty 
$$
$$
\text{(2)  }\sum_{k=1}^{\infty} (-1)^k = \lim_{ n \to \infty } \sum_{k=0}^{n}(-1)^k = \lim_{ n \to \infty } S_{n} = \nexists
$$
### serie telescopica
$$
S_{n} = \sum_{k=k_{0}}^{n} b_{n}
$$
dove:
$$
b_{n} = a_{n} - a_{n+1}
$$
quindi i termini generati dalla serie si semplificano e **sopravvivono** solo $a_{k_{0}} \text{ e } a_{n+1}$,  la sua somma si calcola cosi:
$$
S_{n} = \sum_{k=k_{0}}^{n} a_{n} - a_{n+1} = a_{k_{0}}- a_{n+1}
$$

**esempio**: 
$$
S_{n} = \sum_{n=1}^{\infty} \frac{1}{n(n+1)} =\frac{1}{n} - \frac{1}{n+1} = 1- \frac{1}{n+1}
$$
trasformando la frazione (usando i **fratti semplici**), la serie ha assunto la forma di una serie telescopica

### serie geometrica
$$
S_{n} = \sum_{k=0}^{n} x^k
$$
vale:
- $n+1$ se $x=1$
- $\frac{1-x^{n-1}}{1-x}$ se $x \neq 1$ (per ricavarlo basta notare che facendo la somma parziale fino ad $n$ e moltiplicando per $(1-x)$ si ottiene il numeratore, quindi basta dividere per $(1-x)$ per ottenere il valore originario) 
e il limite di $a_{n}$ vale (ricordando che nel limite il valore che varia e' $n$):
* $\frac{1}{1-x}$ se $|x| < 1$ perché $x^{n-1} \to 0-$
* $+\infty$ se $x\geq1$
* $\nexists$ se $x \leq -1$
### serie armonica
$$
\sum_{k=1}^{\infty} \frac{1}{k} = +\infty
$$

questo e' un contro esempio per la condizione **necessaria** per la convergenza. in questo caso il fatto che $\frac{1}{k} \to 0$ non e' causa sufficiente per affermare che la serie diverga.
**interpretazione geometrica**: area di un rettangolo
$$
S_{2^n}
$$