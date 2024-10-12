### Mean
$\mu_X(t)=E[X(t)]$
### Discrete/continuous value process
Discrete if $X(t)$ is always countable set $S_X$; 
### Discrete/continuous time process
Discrete if $X(t)$ only at $t=nT$ for constant $T$, integer $n$
### Auto-correlation
$R_X(t,\tau)=E[X(t)X(t+\tau)]$
### Auto-covariance
$C_X(t,\tau)=R_X(t,\tau)-\mu_X(t)\mu_X(t+\tau)$
### Counting process
$n(t,s)$ is non-decreasing integer, valued $0$ for $t<0$
### Poisson process
For rate $\lambda$, arrivals in interval $N(t_1)-N(t_0)$ is Poisson with expected value $\lambda(t_1-t_0)$. Arrivals in non-overlapping intervals are independent.
### Brownian motion process
$W(0)=0$, and $W(t+\tau)-W(t)\sim\mathcal{N}(0,\sqrt{\alpha\tau})$ independent of $W(t')$ for $t'\leq t$

For $W=[W(t_1),\dots,W(t_k)]'$,  
$f_w(w)=\prod\limits_{n=1}^k\dfrac{1}{\sqrt{2\pi\alpha(t_n-t_{n-1})}}e^{-(w_n-w_{n-1})^2/[2\alpha(t_n-t_{n-1})]}$
### Stationary process
$f_{X(t_1),\dots,X(t_m)}(x_1,\dots,x_m)=f_{X(t_1+\tau),\dots,X(t_m+\tau)}(x_1,\dots,x_m)$  
$\mu_X(t)=\mu_X$  
$R_X(t,\tau)=R_X(0,\tau)=R_X(\tau)$  
$C_X(t,\tau)=R_X(\tau)-\mu^2_X=C_X(\tau)$
### Wide sense stationary
$E[X(t)]=\mu_X$ and $R_X(t,\tau)=R_X(0,\tau)=R_X(\tau)$  
$R_X(0)\geq0$  
$R_X(0)\geq|R_X(\tau)|$  
$R_X(\tau)=R_X(-\tau)$
### Wide sense stationary average power
$R_X(0)=E[X^2(t)]$
### Cross-correlation function
$R_{XY}(t,\tau)=E[X(t)Y(t+\tau)]$
### Jointly wide sense stationary
$X(t)$ and $Y(t)$ wide sense stationary and $R_{XY}(t,\tau)=R_{XY}(\tau)=R_{YX}(-\tau)$

___

< [[Spring 2024/EEC161/Notes/Central Limit Theorem|Central Limit Theorem]] | Current Page | No next page >