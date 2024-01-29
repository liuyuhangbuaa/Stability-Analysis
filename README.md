# Stability-analysis
Stability analysis of translational loop
$$
    \underbrace{\left( \begin{matrix}
   {{{\dot{\boldsymbol e}}}_{p}}  \\
   {{{\dot{\boldsymbol e}}}_{v}}  \\
\end{matrix} \right)}_{\dot{\boldsymbol e}}=\underbrace{\left( \begin{matrix}
   {{\boldsymbol 0}_{3\times 3}} & {{\boldsymbol I}_{3\times 3}}  \\
   \frac{-{{\boldsymbol K}_{p}}}{m} & \frac{-{{\boldsymbol K}_{v}}}{m}  \\
\end{matrix} \right)}_{\boldsymbol A} \underbrace{\left( \begin{matrix}
   {{\boldsymbol e}_{p}}  \\
   {{\boldsymbol e}_{v}}  \\
\end{matrix} \right)}_{\boldsymbol e}+\underbrace{\left( \begin{matrix}
   {{\boldsymbol 0}_{3\times 3}} & {{\boldsymbol 0}_{3\times 3}}  \\
   {{\boldsymbol 0}_{3\times 3}} & \frac{{{\boldsymbol I}_{3\times 3}}}{m}  \\
\end{matrix} \right)}_{\boldsymbol B} \underbrace{\left( \begin{matrix}
   {{\boldsymbol 0}_{3\times 1}}  \\
   {{{\tilde{\boldsymbol F}}}_{r}^E}  \\
\end{matrix} \right)}_{\tilde {\boldsymbol d}},
$$


where ${{{\tilde{\boldsymbol F}}}_{r}^E}=\hat{\boldsymbol F}_r^E-\boldsymbol F_r^E$.

It can be checked that $\boldsymbol A$ has negative definite structure if $\boldsymbol K_p$ and $\boldsymbol K_v$ have positive definite structures. As a consequence, there must exist a positive definite symmetric matrix $\boldsymbol M$ that meets the equation $\boldsymbol A^T \boldsymbol M+\boldsymbol M \boldsymbol A=-\boldsymbol I$. Subsequently, a Lyapunov function is designed as follows,
$$
\begin{equation} \label{lyapunov}
     V = {\boldsymbol e^T} \boldsymbol{Me} + \frac{1}{2}({{\tilde {\boldsymbol v}_r^E}})^T\tilde {\boldsymbol v}_r^E.
\end{equation}
$$

%where $\boldsymbol v_m^E$ represents  $\boldsymbol v_m^E$ for ease of representation.

Differentiate $V$, it can be implied that 
$$
\begin{align}\label{V-dot}
  \dot{ V} =&\dot{\boldsymbol e}^T \boldsymbol M\boldsymbol e+{\boldsymbol e}^T \boldsymbol M \dot{\boldsymbol e}+(\tilde{\boldsymbol v}_{r}^E)^T\dot{\tilde{\boldsymbol v}}_{r}^E\notag \\
  = &{\boldsymbol e^T}{\boldsymbol A^T}{\boldsymbol M}{\boldsymbol e}+{\boldsymbol {\tilde d}^T}{\boldsymbol B^T}{\boldsymbol M}{\boldsymbol e}+{\boldsymbol e^T}{\boldsymbol M}{\boldsymbol A}{\boldsymbol e}\notag \\
  &+{\boldsymbol e^T}{\boldsymbol M}{\boldsymbol B}{\boldsymbol {\tilde d}}+ (\tilde{\boldsymbol v}_{r}^E)^T\dot{\tilde{\boldsymbol v}}_{r}^E \notag \\
  %\left( {{\boldsymbol e^T}{\boldsymbol A^T} + {\boldsymbol {\tilde d}^T}{\boldsymbol B^T}} \right)\boldsymbol{Me}+ {\boldsymbol e^T}\boldsymbol M\left( {\boldsymbol {Ae} + \boldsymbol B\tilde {\boldsymbol {\boldsymbol d}}} \right)  + (\tilde{\boldsymbol v}_{r}^E)^T\dot{\tilde{\boldsymbol v}}_{r}^E \notag\\
 =& {\boldsymbol e^T}\left( {{\boldsymbol A^T}\boldsymbol M+\boldsymbol{MA}} \right)\boldsymbol e + 2{\boldsymbol e^T}\boldsymbol{MB}\tilde {\boldsymbol d} +
 %{\boldsymbol e^T}\boldsymbol{MB}\tilde {\boldsymbol d} + {{\tilde {\boldsymbol d}}^T}{\boldsymbol B^T}\boldsymbol{Me} + 
 (\tilde{\boldsymbol v}_{r}^E)^T\dot{\tilde{\boldsymbol v}}_{r}^E \notag\\
 =&  - {\boldsymbol e^T}\boldsymbol e + 2{\boldsymbol e^T}\boldsymbol{MB}\tilde {\boldsymbol d} + (\tilde{\boldsymbol v}_{r}^E)^T\dot{\tilde{\boldsymbol v}}_{r}^E.
\end{align}
$$

Furthermore, by resorting to Young's inequality [^1] , it can be verified that 
$$
\begin{align}
        -{{\boldsymbol e}^T}\boldsymbol e &\le -\frac{{{\boldsymbol e}^T}\boldsymbol {Me}}{{{\lambda }_{M}}\left( \boldsymbol M \right)},\tag{4a} \\
        -(\tilde{\boldsymbol v}_{r}^E)^T{{{\dot{{\boldsymbol v}}}}_{r}^E} &\le \frac{1}{4}(\tilde{\boldsymbol v}_{r}^E)^T{{{\tilde{\boldsymbol v}}}_{r}^E}+\delta,\tag{4b} \\
        {{\boldsymbol e}^T}\boldsymbol {MB}\tilde{\boldsymbol d}&\le \frac{1}{2\varepsilon }\lambda _{M}^{2}\left( \boldsymbol {MB} \right){{\boldsymbol e}^T}\boldsymbol e+\frac{\varepsilon }{2}{{\tilde{\boldsymbol d}}^T}\tilde{\boldsymbol d},\tag{4c}
    \end{align}
