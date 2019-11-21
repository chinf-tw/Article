# Chap. 4 Feedback Control System Characteristics

###### tags: `Morden Control System`
The use of error signal, which is defined as a signal proportional to  the between the desired and the actual response, results in a closed-loop sequence of operations that is called a feedback system.

<p style="color: blue;">
<b style="text-decoration:underline;">Def.</b> With the negative feedback scheme, a closed-loop system can use a measurement of the output signal and a comparison with the desired output to generate an error signal that is used by the controller to adjust the actuator.
</p>

### <span style="text-decoration:underline;">Error signal analysis</span>
Denote the signal $T_d(s)$ and $N(s)$ are disturbance and noise, respectively. Then, the tracking error can be defined as
$$E(s)=R(s)-Y(s)$$(4.1)

Now we only consider a unity feedback system, i.e.,$H(s)=1$ in $Fig. 4.4$ We may find that
$$
Y(s)=\frac{G_c(s)G(s)}{1+G_c(s)G(s)}R(s)+\frac{G(s)}{1+G_c(s)G(s)}T_d(s)-\frac{G_c(s)G(s)}{1+G_c(s)G(s)}N(s)
$$
then
$$
E(s)=R(s)-Y(s)=\frac{1}{1+G_c(s)G(s)}R(s)-\frac{G(s)}{1+G_c(s)G(s)}T_d(s)+\frac{G_c(s)G(s)}{1+G_c(s)G(s)}N(s)
$$
Define $L(s)=G_c(s)G(s)$ is known as the loop gain, the tracking error can be rewritten as
$$E(s)=\frac{1}{1+L(s)}R(s)-\frac{G(s)}{1+L(s)}T_d(s)+\frac{L(s)}{1+L(s)}N(s)$$
Therefore, the sensitivity function can be defined as
$$S(s)=\frac{1}{1+L(s)}$$
and the complementary sensitivity function can be defined as 
$$C(s)=\frac{L(s)}{1+L(s)}$$
Further, the tracking error in terns of $S(s)$ and $C(s)$ is
$$
\begin{aligned}
    & E(s)=S(s)R(s)-S(s)G(s)T_d(s)+C(s)N(s)\\
    & s.t.S(s)+C(s)=1\\
\end{aligned}
$$

### <span style="text-decoration:underline;">從系統的角度推導</span>

The system sensitivity is defined as the ratio as given by
$$S=\frac{\Delta T(s)/T(s)}{\Delta G(s)/G(s)}, where\ T(s)=\frac{Y(s)}{R(s)}$$
For small incremental changes, $S$ in $(4.11)$ can become
$$S=\frac{\partial T/T}{\partial G/G}=\frac{\partial lnT}{\partial lnG}$$
Recall that the system transfer function of the closed-loop system is
$$T(s)=\frac{Y(s)}{R(s)}=\frac{G_c(s)G(s)}{1+G_c(s)G(s)}$$
and thus, the sensitivity of the feedback system is
$$
S^T_G=\frac{\partial T}{\partial G}\frac{G}{T}=\frac{G_c}{(1+G_cG)^2}\frac{G}{GG_c/(1+G_cG)}=\frac{1}{1+G_c(s)G(s)}
$$
From this, the sensitivity of the system maybe reduced below that of the open-loop system by increasing $L(s)=G(s)G(s)$ over the range of interest.
Now, the sensitivity can be employed to determine $S^T_{\alpha}$, where $\alpha$ is a pammeter within the transfer $G(s)$.
Using the chain rule can yields
$$S^T_{\alpha}=S^T_GS^G_{\alpha}$$
By assuming $T(s,\alpha)=\frac{N(s,\alpha)}{D(s,\alpha)}$,then $S^T_{\alpha}$ can be rewritten as
$$S^T_{\alpha}=\frac{\partial lnT}{\partial ln\alpha}= \frac{\partial lnN}{\partial ln\alpha} \bigg\vert_{\alpha=\alpha_0}-\frac{\partial lnD}{\partial ln\alpha}\bigg\vert_{\alpha=\alpha_0}=S^N_{\alpha}-S^D_{\alpha}$$
where $\alpha_0$ denotes the nominal value of $\alpha$.
### EX. Feedback Amplifier
For open-loop circuit as in $Fig.4.5 (a)$, the output voltage is $V_o(s)=-K_aV_{in}(s)$ and associated transfer function
$$T(s)=-K_a$$
The sensitivity is $S^T_G=\frac{\partial T/T}{\partial G/G}=1\: (\because T=G)$
By using a potentiometer $R_P$, the closed-loop model in $Fig.4.5(b)$ then has a feedback ratio.
The resulted closed-loop transfer function of the feedback amplifier is
$$T(s)=\frac{-K_a}{1+K_a\beta}$$
Now the sensitivity of the closed-loop system $T(s)$ is
$$S^T_{K_a}=S^T_GS^G_{K_a}=\frac{1}{1+K_a\beta}$$

If $K_a$ is large, the sensitivity can be low.
For example, $K_a=10000$ and $\beta=0.1$, then we have $S^T_{K_a}=\frac{1}{1+10^3}\approx\frac{1}{1000}$
The magnitude of sensitivity can be one-thousandth of the original open-loop amplifier.
<!-- $$S^T_G\cdot S^G_{K_a}=\frac{1}{1+\frac{-K_a}{1+K_a(s+1)}}\cdot -1$$ -->