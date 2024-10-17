---
week: "2"
---
The master theorem allows us to easily analyze any recurrence in the form of
$$
T(n) = a \cdot T\left(\frac{n}{b}\right) + f(n)
$$   
| Condition                                                                                                                                                                                | $T(n)$ Bound                                 | Behavior                          |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------- | --------------------------------- |
| $f(n) = O\left(n^{\log_b a - \epsilon}\right)$ for some $\epsilon>0$                                                                                                                     | $\Theta\left(n^{\log_b a}\right)$            | Recursion dominates               |
| $f(n) = \Theta\left(n^{\log_b a}\right)$                                                                                                                                                 | $\Theta\left(n^{\log_b(a)}  \log (n)\right)$ | Recursion and $f(n)$ are balanced |
| $f(n) = \Omega\left(n^{\log_b a + \epsilon}\right)$ for some $\epsilon>0$<br>and<br>$a \cdot f\left(\frac{n}{b}\right) \leq c \cdot f(n)$<br>for some $c < 1$ and sufficiently large $n$ | $\Theta\left(f(n)\right)$                    | $f(n)$ dominates                  |

# Shortcut Version
If the recurrence is in the form of
$$
T(n)=aT\left(\dfrac{n}{b}\right)+O(n^d)
$$

| Condition | $T(n)$ Bound      |
| --------- | ----------------- |
| $a>b^d$   | $O(n^{log_b(a)})$ |
| $a=b^d$   | $O(n^dlog(n))$    |
| $a<b^d$   | $O(n^d)$.         |
