## forme $1^\infty$
### es 7
$$
\lim_{ x \to \infty } \left( 1+\frac{x}{2x^2+1} \right)
^{3x} = 1^\infty
$$
$$
\lim_{ x \to \infty } \left( 1+\frac{1}{\frac{2x^2+1}{x}} \right)^{[(2x^2+1)/x][x/(2x^x+1)][3x]} = \exp\left( \frac{x}{2x^2+1}3x \right) = e^{3/2} = \sqrt{ e^3 }
$$

### es 8
$$
\lim_{ x \to \infty } \left( \frac{x^3-x-1}{x^3-5x+6} \right)^x
$$
riscrivendo: $x^3-x-1$ come $x^3-5x+6 + 4x - 7$ spezzo la frazione in due somme e ho che:
$$
= \lim_{ x \to \infty } \left( \frac{x^3-5x+6 + 4x - 7}{x^3-5x+6} \right)^x = \left(1+\frac{4x-7}{x^3-5x+6} \right)^x  = \left( 1+\frac{1}{\frac{x^3-5x+6}{4x-7}} \right)^x
$$

$$
=  \left( 1+\frac{1}{\frac{x^3-5x+6}{4x-7}} \right)^{x[\frac{x^3-5x+6}{4x-7}][\frac{4x-7}{x^3-5x+6}]} = e^{x[\frac{4x-7}{x^3-5x+6}]} = 1
$$
## esercizi generali
### es 1
$$
\lim_{ x \to 0 } \frac{2\cos x + x^2-2}{x^4} = \frac{0}{0}
$$
con Hospital:
$$
= \lim_{ x \to 0 } \frac{-2\sin +2x}{4x^3} = \frac{2 -2 \cos x}{12x^2} = \frac{2}{2}\frac{1-\cos x}{6x^2} = \frac{1}{6} \frac{1-\cos x}{x^2} = \frac{1}{12}
$$
con Taylor:
$$
\cos x = 1 - \frac{x^2}{2} + \frac{1}{24}x^4 + o(x^2)
$$
$$
2\cos x = 2 - x^2 + \frac{1}{12}x^4 o(x^4)
$$ 
allora:
$$
\lim_{ x \to 0 } \frac{2-x^2+\frac{1}{12} x^4 + x^2 -2}{x^4} = \frac{1}{12}
$$