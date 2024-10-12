---
aliases:
  - joint CDF
  - joint cumulative distribution function
  - joint probability mass function
  - joint PMF
  - marginal PMF
  - joint PDF
  - marginal PDF
---
## Joint CDF
$F_{X,Y}(x,y)=P[X\leq x,Y\leq y]$
### Theorems
$0\leq F_{X,Y}(x,y)\leq1$  
$F_{X,Y}(\infty,\infty)=1$   
$F_X(x)=F_{X,Y}(x,\infty)$  
$F_Y(y)=F_{X,Y}(\infty,y)$  
$F_{X,Y}(x,-\infty)=0$  
$F_{X,Y}(-\infty,y)$  

For $x\leq x_1$ and $y\leq y_1$,  
$F_{X,Y}(x,y)\leq F_{X,Y}(x_1,y_1)$
## Joint PMF
$P_{X,Y}(x,y)=P[X=x,Y=y]$
## Marginal PMF
For discrete random variables $X$ and $Y$,  
$P_X(x)=\sum\limits_{y\in S_Y}P_{X,Y}(x,y),$  
$P_Y(y)=\sum\limits_{x\in S_X}P_{X,Y}(x,y)$
## Joint PDF
$F_{X,Y}(x,y)=\int\limits_{-\infty}^x\int\limits_{-\infty}^yf_{X,Y}(u,v)dvdu$  
$f_{X,Y}(x,y)=\dfrac{\partial^2F_{X,Y}(x,y)}{\partial x\partial y}$

For event $(X,Y)$ in range $A$,  
$P[A]=\iint\limits_Af_{X,Y}(x,y)dxdy$
## Marginal PDF
$f_X(x)=\int\limits_{-\infty}^{\infty}f_{X,Y}(x,y)dy$  
$f_Y(y)=\int\limits_{-\infty}^{\infty}f_{X,Y}(x,y)dx$
## Independence
Discrete $X\perp Y$ if and only if $P_{X,Y}(x,y)=P_X(x)P_Y(y)$  
Continuous $X\perp Y$ if and only if $f_{X,Y}(x,y)=f_X(x)f_Y(y)$
## Expected Value
For discrete $W=g(X,Y)$,  
$E[W]=\sum\limits_{x\in S_X}\sum\limits_{y\in S_Y}g(x,y)P_{X,Y}{(x,y)}$

For continuous $W=g(X,Y)$,  
$E[W]=\int\limits_{-\infty}^{\infty}\int\limits_{-\infty}^{\infty}g(x,y)f_{X,Y}{(x,y)}dxdy$
## Joint CDF
$F_{X,Y}(x,y)=P[X\leq x,Y\leq y]$
### Theorems
$0\leq F_{X,Y}(x,y)\leq1$  
$F_{X,Y}(\infty,\infty)=1$  
$F_X(x)=F_{X,Y}(x,\infty)$  
$F_Y(y)=F_{X,Y}(\infty,y)$  
$F_{X,Y}(x,-\infty)=0$  
$F_{X,Y}(-\infty,y)$

For $x\leq x_1$ and $y\leq y_1$,  
$F_{X,Y}(x,y)\leq F_{X,Y}(x_1,y_1)$
## Joint PMF
$P_{X,Y}(x,y)=P[X=x,Y=y]$
## Marginal PMF
For discrete random variables $X$ and $Y$,  
$P_X(x)=\sum\limits_{y\in S_Y}P_{X,Y}(x,y),$  
$P_Y(y)=\sum\limits_{x\in S_X}P_{X,Y}(x,y)$
## Joint PDF
$F_{X,Y}(x,y)=\int\limits_{-\infty}^x\int\limits_{-\infty}^yf_{X,Y}(u,v)dvdu$  
$f_{X,Y}(x,y)=\dfrac{\partial^2F_{X,Y}(x,y)}{\partial x\partial y}$

For event $(X,Y)$ in range $A$,  
$P[A]=\iint\limits_Af_{X,Y}(x,y)dxdy$
## Marginal PDF
$f_X(x)=\int\limits_{-\infty}^{\infty}f_{X,Y}(x,y)dy$  
$f_Y(y)=\int\limits_{-\infty}^{\infty}f_{X,Y}(x,y)dx$
## Independence
Discrete $X\perp Y$ if and only if $P_{X,Y}(x,y)=P_X(x)P_Y(y)$  
Continuous $X\perp Y$ if and only if $f_{X,Y}(x,y)=f_X(x)f_Y(y)$
## Expected Value
For discrete $W=g(X,Y)$,  
$E[W]=\sum\limits_{x\in S_X}\sum\limits_{y\in S_Y}g(x,y)P_{X,Y}{(x,y)}$

For continuous $W=g(X,Y)$,  
$E[W]=\int\limits_{-\infty}^{\infty}\int\limits_{-\infty}^{\infty}g(x,y)f_{X,Y}{(x,y)}dxdy$

___

< [[Spring 2024/EEC161/Notes/Families of Continuous Random Variables|Families of Continuous Random Variables]] | Current Page | [[Spring 2024/EEC161/Notes/Covariance, Correlation, and Independence|Covariance, Correlation, and Independence]] >