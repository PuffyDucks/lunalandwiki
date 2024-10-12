---
aliases:
  - Law of Total Probability
  - Bayes' theorem
---
![Partitions](Spring%202024/EEC161/Notes/src/Partitions.png)  
For [[Spring 2024/EEC161/Notes/Set Theory Review#^678476|partition]] $B=\{B_1, B_2, \cdots\}$ and event A in [[Spring 2024/EEC161/Notes/Experiment Terminology#^131988|sample space]], if $C_i=A\cap B_i$, then for $i\neq j$, $C_i$ and $C_j$ are [[Spring 2024/EEC161/Notes/Set Theory Review#^a79e39|mutually exclusive]] and $A=C_i\cup C_2 \cup\cdots$ 
## Law of Total Probability
For any event $A$ and [[Spring 2024/EEC161/Notes/Set Theory Review#^678476|partition]]$\{B_1, B_2, \cdots, B_m\}$, $P[A]=\sum\limits^{m}_{i=1}{P[A\cap B_i]}$  
For partition $\{B_1, B_2, \cdots, B_m\}$ where $P[B_i]>0$ for all $i$, then $P[A]=\sum\limits^{m}_{i=1}{P[A|B_i]\,P[B_i]}$
## Bayes' theorem
$P[B|A]=\dfrac{P[A|B]\,P[B]}{P[A]}$

___

< [[Spring 2024/EEC161/Notes/Conditional Probability|Conditional Probability]] | Current Page | [[Spring 2024/EEC161/Notes/Independence|Independence]] >