# Introduction
This file is a supplemented material serving for stability analysis of the combination of PD
controller and rain speed observer (RSO), which is a innovatively designed observer introduced
in manuscript submitted to IEEE Transactions on Industrial Electronics with paper ID 24-2548.
It can also provide reference for the stability analysis of other similar studies. More standardized and detailed representations can be found in the PDF files. 

# Stability Analysis
Stability analysis of the translational loop.

${\lambda _M}\left(  * \right)$ and ${\lambda _m}\left(  * \right)$ represent the maximum and minimum eigenvalues of a matrix, respectively. $\dot{* }$ and $\tilde {* }$ denote the first-order time derivative of ${* }$ and estimation error of $*$, respectively.

$$\begin{align\*}
\boldsymbol A&=\left\[\\begin{array}{cc}
  {\boldsymbol 0}\_{3\times 3} & {\boldsymbol I}\_{3\times 3} \\\\
  -{\boldsymbol K_p} & -{\boldsymbol K_v}
\\end{array}\right\],\\\\\\
\boldsymbol B&=\left\[\\begin{array}{cc}
  {\boldsymbol 0}\_{3\times 3} & {\boldsymbol 0}\_{3\times 3} \\\\
  {\boldsymbol 0}\_{3\times 3} & \frac{{\boldsymbol I}\_{3\times 3}}{m}
\\end{array}\right\],\\\\\\
\boldsymbol d&=\left\[\\begin{array}{c}
  {\boldsymbol 0}\_{3\times 3}  \\\\
  \tilde{\boldsymbol F}\_r^E 
\\end{array}\right\].
\end{align\*}\tag{1}$$


$$\begin{align\*}
\boldsymbol{\dot e}=\boldsymbol {Ae} +\boldsymbol{Bd},
\end{align\*} \tag{2}$$

where $\boldsymbol{e}=\left\[ {\boldsymbol{ e}\_p^T,\boldsymbol{ e}\_v^T}\right\]^T$, $\boldsymbol e_p$ and $\boldsymbol e_v$ represent the tracking errors of position and velocity, respectively, $\tilde{\boldsymbol F}\_r^E=\hat{\boldsymbol F}\_r^E-\boldsymbol F_r^E=-\boldsymbol {\vartheta} \tilde{\boldsymbol v}_{r}^E$ represent the estimation error of ${\boldsymbol F}\_r^E$.



It can be checked that $\boldsymbol A$ has negative definite structure if $\boldsymbol K_p$ and $\boldsymbol K_v$ have positive definite structures. As a consequence, there must exist a positive definite symmetric matrix $\boldsymbol M$ that meets the equation $\boldsymbol A^T \boldsymbol M+\boldsymbol M \boldsymbol A=-\boldsymbol I$. Subsequently, a Lyapunov function is designed as follows,

$$\begin{align\*} 
V = {\boldsymbol e^T} \boldsymbol{Me} + \frac{1}{2}({{\tilde {\boldsymbol v}_r^E}})^T\tilde {\boldsymbol v}_r^E.
\end{align\*}\tag{3}$$

Differentiate $V$, it can be implied that 

$$\begin{align\*}
\dot{V} &=\dot{\boldsymbol e}^T \boldsymbol M \boldsymbol e+{\boldsymbol e}^T \boldsymbol M \dot{\boldsymbol e}+(\tilde{\boldsymbol v}_ {r}^E)^T\dot{\tilde{\boldsymbol v}}_ {r}^E \\\\\\
&= {\boldsymbol e^T}{\boldsymbol A^T}{\boldsymbol M}{\boldsymbol e}+{\boldsymbol {\tilde d}^T}{\boldsymbol B^T}{\boldsymbol M}{\boldsymbol e}+{\boldsymbol e^T}{\boldsymbol M}{\boldsymbol A}{\boldsymbol e}+{\boldsymbol e^T}{\boldsymbol M}{\boldsymbol B}{\boldsymbol {\tilde d}}+ (\tilde{\boldsymbol v}_ {r}^E)^T\dot{\tilde{\boldsymbol v}}_ {r}^E \\\\\\
&={\boldsymbol e^T}\left( {{\boldsymbol A^T}\boldsymbol M+\boldsymbol{MA}} \right)\boldsymbol e + 2{\boldsymbol e^T}\boldsymbol{MB}\tilde {\boldsymbol d} +(\tilde{\boldsymbol v}_ {r}^E)^T\dot{\tilde{\boldsymbol v}}_ {r}^E\\\\\\
 &=- {\boldsymbol e^T}\boldsymbol e + 2{\boldsymbol e^T}\boldsymbol{MB}\tilde {\boldsymbol d} + (\tilde{\boldsymbol v}_ {r}^E)^T\dot{\tilde{\boldsymbol v}}_{r}^E.
\end{align\*} \tag{4}$$


Furthermore, by resorting to Young's inequality [^1] , it can be verified that 

$$\begin{align\*}
-{{\boldsymbol e}^T}\boldsymbol e &\le -\frac{{{\boldsymbol e}^T}\boldsymbol {Me}}{{{\lambda }_ {M}}\left( \boldsymbol M \right)}, \\\\\\
\end{align\*} \tag{5a}$$
$$\begin{align\*}
-(\tilde{\boldsymbol v}_ {r}^E)^T{{{\dot{{\boldsymbol v}}}}_ {r}^E} &\le \frac{1}{4}(\tilde{\boldsymbol v}_ {r}^E)^T{{{\tilde{\boldsymbol v}}}_{r}^E}+\delta, \\\\\\
\end{align\*}\tag{5b}$$
$$\begin{align\*}
{{\boldsymbol e}^T}\boldsymbol {MB}\tilde{\boldsymbol d}&\le \frac{1}{2\varepsilon }\lambda _{M}^{2}\left( \boldsymbol {MB} \right){{\boldsymbol e}^T}\boldsymbol e+\frac{\varepsilon }{2}{{\tilde{\boldsymbol d}}^T}\tilde{\boldsymbol d},
\end{align\*}\tag{5c}$$

