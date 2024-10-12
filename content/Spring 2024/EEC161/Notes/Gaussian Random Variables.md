## Gaussian (μ, σ) random variable
For μ is real and σ > 0,
$f_X(x)=\dfrac{1}{\sqrt{2\pi\sigma^2}}e^{-(x-\mu)^2/2\sigma^2}$  
$E[X]=\mu$  
$Var[X]=\sigma^2$

For $X$ being Gaussian $(\mu,\sigma)$, then $Y=aX+b$ is Gaussian $(a\mu+b,a\sigma)$

Gaussian $X$ and $Y$ are uncorrelated if and only if $X \perp Y$
## Standard normal random variable
$Z$ - Gaussian $(0,1)$
## CDF of standard normal random variable
$\phi(z)=\dfrac{1}{\sqrt{2\pi}}\int\limits_{-\infty}^{z}e^{-u^2/2}du$  
$\phi(-z)=1-\phi(z)$

## CDF of Gaussian random variable
$F_X(x)=\phi\left(\dfrac{x-\mu}{\sigma}\right)$  
$P[a<X\leq b]=\phi\left(\dfrac{b-\mu}{\sigma}\right)-\phi\left(\dfrac{a-\mu}{\sigma}\right)$

___

< [[Spring 2024/EEC161/Notes/Covariance, Correlation, and Independence|Covariance, Correlation, and Independence]] | Current Page | [[Spring 2024/EEC161/Notes/Multiple Variable Functions|Multiple Variable Functions]] >