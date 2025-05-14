Linear amplifiers have an output which is an input scaled up by [[01 School/01.01 Spring 2024/EEC111/Notes/Gain Calculations|gain]], typically depicted with the equation $v_o=Av_i$. However, linearity can be limited by amplifier *saturation*. Meanwhile, nonlinear amplifiers experience distortion and are approximated with Taylor series. 
# Amplifier Types
Amplifiers are two port networks which can share a common ground.

| Amplifier Type                 |     |     |
| ------------------------------ | --- | --- |
| Voltage Amplifier              |     |     |
| Current Amplifier              |     |     |
| Transresistance <br>Amplifier  |     |     |
| Transconductance <br>Amplifier |     |     |
**Open Circuit Voltage Gain**
$A_{vo}\equiv\dfrac{v_o}{v_i}$

**Short Circuit Current Gain**
$A_{is}\equiv\dfrac{i_o}{i_i}$

**Short Circuit Transconductance**
$R_m\equiv\dfrac{i_o}{v_i}$

**Open Circuit Transresistance**
$G_m\equiv\dfrac{v_o}{i_i}$

**Relationships**
$A_{vo}=A_{is}\left(\dfrac{R_o}{R_i}\right)=G_mR_o=\dfrac{R_m}{R_i}$

**Input Resistance**
$R_i=\dfrac{v_i}{i_i}$

**Output Resistance**
Eliminate input source, then apply test voltage $v_x$ at output
$R_o=\dfrac{v_x}{i_x}$
