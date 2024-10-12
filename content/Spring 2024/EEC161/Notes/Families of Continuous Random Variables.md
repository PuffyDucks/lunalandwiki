## Uniform (a,b) random variable
For $b>a$,  
$f_X(x)=\begin{cases}1/(b-a) &\text{if } a\leq x<b, \\ 0 &\text{otherwise}\end{cases}$

$F_X(x)=\begin{cases} 0 &\text{if } x\leq a, \\ (x-a)/(b-a) &\text{if } a<x\leq b, \\ 1 &\text{if }x>b\end{cases}$

$E[X]=\dfrac{b+a}{2}$

$Var[X]=\dfrac{(b-a)^2}{12}$
## Exponential (λ) random variable
For $\lambda>0$,  
$f_X(x)=\begin{cases}\lambda e^{-\lambda x} &\text{if } x\geq0, \\ 0 &\text{otherwise}\end{cases}$

$F_X(x)=\begin{cases}1-e^{-\lambda x} &\text{if } x\geq0, \\ 0 &\text{otherwise}\end{cases}$

$E[X]=\dfrac{1}{\lambda}$

$Var[X]=\dfrac{1}{\lambda^2}$
## Erlang (n,λ) random variable
For $\lambda>0$ and integer $n\geq1$,  
$f_X(x)=\begin{cases}\dfrac{\lambda^nx^{n-1}e^{-\lambda x}}{(n-1)!} &\text{if } x\geq0, \\ 0 &\text{otherwise}\end{cases}$

$E[X]=\dfrac{n}{\lambda}$

$Var[X]=\dfrac{n}{\lambda^2}$
## Poisson ($\alpha$) random variable $K_\alpha$
$F_X(x)=1-F_{K_{\lambda x}}(n-1)=\begin{cases}1-\sum\limits^{n-1}_{k=0}\dfrac{(\lambda x)^ke^{-\lambda x}}{k!} &\text{if } x\geq0, \\ 0 &\text{otherwise}\end{cases}$

___

< [[Spring 2024/EEC161/Notes/Expected Value of Continuous Random Variables|Expected Value of Continuous Random Variables]] | Current Page | [[Spring 2024/EEC161/Notes/Pairs of Random Variables|Pairs of Random Variables]] >