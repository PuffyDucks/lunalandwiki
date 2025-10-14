---
aliases:
  - NMOS
  - PMOS
  - CMOS
---
---
**MOSFET** stands for metal-oxide-semiconductor field-effect transistors. MOSFETs have four terminals: a source, gate, drain, and body/substrate. The body is assumed to be shorted with the source. The MOSFET is made of a single p-type Si wafer with doped n-type substrate at the source and drain, as well as metal contacts at the source, drain, and body. The gate spans the area above the source and drain, and is in contact with both regions. The gate consists of a thin silicon dioxide insulating layer(thickness $t_{ox}$) between the metal and the semiconductor, hence the name "metal-oxide-semiconductor." The name "field-effect" stems from the movement of charges within MOSFETs through drift current. 

![[EEC111/Notes/src/Diagram_MOSFET.svg|Diagram_MOSFET]]
## Channel Formation
Due to the properties of doped semiconductor regions, a depletion region forms between the n-regions and p-region. When all terminals are grounded, there is no current flowing for $v_{DS}$. However, when a positive voltage $v_{GS}$ is applied to the gate, then majority holes under the gate are repelled and bound negative charges are revealed. Additionally, the positive voltage also attracts electrons, forming an n-type channel below the gate where current can flow. Thus, the p-type substrate below the gate is inverted. 
## Triode Region
I-V relation is curved as channel resistance increases with $v_{DS}$. 

**Lateral (drain-source electric field)** 
$|E|=\dfrac{v_{DS}}{L}$
**Electron drift velocity** 
$v_{n-drift}=\mu_n|E|$
**Triode Resistance**
$r_{DS}=\dfrac{1}{k_n(V_{GS}-V_{T})}$
## Saturation Region
Increasing $v_{DS}$ causes a widening of the depletion region near the drain, leading to a decrease in channel thickness in the region. 
## PMOS
Similar to NMOS but with reversed doping and voltage polarities. The two are complementary. In the PMOS symbol, the source arrowhead points into the MOSFET, or the base arrowhead out of the MOSFET.  $V_{DS}$ and $V_T$ are always negative. 

| Name                        | Equation                                                                      | Info                                                                  |
| --------------------------- | ----------------------------------------------------------------------------- | --------------------------------------------------------------------- |
| Oxide capacitance           | $C_{ox}=\dfrac{\epsilon_{ox}}{t_{ox}}\quad (F/m^2)$                           | $\epsilon_{ox}=3.9\epsilon_0=3.45\times10^{-11}\;F/m$                 |
| Aspect ratio                | $\dfrac{W}{L}$                                                                |                                                                       |
| Process transconductance    | $k'_n=\mu_nC_{ox}\quad(A/V^2)$                                                |                                                                       |
| Transconductance parameter  | $k_n=k'_n\dfrac{W}{L}=\mu_nC_{ox}\dfrac{W}{L}\quad(A/V^2)$                    |                                                                       |
| Threshold voltage           | $V_T$                                                                         | Required to invert channel region<br>Typically $0.3V$ to $1V$         |
| Effective/overdrive voltage | NMOS $V_{OV}=V_{GS}-V_T$<br>PMOS $\vert V_{OV}\vert =V_{SG}-\vert V_{T}\vert$ |                                                                       |
| Device parameter            | $\lambda\quad (V^{-1}$)                                                       | Depends on process parameters  <br>Smaller MOFSET lengths are greater |
| Channel charge              | $\vert Q\vert=C_{ox}(WL)V_{OV}$                                               |                                                                       |
**Operating regions and Current Equations**

| Operating Region | NMOS Conditions                                 | NMOS Current                                                                                                     | PMOS Conditions                                                    | PMOS Current                                                                                                                |
| ---------------- | ----------------------------------------------- | ---------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------- |
| Cutoff           | $V_{GS}<V_T$                                    | $I_D=0$                                                                                                          | $V_{SG}<\vert V_T\vert$                                            | $I_D=0$                                                                                                                     |
| Triode           | $V_{GS}\geq V_{T}$<br>$V_{DS}<V_{GS}-V_{T}$     | $I_D=k_n\left(V_{GS}-V_T-\dfrac{1}{2}V_{DS}\right)V_{DS}$<br>For $V_{DS}<50 mV$, $\dfrac{1}{2}V_{DS}$ negligible | $V_{SG}\geq\vert V_T\vert$<br>$V_{SD}<V_{SG}-\vert V_{T}\vert$     | $I_D=k_p\left(V_{SG}-\vert V_T\vert-\dfrac{1}{2}V_{SD}\right)V_{SD}$<br>For $V_{SD}<50 mV$, $\dfrac{1}{2}V_{SD}$ negligible |
| Saturation       | $V_{GS}\geq V_{T}$<br>$V_{DS}\geq V_{GS}-V_{T}$ | $I_D=\dfrac{k_n}{2}\left(V_{GS}-V_T\right)^2(1+\lambda V_{DS})$                                                  | $V_{SG}\geq\vert V_T\vert$<br>$V_{SD}\geq V_{SG}-\vert V_{T}\vert$ | $I_D=\dfrac{k_p}{2}\left(V_{SG}-\vert V_T\vert\right)^2(1+\lambda V_{SD})$                                                  |
Always $I_G=0$
# Small Signal Model
![[EEC111/Notes/src/Pasted image 20250514141340.png]]
**Transconductance**
$g_m=k(V_{GS}-V_T)=\sqrt{2kI_D}=\dfrac{2I_D}{V_{GS}-V_T}$
**Output Resistance**
$r_o=\dfrac{1}{\lambda I_D}$
![[EEC111/Notes/src/Pasted image 20250514141353.png]]
# Topologies
> See: [[04 Study/04.12 Semiconductor Circuits/Transistor Amplifier|Transistor Amplifier]]

![[EEC111/Notes/src/Pasted image 20250514141405.png]]

| Name                               | $A_v$                       | $R_{in}$         | $R_{out}$                    |
| ---------------------------------- | --------------------------- | ---------------- | ---------------------------- |
| Common Source                      | $-g_mR_D$                   | $\infty$         | $R_D$                        |
| Common Source<br>with Degeneration | $-\dfrac{g_mR_D}{g_mR_S+1}$ | $\infty$         | $R_D$                        |
| Common Gate                        | $g_mR_D$                    | $\dfrac{1}{g_m}$ | $R_D$                        |
| Source Follower                    | $\dfrac{g_mR_S}{g_mR_S+1}$  | $\infty$         | $R_S\parallel\dfrac{1}{g_m}$ |
# Parasitic Capacitance
> See: [[04 Study/04.12 Semiconductor Circuits/Miller Theorem|Miller Theorem]]

![[EEC111/Notes/src/Pasted image 20250514141418.png]]
 