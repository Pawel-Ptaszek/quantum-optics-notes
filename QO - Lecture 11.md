← [[QO - Lecture 10|Lecture 10]] · [[QO - chapter I|Full chapter]]

# Lecture 11

**Recap (Lecture 9).** Normally ordered two-mode moments are averages over $P$,

$$\langle \hat a_1^\dagger \hat a_1 \hat a_2^\dagger \hat a_2\rangle=\int d^2 \alpha_1 \int d^2 \alpha_2\; |\alpha_1|^2 |\alpha_2|^2\,P(\alpha_1,\alpha_2).$$

For a positive semidefinite $P$ the Cauchy–Schwarz inequality gives

$$\big(g_{12}^{(2)}(0)\big)^2 \leq g_1^{(2)}(0)\,g_2^{(2)}(0),$$

and its violation is a nonclassicality witness.

## Light–matter interaction

### Maxwell's equations in reciprocal space

$$\nabla \cdot \mathbf E= \frac{\rho}{\epsilon_0}, \qquad \nabla \cdot \mathbf B=0, \qquad \nabla \times \mathbf E = -\partial_t \mathbf B, \qquad \nabla \times \mathbf B = \frac{1}{c^2} \partial_t \mathbf E + \frac{1}{\epsilon_0 c^2}\mathbf J .$$

With the spatial Fourier transform $\mathbf E(\mathbf r,t)=\frac{1}{(2 \pi)^{3/2}} \int d^3k\, \tilde{\mathbf E}(\mathbf k,t)\, e^{i \mathbf k\cdot \mathbf r}$ (and likewise for the other fields), $\nabla\to i\mathbf k$ and the equations become local in $\mathbf k$:

$$i\mathbf k \cdot \tilde{\mathbf E} = \frac{\tilde \rho}{\epsilon_0}, \qquad i\mathbf k\cdot\tilde{\mathbf B}=0, \qquad i\mathbf k\times\tilde{\mathbf E}=-\partial_t\tilde{\mathbf B}, \qquad i\mathbf k\times\tilde{\mathbf B}=\frac{1}{c^2}\partial_t\tilde{\mathbf E}+\frac{1}{\epsilon_0c^2}\tilde{\mathbf J}.$$

Split every vector field into a longitudinal part ($\parallel\mathbf k$) and a transverse part ($\perp\mathbf k$). Gauss's law fixes $\tilde{\mathbf E}_\parallel=-i\mathbf k\,\tilde\rho/(\epsilon_0k^2)$ instantaneously, so it is not a dynamical variable; $\mathbf B$ is purely transverse. The independent field degrees of freedom are therefore $\mathbf E_\perp$ and $\mathbf B$, i.e. the photons.

### Potentials and the Coulomb gauge

$\mathbf B=\nabla\times\mathbf A$ and $\mathbf E=-\nabla U-\partial_t\mathbf A$, i.e.

$$\tilde{\mathbf E} = - i\mathbf k\, \tilde U - \partial_t \tilde{\mathbf A}, \qquad \tilde{\mathbf B} = i \mathbf k \times \tilde{\mathbf A}.$$

**Gauge freedom**: the fields are unchanged under

$$\mathbf{A}'=\mathbf{A}+\nabla \Lambda, \qquad U'=U -\partial_t \Lambda .$$

In the **Coulomb gauge**, $\nabla \cdot \mathbf A=0$ ($i\mathbf k \cdot \tilde{\mathbf A}=0$), so $\mathbf A=\mathbf A_\perp$ and $\mathbf A_\parallel=0$. Inserting into Gauss's law, $i\mathbf k\cdot\tilde{\mathbf E}=k^2\tilde U=\tilde\rho/\epsilon_0$:

$$\tilde U = \frac{\tilde \rho(\mathbf k,t)}{\epsilon_0 k^2},$$

which is the instantaneous Coulomb potential of the charges. $U$ alone determines $\mathbf E_\parallel=-\nabla U$, and $\mathbf A_\perp$ alone determines the radiation field, $\mathbf E_\perp=-\partial_t\mathbf A_\perp$ and $\mathbf B$.

### Hamiltonian of charges and field

For particles of charge $q_\alpha$, mass $m_\alpha$, position $\mathbf r_\alpha$ and momentum $\mathbf p_\alpha$ (minimal coupling, Coulomb gauge),

$$H=\sum_\alpha \frac{1}{2m_\alpha} \big(\mathbf p_\alpha -q_\alpha \mathbf A(\mathbf r_\alpha)\big)^2+V_{\rm Coul}+H_{\rm field}+H_{\rm spin},$$

$$V_{\rm Coul}=\frac{\epsilon_0}{2}\int d^3 r\; \mathbf E_{\parallel}^2(\mathbf r)=\frac{1}{8\pi\epsilon_0}\sum_{\alpha\ne\beta}\frac{q_\alpha q_\beta}{|\mathbf r_\alpha-\mathbf r_\beta|}+\text{(Coulomb self-energies)},$$

$$H_{\rm field}=\frac{\epsilon_0}{2}\int d^3r\,\big(\mathbf E_\perp^2+c^2\mathbf B^2\big)=\sum_{j} \hbar \omega_j \Big(\hat a^\dagger_j \hat a_j +\frac{1}{2}\Big), \qquad H_{\rm spin}=-\sum_\alpha\frac{g_\alpha q_\alpha}{2m_\alpha}\,\mathbf S_\alpha\cdot\mathbf B(\mathbf r_\alpha).$$

Expanding the square separates the unperturbed part from the coupling:

$$H=H_0+H_{I1}+H_{I2}+H_{\rm spin}, \qquad H_0=\sum_\alpha \frac{\mathbf p_\alpha^2}{2m_\alpha}+V_{\rm Coul}+H_{\rm field},$$

