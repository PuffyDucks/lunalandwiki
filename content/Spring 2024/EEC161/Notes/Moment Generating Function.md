---
aliases:
  - MGF
---
## Moment generating function(MGF)
$\phi_X(s)=E[e^{sX}]$

For $Y=aX+b$,  
$\phi_Y(s)=e^{sb}\phi_X(as)$
## nth moment
$E[X^n]=\dfrac{d^n\phi_X(s)}{ds^n}\biggr\vert_{s=0}$
## Sums
For $W_n=X_1+\cdots+X_n$,  
$\phi_W(s)=\phi_{X_1}(s)\phi_{X_2}(s)\cdots\phi_{X_n}(s)$

For random sum of iid random variables $R=X_1+\cdots+X_N$ and independent non-negative random integer N,  
$\phi_R(s)=\phi_N(ln(\phi_X(s))$

___

< [[Spring 2024/EEC161/Notes/Sums|Sums]] | Current Page | [[Spring 2024/EEC161/Notes/Central Limit Theorem|Central Limit Theorem]] >