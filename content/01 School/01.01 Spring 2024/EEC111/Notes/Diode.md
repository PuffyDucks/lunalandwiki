Diodes are two-terminal and nonlinear circuit elements which only allow current to flow in one direction, implemented using [[01 School/01.01 Spring 2024/EEC111/Notes/p-n Junction|p-n junctions]]. 
# Current/Voltage Models
## Ideal Model
Open circuit when $V_D<0$, and shorted when $V_D>0$.
![[01 School/01.01 Spring 2024/EEC111/Notes/src/Pasted image 20250514135744.png]]
## Constant Voltage Model
Only passes current when $V_D>V_{D,ON}$. Typically $0.7V$ for silicon diodes.
![[01 School/01.01 Spring 2024/EEC111/Notes/src/Pasted image 20250514135800.png]]
## Non-Ideal Exponential Model
**Shockley Diode Equation**
$I_D=I_S\left(e^\dfrac{V_D}{V_T}-1\right)$
$I_S=$ reverse-bias saturation current
$V_T=$ thermal voltage $=\dfrac{kT}{q}$   ($26mV$ at $25\textdegree C$)
Can also be modelled with linear piecewise function.
![[01 School/01.01 Spring 2024/EEC111/Notes/src/Pasted image 20250514135816.png]]
**Solving for current and voltage** 
$I_D\cong I_se^{V_D/V_T} \text{ for } i \gg I_S$
$I_D=\dfrac{V_{DD}-V_D}{R}$
Solve iteratively
# Small Signal Model
![[01 School/01.01 Spring 2024/EEC111/Notes/src/Pasted image 20250514141205.png]]
$r_d=\dfrac{V_T}{I_D}$

# Uses
## Rectifier
Rectifiers convert AC to DC by using a diode to only allow half of an AC source's voltages. A capacitor may be used for filtering out AC frequencies and to act as a reservoir.

**Half Wave Without Capacitor**
![[01 School/01.01 Spring 2024/EEC111/Notes/src/Pasted image 20250514135836.png]]

**Half Wave With Capacitor**
![[01 School/01.01 Spring 2024/EEC111/Notes/src/Pasted image 20250514135849.png]]
$V_{ripple}=\dfrac{V_{max}-V_{D,ON}}{R_LCf}$

**Full Wave Without Capacitor**
![[01 School/01.01 Spring 2024/EEC111/Notes/src/Pasted image 20250514135903.png]]

**Full Wave With Capacitor**
![[01 School/01.01 Spring 2024/EEC111/Notes/src/Pasted image 20250514135921.png]]

$V_{ripple}=\dfrac{V_{max}-2V_{D,ON}}{2R_LCf}$
## Voltage Limiter
Clips voltages which exceed certain thresholds. 
$V_o=\begin{cases}-V_b-V_{D,ON} &\text{if } V_i < -V_b-V_{D,ON} \\ V_i &\text{if } V_b\leq V_I\leq V_a\\ V_a+V_{D,ON} &\text{if } V_i>V_a+V_{D,ON}\end{cases}$
![[01 School/01.01 Spring 2024/EEC111/Notes/src/Diode Limiter.svg|500]]
![[01 School/01.01 Spring 2024/EEC111/Notes/src/Pasted image 20250514135932.png]]
## Voltage Regulator
A voltage regulator generates constant DC voltage. A simple voltage regulator uses many diodes in series, while a more common implementation involves using a zener diode in breakdown. 
![[01 School/01.01 Spring 2024/EEC111/Notes/src/Pasted image 20250514135941.png]]
**Power-supply ripple**: The unwanted sinusoidal residue in a regulator. 

**DC Power Supply**
Power transformer reduces 120V voltage to 8-12V
Diode rectifier converts bipolar voltage to unipolar
Filter reduces voltage variations
Voltage regulator further reduces voltage and ripple