$$H_{I1}=-\sum_\alpha \frac{q_\alpha}{2 m_\alpha}\big(\mathbf p_\alpha \cdot \mathbf A(\mathbf r_\alpha)+\mathbf A(\mathbf r_\alpha) \cdot \mathbf p_\alpha\big)=-\sum_\alpha\frac{q_\alpha}{m_\alpha}\,\mathbf p_\alpha\cdot\mathbf A(\mathbf r_\alpha), \qquad H_{I2}=\sum_\alpha \frac{q_\alpha^2}{2m_\alpha}\,\mathbf A(\mathbf r_\alpha)^2 .$$

($\mathbf p\cdot\mathbf A=\mathbf A\cdot\mathbf p$ because $\nabla\cdot\mathbf A=0$.)

**Order-of-magnitude estimates.**

$$\frac{H_{I2}}{H_{I1}} \approx \frac{q^2A^2/m}{qAp/m}=\frac{qA}{p}\approx\frac{qAp/m}{p^2/m}\approx\frac{H_{I1}}{H_0} ,$$

so $H_{I2}$ is of second order in the weak coupling. With $|\mathbf B|\approx kA$ and $|\mathbf S|\approx\hbar$,

$$\frac{H_{\rm spin}}{H_{I1}}\approx \frac{q\hbar kA/m}{qpA/m}=\frac{\hbar k}{p}\approx ka_0=\frac{2\pi a_0}{\lambda} \ll 1,$$

using $p\approx\hbar/a_0$ for an atomic electron; for optical light $ka_0\sim10^{-3}$.

### Long-wavelength (dipole) approximation

The charges of an atom at the origin are localised within $|\mathbf r_\alpha|\sim a_0$, and for $\lambda \gg a_0$ we have $e^{i\mathbf k\cdot\mathbf r_\alpha}\approx1$, i.e. $\mathbf A(\mathbf r_\alpha) \approx \mathbf A(0)$. Then

$$H \approx \sum_\alpha \frac{1}{2m_\alpha}\big(\mathbf p_\alpha-q_\alpha \mathbf A_\perp(0)\big)^2+V_{\rm Coul} + \sum_j \hbar \omega_j\Big(\hat a_j^\dagger \hat a_j+\frac{1}{2}\Big),$$

and the atom couples to the field only through its **dipole moment** $\mathbf d=\sum_\alpha q_\alpha \mathbf r_\alpha$.

### Power–Zienau–Woolley transformation

With the mode expansion $\mathbf A_\perp(0)=\sum_j\boldsymbol\varepsilon_j\sqrt{\frac{\hbar}{2\epsilon_0\omega_jL^3}}\,(\hat a_j+\hat a_j^\dagger)$ in a box of volume $L^3$, define the unitary

$$T=\exp\Big(-\frac{i}{\hbar}\, \mathbf d \cdot \mathbf A_\perp(0)\Big)=\exp\Big(\sum_j \big(\lambda_j^* \hat a_j - \lambda_j \hat a_j^\dagger\big)\Big), \qquad \lambda_j = \frac{i\, \boldsymbol\varepsilon_j \cdot \mathbf d}{\sqrt{2 \epsilon_0 \hbar \omega_j L^3}} .$$

For each mode $T$ is a displacement operator by $-\lambda_j$ (conditioned on the atomic operator $\mathbf d$). Using $e^S Xe^{-S}=X+[S,X]+\dots$ with $[r_k,p_l]=i\hbar\delta_{kl}$ and $[\hat a_j,\hat a_j^\dagger]=1$, the transformed operators are

$$T\mathbf r_\alpha T^\dagger =\mathbf r_\alpha, \qquad T\mathbf p_\alpha T^\dagger=\mathbf p_\alpha+q_\alpha \mathbf A_\perp(0), \qquad T\hat a_jT^\dagger=\hat a_j +\lambda_j .$$

In $H'=THT^\dagger$ the kinetic term becomes $\big(\mathbf p_\alpha+q_\alpha\mathbf A_\perp-q_\alpha\mathbf A_\perp\big)^2/2m_\alpha=\mathbf p_\alpha^2/2m_\alpha$: the $\mathbf A$-coupling (including $\mathbf A^2$) disappears. The field energy becomes

$$\sum_j\hbar\omega_j(\hat a_j^\dagger+\lambda_j^*)(\hat a_j+\lambda_j)=\sum_j\hbar\omega_j\hat a_j^\dagger\hat a_j+\sum_j\hbar\omega_j(\lambda_j\hat a_j^\dagger+\lambda_j^*\hat a_j)+\sum_j\hbar\omega_j|\lambda_j|^2 .$$

The middle term equals $-\mathbf d\cdot\sum_j i\boldsymbol\varepsilon_j\sqrt{\frac{\hbar\omega_j}{2\epsilon_0L^3}}(\hat a_j-\hat a_j^\dagger)$, and the last is the dipole self-energy $\varepsilon_{\rm dip}=\sum_j(\boldsymbol\varepsilon_j\cdot\mathbf d)^2/2\epsilon_0L^3$. Hence

$$H'=\sum_\alpha\frac{\mathbf p_\alpha^2}{2m_\alpha}+V_{\rm Coul}+\varepsilon_{\rm dip}+\sum_j\hbar\omega_j\Big(\hat a_j^\dagger\hat a_j+\frac12\Big)+H_I', \qquad H_{I}'=-\frac{1}{\epsilon_0}\,\mathbf d \cdot \mathbf D_\perp(0).$$

In the new representation the operator $\sum_j i\boldsymbol\varepsilon_j\sqrt{\hbar\omega_j/2\epsilon_0L^3}\,(\hat a_j-\hat a_j^\dagger)$ is the transverse displacement field divided by $\epsilon_0$, not $\mathbf E_\perp$:

