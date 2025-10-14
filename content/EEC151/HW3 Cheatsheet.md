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
H(z)=1-z^{-1}=\dfrac{z+1}{z}
$$

> [!example] Cascaded First-Difference Filters Example
> **Find the transfer function for a *third-order* cascade of first-difference filters.**
> 
> The transfer function for a single first-difference filter is $H_1(z)=1-z^{-1}$ . To cascade this filter, we multiply it by itself. Thus,
> $$
> H(z)=(1-z^{-1})^3=1-3z^{-1}+3z^{-2}-z^{-3}
> $$
> Alternatively, if we represent the first-difference filter transfer function as $H_1(z)=\dfrac{z+1}{z}$, then:
> $$
> H(z)=\left(\dfrac{z+1}{z}\right)^3=\dfrac{(z+1)^3}{z^3}
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
> [!Example] Geometric Series Example
> **Find the impulse function for the system $y[n]=\dfrac{1}{4}y[n-1]+\dfrac{1}{8}y[n-2]+x[n]-2x[n-1]$** .
> We start off by putting the equation in standard form:
> $$
> y[n]-\dfrac{1}{4}y[n-1]-\dfrac{1}{8}y[n-2]=x[n]-2x[n-1].
> $$
> Then, using Z-transform's time-shifting property $z^{-k}X(z)\xleftrightarrow{\mathcal{Z}^{-1}}x[n-k]$, the equation can be represented in the $z$-domain:
> $$
> Y(z)-\dfrac{1}{4}z^{-1}Y(z)-\dfrac{1}{8}z^{-2}Y(z)=X(z)-2z^{-1}X(z).
> $$
> We can then organize this equation to solve for the transfer function:
> $$
> \begin{align*}
> H(z)&=\dfrac{Y(z)}{X(z)} \\
> &=\dfrac{1-2z^{-1}}{1-\dfrac{1}{4}z^{-1}-\dfrac{1}{8}z^{-2}}\\
> &=\dfrac{1-2z^{-1}}{\left(1+\dfrac{1}{3}z^{-1}\right)\left(1-\dfrac{1}{2}z^{-1}\right)}.
> \end{align*}
> $$
> This can be rewritten using partial fraction decomposition:
> > [!FAQ]- Partial Fraction Decomposition Review!
> > We want to rewrite the fraction as a sum:
> > $$
> > \begin{align*}
> > H(z)= \dfrac{1-2z^{-1}}{\left(1+\dfrac{1}{3}z^{-1}\right)\left(1-\dfrac{1}{2}z^{-1}\right)}=\dfrac{A}{1+\dfrac{1}{3}z^{-1}}+\dfrac{B}{1-\dfrac{1}{2}z^{-1}}
> > \end{align*}
> > $$
> > Multiply both sides with $\left(1+\dfrac{1}{3}z^{-1}\right)\left(1-\dfrac{1}{2}z^{-1}\right)$ to get:
> > $$
> > \begin{align*}
> > 1-2z^{-1}=A\left(1-\dfrac{1}{2}z^{-1}\right)+B\left(1+\dfrac{1}{3}z^{-1}\right).
> > \end{align*}
> > $$
> > When $z=-\dfrac{1}{3}$, $B$ gets cancelled out and we can solve for $A$:
> > $$
> > A=\dfrac{1-2z^{-1}}{1-\dfrac{1}{2}z^{-1}}=\dfrac{14}{5}.
> > $$
> > Similarly, when $z=\dfrac{1}{2}$, we can solve for B:
> > $$
> > B=\dfrac{1-2z^{-1}}{1+\dfrac{1}{3}z^{-1}}=-\dfrac{9}{5}.
> > $$
> > We can plug these values back into the above equation.
> $$
> \begin{align*}
> H(z)&=\dfrac{\dfrac{14}{5}}{1+\dfrac{1}{3}z^{-1}}+\dfrac{-\dfrac{9}{5}}{1-\dfrac{1}{2}z^{-1}} \\
> &=\dfrac{14}{5}\dfrac{1}{1+\dfrac{1}{3}z^{-1}}-\dfrac{9}{5}\dfrac{1}{1-\dfrac{1}{2}z^{-1}}
> \end{align*}
> $$
> Finally, using the transform $\dfrac{1}{1-az^{-1}}\xleftrightarrow{\mathcal{Z}^{-1}}a^nu[n], \quad\text{ROC: }|z|>|a|$,
> $$
> \boxed{h[n]=\dfrac{14}{5}\left(-\dfrac{1}{3}\right)^nu[n]-\dfrac{9}{3}\left(\dfrac{1}{2}\right)^nu[n], \quad\text{ROC: } \lvert z\rvert > \left\lvert\dfrac{1}{2}\right\rvert }
> $$

