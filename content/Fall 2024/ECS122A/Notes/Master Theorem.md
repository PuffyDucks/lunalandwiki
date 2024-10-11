---
week: "2"
---
The master theorem allows us to easily analyze any recurrence in the form of
$T(n)=aT\left(\dfrac{n}{b}\right)+O(n^d)$

| Condition | Bound             |
| --------- | ----------------- |
| $a>b^d$   | $O(n^{log_B(A)})$ |
| $a=b^d$   | $O(n^dlog(n))$    |
| $a<b^d$   | $O(n^d)$.         |
