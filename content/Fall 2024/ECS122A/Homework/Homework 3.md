# 1
```python
binarySearchString(arr, value):
    left = 0
    right = arr.length - 1
    
    while (left <= right):
        mid = (left + right) / 2
        
        if arr[mid] == value:
            return mid
        else if arr[mid] < value:
            right = mid - 1
        else:
            left = mid + 1
    return null
```

Runtime: O(logn), as each while loop cuts down possible elements by half.
# 2
sorting is O(nlogn). the length of strings is not affected by n - we will assume they are constant, so sorting strings is still O(nlogn)

# 3
```python
mult(X, Y):
	n = X.length
	X_L = X[0..n/2]
	X_R = X[n/2+1..n-1]
	Y_L = Y[0..n/2]
	Y_R = Y[n/2..n-1]

	A = mult(X_L, Y_L)
	C = mult(X_R, Y_R)
	B = mult(X_L + X\_R, Y\_L + Y\_R)
	
	B = shift(B - A - D, n/2)
	A = shift(A, n)
	return A + B + C
```
# 4
this algorithm is greedy because it chooses the locally optimal choice based on previous choices. to prove the approach yields an optimal solution, we assume O is the optimal solution with maximum activities chosen, and is different from the greedy solution S. taking the last activity that are different between S and O, as S's algorithm requires the start time to be latest as possible, then the start time of the activity must be later than or equal to O's activity, and can thus replace the activity in O. then, as G and O's next different activity cannot conflict, this process can be repeated for each activity. finally, there are no leftover activities possible in O, as the first activity in G must contain the earliest start time that does not conflict. 

# 5
![[Fall 2024/ECS122A/Homework/src/III-Va.svg|III-Va]]
In this example, choosing least duration activities first would pick the small two activities. however, this is not the optimal solution, as the three larger activities would result in more activities being selected. 

couldn't figure out second one. 

![[Fall 2024/ECS122A/Homework/src/III-Vc.svg|III-Vc]]
In this example, choosing first start activities first causes only one activity to be selected rather than the three. 