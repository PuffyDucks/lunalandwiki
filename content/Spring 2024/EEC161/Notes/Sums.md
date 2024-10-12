## Expected value
For $W_n=X_1+\cdots+X_n$,  
$E[W_n]=E[X_1]+E[X_2]+\cdots+E[X_n]$
## Variance
$Var[W_n]=\sum\limits_{i=1}^nVar[X_i]+2\sum\limits_{i=1}^{n-1}\sum\limits_{j=i+1}^nCov[X_i,X_j]$

When no correlation between $X_1,\dots,X_n$,  
$Var[W_n]=Var[X_1]+\cdots+Var[X_n]$
## Sum theorems
The sum of Poisson random variables $W=K_1+\cdots+K_n$ is a Poisson random variable  
The sum of Gaussian random variables $W=K_1+\cdots+K_n$ is a Poisson random variable  
The sum of iid exponential random variables $W=X_1+\cdots+X_n$ has Erlang PDF:   
$f_W(w)=\begin{cases} \dfrac{\lambda^nw^{n-1}e^{-\lambda w}}{(n-1)!} & w\geq0, \\ 0 & \text{otherwise} \end{cases}$

$E[R]=E[N]E[X]$
$Var[R]=E[N]Var[X]+Var[N](E[X])^2$  

___

< [[Spring 2024/EEC161/Notes/Conditional Probability Models|Conditional Probability Models]] | Current Page | [[Spring 2024/EEC161/Notes/Moment Generating Function|Moment Generating Function]] >