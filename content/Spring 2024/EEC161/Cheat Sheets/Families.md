## Discrete

|                                                                                                           | $P_X(x)$                                                                          | $E[X]$    | $Var[X]$          | $\phi_X(s)$                               |
| --------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- | --------- | ----------------- | ----------------------------------------- |
| **Bernouli (p)**<br>$0<p<1$                                                                               | $\begin{cases}1-p & x=0, \\ p & x=1, \\ 0 &\text{oth.}\end{cases}$                | $p$       | $p(1-p)$          | $1-p+pe^s$                                |
| **Geometric (p)**<br>For $0<p<1$                                                                          | $\begin{cases}p(1-p)^{x-1} & x=1,2,\dots, \\ 0 &\text{oth.}\end{cases}$           | $1/p$     | $(1-p)p^2$        | $\dfrac{pe^s}{1-(1-p)e^s}$                |
| **Binomial (n,p)**<br>$0<p<1$<br>Integer $n\geq 1$                                                        | $\binom{n}{x}p^x(1-p)^{n-x}$                                                      | $np$      | $np(1-p)$         | $(1-p+pe^s)^n$                            |
| **Pascal (k,p)**<br>$0<p<1$ <br>Integer $k\geq 1$                                                         | $\binom{x-1}{k-1}p^k(1-p)^{x-k}$                                                  | $np$      | $k(1-p)/p^2$      | $\left(\dfrac{pe^s}{1-(1-p)e^s}\right)^k$ |
| **Discrete Uniform (k,l)**<br>Integers $k<l$                                                              | $\begin{cases}\dfrac{1}{l-k+1} & x=k,\dots,l \\ 0 &\text{oth.}\end{cases}$        | $(k+l)/2$ | $(l-k)(l-k+2)/12$ | $\dfrac{e^{sk}-e^{s(l+1)}}{1-e^s}$        |
| **Poisson (α)**<br>$\alpha>0$<br>Models $\lambda$ arrivals/sec, interval $T$, and $\alpha=\lambda T$.<br> | $\begin{cases}\alpha^xe^{-\alpha}/x! & x=0,1,\dots, \\ 0 &\text{oth.}\end{cases}$ | $\alpha$  | $\alpha$          | $e^{\alpha(e^s-1)}$                       |
## Continuous

|                                                      | $f_X(x)$                                                                                             | $F_X(x)$                                                                             | $E[X]$               | $Var[X]$               | $\phi_X(s)$                                 |
| ---------------------------------------------------- | ---------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------ | -------------------- | ---------------------- | ------------------------------------------- |
| **Uniform (a,b)**<br>$b>a$                           | $\begin{cases}1/(b-a) &a\leq x<b, \\ 0 &\text{oth.}\end{cases}$                                      | $\begin{cases} 0 & x\leq a, \\ \dfrac{x- a}{b-a} & a<x\leq b, \\ 1 & x>b\end{cases}$ | $\dfrac{b+a}{2}$     | $\dfrac{(b-a)^2}{12}$  | $\dfrac{e^{bs}-e^{as}}{s(b-a)}$             |
| **Exponential (λ)**<br>$\lambda>0$<br>               | $\begin{cases}\lambda e^{-\lambda x} & x\ \geq0, \\ 0 &\text{oth.}\end{cases}$                       | $\begin{cases}1-e^{-\lambda x} & x\geq0, \\ 0 &\text{oth.}\end{cases}$               | $\dfrac{1}{\lambda}$ | $\dfrac{1}{\lambda^2}$ | $\dfrac{\lambda}{\lambda-s}$                |
| **Erlang (n,λ)**<br>$\lambda>0$ <br>Integer $n\geq1$ | $\begin{cases}\dfrac{\lambda^nx^{n-1}e^{-\lambda x}}{(n-1)!} & x\geq0, \\ 0 &\text{oth.}\end{cases}$ | $1-\sum\limits_{n=0}^{k-1}\dfrac{(\lambda x)^ne^{-\lambda x}}{n!}$                   | $\dfrac{n}{\lambda}$ | $\dfrac{n}{\lambda^2}$ | $\left(\dfrac{\lambda}{\lambda-s}\right)^n$ |
| **Gaussian (μ, σ)**<br>$\sigma>0$                    | $\dfrac{1}{\sqrt{2\pi\sigma^2}}e^{-(x-\mu)^2/2\sigma^2}$                                             | $\phi\left(\dfrac{x-\mu}{\sigma}\right)$                                             | $\mu$                | $\sigma^2$             | $e^{s\mu+s^2\sigma^2/2}$                    |
<div style="page-break-after: always;"></div>

## Theorems
For $K_i\sim Pois(\lambda)$ and $W=K_1+\cdots+K_n$, then $W\sim Pois(\lambda)$

For $K_i\sim \mathcal{N}(\lambda)$ and $W=K_1+\cdots+K_n$, then $W\sim \mathcal{N}(\lambda)$

The sum of iid exponential random variables $W=X_1+\cdots+X_n$ has Erlang PDF: 

$f_W(w)=\begin{cases} \dfrac{\lambda^nw^{n-1}e^{-\lambda w}}{(n-1)!} & w\geq0, \\ 0 & \text{otherwise} \end{cases}$

For $K_\alpha\sim Pois(\alpha)$, $X\sim Erlang(n,\lambda)$, and $x>0$,


$F_X(x)=1-F_{K_{\lambda x}}(n-1)=\begin{cases}1-\sum\limits^{n-1}_{k=0}\dfrac{(\lambda x)^ke^{-\lambda x}}{k!} & x\geq0, \\ 0 &\text{oth.}\end{cases}$

## Normal Distributions
$Z=\mathcal{N}(0,1)$

$\phi(z)=F_Z(z)=\dfrac{1}{\sqrt{2\pi}}\int\limits_{-\infty}^{z}e^{-u^2/2}du$

$\phi(-z)=1-\phi(z)$

For $X\sim\mathcal{N}(\mu,\sigma)$ and $Y=aX+b$, $Y\sim\mathcal{N}(a\mu+b,a\sigma)$

Bivariate Gaussian $X$ and $Y$:

Gaussian $r_{X,Y}=0$ if and only if $X \perp Y$

$f_{X,Y}(x,y)=\dfrac{exp\left[-\dfrac{\left(\dfrac{x-\mu_X}{\sigma_X}\right)^2+\dfrac{2\rho_{X,Y}(x-\mu_X)(y-\mu_Y)}{\sigma_X\sigma_Y}+\left(\dfrac{y-\mu_Y}{\sigma_Y}\right)^2}{2(1-\rho^2_{X,Y})}\right]}{2\pi\sigma_X\sigma_Y\sqrt{1-\rho^2_{X,Y}}}$
