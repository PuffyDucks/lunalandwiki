# 1
Hypothesis: $T(n)=O(n^2)$  
Assuming $T(n)\leq cn^2$ for $\forall n\leq k-1$, we determine that $T(k-1)\leq c(k-1)^2=ck^2-2ck+c$. Thus, we know that
$$
\begin{align}
T(k)&=T(k-1)+k \\
&\leq ck^2-2ck+c+k \\
&\leq ck^2-2ck+ck+k \\
&=ck^2-ck+k
\end{align}
$$
From this, we want to prove that
$$
ck^2-ck+k\leq ck^2
$$
By subtracting $ck^2$ and adding $ck$ to both sides, we get the inequality
$$
k\leq ck
$$
Then by solving for $c$, we get
$$
c \geq 1
$$
Thus, $T(n)=O(n^2)$ is proven by definition of big O as $T(n)\leq cn^2$ for $c=1$ and $n_0=1$.

# 2
$T(n)=T\left(\left\lceil\dfrac{n}{2}\right\rceil\right)+1$
Hypothesis: $T(n)=O(\log(n))$  
Assuming $T(n)\leq c\log(n)$ for $\forall n\leq k-1$, we determine that for sufficiently large $k$, $T\left(\left\lceil\dfrac{k}{2}\right\rceil\right)\leq c\log\left(\left\lceil\dfrac{k}{2}\right\rceil\right)$. Thus, we know that
$$
\begin{align}
T(k)&=T\left(\left\lceil\dfrac{k}{2}\right\rceil\right)+1 \\
& \leq c\log\left(\left\lceil\dfrac{k}{2}\right\rceil\right)+1 \\
& \leq c\log\left(\dfrac{k}{2}+1\right)+1 \\
\end{align}
$$
The $+1$ is amortized by the $\dfrac{k}{2}$, so we can say
$$
\begin{align}
& \approx c\log\left(\dfrac{k}{2}\right)+1 \\
& = c\log(k)-c\log(2)+1 \\
& = c\log(k)-c+1 \\
\end{align}
$$
Then for $c\geq1$, this is
$$
\begin{align}
& \leq c\log(k)
\end{align}
$$
Thus, $T(n)=O(\log(n))$ is proven by definition of big O as $T(n)\leq c\log(n)$ for $c=1$ and $n_0=1$.
# 3
Hypothesis: $T(n)=O(n^{\log_3(4)})$  
Assuming $T(n)\leq cn^{\log_3(4)}$ for $\forall n\leq k-1$, we determine that for sufficiently large $k$, $T\left(\dfrac{k}{3}\right)\leq c\left(\dfrac{k}{3}\right)^{\log_3(4)}$. Thus, we know that
$$
\begin{align}
T(k)&=4T\left(\dfrac{k}{3}\right)+k \\
&\leq 4c\left(\dfrac{k}{3}\right)^{\log_3(4)}+k \\
& = ck^{\log_3(4)}+k
\end{align}
$$  
From this, we want to prove that
$$
ck^{\log_3(4)}+k\leq ck^{\log_3(4)}
$$
However, this inequality can never be true for $k>0$, and thus the substitution proof failed. Instead, for $\forall n\leq k-1$, we can try the guess $T(n)\leq cn^{\log_3(4)}-dn$ for $d\geq0$. For sufficient $k$, $T\left(\dfrac{k}{3}\right)\leq c\left(\dfrac{k}{3}\right)^{\log_3(4)}-d\dfrac{k}{3}$. Then,
$$
\begin{align}
T(k)&=4T\left(\dfrac{k}{3}\right)+k \\
&\leq c\left(\dfrac{k}{3}\right)^{\log_3(4)}-d\dfrac{k}{3}+k \\
& = ck^{\log_3(4)}-d\dfrac{k}{3}+k
\end{align}
$$  
From this, we want to prove that
$$
ck^{log_3(4)}-d\dfrac{k}{3}+k\leq ck^{\log_3(4)}
$$
If we set $d=3$, then we get
$$
ck^{log_3(4)}\leq ck^{\log_3(4)}
$$  
which is true for any $c>0$. Therefore, we have shown a substitution proof to work by subtracting a lower-order term for $c=1$, $d=3$, and $n_0=1$
# 4
![[Fall 2024/ECS122A/Homework/src/II-IV.svg]]
0, 2, 3, 3.5, 3.75, 3.875
$a_k=4-\left(\dfrac{1}{2}\right)^{k-2}$
$$
\begin{align*}
\sum\limits_{k=0}^{\log_2(n)}2^k\left(n\right)+4^k\left(4-\left(\dfrac{1}{2}\right)^{k-2}\right)&=\sum\limits_{k=0}^{\log_2(n)}2^k\left(n\right)+4^{k+1}-\left(\dfrac{1}{2}\right)^{k}4^{k+1}\\
&=\sum\limits_{k=0}^{\log_2(n)}2^k(n)+2^{2k+2}-2^{k+2}\\
&=n(2^{\log_2(n)+1}-1)+\dfrac{4(4^{\log_2(n)+1}-1)}{3}+(2^{\log_2(n)+1}-1) \\
&=n(2n-1)+\dfrac{16n^2-4}{3}+(8n-4)\\
&=\dfrac{22n^2-27n+8}{3}\\
&=O(n^2)
\end{align*}
$$

