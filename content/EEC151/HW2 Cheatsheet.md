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
