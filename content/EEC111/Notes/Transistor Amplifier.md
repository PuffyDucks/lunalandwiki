Transistor current under saturation is dependent upon $v_{GS}$, thus making it a transconductance amplifier. A load resistor can be added to turn the transistor into a voltage amplifier. 

$v_o=v_{DS}=V_{DD}-i_DR_D$
$v_{DS}=V_{DD}-\dfrac{1}{2}k_nR_D(v_{GS}-V_t)^2$
![[EEC111/Notes/src/Pasted image 20240430121017.png]]

At saturation triode boundary
$V_{GS}\biggr\vert_B=V_t+\dfrac{\sqrt{2k_nR_DV_{DD}+1}-1}{k_nR_D}$

Saturation
$V_{DS}=V_{DD}-\dfrac{1}{2}k_nR_D(V_{GS}-V{t})^2$

$A_v=\dfrac{\partial v_{DS}}{\partial v_{GS}}\biggr|_{v_{GS}=V_{GS}}$
$A_v=-k_n(V_{OV})R_D$

$I_D=\dfrac{k_n}{2}V^2_{OV}$
$A_v=-\dfrac{I_DR_D}{V_{OV}/2}$
$|A_{v,max}|=\dfrac{V_{DD}-V_{DS}\biggr|_B}{V_{OV}\biggr|_B/2}=\dfrac{V_{DD}-V_{OV}\biggr|_B}{V_{OV}\biggr|_B/2}$

### Small signal
$i_D=\dfrac{k_n}{2}(V_{GS}+v_{gs}-V{t})^2$
$=\dfrac{k_n}{2}(V_{GS}-V_t)^2+k_n(V_{GS}-V_t)v_{gs}+\dfrac{k_n}{2}v_{gs}^2$
Neglect nonlinear term with $v_{gs}\ll2V_{OV}$ 
$g_m=k_nV_{OV}=\sqrt{2k_nI_D}=\dfrac{2I_D}{V_{OV}}$
$A_v=-g_mR_D$
$r_o=\dfrac{1}{\lambda I_D}$
![[EEC111/Notes/src/Pasted image 20240508212716.png]]

### Configurations
Ground one of three terminals, creating two port network with common ground. Common-source most popular. 
![[EEC111/Notes/src/Pasted image 20240508212900.png| 800]]