**Substitution**
Hypothesis: $T(n)=O(n^2)$  
Assuming $T(n)\leq cn^2-dn$ for $\forall n\leq k-1$, we determine that $T\left(\dfrac{k}{2}+2\right)\leq c\left(\dfrac{k}{2}+2\right)^2-dk=\dfrac{ck^{2}}{4} + 2ck + 4c-dk$. Thus, we know that
$$
\begin{align}
T(k)&=4T\left(\dfrac{n}{2}+2\right)+k \\
&\leq\dfrac{ck^{2}}{4} + 2ck + 4c - d + k \\
&\leq\dfrac{ck^{2}}{4} + 2ck^2 + 4ck^2 - dk + k \\
&=\dfrac{25}{4}ck^{2} + k - dk
\end{align}
$$
From this, we want to prove that
$$
\dfrac{25}{4}ck^{2} + k - dk\leq ck^2
$$
By subtracting $ck^2$ and adding $ck$ to both sides, we get the inequality
$$
\dfrac{21}{4}ck\leq d-1
$$

# 5
![[Fall 2024/ECS122A/Quiz Preps/src/II-IV.excalidraw.svg|400]]
Work: $2^k$
Depth: $k=n$
$\sum\limits_{k=1}^{n}k^2$
# 6
![[Fall 2024/ECS122A/Homework/src/II-VI.svg]]
Work: 1
Depth: n
Runtime = $1\cdot n =O(n)$
# 7
![[Fall 2024/ECS122A/Homework/src/II-VII.svg]]
Work: 2
Depth: n
Runtime = $2\cdot n =O(n)$
# 8
$a=2$
$b=4$
$log_b(a)=0.5$
## a
$f(n)=1$
for $n\leq1$, $f(n)=1\leq n^{0.4}$
Thus by definition of big O, $f(n)=O(n^{0.4})$ for $c=1$ and $n_0=1$
Then, $f(n)=O(n^{0.5-\epsilon})$ for $\epsilon=0.1$, and thus $T(n)=\Theta\left(n^{0.5}\right)$
## b
$f(n)=\sqrt{n}$
for $n\leq0$, $f(n)\leq\sqrt{n}$ as well as $f(n)\geq\sqrt{n}$
Thus by definition of big Theta, $f(n)=\Theta(n^{0.5})$ for $c=1$ and $n_0=0$ for both upper and lower bound
Therefore, $T(n)=\Theta(n^{0.5}\log(n))$
## c
$f(n)=n$
for $n\leq1$, $f(n)=n\geq n^{0.9}$
Thus, $f(n)=\Omega(n^{0.5+\epsilon})$ for $\epsilon=0.4$
Then, we must prove that
$2 \cdot f\left(\frac{n}{4}\right) \leq c \cdot f(n)$
We can solve for $c$ by simplifying to
$\dfrac{n}{2}\leq cn$
$c\geq\dfrac{1}{2}$
Thus the statement is true for $c=\dfrac{1}{2}$
As $2 \cdot f\left(\frac{n}{4}\right) \leq c \cdot f(n)$ for $c<1$, sufficiently large $n$, and $f(n)=\Omega(n^{0.5+\epsilon})$ for $\epsilon=0.4$,
$T(n)=\Theta(n)$
## d
$f(n)=n^2$
for $n\leq1$, $f(n)=n^2\geq n$
Thus, $f(n)=\Omega(n^{0.5+\epsilon})$ for $\epsilon=0.5$
Then, we must prove that
$2 \cdot f\left(\frac{n}{4}\right) \leq c \cdot f(n)$
We can solve for $c$ by simplifying to
$\dfrac{n}{2}\leq cn^2$
$c \geq \dfrac{1}{2n}$
Then, for $n\geq1$, the inequality is true for 
$c\geq\dfrac{1}{2}$
Thus the statement is true for $c=\dfrac{1}{2}$
as $2 \cdot f\left(\frac{n}{4}\right) \leq c \cdot f(n)$ for $c<1$, sufficiently large $n$, and $f(n)=\Omega(n^{0.5+\epsilon})$ for $\epsilon=0.5$,
$T(n)=\Theta(n^2)$
# 9
$T(n)=4T\left(\dfrac{n}{2}\right)+n^2\log(n)$
$a=4$
$b=2$
$f(n)=n^2\log(n)$
$\log_b(a)=2$

