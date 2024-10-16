---
week: "1"
---
# Definitions
**Big O**: There exists $c>0$ and $n_0$ such that $0\leq f(n)\leq cg(n)$ for $n\geq n_0$

**Big Omega**: There exists $c>0$ and $n_0$ such that $cg(n)\leq f(n)$ for $n\geq n_0$

**Big Theta**: The asymptotic function that is both big O and big omega. 

# Limit Lemma
The asymptotic relationship between two positive functions can be determined by dividing their horizontal asymptotes.  
$$
\lim\limits_{n\to\infty}\dfrac{f(n)}{g(n)}=L
$$

| Condition  | **Asymptotic Relationship** |
| ---------- | --------------------------- |
| $L=0$      | $f(n)=O(g(n))$              |
| $L=\infty$ | $f(n)=\Omega(g(n))$         |
| $L=c>0$    | $f(n)=\Theta(g(n))$         |
