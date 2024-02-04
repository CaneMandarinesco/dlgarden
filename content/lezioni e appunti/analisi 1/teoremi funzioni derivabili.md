## massimi e minimi di una funzione
* $x_{0}$ si dice  punto di massimo **assoluto** in A se: $\forall x \in A: \, f(x)\leq f(x_{0})$ ossia $f(x_{0}) = max \{f(x):x \in A\}$
* $x_{0}$ si dice punto di massimo **relativo** in A se: $\exists r > 0: \forall x \in [I(x_{0},r) \cap{} A$] -> $f(x) \leq f(x_{0})$
* similmente per minimo **assoluto**/**relativo**
## teorema di fermat
sia $f(x)$ una funzione continua in $(a,b)$ e sia $x_{0}$ un punto di **massimo o minimo  relativo** (o anche assoluto), se f e' derivabile in $x_{0}$ allora $f^I(x_{0}) = 0$ ossia $x_{0}$ e' un **punto stazionario**

> [!note] DIM.
> dimostrazione per $x_{0}$ **massimo relativo**.
> andiamo a dimostrare che il massimo relativo ha derivata destra e sinistra e che hanno un'**unica soluzione comune**.
> 
> sicuramente $\exists r>0 \text{ t.c.  } (x_{0}-r,x_{0}+r)$ e' sotto insieme di $(a,b)$ (quindi $x_{0}$ si trova dentro $(a,b)$) ed essendo $x_{0}$ massimo relativo -> $\forall x \in (x_{0}-r, x_{0}+r) \to f(x)\leq f(x_{0})$.
> ora andiamo a studiare il segno del numeratore e del denominatore del **rapporto incrementale** da destra e da sinistra($\frac{f(x_{0}+h)-f(x_{0})}{h}$)in $x_{0}$:
> - per $h\to 0^+$:  $\frac{\leq 0}{+} \text{ ovvero } \leq 0$
> - per $h\to 0^-$: $\frac{\geq 0}{-} \text{ ovvero } \geq 0$
> 
> dato che $f(x)$ e'derivabile in $f(x_{0})$ applichiamo la [[limiti di successioni e di funzioni#3. tipo permanenza del segno|permanenza del segno]] sulla derivata destra e sinistra(???)
> applicando la permanenza del segno sappiamo che :
> - $f^I_{+}(x) \leq 0$ 
> - $f^I_{-}(x) \geq 0$ 
> hanno un'unica soluzione comune ovvero: $f^I(x_{0}) = 0$
> 

## teorema di Bolzano-Weierstrass
se $\{a_{n}\}_{n}$ limitata allora $\exists a_{n_{k}}$  convergente.
ovvero se esiste una successione limitata -> esiste una sua sotto-successione convergente

### teorema di Weierstrass
* [dimostrazione simile a quella del tauraso](https://www.youmath.it/forum/analisi-1/61639-dimostrazione-del-teorema-di-weierstrass.html)
se $f(x)$ e' continua in $[a,b]$ (***COMPATTO***) allora $\exists x_{min} \in [a,b]$ e $\exists x_{max} \in [a,b]$ t.c $\forall x \in [a,b]: f(x_{min}) \leq f(x) \leq f(x_{max})$
ovvero se f e' continua in $[a,b]$ allora esistono un $x_{min}$ (punto di **minimo** in $[a,b]$) e un $x_{max}$ (punto di **massimo** in $[a,b]$) tali che $f(x)$ in $[a,b]$ e' **compresa** tra $f(x_{min})$ e $f(x_{max})$ (ossia $f(x_{min})$ e' **minimo assoluto** in $[a,b]$  e $f(x_{max})$ e' **massimo assoluto** in $[a,b]$

> OSS. $x_{min} \text{ e } x_{max}$ sono i termini n-esimi di una successione $x_{n}$

>[!note] OSS.
> quindi per il [[proprieta' delle funzioni continue#teorema dei valori intermedi|teorema dei valori intermedi]] $f(x)$ e per il teorema di Weierstrass  $f(x)$ assume **tutti i valori** in $[a,b]$ ed ha anche un **massimo** e un **minimo** **assoluto** in $[a,b]$

>[!note] DIM.
> consideriamo $M = sup \{f(x_{n}), \forall x \in [a,b]\}$ (valore massimo di $f(x)$ in $[a,b]$)
> per dimostrare che esiste un **massimo assoluto**, bisogna far vedere che $M$ non puo essere $+\infty$.
>
> per $M = +\infty$, vuol dire  che in un qualsiasi intorno di $+\infty$, $f(x_{n})$ e' compresa in $(n, +\infty)$ e quindi $f(x_{n}) > n$. dato che noi stiamo studiando $f(x_{n})$ in $[a,b]$, $x_{n}$ in $[a,b]$ e limitata e per **Bolzano-Weierestrass** esiste un $x_{n_{k}}$ che **converge**
> 




