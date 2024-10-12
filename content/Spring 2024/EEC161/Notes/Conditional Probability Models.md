---
aliases:
  - Conditional CDF
---
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

___

< [[Spring 2024/EEC161/Notes/Multiple Variable Functions|Multiple Variable Functions]] | Current Page | [[Spring 2024/EEC161/Notes/Sums|Sums]] >