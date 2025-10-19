
 [!Example] Geometric Series Example
 **Find the impulse function for the system $y[n]=\dfrac{1}{6}y[n-1]+\dfrac{1}{6}y[n-2]+x[n]-2x[n-1]$** .
 We start off by putting the equation in standard form:
 $$
 y[n]-\dfrac{1}{6}y[n-1]-\dfrac{1}{6}y[n-2]=x[n]-2x[n-1].
 $$
 Then, using Z-transform's time-shifting property $z^{-k}X(z)\xleftrightarrow{\mathcal{Z}^{-1}}x[n-k]$, the equation can be represented in the $z$-domain:
 $$
 Y(z)-\dfrac{1}{6}z^{-1}Y(z)-\dfrac{1}{6}z^{-2}Y(z)=X(z)-2z^{-1}X(z).
 $$
 We can then organize this equation to solve for the transfer function:
 $$
 \begin{align*}
 H(z)&=\dfrac{Y(z)}{X(z)} \\
 &=\dfrac{1-2z^{-1}}{1-\dfrac{1}{6}z^{-1}-\dfrac{1}{6}z^{-2}}\\
 &=\dfrac{z^2-2z}{z^{2}-\dfrac{1}{6}z-\dfrac{1}{6}}\\
 &=\dfrac{z-2z}{\left(z+\dfrac{1}{3}\right)\left(z-\dfrac{1}{2}\right)}.
 \end{align*}
 $$
 This can be rewritten using partial fraction decomposition:
  [!FAQ]+ Partial Fraction Decomposition Review!
  We want to rewrite the fraction as a sum:
  $$
  \begin{align*}
  H(z)= \dfrac{z^{2}-2z}{\left(z+\dfrac{1}{3}\right)\left(z-\dfrac{1}{2}\right)}=\dfrac{A}{z+\dfrac{1}{3}}+\dfrac{B}{z-\dfrac{1}{2}}
  \end{align*}
  $$
  Multiply both sides with $\left(z+\dfrac{1}{3}\right)\left(z-\dfrac{1}{2}\right)$ to get:
  $$
  \begin{align*}
  z^{2}-2z=A\left(z-\dfrac{1}{2}\right)+B\left(z+\dfrac{1}{3}\right).
  \end{align*}
  $$
  When $z=-\dfrac{1}{3}$, $B$ gets cancelled out and we can solve for $A$:
  $$
  A=\dfrac{z^{2}-2z}{z-\dfrac{1}{2}}=-\dfrac{14}{15}.
  $$
  Similarly, when $z=\dfrac{1}{2}$, we can solve for B:
  $$
  B=\dfrac{z^{2}-2z}{z+\dfrac{1}{3}}=-\dfrac{9}{10}.
  $$
  We can plug these values back into the above equation.
 $$
 \begin{align*}
 H(z)&=\dfrac{-\dfrac{14}{15}}{1+\dfrac{1}{3}z^{-1}}+\dfrac{-\dfrac{9}{10}}{1-\dfrac{1}{2}z^{-1}} \\
 &=-\dfrac{14}{15}\dfrac{1}{z^{2}+\dfrac{1}{3}z}-\dfrac{9}{10}\dfrac{1}{z^{2}-\dfrac{1}{2}z}
 \end{align*}
 $$
 Finally, using the transform $\dfrac{1}{1-az^{-1}}\xleftrightarrow{\mathcal{Z}^{-1}}a^nu[n], \quad\text{ROC: }|z||a|$,
 $$
 \boxed{h[n]=\dfrac{14}{5}\left(-\dfrac{1}{3}\right)^nu[n]-\dfrac{9}{3}\left(\dfrac{1}{2}\right)^nu[n], \quad\text{ROC: } \lvert z\rvert  \left\lvert\dfrac{1}{2}\right\rvert }
 $$
