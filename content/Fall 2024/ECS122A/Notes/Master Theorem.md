---
week: "2"
---
For $T(n)=aT\left(\dfrac{n}{b}\right)+O(n^d)$:

| Condition | Recurrence        |
| --------- | ----------------- |
| $a>b^d$   | $O(n^{log_B(A)})$ |
| $a=b^d$   | $O(n^dlog(n))$    |
| $a<b^d$   | $O(n^d)$.         |
