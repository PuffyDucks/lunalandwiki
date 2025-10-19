3Blue1Brown video about convolution that I like: https://www.youtube.com/watch?v=KuXjwB4LzSA

**Impulse Response**
In an *LTI* system, the *impulse response* is the output, $y[n]$, of the system given an input of $x[n]=\delta[n]$. The impulse response of a system characterizes it such that the system output is the *convolution* between the input and the impulse response:
$$
y[n] = x[n]*h[n]
$$
**Discrete Convolution**
> [!tip] Reminder
> Convolution is *commutative*! That means $(x*h)[n] = (h*x)[n]$.

$$
(x*h)[n] = \sum_{k=-\infty}^{\infty} x[k] \, h[n-k]
$$
> [!Example] Polynomial Convolution Example
> $x[n]=3\delta[n]+2\delta[n-1]$
> $h[n]=4\delta[n]-\delta[n-2]$
> 
> Convert $a_n\delta[n-k]\;\Rightarrow\;a_nx^k$, then multiply
> $(3+2x)(4-x^2)=12+8x-3x^{2}-2x^{3}$
> 
> Convert back
> $(x*h)[n]=12\delta[n]+8\delta[n-1]-3\delta[x-2]-2\delta[x-3]$

**Graphical Methods**
uh im too lazy to draw this one out rn... go look at lecture 4 or something

**Z-Transform**
The Z-transform converts discrete signals from the time domain to the complex frequency domain (aka the $z$-domain).
$$
X(z) = \sum_{n=-\infty}^{\infty} x[n]z^{-n}
$$
Taking the Z-transform of the impulse function, $h[n]\Rightarrow H(z)$, is called the *transfer function*. Instead of using convolution, like so: 
$$
y[n]=(x*h)[n],
$$
we can instead multiply the input's Z-transform with the transfer function:
$$
Y(z)=X(z)H(z)
$$
> [!Example] Z-Transform Example
> Given equations:
> $x[n]=3\delta[n]+2\delta[n-1]$
> $h[n]=4\delta[n]-\delta[n-2]$
>
> The Z-transforms give us:
> $X(z)=3+2z^{-1}$
> $H(z)=4-x^{-2}$
>
> Then, $Y(z)=X(z)H(z)=12+8x^{-1}-3x^{-2}-2x^{-3}$
>
> Transforming back, we get: 
> $y[n]=(x*h)[n]=12\delta[n]+8\delta[n-1]-3\delta[x-2]-2\delta[x-3]$



> [!Example] Geometric Series Example
> **Find the impulse function for the system $y[n]=\dfrac{1}{6}y[n-1]+\dfrac{1}{6}y[n-2]+x[n]-2x[n-1]$** .
> We start off by putting the equation in standard form:
> $$
> y[n]-\dfrac{1}{6}y[n-1]-\dfrac{1}{6}y[n-2]=x[n]-2x[n-1].
> $$
> Then, using Z-transform's time-shifting property $z^{-k}X(z)\xleftrightarrow{\mathcal{Z}^{-1}}x[n-k]$, the equation can be represented in the $z$-domain:
> $$
> Y(z)-\dfrac{1}{6}z^{-1}Y(z)-\dfrac{1}{6}z^{-2}Y(z)=X(z)-2z^{-1}X(z).
> $$
> We can then organize this equation to solve for the transfer function:
> $$
> \begin{align*}
> H(z)&=\dfrac{Y(z)}{X(z)} \\
> &=\dfrac{1-2z^{-1}}{1-\dfrac{1}{6}z^{-1}-\dfrac{1}{6}z^{-2}}\\
> &=\dfrac{z-2z}{z^{2}-\dfrac{1}{6}z-\dfrac{1}{6}}\\
> &=\dfrac{z-2z}{\left(z+\dfrac{1}{3}\right)\left(z-\dfrac{1}{2}\right)}.
> \end{align*}
> $$
> This can be rewritten using partial fraction decomposition:
> > [!FAQ]+ Partial Fraction Decomposition Review!
> > We want to rewrite the fraction as a sum:
> > $$
> > \begin{align*}
> > H(z)= \dfrac{z^{2}-2z}{\left(z+\dfrac{1}{3}\right)\left(z-\dfrac{1}{2}\right)}=\dfrac{A}{z+\dfrac{1}{3}}+\dfrac{B}{z-\dfrac{1}{2}}
> > \end{align*}
> > $$
> > Multiply both sides with $\left(z+\dfrac{1}{3}\right)\left(z-\dfrac{1}{2}\right)$ to get:
> > $$
> > \begin{align*}
> > z^{2}-2z=A\left(z-\dfrac{1}{2}\right)+B\left(z+\dfrac{1}{3}\right).
> > \end{align*}
> > $$
> > When $z=-\dfrac{1}{3}$, $B$ gets cancelled out and we can solve for $A$:
> > $$
> > A=\dfrac{z^{2}-2z}{z-\dfrac{1}{2}}=-\dfrac{14}{15}.
> > $$
> > Similarly, when $z=\dfrac{1}{2}$, we can solve for B:
> > $$
> > B=\dfrac{z^{2}-2z}{z+\dfrac{1}{3}}=-\dfrac{9}{10}.
> > $$
> > We can plug these values back into the above equation.
> $$
> \begin{align*}
> H(z)&=\dfrac{-\dfrac{14}{15}}{1+\dfrac{1}{3}z^{-1}}+\dfrac{-\dfrac{9}{10}}{1-\dfrac{1}{2}z^{-1}} \\
> &=-\dfrac{14}{15}\dfrac{1}{z^{2}+\dfrac{1}{3}z}-\dfrac{9}{10}\dfrac{1}{z^{2}-\dfrac{1}{2}z}
> \end{align*}
> $$
> Finally, using the transform $\dfrac{1}{1-az^{-1}}\xleftrightarrow{\mathcal{Z}^{-1}}a^nu[n], \quad\text{ROC: }|z|>|a|$,
> $$
> \boxed{h[n]=\dfrac{14}{5}\left(-\dfrac{1}{3}\right)^nu[n]-\dfrac{9}{3}\left(\dfrac{1}{2}\right)^nu[n], \quad\text{ROC: } \lvert z\rvert > \left\lvert\dfrac{1}{2}\right\rvert }
> $$