$$\mathbf D = \epsilon_0 \mathbf E+\mathbf P, \qquad \mathbf P(\mathbf r)=\mathbf d\,\delta(\mathbf r), \qquad \mathbf P_\perp(\mathbf r) = \sum_j \frac{\boldsymbol\varepsilon_j (\boldsymbol\varepsilon_j \cdot \mathbf d)}{L^3}\, e^{i \mathbf k_j\cdot \mathbf r}.$$

Outside the atom $\mathbf P=0$, so $\mathbf P_\perp=-\mathbf P_\parallel=\epsilon_0\mathbf E_\parallel$ and $\mathbf D_\perp=\epsilon_0\mathbf E$. There the field operator is the full electric field, which is what a detector measures. The result is the familiar $-\mathbf d\cdot\mathbf E$ coupling, without an $\mathbf A^2$ term.

### Perturbation theory: the Dyson series

Write $H=H_0+H_I$ with eigenstates $H_0\ket{\varphi_k}=E_k\ket{\varphi_k}$ (atom $\otimes$ photon Fock states) and $U_0(t,t')=e^{-iH_0(t-t')/\hbar}$. The evolution operator satisfies $i\hbar\,\partial_tU=(H_0+H_I)U$, which is equivalent to the integral equation

$$U(t_f,t_i)=U_0(t_f,t_i)+\frac{1}{i\hbar}\int_{t_i}^{t_f}d\tau\;U_0(t_f,\tau)\,H_I\,U(\tau,t_i).$$

Iterating it (substituting $U$ on the right again and again) and inserting $\sum_k\ket{\varphi_k}\bra{\varphi_k}$ between the factors gives

$$\langle \varphi_f | U(t_f,t_i) | \varphi_i \rangle = \delta_{fi}\,e^{-iE_i(t_f-t_i)/\hbar}
+\frac{1}{i\hbar}\int_{t_i}^{t_f}d\tau_1\;e^{-iE_f(t_f-\tau_1)/\hbar}\,\langle\varphi_f|H_I|\varphi_i\rangle\,e^{-iE_i(\tau_1-t_i)/\hbar}$$
$$+\frac{1}{(i\hbar)^2}\sum_k\int_{t_i}^{t_f}d\tau_2\int_{t_i}^{\tau_2}d\tau_1\;e^{-iE_f(t_f-\tau_2)/\hbar}\,\langle\varphi_f|H_I|\varphi_k\rangle\,e^{-iE_k(\tau_2-\tau_1)/\hbar}\,\langle\varphi_k|H_I|\varphi_i\rangle\,e^{-iE_i(\tau_1-t_i)/\hbar}+\dots$$

and in general the $n$-th order term is

$$\frac{1}{(i\hbar)^n}\sum_{k_1\dots k_{n-1}}\int_{t_i\le\tau_1\le\dots\le\tau_n\le t_f}\!\!d\tau_n\cdots d\tau_1\;e^{-iE_f(t_f-\tau_n)/\hbar}\langle\varphi_f|H_I|\varphi_{k_{n-1}}\rangle e^{-iE_{k_{n-1}}(\tau_n-\tau_{n-1})/\hbar}\cdots \\\langle\varphi_{k_1}|H_I|\varphi_i\rangle e^{-iE_i(\tau_1-t_i)/\hbar}.$$

Read from right to left: the system evolves freely in $\ket{\varphi_i}$, interacts at $\tau_1$, propagates in the intermediate state $\ket{\varphi_{k_1}}$, and so on, up to the final state $\ket{\varphi_f}$. Each term is a diagram, and the intermediate states need not conserve energy, since the time integrals enforce energy conservation only between $\ket{\varphi_i}$ and $\ket{\varphi_f}$ for long times.

### Absorption and emission

