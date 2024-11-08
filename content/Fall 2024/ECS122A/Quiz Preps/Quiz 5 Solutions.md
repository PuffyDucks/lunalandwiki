> [!question]  v1 Patch Notes 
> ![[Fall 2024/ECS122A/Quiz Preps/src/Pasted image 20241107151608.png | 200]]  
> girl wdym 'image.png' 😭😭😭 

# 1) Run Rod-Cutting DP algorithm including traceback array S[i]. What is the optimal cut?
![[Fall 2024/ECS122A/Quiz Preps/src/Pasted image 20241108135121.png | 300]]

starting with **length 1**: 
price[1] = 10. no other cuts to make, so we put these in our array

| length        | 1   | 2   | 3   | 4   | 5   |
| ------------- | --- | --- | --- | --- | --- |
| optimal price | 10  |     |     |     |     |
| traceback     | 1   |     |     |     |     |

oke now **length 2**  
cut size 1, price[1] + opt_price[1] = 10 + 10 = 20  
cut size 2, price[2] + 0 = 24  
**cut size 2** has highest price  

| length        | 1   | 2   | 3   | 4   | 5   |
| ------------- | --- | --- | --- | --- | --- |
| optimal price | 10  | 24  |     |     |     |
| traceback     | 1   | 2   |     |     |     |

**length 3**  
cut size 1, price[1] + opt_price[2] = 10 + 24 = 34  
cut size 2, price[2] + opt_price[1] = 24 + 10 = 34  
cut size 3, price[3] + 0 = 30 + 0 = 30  
**cut size 1** is the smallest cut with the highest price

| length        | 1   | 2   | 3   | 4   | 5   |
| ------------- | --- | --- | --- | --- | --- |
| optimal price | 10  | 24  | 34  |     |     |
| traceback     | 1   | 2   | 1   |     |     |

**length 4**  
cut size 1, price[1] + opt_price[3] = 10 + 34 = 44  
cut size 2, price[2] + opt_price[2] = 24 + 24 = 48  
cut size 2, price[3] + opt_price[1] = 30 + 10 = 44  
cut size 3, price[4] + 0 = 40 + 0 = 340  
**cut size 2** has highest price  

| length        | 1   | 2   | 3   | 4   | 5   |
| ------------- | --- | --- | --- | --- | --- |
| optimal price | 10  | 24  | 34  | 48  |     |
| traceback     | 1   | 2   | 1   | 2   |     |

**length 5**  
cut size 1, price[1] + opt_price[4] = 10 + 48 = 58  
cut size 2, price[2] + opt_price[3] = 24 + 34 = 58  
cut size 2, price[3] + opt_price[2] = 34 + 24 = 58  
cut size 2, price[4] + opt_price[1] = 48 + 10 = 58  
cut size 3, price[5] + 0 = 40 + 0 = 45  
**cut size 1** is the smallest cut with the highest price  

| length        | 1   | 2   | 3   | 4   | 5   |
| ------------- | --- | --- | --- | --- | --- |
| optimal price | 10  | 24  | 34  | 48  | 58  |
| traceback     | 1   | 2   | 1   | 2   | 1   |

yay we have our arrays. now we find optimal cut for rod length 5. looking at the traceback array, we first cut off a 1 length rod. this leaves us with a rod of length 4, which the traceback table says to cut a length of 2 next. finally this leaves us with a 2 long rod, which the traceback says cut a length of 2 again. this leaves us with no rod, so:  

our final optimal cuts are of **length 1, 2, and 2**. our traceback array is **S = [1, 2, 1, 2, 1]**

# 2) Given S[10]=4 S[7]=7 and S[6]=3 and S[3]=2 What is the optimal cut strategy?
ok similar to what we did at end of problem 1. taking a rod of length 10, S[10]=4 so we want to first cut off a 4 long piece. this leaves a 6 long piece, and S[6]=3. thus lets cut off a 3 long piece, leaving us with a 3 long piece. S[3] = 2, so we cut off a 2 long piece, leaving us with a 1 long piece. the cuts we need to make are of lengths **4, 3, 2, 1**.
# 3) Given rod cutting problem is changed so that you have to pay $3 dollars every time you cut the rod
## a) Solve via BF and provide runtime
``` python
cutRod(n, sell_prices[]):
    if n == 0:
        return 0

	# instead of setting the initial max_price to -Inf or 0, we set it to 
	# sell_prices[n] to account for the scenario where we don't make any cuts,
	# so theres no need to subtract the cut fee. 
    max_price = sell_prices[n]

	# for loop iterates to n-1 since we already account for the price of 
	# a cut_size of n, aka no cut, above.  
    for (cut_size=1 to n-1):
        # subtract 3 every time a cut is made
        tmp_price = sell_prices[cut_size] + cutRod(n - cut_size, prices) - 3
        max_price = max(max_price, tmp_price)
    
    return max_price
```
## b) What is the recurrence of this new problem
> [!question] what am i even doing
> idk what im talking about

ummm the runtime is $O(2^n)$ i guess cuz for every length in $n$ we decide to cut or not cut and this splits into 2 branches so every length we're doubling the num of combinations we check waowwwwww yeah i def did not prove this one correctly ok next problem!! 
## c) Create a DP algorithm for this new problem and state its run-time.
pretty similar to the standard rod cutting problem, but now when we make our optimal cut table we must factor in the $3 fee. 
```python
cutRod(n, sell_prices[]):
    optimal_price = [0] * (n + 1)
    
    for (rod_length=1 to n):
        # instead of setting the initial optimal price to -Inf or 0, we set it to 
        # sell_prices[rod_length] to account for the scenario where we don't make any
        # cuts, so theres no need to subtract the cut fee. 
		optimal_price[rod_length] = sell_prices[rod_length]

        # for loop iterates to rod_length-1 since we already account for the price of 
        # a cut_size of rod_length, aka no cut, above.  
        for (cut_size=1 to rod_length-1):
            # subtract 3 for the cut fee
            tmp_price = sell_prices[cut_size] + optimal_price[rod_length - cut_size] - 3
            optimal_price[rod_length] = max(tmp_price, optimal_price[rod_length])
```

### Runtime
first line is $O(n)$. then the for loop iterates from `1` to `n`, and is thus $O(n)$. the line afterwards is $O(1)$, but the following for loop is from `1` to `length-1`. since rod_length is $O(n)$, then this for loop is also $O(n)$. then, everything inside that for loop is $O(1)$. with all this, we can determine the runtime of the program to be $O(n)\cdot O(n)\cdot O(1)=O(n^2)$.

## d) Prove that this problem has an optimal substructure
> [!question] lmao
> idk how to do this one man 

optimal solution is found with $R(n) = \max\limits_{1 \leq i \leq n} \{ p[i] + R(n - i) \}$  
$R(n)$ is constructed with the subproblem $R(n - i)$ therefore it is a optimal substructure!!!! wow!!!! 