### 1
$\sum\limits_{i=0}^{n}ar^i=\dfrac{a(1-r^{n+1})}{1-r}$
$\sum\limits_{i=1}^n4^i=\sum\limits_{i=0}^{n-1}4\cdot4^i=\dfrac{4(1-4^{n})}{1-4}$
$=\dfrac{4-16^{n}}{-3}=\dfrac{4\cdot4^n-4}{3}$

Proving $\sum\limits_{i=1}^n4^i=\dfrac{4\cdot4^n-4}{3}$ through induction:
Base case: $n=1$
$\sum\limits_{i=1}^n4^i=4^1=4$
$\dfrac{4\cdot4^n-4}{3}=\dfrac{16-4}{3}=4$
Thus, the closed-form formula is true for the base case $n=1$

Assuming it is true for $n=k$, if $n=k+1$ then
$\sum\limits_{i=1}^{k+1}4^i=\dfrac{4\cdot4^k-4}{3}+4^{k+1}$
$=\dfrac{4^{k+1}-4}{3}+\dfrac{3\cdot4^{k+1}}{3}$
$=\dfrac{4\cdot4^{k+1}-4}{3}$
Thus, the closed-form formula is true for $n=k+1$
Therefore, through induction we have proven that $\sum\limits_{i=1}^n4^i=\dfrac{4\cdot4^n-4}{3}$.
$\blacksquare$

### 2
while(i>1)
i /= 2
O(logn)

while (j<n)
j*=2
O(logn)

while (k<n)
k+=2
O(n)

upper bound=$O(nlog^2n)$

### 3
A.length is O(1)
for (i=0 to n/2-1) is O(n)

for (i=0 to n/2-1) is O(n)
for (j=i+1 to n/2-1) is O(n)
nested is **$O(n^2)$

useless(A) is T(n/2)
useless(B) is T(n/2)
max is O(1)

$T(n)=2T(n/2)+O(n^2)$
### 4
#### a
push(2):
![[Fall 2024/ECS122A/Homework/src/I-IV-A.excalidraw|I-IV-A.excalidraw]]
push(31):
![[Fall 2024/ECS122A/Homework/src/I-IV-B.excalidraw|I-IV-B.excalidraw]]
pop():
![[Fall 2024/ECS122A/Homework/src/I-IV-C.excalidraw|I-IV-C.excalidraw]]
pop():
![[Fall 2024/ECS122A/Homework/src/I-IV-D.excalidraw|I-IV-D.excalidraw]]
update key of 7 to -2:
![[Fall 2024/ECS122A/Homework/src/I-IV-E.excalidraw|I-IV-E.excalidraw]]
#### b
Running build heap on an unsorted heap is O(n). This is done by bubbling down the leaf nodes at the bottom height of the heap. Then, the parent nodes at the above height are bubbled down. This is repeated until the root node is reached. If we represent the bottom of the heap as height $h=0$, then the number of nodes at height $h$ can be represented with $\dfrac{n}{2^{h+1}}$ as half the nodes are leaves, half the number of leaves are parents of leaves, and etc. Then, the number of swaps needed to bubble a node down is proportional to its height $h$. By multiplying these two values, we determine the total runtime to bubble every node at height $h$ is $h\left(\dfrac{n}{2^{h+1}}\right)$. Then, this can be put in a summation with the height of the heap. As heap height is logarithmic, the final runtime is $O\left(\sum\limits_{h=0}^{log(n)}h\left(\dfrac{n}{2^{h+1}}\right)\right)$. 
$\sum\limits_{h=0}^{log(n)}h\left(\dfrac{n}{2^{h+1}}\right)\leq\sum\limits_{h=0}^{\infty}h\left(\dfrac{n}{2^{h+1}}\right)=\dfrac{n}{2}\sum\limits_{h=0}^{\infty}\dfrac{h}{2^{h}}=n$
Therefore, build heap has a runtime of $O(n)$.
### 5
++sum is O(1) 
#### a
i to n is O(n)
O(n)
#### b
i to n is O(n)
j to n is O(n)
nested is $O(n^2)$
$O(n^3)$
#### c
i to n is O(n)
j to n\*n is $O(n^2)$
nested is $O(n^3)$
$O(n^3)$
#### d
i to n is O(n)
j to i is O(n)
nested is $O(n^2)$
$O(n^2)$
#### e
i to n is O(n)
j to i\*i is $O(n^2)$
k to j is $O(n^2)$
nested is $O(n^5)$
$O(n^5)$
#### f
i to n is O(n)
j to i\*i is $O(n^2)$
k to j when j%i=\=0 runs in multiples of i, or so j's runs divided by i which is i. this gives complexity of O(n)
nested is $O(n^4)$
$O(n^4)$
### 6
Yes to both, as different log bases are the same equation with a different constant. 
$log_4(n)=\dfrac{log_{16}(n)}{log_{16}(4)}=2log_{16}(n)$
Thus, $log_4(n)\leq c\cdot\log_{16}(n)$ for $c=2$ and $n_0=1$ which proves $log_4(n)=O(log_{16}(n))$