<div style="text-align:center"><svg width="460" height="275" viewBox="0 0 460 275" xmlns="http://www.w3.org/2000/svg" fill="none" stroke="currentColor" stroke-width="1.5" font-family="Times New Roman, serif" font-size="17"><defs><marker id="arrL11" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="7" markerHeight="7" orient="auto"><path d="M0,0 L10,5 L0,10 z" fill="currentColor" stroke="none"/></marker></defs><line x1="12" y1="230" x2="12" y2="40" stroke-width="1" marker-end="url(#arrL11)"/><text x="18" y="48" font-size="13" font-style="italic" fill="currentColor" stroke="none">t</text><line x1="100" y1="230" x2="100" y2="40" stroke-width="2.4"/><circle cx="100" cy="135" r="4" fill="currentColor" stroke="none"/><polyline points="190.0,210.0 189.2,209.4 188.5,208.7 187.7,208.1 186.9,207.4 187.7,204.9 185.4,206.2 183.0,207.5 181.1,208.2 179.9,208.1 179.5,206.9 179.9,204.9 180.8,202.3 181.6,199.8 182.0,197.7 181.6,196.6 180.5,196.5 178.5,197.2 176.1,198.5 173.8,199.8 171.8,200.6 170.6,200.4 170.3,199.3 170.7,197.2 171.5,194.7 172.4,192.1 172.8,190.1 172.4,188.9 171.2,188.8 169.3,189.6 166.9,190.8 164.5,192.1 162.6,192.9 161.4,192.8 161.1,191.6 161.5,189.6 162.3,187.0 163.1,184.5 163.5,182.4 163.2,181.3 162.0,181.1 160.0,181.9 157.7,183.2 155.3,184.5 153.4,185.2 152.2,185.1 151.8,184.0 152.2,181.9 153.1,179.4 153.9,176.8 154.3,174.7 153.9,173.6 152.7,173.5 150.8,174.2 148.4,175.5 146.1,176.8 144.1,177.6 142.9,177.5 142.6,176.3 143.0,174.3 143.8,171.7 144.6,169.1 145.0,167.1 144.7,165.9 143.5,165.8 141.6,166.6 139.2,167.9 136.8,169.1 134.9,169.9 133.7,169.8 133.4,168.6 133.8,166.6 134.6,164.0 135.4,161.5 135.8,159.4 135.5,158.3 134.3,158.1 132.3,158.9 130.0,160.2 127.6,161.5 125.7,162.3 124.5,162.1 124.1,161.0 124.5,158.9 125.3,156.4 126.2,153.8 126.6,151.8 126.2,150.6 125.0,150.5 123.1,151.3 120.7,152.5 118.4,153.8 116.4,154.6 115.2,154.5 114.9,153.3 115.3,151.3 116.1,148.7 116.9,146.1 117.3,144.1 117.0,142.9 115.8,142.8 113.9,143.6 111.5,144.9 109.1,146.2 107.2,146.9 106.0,146.8 105.7,145.7 106.1,143.6 106.9,141.0 107.7,138.5 108.1,136.4 104.6,139.1 103.8,138.5 103.0,137.9 102.3,137.2" marker-end="url(#arrL11)"/><g fill="currentColor" stroke="none"><text x="80" y="200" font-style="italic" text-anchor="end">g</text><text x="80" y="80" font-style="italic" text-anchor="end">e</text><text x="190" y="226" font-style="italic">ω<tspan font-size="11" dy="4">j</tspan></text><text x="120" y="120" font-size="13">a<tspan font-size="10" dy="4">j</tspan><tspan dy="-4">: √n<tspan font-size="10" dy="4">j</tspan></tspan></text><text x="130" y="262" text-anchor="middle" font-size="14">absorption</text><text x="92" y="140" font-size="13" text-anchor="end">τ</text></g><line x1="310" y1="230" x2="310" y2="40" stroke-width="2.4"/><circle cx="310" cy="135" r="4" fill="currentColor" stroke="none"/><polyline points="312.0,133.0 312.8,132.4 313.5,131.7 314.3,131.1 315.1,130.4 317.4,131.7 316.6,129.2 315.8,126.6 315.4,124.6 315.7,123.4 316.9,123.3 318.9,124.1 321.2,125.3 323.6,126.6 325.5,127.4 326.7,127.3 327.1,126.1 326.7,124.1 325.9,121.5 325.0,118.9 324.6,116.9 325.0,115.7 326.2,115.6 328.1,116.4 330.5,117.7 332.8,119.0 334.8,119.7 336.0,119.6 336.3,118.5 335.9,116.4 335.1,113.8 334.3,111.3 333.9,109.2 334.2,108.1 335.4,108.0 337.3,108.7 339.7,110.0 342.1,111.3 344.0,112.1 345.2,111.9 345.6,110.8 345.2,108.7 344.3,106.2 343.5,103.6 343.1,101.6 343.4,100.4 344.6,100.3 346.6,101.1 348.9,102.4 351.3,103.6 353.2,104.4 354.4,104.3 354.8,103.1 354.4,101.1 353.6,98.5 352.7,96.0 352.3,93.9 352.7,92.8 353.9,92.6 355.8,93.4 358.2,94.7 360.5,96.0 362.5,96.7 363.7,96.6 364.0,95.5 363.6,93.4 362.8,90.9 362.0,88.3 361.6,86.3 361.9,85.1 363.1,85.0 365.0,85.7 367.4,87.0 369.8,88.3 371.7,89.1 372.9,89.0 373.3,87.8 372.9,85.8 372.0,83.2 371.2,80.6 370.8,78.6 371.1,77.4 372.3,77.3 374.3,78.1 376.7,79.4 379.0,80.7 381.0,81.4 382.2,81.3 382.5,80.1 382.1,78.1 381.3,75.5 380.4,73.0 380.0,70.9 380.4,69.8 381.6,69.7 383.5,70.4 385.9,71.7 388.3,73.0 390.2,73.8 391.4,73.6 391.7,72.5 391.3,70.4 390.5,67.9 389.7,65.3 389.3,63.3 389.6,62.1 390.8,62.0 392.8,62.8 395.1,64.0 397.5,65.3 399.4,66.1 397.4,62.1 398.2,61.5 399.0,60.9 399.7,60.2" marker-end="url(#arrL11)"/><g fill="currentColor" stroke="none"><text x="290" y="200" font-style="italic" text-anchor="end">e</text><text x="290" y="80" font-style="italic" text-anchor="end">g</text><text x="400" y="52" font-style="italic">ω<tspan font-size="11" dy="4">j</tspan></text><text x="340" y="160" font-size="13">a<tspan font-size="10" dy="-6">†</tspan><tspan font-size="10" dy="10">j</tspan><tspan dy="-4">: √(n<tspan font-size="10" dy="4">j</tspan><tspan dy="-4">+1)</tspan></tspan></text><text x="340" y="262" text-anchor="middle" font-size="14">emission</text><text x="302" y="140" font-size="13" text-anchor="end">τ</text></g></svg></div>

With $H_I'=-\mathbf d\cdot\mathbf D_\perp(0)/\epsilon_0$ and product states $\ket{\varphi}=\ket{\varphi^{\rm el}}\otimes\ket{\{n_j\}}$, the matrix element factorises:

$$\langle \varphi_f | H_I | \varphi_i \rangle = -\frac{1}{\epsilon_0}\,\langle \varphi_f^{\rm el}| \mathbf d | \varphi_i^{\rm el}\rangle\cdot\langle\{n_j\}_f|\mathbf D_\perp(0)|\{n_j\}_i\rangle .$$

$\mathbf D_\perp$ is linear in $\hat a_j$ and $\hat a_j^\dagger$, so at first order exactly one photon is absorbed or emitted:

- absorption $\ket{g;n_j}\to\ket{e;n_j-1}$ through $\hat a_j$, amplitude $\propto\sqrt{n_j}\,\boldsymbol\varepsilon_j\cdot\langle e|\mathbf d|g\rangle$;
- emission $\ket{e;n_j}\to\ket{g;n_j+1}$ through $\hat a_j^\dagger$, amplitude $\propto\sqrt{n_j+1}\,\boldsymbol\varepsilon_j\cdot\langle g|\mathbf d|e\rangle$, which is non-zero even for $n_j=0$: **spontaneous emission**.

