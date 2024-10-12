## PMF of Discrete Multiple Variable Function
For discrete $W=g(X,Y)$,  
$P_W(w)=\sum\limits_{(x,y):g(x,y)=w}P_{X,Y}(x,y)$
## PDF of Continuous Multiple Variable Function
For continuous $W=g(X,Y)$,  
$f_W(w)=\dfrac{dF_W(w)}{dw}$
## CDF of Continuous Multiple Variable Function
For continuous $W=g(X,Y)$,  
$F_W(w)=P[W\leq w]=\iint\limits_{g(x,y)\leq w}f_{X,Y}(x,y)dxdy$
## Theorems
For $W=X+Y$,  
$f_W(w)=\int\limits_{-\infty}^{\infty}f_{X,Y}(x,w-x)dx=\int\limits_{-\infty}^{\infty}f_{X,Y}(w-y,y)dy$

For continuous $W=max(X,Y)$,  
$F_W(w)=F_{X,Y}(w,w)=\int\limits_{-\infty}^{w}\int\limits_{-\infty}^{w}f_{X,Y}(x,y)dxdy$
## Conditional CDF
Given $P[B]>0$,  
$F_{X|B}(x)=P[X\leq x\;|\;B]$
## Conditional PMF
Given $P[B]>0$,  
$P_{X|B}(x)=P[X=x\;|\;B]$  
$P_{X|B}(x)=\begin{cases} \dfrac{P_X(x)}{P[B]} & x\in B, \\ 0 & \text{otherwise} \end{cases}$

For $X$ in partition $B_1,\dots,B_m$,  
$P_X(x)=\sum\limits_{i=1}^{m}P_{X|B_i}(x)P[B_i]$
## Conditional PDF
$f_{X|B}(x)=\dfrac{dF_{X|B}(x)}{dx}$

$f_{X|B}(x)=\begin{cases} \dfrac{f_X(x)}{P[B]} & x\in B, \\ 0 & \text{otherwise} \end{cases}$

$P_X(x)=\sum\limits_{i-1}^mP_{X|B_i}(x)P[B_i]$

$f_X(x)=\sum\limits_{i-1}^mf_{X|B_i}(x)P[B_i]$

___

< [[Spring 2024/EEC161/Notes/Gaussian Random Variables|Gaussian Random Variables]] | Current Page | [[Spring 2024/EEC161/Notes/Conditional Probability Models|Conditional Probability Models]] >