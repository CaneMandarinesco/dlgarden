## es 1
$$
\sum_{n=2}^{\infty} \frac{n}{e^n}
$$
il termine generale della serie e' infinitesimo.  
posso applicare il **criterio della radice**:
$$
\lim_{ n \to \infty } \sqrt[n]{| \frac{n}{e^n}|} = \lim_{ n \to \infty } \frac{\sqrt[n]{ n}}{e} = \frac{n^{1/n}}{e} = \frac{e^{\frac{1}{n} \log n}}{e} = \frac{1}{e} < 1 \text{ quindi converge}
$$
si poteva anche fare confrontando con la serie: $\frac{1}{e^n} \text{ che e' t.c.} > \frac{n}{e^n}$ 
infatti la serie $\frac{1}{e^n}$ e' una serie geometrica di **ragione**: $\frac{1}{e}$

## es 2
$$
\sum_{n=1}^{\infty} \left( \frac{n}{2} \log\left( \frac{n+1}{n} \right)\right)^n
$$
e' una serie a caratteri positivi? si.
il limite del termine generale e' infinitesimo?
$$
\lim_{ n \to \infty } \left( \frac{n}{2} \log\left( \frac{n+1}{n} \right)\right)^n = \left( \frac{\log\left( \left( 1 + \frac{1}{n} \right)^n \right)}{2} \right)^n = \left( \frac{\log(e)}{2} \right)^n = \lim_{ n \to \infty }  \frac{1}{2^n} = 0 
$$
verificata la convergenza applico il criterio della radice: 
$$
\lim_{ n \to \infty } \sqrt[n]{ \left( \frac{n}{2}\log \left( \frac{n+1}{n} \right) \right)^n } = \frac{n}{2}\log \left( \frac{n+1}{n} \right) = \frac{1}{2} < 1 \text{ quindi converge }
$$
oppure posso usare il confronto asintotico avendo svolto in precedenza il limite so che:
$$
\left( \frac{n}{2} \log\left( \frac{n+1}{n} \right)\right)^n \sim \frac{1}{2^n}
$$
e $\frac{1}{2^n}$ e' una serie geometrica di ragione < 1 quindi converge

## es 3
$$
\sum_{n=1}^{\infty} \sqrt[n]{n+1} - \sqrt[n]{ n }
$$
e' una serie a termini positivi.
studio il limite:
$$
\lim_{ n \to \infty } (\sqrt[n]{n+1} - \sqrt[n]{ n } = \sqrt[n]{ n }\left( \left( 1+\frac{1}{n} \right)^{\frac{n}{n^2}} -1\right) = \sqrt[n]{ n }\left( e^{\frac{1}{n^2}} -1  \right) = \sqrt[n]{ n } \,\frac{n^2\left( e^{\frac{1}{n^2}} -1  \right)}{n^2} = \frac{\sqrt[n]{ n }}{n^2} = n^{\frac{1}{n}-2} =
$$
svolgendo con i limiti notevoli mi viene $\frac{1}{n^2}$, quindi 0.

per confronto asintotico con: $\sum_{n=1}^{\infty} \frac{1}{n^2}$ , la serie data converge

## es 4 
$$
\sum_{n=1}^{\infty} \sqrt{ n }\, lg \frac{2n^2+3}{2n^2+2}
$$
$$
= \lim_{ n \to \infty } \sqrt{ n }\log\left( \frac{n^2}{n^2} \frac{2+\frac{3}{n^2}}{2+\frac{2}{n^2}}\right) = n^{\frac{1}{2}}\left[ \log\left( 2+\frac{3}{n^2} \right) - \log \left( 2+\frac{2}{n^2} \right) \right] 
$$
$$
= \lim_{ n \to \infty }\log \left(2 \left(1 + \frac{3}{2n^2}  \right)^{n/2}\right) - \log \left( 2 \left( 1+\frac{1}{n^2} \right) \right)  = \lim_{ n \to \infty } 2e^{3} - 1
$$