$\langle e|\mathbf d|g\rangle\ne0$ requires states of opposite parity (dipole selection rules).



## Atom coupled to quantised modes

Write the atom in second quantisation over its levels, $H_{\rm atom} = \sum_j E_j\, \hat b^\dagger_j \hat b_j$. The dipole operator becomes $\mathbf d=\sum_{jk}\mathbf d_{jk}\hat b_j^\dagger\hat b_k$, and $-\mathbf d\cdot\mathbf E$ with $\mathbf E$ linear in $\hat a_\lambda,\hat a_\lambda^\dagger$ gives

$$H=\sum_\lambda \hbar \omega_\lambda \hat a^\dagger_\lambda \hat a_\lambda+\sum_j E_j\, \hat b_j^\dagger \hat b_j+\hbar\sum_{jk\lambda}g_{\lambda jk}\,\hat b^\dagger_j \hat b_k\,\big(\hat a_\lambda + \hat a_\lambda^\dagger\big), \qquad \hbar g_{\lambda jk}\propto-\boldsymbol\varepsilon_\lambda\cdot\mathbf d_{jk}\sqrt{\frac{\hbar\omega_\lambda}{2\epsilon_0L^3}} .$$

**Interaction picture.** With $H_0$ the first two terms and $U_0=e^{-iH_0t/\hbar}$, $V_I=U_0^\dagger VU_0$ follows from $\hat b_{j,I}(t) = e^{-iE_jt/\hbar}\hat b_j$ and $\hat a_{\lambda,I}(t)=e^{-i\omega_\lambda t}\hat a_\lambda$:

$$V_I(t)=\hbar \sum_{jk\lambda} g_{\lambda jk}\,\hat b_j^\dagger \hat b_k\, e^{i\omega_{jk}t}\big(\hat a_\lambda e^{-i\omega_\lambda t}+\hat a_\lambda^\dagger e^{i\omega_\lambda t}\big), \qquad \omega_{jk}=\frac{E_j-E_k}{\hbar}.$$

For an upward transition ($\omega_{jk}>0$), the term with $\hat a_\lambda$ oscillates at $\omega_{jk}-\omega_\lambda\approx0$ near resonance. The term with $\hat a_\lambda^\dagger$ oscillates at $\omega_{jk}+\omega_\lambda$, which is fast and averages out over the slow dynamics. Dropping it is the **rotating-wave approximation (RWA)**: excitation is accompanied by absorption, de-excitation by emission.

**Two levels, one mode.** Keeping $\ket1=\ket g$, $\ket2=\ket e$ and a single resonant mode,

$$V_I = \hbar g\, \hat b_2^\dagger \hat b_1\, \hat a+ \text{h.c.}$$

This is the **Jaynes–Cummings model**: a two-level atom inside a single-mode cavity.