because of the $\log(n)$, we know $f(n)$ is not bound by $n^2$ or $n^{2-\epsilon}$
Then, we can attempt to prove $f(n) = \Omega\left(n^{2 + \epsilon}\right)$ for some $\epsilon>0$
Limit lemma:
For $\epsilon>0$,
$$
\begin{align}
\lim\limits_{n\to\infty}\dfrac{n^2\log(n)}{n^{2 + \epsilon}}&=\lim\limits_{n\to\infty}\dfrac{n+2n\log(n)}{(2 + \epsilon)n^{1 + \epsilon}}=\\
&= \lim\limits_{n\to\infty}\dfrac{3+2\log(n)}{(2 + \epsilon)(1 + \epsilon)n^{\epsilon}} \\
&= \lim\limits_{n\to\infty}\dfrac{3+2\log(n)}{(2 + \epsilon)(1 + \epsilon)n^{\epsilon}} \\
&= \lim\limits_{n\to\infty}\dfrac{2}{\epsilon(2 + \epsilon)(1 + \epsilon)n^{\epsilon}} \\
&=0
\end{align}
$$
Therefore, as the limit approaches 0, no value of $\epsilon>0$ results in $f(n) = \Omega\left(n^{2 + \epsilon}\right)$
This proves that master method cannot be used on this recurrence as it fits none of the 3 cases.
# 10
## a
### 1
Already known
$T(N)=T(N/2)+1$
$O(N)=\log(N)$
### 2
Work: Extra $O(N)$ to copy entire array
$T(N)=T(N/2)+N$
Master theorem $a<b^d$
$O(N)=N$
### 3
Work: Extra $O(N)$ to copy entire array
$T(N)=T(N/2)+n$
Master theorem $a<b^d$
$O(N)=N$
## b
### 1
Already known
$T(N)=2T(N/2)+n$
$O(N)=N\log(N)$
### 2
Work: Extra $O(N)$ to copy entire array. merging is already O(N) anyways, no change
$T(N)=2T(N/2)+N$
$O(N)=N\log(N)$
### 3
Work: Extra $n$ to copy subarray. merging is already O(N) anyways, no change
$T(N)=2T(N/2)+N$
$O(N)=N\log(N)$
# 11
## a
```python
merge(list1, list2, list3):
  intermediateList = []
  i = j = 0
  while (i < n/3 - 1 && j < n/3 - 1):
    if (list1[i] < list2[j]):
      intermediateList.push(list1[i])
      i++
    else:
      intermediateList.push(list2[j])
      j++
  for (k=i to n/3 - 1):
    intermediateList.push(list1[k])
  for (k=j to n/3 - 1):
    intermediateList.push(list1[k])
  
  finalList = []
  i = j = 0
  while (i < 2*n/3 - 1 && j < n/3 - 1):
    if (list1[i] < list2[j]):
      finalList.push(intermediateList[i])
      i++
    else:
      finalList.push(list3[j])
      j++
  for (k=i to 2*n/3 - 1):
    finalList.push(list1[k])
  for (k=j to n/3 - 1):
    finalList.push(list1[k])
  return finalList
```
## b
$T(n)=3T\left(\dfrac{n}{3}\right)+\dfrac{5}{3}n$

Master theorem:
$a=3$
$b=3$
$\log_b(a)=1$
$f(n)=\dfrac{5}{3}n$

$f(n)=\dfrac{5}{3}n\geq\dfrac{5}{3}n$ and $\dfrac{5}{3}n\leq\dfrac{5}{3}n$ 
Thus, by definition of big theta, $f(n)=\Theta(n)$ for $c=\dfrac{5}{3}$ and $n_0=1$ for both the upper and lower bound
Therefore, $T(n)=\Theta(n^{\log_b(a)}\log(n))=\Theta(n\log(n))$
# 12
```python
findTwoSmallest(arr):
  n = arr.length
  if n == 2:
    if (arr[0] < arr[1]):
      return (arr[0], arr[1])
    return (arr[1], arr[0])

  (min1, secondMin1) = findTwoSmallest(arr[0..n/2])
  (min2, secondMin2) = findTwoSmallest(arr[n/2+1..n-1])
  
  if (min1 < min2):
    secondSmallest = min(min2, secondMin1, secondMin2)
    return (min1, secondSmallest)
  secondSmallest = min(min1, secondMin1, secondMin2)
  return (min2, secondSmallest)
```

Time complexity recurrence: $T(n)=2T(n/2)+1$
Comparisons:
Total comparisons from `if (arr[0] < arr[1])` is $\dfrac{n}{2}$
Depth: $k=\log_2(n)$
Work: 3 comparisons
$\dfrac{n}{2}+\sum\limits_{k=0}^{\log_2(n)-1}3(2^k)$
$=\dfrac{n}{2}+\dfrac{3(1-2^{\log_2(n)-1+1})}{1-2}$
$=7.5n-3$