$$

where  $\varepsilon$ is an arbitrary positive constant, and ${\delta}=(\dot{\boldsymbol v}_{r}^E)^T{{{\dot{\boldsymbol v}}}_{r}^E}$  is a bounded value concerned with $\dot{\boldsymbol v}_{r}^E$ according to Assumption \ref{assumption1}.

From the stability analysis of the RSO, it can be obtained that 
$$
\begin{align} 
   (\tilde{\boldsymbol v}_{r}^E)^T{{{\dot{\tilde{\boldsymbol v}}}}_{r}^E}&=-\boldsymbol {L\vartheta} (\tilde{\boldsymbol v}_{r}^E)^T{{{\tilde{\boldsymbol v}}}_{r}^E}-(\tilde{\boldsymbol v}_{r}^E)^T{{{\dot{\boldsymbol v}}}_{r}^E}\notag \\ 
 & \le -{{\lambda }_{m}}(\boldsymbol L\boldsymbol \vartheta )(\tilde{\boldsymbol v}_{r}^E)^T{{{\tilde{\boldsymbol v}}}_{r}^E}+\frac{1}{4}(\tilde{\boldsymbol v}_{r}^E)^T{{{\tilde{\boldsymbol v}}}_{r}^E}+\delta,\tag{5a}\\
  \label{inequalities2-b} {{{\tilde{\boldsymbol d}}}^T}\tilde{\boldsymbol d}&=(\tilde{\boldsymbol v}_{r}^E)^T{{\boldsymbol \vartheta }^T}\boldsymbol \vartheta {{{\tilde{\boldsymbol v}}}_{r}^E} \le {{\lambda }_{M}}({{\boldsymbol \vartheta }^T}\boldsymbol {\vartheta} )(\tilde{\boldsymbol v}_{r}^E)^T{{{\tilde{\boldsymbol v}}}_{r}^E}.\tag{5b}
 \end{align}\label{inequalities2}
$$
Combining $\eqref{V-dot}$ - $\eqref{inequalities2}$, $\eqref{V-dot}$ can be adjusted that
$$
\begin{align}
\dot{ V} \le &-{{\boldsymbol e}^T}\boldsymbol e+\frac{1}{ \varepsilon }\lambda _{M}^{2}\left( \boldsymbol {MB} \right){{\boldsymbol e}^T}\boldsymbol e+ \varepsilon {{{\tilde{\boldsymbol d}}}^T}\tilde{\boldsymbol d}+(\tilde{\boldsymbol v}_{r}^E)^T\dot{\tilde{\boldsymbol v}}_{r}^E \notag\\
 \le &-\frac{ \varepsilon -\lambda _{M}^{2}\left( \boldsymbol {MB} \right)}{ \varepsilon {{\lambda }_{M}}\left( \boldsymbol M \right)}{{\boldsymbol e}^T}\boldsymbol {Me}+ \varepsilon {{\lambda }_{M}}({{\boldsymbol \vartheta }^T}\boldsymbol \vartheta )(\tilde{\boldsymbol v}_{r}^E)^T{{{\tilde{\boldsymbol v}}}_{r}^E}\notag\\
&-{{\lambda }_{m}}(\boldsymbol {L\vartheta} )(\tilde{\boldsymbol v}_{r}^E)^T{{{\tilde{\boldsymbol v}}}_{r}^E}+\frac{1}{4}(\tilde{\boldsymbol v}_{r}^E)^T{{{\tilde{\boldsymbol v}}}_{r}^E}+\delta \notag\\
  \le&-{{\sigma }_{1}}{{\boldsymbol e}^T}\boldsymbol {Me}-{{\sigma }_{2}}(\tilde{\boldsymbol v}_{r}^E)^T{{{\tilde{\boldsymbol v}}}_{r}^E}+\delta,\tag{5}
\end{align}
$$
where ${{\sigma }_{1}}=\frac{\varepsilon -\lambda _{m}^{2}\left( \boldsymbol {MB} \right)}{\varepsilon {{\lambda }_{m}}\left( \boldsymbol M \right)}$ and ${{\sigma }_{2}}={{\lambda }_{m}}(\boldsymbol {L\vartheta} )-\varepsilon {{\lambda }_{M}}({{\boldsymbol \vartheta }^T}\boldsymbol \vartheta )-\frac{1}{4}$. $\sigma_1$ can be ensured to be positive with $\varepsilon -\lambda _{m}^{2}\left( \boldsymbol {MB} \right)>0$ satisfied. $\sigma_2$ can be guaranteed to be positive by adjusting $\boldsymbol L$ properly.
We can obtain that $\dot{V} \le -\sigma_1V+\delta$ where $\gamma =\min \left\{ {{\sigma }_{1}},2{{\sigma }_{2}} \right\}$, which implies that
$$
\begin{align}
 0\le V\left( t \right)\le {{e}^{-\gamma t}}\left[ V(0)-\frac{\delta }{\gamma } \right]+\frac{\delta }{\gamma }.\tag{6}
 \end{align}
$$



[^1]: https://doi.org/10.1098/rspa.1912.0076 [W. H. Young, “On classes of summable functions and their Fourier series,” Proceedings of the Royal Society of London. Series A, Containing Papers of a Mathematical and Physical Character, vol. 87, no. 594, pp. 225–229, 1912.] 