<div style="text-align:center"><svg width="440" height="220" viewBox="0 0 440 220" xmlns="http://www.w3.org/2000/svg" fill="none" stroke="currentColor" stroke-width="1.6" font-family="Times New Roman, serif" font-size="16"><path d="M80,30 Q58,110 80,190" stroke-width="5"/><path d="M360,30 Q382,110 360,190" stroke-width="5"/><polyline points="80.0,110.0 82.0,107.4 84.0,104.9 86.0,102.4 88.0,99.9 90.0,97.4 92.0,95.1 94.0,92.7 96.0,90.5 98.0,88.4 100.0,86.3 102.0,84.4 104.0,82.5 106.0,80.8 108.0,79.3 110.0,77.8 112.0,76.5 114.0,75.4 116.0,74.4 118.0,73.6 120.0,73.0 122.0,72.5 124.0,72.2 126.0,72.0 128.0,72.0 130.0,72.2 132.0,72.6 134.0,73.2 136.0,73.9 138.0,74.7 140.0,75.8 142.0,76.9 144.0,78.3 146.0,79.8 148.0,81.4 150.0,83.1 152.0,85.0 154.0,87.0 156.0,89.1 158.0,91.2 160.0,93.5 162.0,95.9 164.0,98.3 166.0,100.7 168.0,103.2 170.0,105.7 172.0,108.3 174.0,110.9 176.0,113.4 178.0,115.9 180.0,118.5 182.0,120.9 184.0,123.4 186.0,125.7 188.0,128.0 190.0,130.2 192.0,132.3 194.0,134.4 196.0,136.3 198.0,138.0 200.0,139.7 202.0,141.2 204.0,142.6 206.0,143.9 208.0,144.9 210.0,145.9 212.0,146.6 214.0,147.2 216.0,147.7 218.0,147.9 220.0,148.0 222.0,147.9 224.0,147.7 226.0,147.2 228.0,146.6 230.0,145.9 232.0,144.9 234.0,143.9 236.0,142.6 238.0,141.2 240.0,139.7 242.0,138.0 244.0,136.3 246.0,134.4 248.0,132.3 250.0,130.2 252.0,128.0 254.0,125.7 256.0,123.4 258.0,120.9 260.0,118.5 262.0,115.9 264.0,113.4 266.0,110.9 268.0,108.3 270.0,105.7 272.0,103.2 274.0,100.7 276.0,98.3 278.0,95.9 280.0,93.5 282.0,91.2 284.0,89.1 286.0,87.0 288.0,85.0 290.0,83.1 292.0,81.4 294.0,79.8 296.0,78.3 298.0,76.9 300.0,75.8 302.0,74.7 304.0,73.9 306.0,73.2 308.0,72.6 310.0,72.2 312.0,72.0 314.0,72.0 316.0,72.2 318.0,72.5 320.0,73.0 322.0,73.6 324.0,74.4 326.0,75.4 328.0,76.5 330.0,77.8 332.0,79.3 334.0,80.8 336.0,82.5 338.0,84.4 340.0,86.3 342.0,88.4 344.0,90.5 346.0,92.7 348.0,95.1 350.0,97.4 352.0,99.9 354.0,102.4 356.0,104.9 358.0,107.4 360.0,110.0" stroke-opacity="0.45"/><polyline points="80.0,110.0 82.0,112.6 84.0,115.1 86.0,117.6 88.0,120.1 90.0,122.6 92.0,124.9 94.0,127.3 96.0,129.5 98.0,131.6 100.0,133.7 102.0,135.6 104.0,137.5 106.0,139.2 108.0,140.7 110.0,142.2 112.0,143.5 114.0,144.6 116.0,145.6 118.0,146.4 120.0,147.0 122.0,147.5 124.0,147.8 126.0,148.0 128.0,148.0 130.0,147.8 132.0,147.4 134.0,146.8 136.0,146.1 138.0,145.3 140.0,144.2 142.0,143.1 144.0,141.7 146.0,140.2 148.0,138.6 150.0,136.9 152.0,135.0 154.0,133.0 156.0,130.9 158.0,128.8 160.0,126.5 162.0,124.1 164.0,121.7 166.0,119.3 168.0,116.8 170.0,114.3 172.0,111.7 174.0,109.1 176.0,106.6 178.0,104.1 180.0,101.5 182.0,99.1 184.0,96.6 186.0,94.3 188.0,92.0 190.0,89.8 192.0,87.7 194.0,85.6 196.0,83.7 198.0,82.0 200.0,80.3 202.0,78.8 204.0,77.4 206.0,76.1 208.0,75.1 210.0,74.1 212.0,73.4 214.0,72.8 216.0,72.3 218.0,72.1 220.0,72.0 222.0,72.1 224.0,72.3 226.0,72.8 228.0,73.4 230.0,74.1 232.0,75.1 234.0,76.1 236.0,77.4 238.0,78.8 240.0,80.3 242.0,82.0 244.0,83.7 246.0,85.6 248.0,87.7 250.0,89.8 252.0,92.0 254.0,94.3 256.0,96.6 258.0,99.1 260.0,101.5 262.0,104.1 264.0,106.6 266.0,109.1 268.0,111.7 270.0,114.3 272.0,116.8 274.0,119.3 276.0,121.7 278.0,124.1 280.0,126.5 282.0,128.8 284.0,130.9 286.0,133.0 288.0,135.0 290.0,136.9 292.0,138.6 294.0,140.2 296.0,141.7 298.0,143.1 300.0,144.2 302.0,145.3 304.0,146.1 306.0,146.8 308.0,147.4 310.0,147.8 312.0,148.0 314.0,148.0 316.0,147.8 318.0,147.5 320.0,147.0 322.0,146.4 324.0,145.6 326.0,144.6 328.0,143.5 330.0,142.2 332.0,140.7 334.0,139.2 336.0,137.5 338.0,135.6 340.0,133.7 342.0,131.6 344.0,129.5 346.0,127.3 348.0,124.9 350.0,122.6 352.0,120.1 354.0,117.6 356.0,115.1 358.0,112.6 360.0,110.0" stroke-opacity="0.45"/><line x1="200" y1="96" x2="240" y2="96" stroke-width="2"/><line x1="200" y1="128" x2="240" y2="128" stroke-width="2"/><line x1="220" y1="126" x2="220" y2="100" stroke-width="1.2" marker-end="url(#arrJC)"/><defs><marker id="arrJC" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="6" markerHeight="6" orient="auto"><path d="M0,0 L10,5 L0,10 z" fill="currentColor" stroke="none"/></marker></defs><g fill="currentColor" stroke="none"><text x="246" y="100" font-style="italic">|e⟩</text><text x="246" y="132" font-style="italic">|g⟩</text><text x="180" y="117" font-size="13" font-style="italic">ω<tspan font-size="10" dy="4">0</tspan></text><text x="220" y="70" text-anchor="middle" font-size="14">atom, coupling g</text><text x="220" y="205" text-anchor="middle" font-size="14">cavity mode â, frequency ω</text><text x="58" y="24" font-size="12">mirror</text><text x="346" y="24" font-size="12">mirror</text></g></svg></div>

## Rabi model: two levels, one mode, no RWA

Keeping the counter-rotating terms,

$$V=\hbar g\,\big(\hat b_2^\dagger \hat b_1 + \hat b_1^\dagger\hat b_2\big)\big(\hat a+\hat a^\dagger\big)=\hbar g\,\hat\sigma_x(\hat a+\hat a^\dagger).$$

The extra terms $\hat\sigma^+\hat a^\dagger$ and $\hat\sigma^-\hat a$ create or destroy two excitations at once. The excitation number is then not conserved, and every $\ket{g,n}$, $\ket{e,n}$ is coupled to every other in one infinite chain. They matter only for ultrastrong coupling, $g\sim\omega$.

## Solving the Jaynes–Cummings model

Treat $\{\ket g,\ket e\}$ as a spin ½ ($\hat\sigma^+=\ket e\bra g$, $\hat\sigma_z=\ket e\bra e-\ket g\bra g$):

$$H=\frac{1}{2}\hbar \omega_0 \hat\sigma_z + \hbar\omega\, \hat a^\dagger \hat a + \hbar \big(g\, \hat a\, \hat\sigma^+ +g^*\, \hat a^\dagger \hat\sigma^-\big), \qquad \Delta = \omega_0-\omega .$$

**Conserved quantity.** The number of excitations $\hat N_e =\hat a^\dagger \hat a + \ket{e}\bra{e}$ commutes with $H$: $\hat a\hat\sigma^+$ removes a photon and excites the atom, so $[H,\hat N_e]=0$.

**Diagonalisation.** $H$ therefore only couples states with the same $N_e=n+1$:

