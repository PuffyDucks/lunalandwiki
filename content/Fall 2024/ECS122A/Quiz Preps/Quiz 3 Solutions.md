> [!info] v1 Patch Notes - Oct. 25, 4:00 pm
> i bombed the midterm :') me when 40 min delay. ive been slacking a bit... but this quiz doesnt seem so bad at least. ok luna blog uhh sorry i got this one out kinda late i havent done 2 yet ill do it in v2 im playing smash rn lol
> ![[Fall 2024/ECS122A/Quiz Preps/src/Pasted image 20241025200715.png | 500]]

# a.) Find the closed form of  T(n)=T(n/2)+ 4 if the base case is 2 using recurrence tree.  
![[Fall 2024/ECS122A/Quiz Preps/src/III-a.excalidraw.svg]]  
This one's pretty similar to other recurrence tree problems. Only difference is for our base case we stop at T(2) rather than T(1), so our depth equation changes. For this problem, we must solve for  
$$
n\left(\frac{1}{2}\right)^i=2
$$
Which solves to  
$$
i=\log_2(n)-1
$$
Our work at each level is 4, so we can calculate the closed form with  
$$
\sum\limits_{i=0}^{\log_2(n)-1}4=4(\log_2(n)-1+1)=4\log_2(n)
$$
# b.) Use all **possible**  method to find T(n)=T(2n/3)+T(n/3)+n to find the closed form of the T(n)  
> [!warning] ermm
> Masters theorem not possible cuz not in the right form. heres the other 2 tho
## Recursion Tree  
![[Fall 2024/ECS122A/Quiz Preps/src/III-b.excalidraw|III-b.excalidraw]]
Work per level: $n$
Depth: $O(\log(n))$
Runtime: $O(n\log(n))$
## Substitution  
Hypothesis: $T(n)=O(n\log(n))$
Assuming $T(n)\leq cn\log(n)$ for $\forall n\leq k-1$, for great enough $k$ we can use this assumption to determine that $T\left(\frac{k}{3}\right)\leq c\frac{k}{3}\log\left(\frac{k}{3}\right)$ and $T\left(\frac{2k}{3}\right)\leq c\frac{2k}{3}\log\left(\frac{2k}{3}\right)$. Thus, we know that
$$
\begin{align}
T(k)&=T\left(\frac{2k}{3}\right)+T\left(\frac{k}{3}\right)+k \\
& \leq c\frac{2k}{3}\log\left(\frac{2k}{3}\right)+c\frac{k}{3}\log\left(\frac{k}{3}\right)+k \\
& = c \frac{2k}{3} \log(2) + c k \log(k) - c k \log(3) + k \\

\end{align}
$$
From this, we want to prove that 
$$
c \frac{2k}{3} \log(2) + c k \log(k) - c k \log(3) + k\leq ck\log(k)
$$
We can divide by $k$ to rewrite the inequality as
$$
c \frac{2}{3} \log(2) + c \log(k) - c \log(3) + 1\leq c\log(k)
$$
If we use base 10 for the log, then we can rewrite the entire inequality as  
$$
c\log(k)-0.2764c+1\leq c\log(k)
$$
This allows us to solve for $c$, getting
$$
c\geq3.618
$$
Thus, $T(n)=O(n\log(n))$ is proven by definition of big O as $T(n)\leq cn\log(n)$ for $c=4$ and $n_0=1$
# c.) Design a function that does the following

> **Name**: Silly
> **Input**: int x
> **Output**: translate the to its interger in base 3  in an array size log_3(x)+1
> for example silly(5) returns A=[1,2]  because  1\*3+2\*1=5
> silly(12)returns A=[1,1,0]                  because (3^2\*1+3\*1+1\*0)=12

```python
Silly(x):
    digits = floor(log(x, 3)) + 1 # result will have log base 3 of x + 1 digits 
    converted = [0] * digits # idk u can do this in python. im not even a python girlie lol 

    for (i = digits-1 to 0; i--): # decrementing by -1 from n-1 to 0. this isnt real code just pseudocode
	    converted[i] %= 3 # set rightmost unfilled digit to remainder 
	    x = floor(x/3) # remove the remainder 
    return converted
```

> [!info]- miku code explanation. click me if u care
> uhsfuhsdfkj ok uhhh basically i first calculate n which is how many digits our result will have cuz like 1 digit in base 3 covers 0-2, then another digit covers 3-8, then 9-26, etc so basically once u reach $3^i$ u need i+1 digits to represent. ok after that i initialize an array with that many digits. then i loop thru from n-1 to 0. i start from n-1 cuz i wanna begin with the index storing the smallest number. then i find the value of this index by dividing by 3 and getting remainder. this works cuz anything not in remainder can fit into the above digits. here ill walk thru with example of x=26. if x=26, then 24 can be evenly fit into higher digits since theyre divisible by 3. meanwhile the leftover 2 cannot be fit so we can put 2 in the ones place. then we floor the divided value and get 8. this means our remaining 24 is equivalent to eight 3's. repeating the process, 8/3 = 2R2. this means two 3's will not fit into upper digits, and we can write 2 into the 3's place. finally we're left with the quotient of 2. theres two 9's left, which divided by 3 we see none can fit into above digits cuz 2/3 = 0R2. so we get result of 222. that wasnt the best explanation but idc i wanna go home lol ping me if u need clarification 
> 
> oh another method, from left to right: calculate some `a = pow(i, 3)` and then divide by 3. quotient is value of leftmost unfilled digit, then make x = the remainder. too lazy to explain this one err i mean left as an exercise for the reader ok next problem!! (jk ping and ill explain)

## Runtime

first two lines are O(1). the for loop iterates log(n) times. the contents inside for loop is O(1), so the entire for loop is log(n). the dominant of these two is log(n), which is the function's runtime. 

# d.) 
> [!info] tbh i totally i read off of the wikipedia page's code 
> https://en.wikipedia.org/wiki/Maximum_subarray_problem
```python
maxSubarray(arr):
    n = arr.length
    max_sum = float('-inf') # TIL python has a -inf float thing,,, kinda like INT_MIN for C  
    local_sum = 0
    
    for (i=0 to n-1):
        local_sum = max(arr[i], local_sum + arr[i])
        max_sum = max(local_sum, max_sum)
    
    return max_sum
```
# e.) Show the bruteforce algorithm for maxsubarray problem.

```python
maxSubarrayBruteforce(arr):
    n = arr.length
    max_sum = float('-inf')

    for (i=0 to n-1):
        current_sum = 0
        for (j=i to n-1):
            sum += arr[j]
            max = max(max_sum, current_sum)
            
    return max_sum
```
