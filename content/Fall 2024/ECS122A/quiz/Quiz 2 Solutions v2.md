> [!info] V1 Patch Notes - Oct. 9, 5:49 am
> hey losers :3 !!! its 5:49 am i didnt check any of my work please ping me with any errors so i can revise a v2, , ,,, i should just host a website for these so i dont have to keep uploading new versions.... im hungry.. . could go for a warm bowl of soondubu rn. oh god i have to wake up at like 6:30 im so cooked time to faint in bed. miku out!! 🛌🌙
> ![[Fall 2024/ECS122A/quiz/src/Pasted image 20241009020843.png|200]]

> [!info] V2 Patch Notes - Oct 11, 12:45 am
> hi i filled out question 1 with some explanation of previous problems, did some fixups throughout the doc to make explanations clearer, added more info and fixed an error in question 2.b, added some formulas uhh oh yeah i made the soondubu i was talking about in v1 lol looks like im starting a mini blog in the patch notes hehehehe
> ![[Fall 2024/ECS122A/quiz/src/Pasted image 20241010202319.png | 300]]
### 1) Code analysis like quiz1 or hw1 or any class code analysis 
> [!abstract] Note From Miku
> uhh uhhhhnmmm ermmm she didnt really give problems here... so instead i will show you guys my thought process with the hw ones...

okay first for **5.e from homework 1**
![[Fall 2024/ECS122A/quiz/src/Pasted image 20241010152949.png]]
what i usually do w these nested loops is find the number of iterations each loop has in O(n) form. so at the top we have a loop from i to n. obviously this is O(n). after that, the j goes from 0 to i$^2$. we just determined i to iterate O(n) times. so we can square that and determine j iterates O(n$^2$) times. then we have k which loops from 0 to j. we just determined j to iterate O(n$^2$) times, so k also iterates O(n$^2$) times. finally, inside that loop, `++sum` is O(1). multiply all those numbers together and we get O(n$^4$).

> [!warning] Be Careful !!!
> watch out when doing these problems!!! this first example was much easier bc the iterators were only affected by the for loop and nothing else. additionally, the contents of the innermost for loop was O(1), keeping things simple. she will probably give more complex problems on exams and quizzes!! make sure you look thru the code line by line and deeply analyze how certain lines could affect other parts. up next ill go over examples of some things to pay attention for.

**hw1 problem 10**
![[Fall 2024/ECS122A/quiz/src/Pasted image 20241010164302.png]]
questions like hw1 problem 10 modify the iterator values outside of the main for loop iteration. keep the behavior of these in mind and think about how they affect each loop. if we think about what j does here, it adds 1 to j every inner for loop; this causes j to increment by 2 instead of 1, which is still O(n). for i, at the end of the inner j for loop, it has increased by n/2. This means the outer for loop can only run twice, which is still an O(1) operation. 

