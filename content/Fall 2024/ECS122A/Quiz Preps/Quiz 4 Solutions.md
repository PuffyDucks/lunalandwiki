> [!info] v1 Patch Notes 
> happy halloween. is this quiz prep not identical to our hw?? heres my rascal cat who learned to hop onto the fridge 
> ![[Fall 2024/ECS122A/Quiz Preps/src/luma_fridge.png| 400]] 
# Problem 1: For the strategy of latest selecting the activity latest to start
## Part 1.) Design an algorithm that follows this strategy.
```python
maxActivities(activities):
    sorted_activities = sortBackwardsByStart(activities)
    optimal_solution = []
    earliest_start = Inf

    for activity in sorted_activities:
        if activity.finish <= earliest_start:
             optimal_solution.push(activity)
             earliest_start = activity.start
    return optimal_solution
```
## Part 2.) Provide the runtime of the algorithm in part 1
sorting takes $O(\log(n))$. then when we iterate over activities, we do so $n$ times so that takes $O(n)$. thus sorting dominates and the algorithm has a runtime of $O(\log(n))$
## Part 3.) Provide a greedy choice proof for the algorithm
assume $O$ is the optimal solution with maximum activities chosen, and is different from the greedy solution $S$. taking the first activity thats different between $S$ and $O$: as $S$'s algorithm requires the start time to be latest as possible, then the start time of the activity must be later than or equal to $O$'s activity's start time. thus it can replace the activity in $O$. then, as $S$ and $O$'s next different activity cannot conflict, this process can be repeated for each activity. finally, there are no leftover activities possible in $O$, as the first activity in $S$ must contain the earliest start time that does not conflict. 
# Problem 2 
## Given $X=X_L+X_R$ where $X_L=X[1..n/2]$ and $X_R=X[n/2+1...n]$ and similarly you can breakup $Y$, Then $X\cdot Y=(X_L\cdot10^{n/2}+Xr)(Y_L\cdot10^{n/2}+Yr)$. Create pseudocode for a divide and conquer algorithm that achieves the above goal.
> [!tldr] 
> honestly for this one just watch 10/22 lecture
```python
multiply(X, Y):
	n = X.length
	X_L = X[1..n/2]
	X_R = X[n/2+1..n]
	Y_L = Y[1..n/2]
	Y_R = Y[n/2..n]

	A = multiply(X_L, Y_L)
	C = multiply(X_R, Y_R)
	B = multiply(X_L + X\_R, Y\_L + Y\_R)
	
	B = shift(B - A - D, n/2)
	A = shift(A, n)
	return A + B + C
```

# Problem 3: Pure analysis
## Provide binary search algorithm that takes a sorted list of n strings each of length and finds a specific string x. What is the runtime of your algorithm?
> [!question] what
> "strings each of length and finds a..." each of length what????? ima make the assumption she meant length $m$. 
```python
# pretty straightforwards alg. 
binarySearchString(arr, x):
	# get left and right indices of array
    left = 0
    right = arr.length - 1

    # loop until we check left == right
    while (left <= right):
        # find middle of left and right
        mid = (left + right) / 2

        # check if middle is x
        if arr[mid] == value:
            return mid
        # if middle is lesser then move left to one greater than middle so we can search right side
        else if arr[mid] < value:
            right = mid - 1
        # if middle is greater then move right to one lesser than middle to search left side. 
        else:
            left = mid + 1
    
    # return -1 if x is not found
    return -1
```
## What is the runtime of an algorithm that sorts n strings each of length m?
sorting takes $O(\log(n))$. but the strings have $m$ chars, so comparisons take $O(m)$ for each char in the string. multiply the two and we get $O(m\cdot\log(n))$