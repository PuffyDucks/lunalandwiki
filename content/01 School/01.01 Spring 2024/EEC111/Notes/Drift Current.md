---
aliases:
  - hole mobility
  - electron mobility
  - charge mobility
  - drift current density
  - drift current
---
An electric field $E$ is applied across a silicon bar, causing drift current to occur.

**Charge mobilities**
$\mu_p$ - Hole mobility ($\mu_p=480\dfrac{cm^2}{V\cdot s}$ for intrinsic Si)
$\mu_n$ - Electron mobility ($\mu_n=1350\dfrac{cm^2}{V\cdot s}$ for intrinsic Si)

**Einstein Relation**
The [[01 School/01.01 Spring 2024/EEC111/Notes/Diffusion Current#^diffusionconstant|diffusion constants]] and charge mobility are related by the thermal voltage. 
$\dfrac{D_n}{\mu_n}=\dfrac{D_p}{\mu_p}=V_T$
$V_T=\dfrac{kT}{q}$ (~25.9mV at room temperature of $T=300K$)
$k=8.617\times10^{-5}eVK^{-1}$

**Drift velocity**
$v_{p-drift}=\mu_pE$
$v_{n-drift}=-\mu_nE$

**Drift current**
$I_{S,p}=Aqp\mu_pE_{drift}$
$I_{S,n}=-Aqn\mu_nE_{drift}$

**Drift current density**
$J_{S,p}=\dfrac{I_{S,p}}{A}=pq\mu_pE$
$J_{S,n}=\dfrac{I_{S,n}}{A}=nq\mu_nE$

**Total drift current density**
$J_s = JS,p + J_S,n = q(p\mu_p+n\mu_n)E$

**Vector form of Ohm's law**
$J_s = E/\rho$ 

**Resistivity**
$\rho=\dfrac{1}{q(p\mu_p+n\mu_n)}$

**Resistance**
$R=\dfrac{\rho L}{A}$