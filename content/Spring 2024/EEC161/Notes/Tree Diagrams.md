Tree diagrams are useful for modelling experiments which are followed up by a sub-experiment. The sub-experiment may be dependent of previous experiments.  
```mermaid
graph LR;
	START--0.3-->A1--0.1-->A1B1[B1]-->PA1B1["P[A1B1] = 0.03"]
		A1--0.9-->A1B2[B2]-->PA1B2["P[A1B2] = 0.27"]
	START--0.25-->A2--0.5-->A2B1[B1]-->PA2B1["P[A2B1] = 0.125"]
		A2--0.5-->A2B2[B2]-->PA2B2["P[A2B2] = 0.125"]
	START--0.45-->A3--0.7-->A3B1[B1]-->PA3B1["P[A3B1] = 0.315"]
		A3--0.3-->A3B2[B2]-->PA3B2["P[A3B2] = 0.135"]
```
___
< [[Spring 2024/EEC161/Notes/Independence|Independence]] | Current Page | [[Spring 2024/EEC161/Notes/Counting Methods|Counting Methods]] >