$log_{16}(n)=\dfrac{log_{4}(n)}{log_{4}(16)}=\dfrac{1}{2}log_{4}(n)$
Thus, $log_{16}(n)\leq c\cdot\log_{4}(n)$ for $c=\dfrac{1}{2}$ and $n_0=1$ which proves $log_{16}(n)=O(log_{4}(n))$
### 7
#### a
$f_1=nlog(n^{1000})$
$f_2=1024n^2$
$f_3=7n^3log(n)$
$f_4=3n^4+6n$
$f_5=3^n$
$f_6=6^n$

$nlog(n^{1000})=1000nlog(n)$
$\lim\limits_{n\to\infty}\dfrac{1000nlog(n)}{1024n^2}=\lim\limits_{n\to\infty}\dfrac{1000(log(n)+1)}{2048n}=\lim\limits_{n\to\infty}\dfrac{1000/n}{2048}=0$
Thus, as the limit approaches a constant, $f_1=O(f_2)$.

For $n\geq10$,
$1024n^2\leq1024n^3log(n)=\dfrac{1024}{7}(7n^3log(n))$
Thus, $1024n^2\leq c(7n^3log(n))$ for $c=\dfrac{1024}{7}$ and $n_0=10$
Therefore, by definition of big O, $f_2=O(f_3)$. 

$\lim\limits_{n\to\infty}\dfrac{7n^3log(n)}{3n^4+6n}=\lim\limits_{n\to\infty}\dfrac{21n^2log(n)+7n^2}{12n^3+6}=\lim\limits_{n\to\infty}\dfrac{42nlog(n)+35n}{36n^2}$
$=\lim\limits_{n\to\infty}\dfrac{42log(n)+77}{72n}=\lim\limits_{n\to\infty}\dfrac{42/n}{72}=0$
Thus, as the limit approaches a constant, $f_3=O(f_4)$.

$\lim\limits_{n\to\infty}\dfrac{3n^4+6n}{3^n}=\lim\limits_{n\to\infty}\dfrac{12n^3+6}{3^nln(3)}=\lim\limits_{n\to\infty}\dfrac{72}{3^n(ln(3))^4}=0$
Thus, as the limit approaches a constant, $f_4=O(f_5)$.

For $n\geq0$,
$3^n\leq3^n2^n=6^n$
Thus, $3^n\leq c\cdot 6^n$ for $c=1$ and $n_0=0$
Therefore, by definition of big O, $f_5=O(f_6)$. 
#### b
$k(n)=n^2+3n$
$\lim\limits_{n\to\infty}\dfrac{n^2+3n}{n^2}=\lim\limits_{n\to\infty}\dfrac{2n+3}{2n}=\lim\limits_{n\to\infty}\dfrac{2}{2}=1$
As the limit does not approach 0, $k(n)=\Omega(n^2)$
### 8
#### a.i
$\mathcal{P}(S)=\{\{\}, \{z\}, \{b\}, \{g\}, \{z, b\}, \{z, g\}, \{b, g\}, \{z, b, g\}\}$
#### a.ii
$\mathcal{P}(S)=\{\{\}, \{z\}, \{b\}, \{g\}, \{r\}, \{z, b\}, \{z, g\}, \{z, r\}, \{b, g\},$ 
$\{b, r\}, \{g, r\}, \{z, b, g\}, \{z, b, r\}, \{z, g, r\}, \{b, g, r\}, \{z,b,g,r\}\}$
#### b
"cdef" substrings: "c", "d", "e", "f", "cd", "de", "ef", "cde", "def", "cdef"
#### c
$|\mathcal{P}(S)|=|S|^2=100^2=10000$
S can create 10,000 subsets
#### d
```python
decode(S, x):
  n = S.length
  subset = []
  for (i=0 to n-1):
    if x & (1 << i):
      subset.push(S[i])
  return subset
```
####  e
```python
powerSet(S):
  n = S.length
  allSubsets = []
  for (i=0 to 2^n-1): 
    subset = []
    for (j=0 to n-1):
      if i & (1 << j):
        subset.push(S[j])
    allSubsets.push(subset)
  return allSubsets
```
#### f
```python
possibleSubstrings(s):
  n = s.length
  allSubstrings = []
  for (i=0 to n-1):
    for (j=i to n-1):
      allSubstrings.push(s.substring(i, j))
  return allSubstrings
```
### 9
#### a
3 ways
$\{\{y, b\}, \{y, g\}, \{b, g\}\}$
#### b
```python
setsOfTwo(S):
  n = S.length
  sets = []
  for (i=0 to n-2):
    for (j=i+1 to n-1):
      sets.push([S[i], S[j]])
  return sets
```
### 10
for j to n is O(n) 
for i to n is O(1) as the i++ in j's loop increments it to n
runtime is O(n) 
### 11
```python
minimum(arr):
  n = arr.length
  if !n:
    return "Empty Array"
  smallest = arr[0]
  for (i=1 to n-1):
    if arr[i] < smallest:
      smallest = arr[i]
  return smallest
```
for i to n-1 is O(n)
runtime is O(n)
### 12
```python
total(arr):
  arrTotal = 0
  for (i=0 to arr.length-1):
    arrTotal += arr[i]
  return arrTotal
```
for i to n is O(n)
runtime is O(n)