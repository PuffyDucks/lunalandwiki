The asymptotic relationship between two positive functions can be determined by dividing their horizontal asymptotes.  
$$
\lim\limits_{n\to\infty}\dfrac{f(n)}{g(n)}=L
$$

| Condition  | **Asymptotic Relationship** |
| ---------- | --------------------------- |
| $L=0$      | $f(n)=O(g(n))$              |
| $L=\infty$ | $f(n)=\Omega(g(n))$         |
| $L=c>0$    | $f(n)=\Theta(g(n))$         |