$$\hat a^\dagger\hat\sigma^-\ket{e,n}=\sqrt{n+1}\,\ket{g,n+1}, \qquad \hat a\,\hat\sigma^+\ket{g,n+1}=\sqrt{n+1}\,\ket{e,n} .$$

Each pair $\{\ket{e,n},\ket{g,n+1}\}$ is closed. In it,

$$H_n=\hbar\begin{pmatrix}\omega(n+\frac12)+\frac\Delta2 & g\sqrt{n+1}\\ g^*\sqrt{n+1} & \omega(n+\frac12)-\frac\Delta2\end{pmatrix}
\quad\Rightarrow\quad E_{n,\pm}=\hbar\omega\Big(n+\frac12\Big)\pm\frac\hbar2\sqrt{\Delta^2+4|g|^2(n+1)} .$$

The eigenstates ("dressed states") are $c_1\ket{e,n}+c_2\ket{g,n+1}$, plus the uncoupled ground state $\ket{g,0}$ with $E=-\hbar\omega_0/2$. In the Rabi model, by contrast, all states are coupled and no such $2\times2$ blocks exist.

### Dynamics of $\ket{e,n}$

At resonance ($\Delta=0$, $g$ real), work in the interaction picture, $i\hbar\,\partial_t\ket{\psi_I}=V_I\ket{\psi_I}$, with

$$\ket{\psi(t)}=c_1(t)\ket{e,n}+c_2(t)\ket{g,n+1}, \qquad c_1(0)=1, \quad c_2(0)=0 .$$

$$\dot{c}_1=-ig \sqrt{n+1}\,c_2, \quad \dot{c}_2=-ig \sqrt{n+1}\, c_1
\quad\Rightarrow\quad c_1(t)=\cos\big(g \sqrt{n+1}\,t\big), \quad c_2(t)=-i\sin\big(g \sqrt{n+1}\, t\big).$$

The excited-state population oscillates,

$$P_e(t)=|c_1|^2=\frac12\Big(1+\cos\Omega_nt\Big), \qquad \Omega_n=2g\sqrt{n+1}.$$

The atom emits faster when more photons are present, which is **stimulated emission** ($\propto\sqrt{n+1}$). Even for $n=0$ it oscillates at $2g$: the **vacuum Rabi oscillation**, a reversible form of spontaneous emission into a single mode.

### Dynamics of an arbitrary state

Start from $\ket{\psi(0)}=(c_g \ket{g}+c_e \ket{e})\otimes \sum_n c_n \ket{n}$. Each $\ket{e,n}$ evolves as above, and each $\ket{g,n}$ couples to $\ket{e,n-1}$ with frequency $g\sqrt n$. Collecting terms,

$$\ket{\psi(t)}=\sum_n \Big[\big(c_e c_n \cos(g t\sqrt{n+1})-ic_g c_{n+1} \sin(g t\sqrt{n+1})\big)\ket{e} + \big(c_g c_n \cos(g t \sqrt{n})-i c_e c_{n-1} \sin(g t\sqrt{n})\big)\ket{g} \Big]\ket{n}.$$

**Atomic inversion.** Write $\ket{\psi} = \ket{e}\ket{\psi_e}+\ket{g}\ket{\psi_g}$ and define

$$Z(t)=\langle \psi_e | \psi_e \rangle - \langle \psi_g | \psi_g \rangle=\langle\hat\sigma_z\rangle$$

 For $c_e=1$,

$$Z(t)=\sum_n p_n\big(\cos^2(gt\sqrt{n+1})-\sin^2(gt\sqrt{n+1})\big)=\sum_n p_n\cos\big(2gt\sqrt{n+1}\big),$$

and for a coherent state

$$Z(t)=e^{-|\alpha|^2}\sum_n \frac{|\alpha|^{2n}}{n!}\, \cos\big(2gt \sqrt{n+1}\big).$$

### Collapse and revival

![[e24db40f-2a29-44f8-adf3-d358c4c5cd79.png|center|550]]

$Z(t)$ is a sum of oscillations with incommensurate frequencies $\Omega_n=2g\sqrt{n+1}$, weighted by the Poisson distribution of mean $\bar n=|\alpha|^2$ and width $\Delta n=\sqrt{\bar n}$.

- **Rabi oscillation.** At short times $W$ oscillates at $\Omega(\bar n) \approx 2 g|\alpha|$.
- **Collapse.** The oscillations get out of phase once the spread of frequencies over the occupied $n$ has accumulated a phase of order one:
$$t_c \approx \frac{1}{\Omega(\bar n + \sqrt{\bar n})-\Omega(\bar n - \sqrt{\bar n})}, \qquad \Omega(\bar n\pm\sqrt{\bar n})\approx2g\sqrt{\bar n}\pm g \ \Rightarrow\ t_c\approx\frac{1}{2g}.$$
A Gaussian average over $n$ gives the envelope $e^{-g^2t^2/2}$, i.e. $t_c\approx\sqrt2/g$, independent of $\bar n$.
- **Revival.** Because $n$ is discrete, neighbouring terms come back into phase when $\big(\Omega(\bar n+1)-\Omega(\bar n)\big)\,t_r = 2 \pi k$. With $\Omega(\bar n+1)-\Omega(\bar n)\approx g/\sqrt{\bar n}$,
$$t_r \approx \frac{2\pi k\sqrt{\bar n}}{g}=\frac{2\pi k|\alpha|}{g}, \qquad \frac{t_r}{t_c}\propto\sqrt{\bar n}.$$
The revivals are a direct signature of the discreteness of photon number. A classical field with the same intensity spread would only collapse.

**Interactive plot.** $W(t)$ for an atom starting in $\ket e$, for a coherent, thermal or Fock field. The dashed line marks the first revival $t_r=2\pi|\alpha|/g$.

