### Family

A categorization of random variables which follow a similar mathematical form, with one or two parameter differences
## Bernoulli (p) random variable
For $0<p<1$,  
$P_X(x)=\begin{cases}1-p &\text{if } x=0, \\ p &\text{if } x=1, \\ 0 &\text{otherwise}\end{cases}$
## Geometric (p) random variable
For $0<p<1$,  
$P_X(x)=\begin{cases}p(1-p)^{x-1} &\text{if } x=1,2,\cdots \\ 0 &\text{otherwise}\end{cases}$
## Binomial (n,p) random variable
For $0<p<1$ and integer $n$ where $n\geq 1$,  
$P_X(x)=\binom{n}{x}p^x(1-p)^{n-x}$
## Pascal (k,p) random variable
For $0<p<1$ and integer $k$ where $k\geq 1$,  
$P_X(x)=\binom{x-1}{k-1}p^k(1-p)^{x-k}$
## Discrete Uniform (k,l) random variable
For integers $k$ and $l$ where $k<l$,  
$P_X(x)=\begin{cases}1/(l-k+1) &\text{if } x=k,k+1,k+2,\cdots,l \\ 0 &\text{otherwise}\end{cases}$
## Poisson ($ɑ$) random variable
Used to model arrival of phenomenon of interest with $\lambda$ arrivals/sec, interval $T$, and $\alpha=\lambda T$.  
For $\alpha>0$,  
$P_X(x)=\begin{cases}\alpha^xe^{-\alpha}/x! &\text{if } x=0,1,2,\cdots, \\ 0 &\text{otherwise}\end{cases}$

___

< [[Spring 2024/EEC161/Notes/Discrete Random Variable Definitions|Discrete Random Variable Definitions]] | Current Page | [[Spring 2024/EEC161/Notes/Cumulative Distribution Function|Cumulative Distribution Function]] >