---
aliases:
  - correlation
  - covariance
  - correlation coefficient
---
## Correlation
$r_{X,Y}=E[XY]$
## Covariance
$Cov[X,Y]=E[(X-\mu_x)(Y-\mu_Y)]=r_{X,Y}-\mu_X\mu_Y$
## Correlation Coefficient
$\rho_{X,Y}=\dfrac{Cov[X,Y]}{\sqrt{Var[X]Var[Y]}}=\dfrac{Cov[X,Y]}{\sigma_X\sigma_Y}$ 
$-1\leq\rho_{X,Y}\leq1$

For $Y=aX+b$  
$\rho_{X,Y}=\begin{cases}-1 & a<0, \\ 0 & a=0, \\ 1 & a>0\end{cases}$

## Relevant Theorems
$Var[X+Y]=Var[X]+Var[Y]+2Cov[X,Y]$

For $X=Y$, $Cov[X,Y]=Var[X]=Var[Y]$ and $r_{X,Y}=E[X^2]=E[Y^2]$
## Independent Random Variable Theorems
For $X \perp Y$,  
$Var[X+Y]=Var[X]+Var[Y]$

$E[g(X)h(Y)]=E[g(X)]E[h(Y)]$
$r_{X,Y}=E[XY]=E[X]E[Y]$
$Cov[X,Y]=\rho_{X,Y}=0$

___

< [[Spring 2024/EEC161/Notes/Pairs of Random Variables|Pairs of Random Variables]] | Current Page | [[Spring 2024/EEC161/Notes/Gaussian Random Variables|Gaussian Random Variables]] >