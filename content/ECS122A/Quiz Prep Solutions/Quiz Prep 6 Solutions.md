## Problem 1 Show sample full computation and both r and s array for rod length 5 given price array p = [1, 5, 8, 9, 10]
**length 1**:  
**cut size 1:** p[1] + R[0] = 1 + 0 = 1  
R[1] = 1, S[1] = 1  

**length 2**  
cut size 1: p[1] + R[1] = 1 + 1 = 2  
**cut size 2:** p[2] + R[0] = 5 + 0 = 5  
R[2] = 5, S[2] = 2  

**length 3**  
cut size 1: p[1] + R[2] = 1 + 5 = 6  
cut size 2: p[2] + R[1] = 5 + 1 = 6  
**cut size 3:** p[3] + R[0] = 8 + 0 = 8  
R[3] = 8, S[3] = 3  

**length 4**  
cut size 1: p[1] + R[3] = 1 + 8 = 9  
**cut size 2:** p[2] + R[2] = 5 + 5 = 10  
cut size 3: p[3] + R[1] = 8 + 1 = 9  
cut size 4: p[4] + R[0] = 9 + 0 = 9  
R[4] = 10, S[4] = 2  

**length 5**  
cut size 1: p[1] + R[4] = 1 + 10 = 11  
**cut size 2:** p[2] + R[3] = 5 + 8 = 13  
cut size 3: p[3] + R[2] = 8 + 5 = 13  
cut size 4: p[4] + R[1] = 9 + 1 = 10  
cut size 5: p[4] + R[0] = 10 + 0 = 10  
R[5] = 13, S[5] = 2  

| length           | 1   | 2   | 3   | 4   | 5   |
| ---------------- | --- | --- | --- | --- | --- |
| optimal price, R | 1   | 5   | 8   | 10  | 13  |
| traceback, S     | 1   | 2   | 3   | 2   | 3   |
## NOT Problem 2: given cat and tatt show the solution matrix and the traceback for longest common subsequence.
> [!danger] UHHHH OOPS
> errrr oops i accidentally misread problem 2 as 'subsequence' instead of 'substring'..... but like i already made all the diagrams and stuff .,. ,,. . .aHHHHHHHHHHHH ima leave it up just for learning but ITS NOT the quiz prep question aghhhhh 
> 
> also for traceback arrays if theres a tie idk if she wants us to show all the arrows or just 1. lmk if u know the answer, but rn ima prioritize diagonal > left > up

ok first we setup the solution matrix  
![[ECS122A/Quiz Prep Solutions/src/VI-II-a.excalidraw.svg]]

now we have to fill the matrix out. ill walk u thru the first row.  
  
lets start at 1, 1. `c != t`, so we cant increment by 1. we look at the 3 other options then - removing a letter from string1, removing a letter from string2, or removing one from both. the max of these is 0, tied between all three - ima choose removing one from both for the traceback. we represent this with a diagonal arrow on the array.  
  
now for 2, 1. `a != t`, so same as before - cant increment by 1, look at other 3, all tied at 0, ima choose diagonal and add the arrow.  
  
finally for 3, 1. will you look at that, `t == t` so we can actually increment this time. this uses up the letter from both words, so we add 1 to the diagonal value, and add a diagonal arrow. basically, lcs("cat", "t") = 1 + lcs("ca", "").  
  
![[ECS122A/Quiz Prep Solutions/src/VI-II-b.excalidraw.svg]]  
  
repeat for each value and we get this matrix.  
![[ECS122A/Quiz Prep Solutions/src/VI-II-c.excalidraw.svg]]  
  
finally, if we follow the traceback from the end of both words at 3, 4, then we get this traceback for the longest common substring. 
![[ECS122A/Quiz Prep Solutions/src/VI-II-d.excalidraw.svg]]  

## Problem 3: Prove that pretty printing problem has optimal substructure. 
idk that is tbh and im very eepy sorry 