where  $\varepsilon$ is an arbitrary positive constant, and ${\delta}=(\dot{\boldsymbol v}_ {r}^E)^T{{{\dot{\boldsymbol v}}}_ {r}^E}$  is a bounded value concerned with $\dot{\boldsymbol v}_{r}^E$.

From the stability analysis of the RSO, it can be obtained that 

$$\begin{align\*}
(\tilde{\boldsymbol v}_ {r}^E)^T{{{\dot{\tilde{\boldsymbol v}}}}_ {r}^E}&=-\boldsymbol {L\vartheta} (\tilde{\boldsymbol v}_ {r}^E)^T{{{\tilde{\boldsymbol v}}}_ {r}^E}-(\tilde{\boldsymbol v}_ {r}^E)^T{{{\dot{\boldsymbol v}}}_ {r}^E} \\\\\\\\ 
&\le -{{\lambda }_ {m}}(\boldsymbol L\boldsymbol \vartheta )(\tilde{\boldsymbol v}_ {r}^E)^T{{{\tilde{\boldsymbol v}}}_ {r}^E}+\frac{1}{4}(\tilde{\boldsymbol v}_ {r}^E)^T{{{\tilde{\boldsymbol v}}}_ {r}^E}+\delta,\\\\\\
\end{align\*} \tag{6a}$$
$$\begin{align\*}
{{{\tilde{\boldsymbol d}}}^T}\tilde{\boldsymbol d}&=(\tilde{\boldsymbol v}_ {r}^E)^T{{\boldsymbol \vartheta }^T}\boldsymbol \vartheta {{{\tilde{\boldsymbol v}}}_ {r}^E} \le {{\lambda }_ {M}}({{\boldsymbol \vartheta }^T}\boldsymbol {\vartheta} )(\tilde{\boldsymbol v}_ {r}^E)^T{{{\tilde{\boldsymbol v}}}_ {r}^E}.
\end{align\*}\tag{6b}$$


Combining (4)-(6), (4) can be adjusted that

$$\begin{align\*}
\dot{ V} &\le -{{\boldsymbol e}^T}\boldsymbol e+\frac{1}{ \varepsilon }\lambda _ {M}^{2}\left( \boldsymbol {MB} \right){{\boldsymbol e}^T}\boldsymbol e+ \varepsilon {{{\tilde{\boldsymbol d}}}^T}\tilde{\boldsymbol d}+(\tilde{\boldsymbol v}_ {r}^E)^T\dot{\tilde{\boldsymbol v}}_ {r}^E\\\\\\
&\le -\frac{ \varepsilon -\lambda _ {M}^{2}\left( \boldsymbol {MB} \right)}{ \varepsilon {{\lambda }_ {M}}\left( \boldsymbol M \right)}{{\boldsymbol e}^T}\boldsymbol {Me}+ \varepsilon {{\lambda }_ {M}}({{\boldsymbol \vartheta }^T}\boldsymbol \vartheta )(\tilde{\boldsymbol v}_ {r}^E)^T{{{\tilde{\boldsymbol v}}}_ {r}^E}\\\\\\
&-{{\lambda }_ {m}}(\boldsymbol {L\vartheta} )(\tilde{\boldsymbol v}_ {r}^E)^T{{{\tilde{\boldsymbol v}}}_ {r}^E}+\frac{1}{4}(\tilde{\boldsymbol v}_ {r}^E)^T{{{\tilde{\boldsymbol v}}}_ {r}^E}+\delta\\\\\\
&\le -{{\sigma }_ {1}}{{\boldsymbol e}^T}\boldsymbol {Me}-{{\sigma }_ {2}}(\tilde{\boldsymbol v}_ {r}^E)^T{{{\tilde{\boldsymbol v}}}_ {r}^E}+\delta,
\end{align\*}\tag{7}$$

where ${{\sigma }_ {1}}=\frac{\varepsilon -\lambda _ {M}^{2}\left( \boldsymbol {MB} \right)}{\varepsilon {{\lambda }_ {M}}\left( \boldsymbol M \right)}$ and ${{\sigma }_ {2}}={{\lambda }_ {m}}(\boldsymbol {L\vartheta} )-\varepsilon {{\lambda }_ {M}}({{\boldsymbol \vartheta }^T}\boldsymbol \vartheta )-\frac{1}{4}$. $\sigma_1$ can be ensured to be positive with $\varepsilon -\lambda _ {M}^{2}\left( \boldsymbol {MB} \right)>0$ satisfied. $\sigma_2$ can be guaranteed to be positive by adjusting $\boldsymbol L$ properly.
We can obtain that $\dot{V} \le -\gamma V+\delta$ where $\gamma =\min \\{ {{\sigma }_ {1}},2{{\sigma }_{2}} \\}$, which implies that
$$0\le V( t)\le {{e}^{-\gamma t}} \left\[ V(0)-\frac{\delta }{\gamma } \right\]+\frac{\delta }{\gamma }.\tag{8}$$



[^1]: https://doi.org/10.1098/rspa.1912.0076 [W. H. Young, “On classes of summable functions and their Fourier series,” Proceedings of the Royal Society of London. Series A, Containing Papers of a Mathematical and Physical Character, vol. 87, no. 594, pp. 225–229, 1912.] 

