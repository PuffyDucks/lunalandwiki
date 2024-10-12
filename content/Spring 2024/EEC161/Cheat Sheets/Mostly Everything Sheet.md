### Experiment
procedure and experiment of uncertainty
### Outcome
observation of experiment
### Sample space
set of all possible outcomes for experiment
### Event
set of outcomes of experiment
### Complement
Elements of $S$ not in $A$ is $A^{c}$ 
$S^c=\varnothing$
### Mutually exclusive
Sets share no element
### Collectively exhaustive sets
Sets make up all of $S$
### Partition
Both mutually exclusive and collectively exhaustive
$P[\varnothing]=0$

$A\perp B$ if and only if $P[A\cap B]=P[A]P[B]$
### Mutual independence
Every combination of events from collection are independent.  
### Permutation
Number of ways to choose $r$ objects out of $n$, where order matters.
$_nP_r=\dfrac{n!}{(n-r)!}$
### Combination
Number of ways to choose $k$ objects out of $n$, where order does not matter. 

$_nC_k=\dbinom{n}{k}=\dfrac{(n)_k}{k!}=\dfrac{n!}{k!(n-k)!}$ 

For $n$ repetitions of sub-experiment with sample space $S=\{s_0,\cdots,s_{m-1}\}$, number of length $n=n_0+\dots+n_{m-1}$ observation sequences with $s_i$ appearing $n_i$ times 

$\dbinom{n}{n_0,\cdots,n_{m-1}}=\dfrac{n!}{n_0!n_1!\cdots n_{m-1}!}$

$P[E_{n0},\dots,n_{m-1}]=\binom{n}{n_0,\dots,n_{m-1}}p_0^{n_0}\dots p_{m-1}^{m-1}$
### PMF - Probability Mass Function
$P_X(x)=P[X=x]$ 
$P_Y(y)=\sum\limits_{x:g(x)=y}P_X(x)$
### PDF - Probability Density Function
$f_X(x)=\dfrac{dF_X(x)}{dx}$
### CDF - Cumulative Distribution Function
$F_X(x)=P[X\leq x]$
### Expected value
$E[X]=\int\limits^{\infty}_{-\infty}xf_X(x)dx$

$E[g(X)]=\int\limits^{\infty}_{-\infty}g(x)f_X(x)dx$

$E[aX+b]=aE[X]+b$

$E[W_n]=E[X_1]+E[X_2]+\cdots+E[X_n]$
### Variance
$Var[X]=E[(X-\mu_x)^2]=E[X^2]-\mu^2_X$

$Var[X+Y]=Var[X]+Var[Y]+2Cov[X,Y]$

$Var[aX+b]=a^2Var[X]$

$Var[W_n]=\sum\limits_{i=1}^nVar[X_i]+2\sum\limits_{i=1}^{n-1}\sum\limits_{j=i+1}^nCov[X_i,X_j]$
### Standard deviation
$\sigma_X=\sqrt{Var[X]}$
### Correlation
$r_{X,Y}=E[XY]$
### Covariance
$Cov[X,Y]=E[(X-\mu_x)(Y-\mu_y)]=r_{X,Y}-\mu_X\mu_Y$
### Correlation Coefficient
$\rho_{X,Y}=\dfrac{Cov[X,Y]}{\sqrt{Var[X]Var[Y]}}=\dfrac{Cov[X,Y]}{\sigma_X\sigma_Y}$

$-1\leq\rho_{X,Y}\leq1$

For $Y=aX+b$

$\rho_{X,Y}=\begin{cases}-1 & a<0, \\ 0 & a=0, \\ 1 & a>0\end{cases}$

For $X \perp Y$,

$Cov[X,Y]=\rho_{X,Y}=0$

$E[g(X)h(Y)]=E[g(X)]E[h(Y)]$

$r_{X,Y}=E[XY]=E[X]E[Y]$

For $W=g(X,Y)$,

$P_W(w)=\sum\limits_{(x,y):g(x,y)=w}P_{X,Y}(x,y)$

$f_W(w)=\dfrac{dF_W(w)}{dw}$

$F_W(w)=P[W\leq w]=\iint\limits_{g(x,y)\leq w}f_{X,Y}(x,y)dxdy$

For $W=X+Y$,

$f_W(w)=\int\limits_{-\infty}^{\infty}f_{X,Y}(x,w-x)dx=\int\limits_{-\infty}^{\infty}f_{X,Y}(w-y,y)dy$
### Bayes' theorem
$P[B|A]=\dfrac{P[A|B]\,P[B]}{P[A]}$

$P[C|B]=\int_{C}f_{X|B}(x)dx$

$E[X]=\sum\limits_{i=1}^mE[X|B_i]P[B_i]$

$E[E[X|Y]]=E[X]$

If $X\perp Y$,

$E[X|Y=y]=E[X]$

$E[Y|X=x]=E[Y]$

$P_{X,Y}(x,y)=P_{Y|X}(y|x)P_X(x)=P_{X|Y}(x|y)P_Y(y)$

$f_{X,Y}(x,y)=f_{Y|X}(y|x)f_X(x)=f_{X|Y}(x|y)f_Y(y)$

For random sum of iid $R=X_1+\dots+X_N$,

$E[R]=E[N]E[X]$

$Var[R]=E[N]Var[X]+Var[N](E[X])^2$
### Moment generating function(MGF)
$\phi_X(s)=E[e^{sX}]$

For $Y=aX+b$,

$\phi_Y(s)=e^{sb}\phi_X(as)$

$\phi_W(s)=\phi_{X_1}(s)\phi_{X_2}(s)\cdots\phi_{X_n}(s)$

For random sum of iid random variables $R=X_1+\cdots+X_N$ and independent non-negative random integer N,

$\phi_R(s)=\phi_N(ln(\phi_X(s))$

### nth moment
$E[X^n]=\dfrac{d^n\phi_X(s)}{ds^n}\biggr\vert_{s=0}$E[Y|X=x]=E[Y]$
### Central limit theorem
For iid random variables $X_1,X_2,\dots,$ 

the CDF of $Z_n=\dfrac{\sum\limits^n_{i=1}X_i-n\mu_X}{\sqrt{n\sigma^2_X}}$ has property $\lim\limits_{n\to\infty}F_{Z_n}(z)=\Phi(z)$

For sum of iid random variables $W_n=X_1+\dots+X_n$, an approximation of its CDF's central limit theorem is

$F_{W_n}(w)\approx\Phi\left(\dfrac{w-n\mu_X}{\sqrt{n\sigma^2_X}}\right)$
### De Moivre–Laplace Formula
For binomial $K$,

$P[k_1\leq K\leq k_2]\approx\Phi\left(\dfrac{k_2+0.5-np}{\sqrt{np(1-p)}}\right)-\Phi\left(\dfrac{k_1-0.5-np}{\sqrt{np(1-p)}}\right)$