other thing to watch out for the innermost for loop may not contain an O(1) operation! heres one a lot of ppl struggled w on **hw1 problem 5.f**
![[Fall 2024/ECS122A/quiz/src/Pasted image 20241010165621.png]]
lets start with loop analysis on this one. i iterates from 1 to n, so thats O(n). j iterates from 1 to i$^2$ and is thus O(n$^2$). then, the innermost loop iterates k from 0 to j, which is again O(n$^2$). however, the if statement in the 2nd loop prevents this from being the same as problem e. the innermost loop is nested in an if statement which checks if j%i == 0. this means while j iterates O(n$^2$) times, its contents only run every $i$ times, which is linked to O(n). then, we can divide to determine j's loop only runs its content O(n) times, not O(n$^2$). Then we can multiply these nests and find that the runtime of this code is O(n$^4$).
### 2) Solve via recurrence tree, and **confirm via substitution.**
> [!tip] Formulas!!
> Here are some formulas that are super useful for solving **geometric series**!! ^^
> The main formula u should know is
> $$\sum\limits_{k=0}^{n}ar^k=\dfrac{a(1-r^{n+1})}{1-r}$$
> When $|r|<1$, then as $n$ approaches $\infty$ we know that  
> $$\sum\limits_{k=0}^{\infty}ar^k=\dfrac{a}{1-r}$$
> Then, when $r=1$ aka there's no exponent, then
>  $$\sum\limits_{k=0}^{n}a=a(n+1)$$
> As a bonus heres **Masters Theorem**. Makes lots of problems so easy :D
For $T(n)=aT\left(\dfrac{n}{b}\right)+O(n^d)$,
if $a>b^d$ then the recurrence is $O(n^{log_B(A)})$.
if $a=b^d$ then the recurrence is $O(n^dlog(n))$.
if $a<b^d$ then the recurrence is $O(n^d)$.
#### T(n)=27T(n/3)+5n^3  
![[Fall 2024/ECS122A/quiz/src/II-II-A.excalidraw.svg|600]]
Work: $5n^3$
Depth: Largest recursive constant is 1/3.
$k=log_3(n)$
$$\begin{align}
\sum\limits_{k=0}^{log_3(n)}5n^3&=(1+log_3(n))(5n^3)\\
&=5n^3log_3(n)+5n^3\\
&=O(n^3log(n))
\end{align}$$
**Substitution**
Hypothesis: $T(n)=O(n^3log(n))$
Assuming $T(n)\leq cn^3log(n)$ for $\forall n\leq k-1$, for great enough $k$ we can use this assumption to determine that $T\left(\frac{k}{3}\right)\leq c(\frac{k}{3})^3log\left(\frac{k}{3}\right)$. Thus, we know that
$$T(k)=27\cdot T\left(\frac{k}{3}\right)+5k^3\leq ck^3log\left(\dfrac{k}{3}\right)+5k^3$$
From this, we want to prove that 
$$ck^3log\left(\frac{k}{3}\right)+5k^3\leq ck^3log(k)$$ 
We can divide by $k^3$ to rewrite the inequality as
$$c\cdot\log\left(\dfrac{k}{3}\right)+5\leq c\cdot log(k)$$
Logarithm rules further simplify this inequality to
$$c\cdot log(k) - c\cdot log(3) + 5 \leq c\cdot log(k)$$
By cancelling out $c\cdot log(k)$ and treating the log base as 3 we can solve for $c$ and get
$$c\geq5$$
Thus, $T(n)=O(n^3log(n))$ is proven by definition of big O as $T(n)\leq cn^3log(n)$ for $c=5$ and $n_0=1$
#### T(n)=27T(n/3)+5n^2  
![[Fall 2024/ECS122A/quiz/src/II-II-B.excalidraw.svg|600]]
Work: $3^i(5n^2)$
Depth: Largest recursive constant is 1/3.
$k=log_3(n)$

$$
\begin{align}
\sum\limits_{k=0}^{log_3(n)}3^k(5n^2)
&=5n^2\dfrac{(3^{log_3(n)+1}-1)}{3-1} \\
&=5n^2\dfrac{(3n-1)}{2} \\
&=\dfrac{15}{2}n^3-\dfrac{5}{2}n^2 \\
& =O(n^3)
\end{align}
$$

**Substitution**
> [!warning] disclaimer!! 
> The first hypothesis below does not successfully prove the recurrence through substitution. However, I'm still showing its process so you can understand why it fails, recognize the issue, and know how to deal with it.

Hypothesis: $T(n)=O(n^3)$
Assuming $T(n)\leq cn^3$ for $\forall n\leq k-1$, for great enough $k$ we can use this assumption to determine that $T\left(\dfrac{k}{3}\right)\leq \dfrac{c}{27}k^3$. Thus, we know that
$$T(k)=27\cdot T\left(\frac{k}{3}\right)+5k^2 \leq ck^3+5k^2$$
From this, we want to prove that 
$$ck^3+5k^2\leq ck^3$$
We can cancel out $ck^3$ from both sides and end with
$$5k^2\leq0$$
>[!failure] ermmmm what the flip!!
> This inequality can never hold true for any non-zero values of $k$! Despite this, a failed substitution proof does not indicate an incorrect hypothesis. Sometimes a new hypothesis must be formed where a lower degree term is subtracted from the original term. Below is an application of such, where $n^2$ is subtracted to deal with the $5k^2$.

Hypothesis: $T(n)=O(n^3-n^2)$
Assuming $T(n)\leq cn^3-cn^2$ for $\forall n\leq k-1$, for great enough $k$ we can use this assumption to determine that $T\left(\dfrac{k}{3}\right)\leq \dfrac{c}{27}k^3-\dfrac{c}{9}k^2$. Thus, we know that
$$T(k)=27\cdot T\left(\frac{k}{3}\right)+5k^2 \leq ck^3-3ck^2+5k^2$$
From this, we want to prove that
$$ck^3-3ck^2+5k^2\leq ck^3$$
We can cancel out the $ck^3$ from both sides and get
$$5k^2\leq3ck^2$$
This time, we can solve for $c$ and get the inequality
$$c\geq \dfrac{5}{3}$$
As $O(n^3-n^2)=O(n^3)$, we have proven $T(n)=O(n^3)$ through definition of big O as $T(n)\leq cn^3$ for $c=\dfrac{5}{4}$ and $n_0=1$.
#### T(n)=27T(n/3)+5n\^4------------------------------
![[Fall 2024/ECS122A/quiz/src/II-II-C.excalidraw.svg|600]]
Work: $\dfrac{5n^4}{3^i}$
Depth: Largest recursive constant is 1/3.
$k=log_3(n)$
$$
\begin{align}
\sum\limits_{k=0}^{log_3(n)}\dfrac{5n^4}{3^k}
& \leq\sum\limits_{k=0}^{\infty}\dfrac{5n^4}{3^k} \\
& =\dfrac{5n^4}{1-\dfrac{1}{3}} \\
& =\dfrac{15}{2}n^4 \\
& =O(n^4)
\end{align}
$$

