## Probability measure
$P[\cdot]$ function that maps [[Spring 2024/EEC161/Notes/Experiment Terminology#^2613a6|event]] from the [[Spring 2024/EEC161/Notes/Experiment Terminology#^131988|sample space]] to real numbers
### Axiom 1
For any event $A, P[A]\ge 0$
### Axiom 2
$P[S] = 1$
### Axiom 3
For countable collections of mutually exclusive events,
$P[A_1\cup A_2\cup\cdots]=P[A_1]+P[A_2]+\cdots$
## Theorems
$P[\varnothing]=0$  
$P[A^c]=1-P[A]$  
$P[A\cup B]=P[A]+P[B]-P[A\cap B]$  
If $A \subset B$, then $P[A]\leq P[B]$  

For outcomes $s_n$ and event $B$:  
$P[B]=\sum\limits_{i=1}^{m}{P[{s_i}]}$

For experiment with equally likely outcomes  
$P[s_i]=1/n \text{ for } 1\le i\le n$

___

< [[Spring 2024/EEC161/Notes/Experiment Terminology|Experiment Terminology]] | Current Page | [[Spring 2024/EEC161/Notes/Conditional Probability|Conditional Probability]] >