```dataviewjs
// ===== CONFIG =====
const CFG = { state: "coh", nbar: 10, nbarMax: 40, tMax: 60, N: 400 };   // t in units of 1/g
// ==================
// ---- loader (leave as is) ----
const LIB = "FUW/lib/";
const load = (src) => new Promise((ok, no) => { const s = document.createElement("script"); s.src = src; s.onload = ok; s.onerror = () => no(new Error("could not load " + src)); document.head.append(s); });
const libPath = async (n) => { const here = dv.current().file.folder, up = here.includes("/") ? here.slice(0, here.lastIndexOf("/")) + "/" : ""; for (const p of [LIB + n, "lib/" + n, here + "/lib/" + n, up + "lib/" + n, ...app.vault.getFiles().filter((x) => x.path.endsWith("lib/" + n)).map((x) => x.path)]) if (await app.vault.adapter.exists(p)) return p; throw new Error("lib/" + n + " not found in this vault (is the lib folder synced to this computer?)"); };
if (!window.JXG) await (window.__jxg ??= libPath("jsxgraphcore.js").then((p) => load(app.vault.adapter.getResourcePath(p))).catch(() => load("https://cdn.jsdelivr.net/npm/jsxgraph@1.10.1/distrib/jsxgraphcore.js")).catch((e) => { window.__jxg = null; throw e; }));
if (!window.RL) await (window.__rl ??= libPath("rlti.js").then((p) => load(app.vault.adapter.getResourcePath(p))).catch((e) => { window.__rl = null; throw e; }));
const K = await RL.init(dv), { f, el, C } = K;
// ---- controls ----
const sel = K.select([["coh", "coherent |α⟩"], ["th", "thermal"], ["fock", "Fock |n⟩"]]); sel.value = CFG.state;
const sN = K.slider("n̄", 0, CFG.nbarMax, 0.1, CFG.nbar), sT = K.slider("g t_max", 5, 200, 1, CFG.tMax, (v) => (+v).toFixed(0));
const box = "background:#fff;border:1px solid #e5e7eb;border-radius:10px";
const div = el("div", `width:${K.W}px;height:${Math.round(K.W * 0.45)}px;${box};touch-action:none;margin-top:6px`);
const panel = el("div", "font-family:var(--font-monospace,monospace);font-size:0.8em;line-height:1.55;white-space:pre-wrap;color:var(--text-normal);margin-top:6px");
K.root.append(div, panel);
const ax = (n) => ({ name: n, withLabel: true, strokeColor: "#9ca3af", label: { position: "rt", offset: [-14, 14], fontSize: 14, strokeColor: C.ink }, ticks: { minorTicks: 0, strokeColor: "#9ca3af", label: { fontSize: 10, strokeColor: C.muted } } });
const b = JXG.JSXGraph.initBoard(div, { boundingbox: [-3, 1.15, CFG.tMax, -1.15], keepAspectRatio: false, axis: true, showCopyright: false, showNavigation: false, pan: { enabled: false }, zoom: { enabled: false }, defaultAxes: { x: ax("g t"), y: { ...ax("W(t)"), label: { position: "rt", offset: [8, -6], fontSize: 14, strokeColor: C.ink } } } });
const LF = [0]; for (let n = 1; n <= CFG.N; n++) LF[n] = LF[n - 1] + Math.log(n);
// photon-number distributions
function pn(kind, m) { const P = [];
  for (let n = 0; n < CFG.N; n++) P.push(kind === "coh" ? (m > 0 ? Math.exp(n * Math.log(m) - m - LF[n]) : +(n === 0)) : kind === "th" ? Math.pow(m / (1 + m), n) / (1 + m) : +(n === Math.round(m)));
  return P; }
let P = pn(CFG.state, CFG.nbar);
// inversion of an atom starting in |e⟩:  W(t) = Σ_n p_n cos(2 g t √(n+1))
const W = (t) => { let s = 0; for (let n = 0; n < CFG.N; n++) if (P[n] > 1e-12) s += P[n] * Math.cos(2 * t * Math.sqrt(n + 1)); return s; };
b.create("line", [[0, 0], [1, 0]], { fixed: true, highlight: false, strokeColor: C.muted, strokeWidth: 0.5 });
b.create("functiongraph", [W, 0, () => +sT.value], { fixed: true, highlight: false, strokeColor: C.obs, strokeWidth: 1.4, numberPointsHigh: 4000, numberPointsLow: 1500 });
const rev = b.create("line", [[() => 2 * Math.PI * Math.sqrt(+sN.value), -1], [() => 2 * Math.PI * Math.sqrt(+sN.value), 1]], { straightFirst: false, straightLast: false, fixed: true, highlight: false, strokeColor: C.sel, dash: 2, visible: () => sel.value === "coh" && +sN.value > 1 });
function update() {
  const m = +sN.value, kind = sel.value, tm = +sT.value; P = pn(kind, m);
  b.setBoundingBox([-0.04 * tm, 1.15, tm, -1.15], false); b.update();
  const tc = Math.SQRT2, tr = 2 * Math.PI * Math.sqrt(m);
  panel.textContent = kind === "fock"
    ? `Fock |${Math.round(m)}⟩: pure Rabi oscillation, period π/(g√(n+1)) = ${f(Math.PI / Math.sqrt(Math.round(m) + 1))}/g — no collapse`
    : kind === "coh"
    ? `coherent, n̄ = |α|² = ${f(m)}:  Rabi frequency ≈ 2g|α| = ${f(2 * Math.sqrt(m))} g   collapse t_c ≈ √2/g = ${f(tc)}/g   first revival t_r ≈ 2π|α|/g = ${f(tr)}/g (dashed)`
    : `thermal, n̄ = ${f(m)}: broad p_n → collapse without clean revivals`;
}
sel.onchange = update; for (const s of [sN, sT]) s.addEventListener("input", update);
update();
```

---
[[QO - Lecture 10|← Previous: Lecture 10]] · [[QO - Lecture 12|Next: Lecture 12 →]]