**Substitution**
Hypothesis: $T(n)=O(n^4)$
Assuming $T(n)\leq cn^4$ for $\forall n\leq k-1$, for great enough $k$ we can use this assumption to determine that $T\left(\dfrac{k}{3}\right)\leq \dfrac{c}{81}k^4$. Thus, we know that
$$T(k)=27\cdot T\left(\frac{k}{3}\right)+5k^4\leq\dfrac{c}{3}k^4+5k^4$$
From this, we want to prove that 
$$\dfrac{c}{3}k^4+5k^4\leq ck^4$$
We can divide by $k^4$ to rewrite the inequality as 
$$\dfrac{c}{3}+5\leq c$$
Then by solving for $c$, we get
$$c\geq\dfrac{15}{2}$$
Thus, $T(n)=O(n^4)$ is proven by definition of big O as $T(n)\leq cn^4$ for $c=7.5$ and $n_0=1$.
### 3) Create a linear algorithm that adds an array of numbers, and analyze it. 
>[!abstract]  Note From Miku
 uhhhh we already did this for hw but i think its to set up for problem 4. ill just copy my prev code lol

```python
arraySum(arr):
  total = 0
  for (i=0 to arr.length-1):
    total += arr[i]
  return arrTotal
```
### 4) Create a divide & conquer algorithm that adds up an array of numbers and analyzes it using the recurrence tree method.
```python
divAndConqSum(arr, start, end):
  if start == end: # base case
    return arr[start]

  middle = floor((start + end) / 2) # MAKE SURE TO ROUND DOWN
  a = divAndConqSum(arr, start, middle)
  b = divAndConqSum(arr, middle+1, end)
  return a + b
```

Recurrence equation: $T(n)=2T\left(\dfrac{n}{2}\right)+O(1)$
![[Fall 2024/ECS122A/quiz/src/II-IV.excalidraw.svg|400]]
Work: $2^k$
Depth: Largest recursive constant is 1/2.
$k=log_2(n)$
$$
\begin{align}
\sum\limits_{k=0}^{log_2(n)}2^k&=\dfrac{2^{log_2(n)+1}-1}{2-1} \\
& =2n-1 \\
& =O(n)
\end{align}
$$
### 5)  
> [!abstract] Note From Miku
> we already did all of these for quiz1/hw1. my guess is that it'll be on the quiz this time?? dont quote me on that im yapping but ima copy my prev hw/quiz answers onto here
#### Write pseudocode that lists the subsets of an array of ints.
```python
listSubsets(arr):
  n = arr.length
  subsets = []
  
  for (i=0 to 2^n-1):
    subset = []
    for (j=0 to n-1):
      if i & (1 << j):
        subset.push(arr[j])
    subsets.push(subset)
  return subsets
```
#### Write pseudocode finds the smallest number of an array of ints.  
```python
findMinimum(arr):
  n = arr.length
  if !n:
    return "Empty Array"

  smallest = arr[0]
  for (i=1 to n-1):
    if arr[i] < smallest:
      smallest = arr[i]
  return smallest
```
#### Write pseudocode to list all possible substrings of a string S.  
```python
possibleSubstrings(S):
  n = S.length
  substrings = []
  
  for (i=0 to n-1):
    for (j=i to n-1):
      substrings.push(S.substring(i, j))
  return substrings
```
#### Given you have two sort lists write pseudocode that returns a new merged sorted
```python
mergeSortedLists(list1, list2):
    mergedList = []
    # initializing iterators
    i = j = 0  

    # we run thru the lists until one of them runs out of elements
    while (i < list1.length && j < list2.length):
        # compare the smallest elements of both lists, then add 
        # it to mergedList. increment that list's iterator 
        if list1[i] < list2[j]:
            mergedList.push(list1[i])
            i++
        else:
            mergedList.push(list2[j])
            j++

    # once one of the lists runs out of elements, add the rest
    # of the elements from the other list
    while (i < list1.length):
        mergedList.push(list1[i])
        i++
    while (j < list2.length):
        mergedList.push(list2[j])
        j++
    return mergedList
```