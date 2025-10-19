# Transfer Functions
## Zeroes and Poles
Suppose that we represent a transfer function as:
$$
H(z)=\dfrac{N(z)}{D(z)}
$$
To find the **zeroes** of a transfer function, solve for $z$ such that
$$
N(z)=0.
$$
Similarly, to find the **poles** of a transfer function, solve for $z$ such that
$$
D(z)=0.
$$
Solving for roots in polynomials may result in complex and/or *repeated roots*.
## Factoring roots with NumPy
```python
import numpy as np

coeffs = [1, -0.25, -1, -1.2]
roots = np.roots(coeffs)
print(roots)
```
## Plotting roots with matplotlib
```python
import matplotlib.pyplot as plt

fig, ax = plt.subplots(figsize=(5,5))

# draw unit circle
theta = np.linspace(0, 2*np.pi, 400)
ax.plot(np.cos(theta), np.sin(theta))

# plot roots
ax.scatter(roots.real, roots.imag, marker='o')

# set up axes
ax.axhline(0)
ax.axvline(0)
ax.set_aspect('equal', adjustable='box')
ax.set_xlabel('Re')
ax.set_ylabel('Im')
plt.tight_layout()
plt.show()
```
![[EEC151/src/hw3-1.png]]
# First-Difference Filters
**Impulse Function:**
$$
h[n]=\delta[n]-\delta[n-1]
$$

**Transfer Function:**
$$
H(z)=1-z^{-1}=\dfrac{z-1}{z}
$$

> [!example] Cascaded First-Difference Filters Example
> **Find the transfer function for a *third-order* cascade of first-difference filters.**
> 
> The transfer function for a single first-difference filter is $H_1(z)=1-z^{-1}$ . To cascade this filter, we multiply it by itself. Thus,
> $$
> H(z)=(1-z^{-1})^3=1-3z^{-1}+3z^{-2}-z^{-3}
> $$
> Alternatively, if we represent the first-difference filter transfer function as $H_1(z)=\dfrac{z-1}{z}$, then:
> $$
> H(z)=\left(\dfrac{z-1}{z}\right)^3=\dfrac{(z-1)^3}{z^3}
> $$
> This fraction form makes it easier to find the zeroes and pole of the filter. 

# Inverse Z-transforms
## Properties
### Linearity
If $X(z) \xleftrightarrow{\mathcal{Z}^{-1}} x[n]$ and $Y(z) \xleftrightarrow{\mathcal{Z}^{-1}} y[n]$, then:
$$
aX(z) + bY(z) \xleftrightarrow{\mathcal{Z}^{-1}} a x[n] + b y[n].  
$$
### Time-Shifting
$$
z^{-k}X(z)\xleftrightarrow{\mathcal{Z}^{-1}}x[n-k]
$$
## Transforms to Know
### Polynomial
$$
z^{-k}\xleftrightarrow{\mathcal{Z}^{-1}}\delta[n-k]
$$
> [!help]- Proof
> Recall that the equation for Z-transforms is given by:
> $$X(z) = \sum\limits_{n=-\infty}^{\infty} x[n]z^{-n}$$
> Then, if $x[n]=\delta[n-k]$,
> $$
> \begin{align*}X(z) &= \sum\limits_{n=-\infty}^{\infty} \delta[n-k]z^{-n} \\ &= z^{-k}\end{align*}
> $$

> [!example] Polynomial Example
> **Find the impulse function for $X(z)=3+4z^{-2}-6z^{-5}$.**
> Using $z^{-k}\xleftrightarrow{\mathcal{Z}^{-1}}\delta[n-k]$:
> $$
> \boxed{x[n]=3\delta[n]+4\delta[n-2]-6\delta[n-5]}
> $$

### Geometric Series
$$
\dfrac{1}{1-az^{-1}}\xleftrightarrow{\mathcal{Z}^{-1}}a^nu[n], \quad\text{ROC: }\lvert z\rvert > \lvert a\rvert 
$$