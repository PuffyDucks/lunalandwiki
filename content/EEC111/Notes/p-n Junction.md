---
aliases:
  - depletion region
  - reverse breakdown
  - saturation current
  - scale current
---
A p-n junction contains [[EEC111/Notes/Doping Semiconductors|p-type and n-type]] [[EEC111/Notes/Semiconductor Materials|semiconductor]] in the same crystal. On the sides are metal contacts, with a *positive anode* and *negative cathode* forming a [[EEC111/Notes/Diode|diode]].

### Depletion Region
Holes diffuse from the p-region to n-region, and electrons diffuse from the n-region to the p-region. The majority carriers form a **total current** $I_D$ from the p-region to n-region. The majority carriers are depleted due to [[EEC111/Notes/Silicon Crystal Lattice#Recombination|recombination]] near the junction interface, which thus creates a **depletion region**. The decrease in p-region holes results in a negative net charge, and the decrease in n-region electrons results in a positive net charge. This creates an electric field from the n-region to the p-region, which opposes the charge carrier diffusion. The electric field grows until its force prevents further diffusion, putting the depletion region in *equilibrium*. The voltage across the depletion region, $V_0$, is a barrier which carriers must overcome to diffuse. $I_D$ is strongly dependent on $V_0$.

Then, the thermally-generated holes in the n-region are sent to the p-region, and the thermally-generated electrons in the p-region are sent to the n-region. The movement of these minority carriers form a [[EEC111/Notes/Drift Current|drift current]] $I_s$ 

**Built-in voltage(no external bias)** 
$V_0=V_T\ln\left(\dfrac{N_aN_D}{n_i^2}\right)$ (around 0.6 - 0.9V for room temperature Si). 
However, the voltage across the junction is still 0V.  

Under equilibrium with no external current, $I_D=I_S$. 

### Depletion Region Width
When $N_A>N_D$, the depletion region goes further into the n-region to balance out the greater acceptor charge.  When $N_D>N_A$, the depletion region goes further into the p-region to balance out the greater donor charge. The charges of both sides must equal each other, so $AqN_Ax_p=AqN_Dx_n$. Therefore, $\dfrac{x_n}{x_p}=\dfrac{N_A}{N_D}$. 

**Total depletion region width** 
Tends to be within 0.1-1 $\upmu$m, and can be calculated using electrostatics $W=x_n+x_p=\sqrt{\dfrac{2\epsilon_s}{q}\left(\dfrac{1}{N_A}+\dfrac{1}{N_D}\right)V_0}$, 
Si permittivity: $\epsilon_s=11.7\epsilon_0=1.04\times10^{-12}\frac{F}{cm}$. 

**Values in terms of $W$ and $V_0$
$x_n=W\dfrac{N_A}{N_A+N_D}$
$x_p=W\dfrac{N_D}{N_A+N_D}$
$|Q_+|=|Q_-|=Q_J=Aq\left(\dfrac{N_AN_D}{N_A+N_D}\right)W=A\sqrt{2\epsilon_sq\left(\dfrac{N_AN_D}{N_A+N_D}\right)V_0}$

### Reverse Bias
Adding a reverse bias $V_R$ significantly reduces [[EEC111/Notes/Diffusion Current|diffusion current]] so that $I_D\cong 0$
Thus, $I=I_D-I_S=-I_S$.  This current is very small and strongly depends on temperature. The barrier voltage increases to $V_0+V_R$. The depletion region width and junction charge are also greater due to an increase in uncovered fixed charges. 

**Depletion region width under reverse bias** 
$W=x_n+x_p=\sqrt{\dfrac{2\epsilon_s}{q}\left(\dfrac{1}{N_A}+\dfrac{1}{N_D}\right)(V_0+V_R)}$

**Junction charge under reverse bias** 
$Q_J=A\sqrt{2\epsilon_sq\left(\dfrac{N_AN_D}{N_A+N_D}\right)(V_0+V_R)}$

### Forward Bias
Adding a forward bias $V_F$ significantly increases diffusion current, which has the equation $I=I_D-I_S$.  Additionally, the barrier voltage is reduced to $V_0-V_F$.

**Total hole concentration under forward bias**
$p_n(x)=p_{n0}+p_{n0}\left(e^{V/V_T}-1\right)e^{-(x-x_n)/L_p}$ for $x > x_n$

**Hole [[EEC111/Notes/Diffusion Current|diffusion current]] density**
$J_p(x)=q\left(\dfrac{D_p}{L_p}\right)p_{n0}(e^{V/V_T}-1)e^{-(x-x_n)/L_p}$
For $x>x_n$, electrons are externally injected and balance out [[EEC111/Notes/Silicon Crystal Lattice|recombination]], making the total diffusion current density constant. 

**Electron [[EEC111/Notes/Diffusion Current|diffusion current]] density**
$J_n(x)=q\left(\dfrac{D_n}{L_n}\right)n_{p0}(e^{V/V_T}-1)e^{-(x-x_p)/L_n}$
For $x<x_p$, electrons are externally injected and balance out [[EEC111/Notes/Silicon Crystal Lattice|recombination]], making the total diffusion current density constant. 

**Total diffusion current**
$I=A(J_p+J_n)=Aq\left(\dfrac{D_p}{L_p}p_{n0}+\dfrac{D_n}{L_n}n_{p0}\right)(e^{V/V_T}-1)$
$=Aqn_i^2\left(\dfrac{D_p}{L_pN_D}+\dfrac{D_n}{L_nN_A}\right)(e^{V/V_T}-1)$
$=I_S(e^{V/V_T}-1)$ ^forwardcurrent

**Saturation/Scale Current**
$I_S=Aqn^2_i\left(\dfrac{D_p}{L_pN_D}+\dfrac{D_n}{L_nN_A}\right)$
Ranges from $10^{-18}$ to $10^{-12}$^saturationcurrent

### Reverse Breakdown
**Junction breakdown**: The significant increase in reversed current due to a large reverse bias. However, breakdown is non-destructive.  

**Zener breakdown**: High E field breaks covalent bonds, $V_{BR}<5V$

**Avalanche breakdown**: Carriers with high kinetic energy break bonds, $V_{BR}>8 V)$

### Capacitance
$C_{j0}=A\sqrt{\left(\dfrac{\epsilon_sq}{2}\right)\left(\dfrac{N_AN_D}{N_A+N_D}\right)\left(\dfrac{1}{V_0}\right)}$
$C_j=\dfrac{C_{j0}}{\sqrt{1+\dfrac{V_R}{V_0}}}$

**Graded junction**: Carrier concentration gradually changes from p-type to n-type
$C_j=\dfrac{C_{j0}}{\left(1+\dfrac{V_R}{V_0}\right)^m}$
$m$ - grading coefficient, between $1/3$ to $1/2$

**Excess hole charge in n-type region**
$Q_p=Aq(p_n(x_n)-p_{n0})L_p$
$=\dfrac{L^2_p}{D_p}I_p=\tau_pI_p$

**Excess electron charge in p-type region**
$Q_n=Aq(p_p(x_p)-n_{p0})L_n$
$=\dfrac{L^2_n}{D_n}I_n=\tau_pI_n$

**Excess minority carrier lifetime**: Average time for minority carrier to [[EEC111/Notes/Silicon Crystal Lattice|recombine]] 
$\tau_p=\dfrac{L^2_p}{D_p}$
$\tau_n=\dfrac{L^2_n}{D_n}$

**Total charge**
$Q=\tau_pI_p+\tau_nI_n=\tau_TI$

$\tau_T$ - mean transit time
When $N_A \gg N_D$, $\tau_T \cong \tau_p$
When $N_D \gg N_A$, $\tau_T \cong \tau_n$

**Incremental diffusion capacitance**
$C_d=\dfrac{dQ}{dV}=\tau_T\dfrac{dI}{dV}$

When approximating $I \approx I_Se^{V/V_T}$, $C_d=\left(\dfrac{\tau_T}{V_T}\right)I$
