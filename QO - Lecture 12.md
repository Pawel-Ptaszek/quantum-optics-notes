← [[QO - Lecture 11|Lecture 11]] · [[QO - chapter I|Full chapter]]

# Lecture 12

> [!info] Midterm
> 2 problems, 1 sheet of paper allowed. Topics:
> - states of light in Fock space
> - beam splitters, linear optics
> - correlation functions
> - phase space, Wigner function
> - nonclassical states (squeezed)

## Nondegenerate parametric amplification

$$H=\hbar\omega_1 \Big(\hat n_1+\frac{1}{2}\Big)+\hbar\omega_2 \Big(\hat n_2 +\frac{1}{2}\Big)+i\hbar \big(g(t)\,\hat a_1^\dagger \hat a_2^\dagger - g^*(t)\,\hat a_1 \hat a_2\big), \qquad g(t)=g\,e^{-i\omega_pt},\quad \omega_p=\omega_1+\omega_2 .$$

**Where $g$ comes from.** In a $\chi^{(2)}$ crystal the interaction energy contains $\chi^{(2)}E_pE_1E_2$. A strong pump is treated as a classical, undepleted field $E_p\propto e^{-i\omega_pt}$. Then $g\propto\chi^{(2)}E_p$: the coupling is proportional to the pump amplitude and carries its phase and time dependence.

**Atomic implementations.** The same Hamiltonian appears in four-wave mixing in atomic vapours (e.g. a double-Λ scheme in Rb, where two pump photons create a signal–idler pair through $\chi^{(3)}$). It also describes spontaneous Raman scattering, where a Stokes photon $\hat a_S^\dagger$ is created together with a collective spin excitation $\hat S^\dagger$, $H\propto\hat a_S^\dagger\hat S^\dagger+\text{h.c.}$ (the write-in step of DLCZ-type quantum memories).

In the interaction picture with respect to $\hbar\omega_1\hat n_1+\hbar\omega_2\hat n_2$, the phase $e^{-i\omega_pt}$ cancels and

$$H_I=i\hbar g\,\big(\hat a_1^\dagger \hat a_2^\dagger-\hat a_1 \hat a_2\big)\qquad(g \text{ real}).$$

### SU(1,1) structure

Define

$$\hat K_+=\hat a_1^\dagger\hat a_2^\dagger, \qquad \hat K_-=\hat a_1\hat a_2, \qquad \hat K_0=\frac12\big(\hat n_1+\hat n_2+1\big).$$

Using $[\hat a_i,\hat a_i^\dagger]=1$,

$$[\hat K_-,\hat K_+]=(1+\hat n_1)(1+\hat n_2)-\hat n_1\hat n_2=2\hat K_0, \qquad [\hat K_0,\hat K_\pm]=\pm\hat K_\pm .$$

This is the algebra su(1,1). It differs from su(2), $[\hat J_+,\hat J_-]=2\hat J_0$, only by the sign. So $H_I=i\hbar g(\hat K_+-\hat K_-)$ generates a "hyperbolic rotation": $\cosh$ and $\sinh$ appear where su(2) would give $\cos$ and $\sin$.

### Heisenberg equations

$$\dot{\hat a}_1=\frac{1}{i\hbar}[\hat a_1,H_I]=g\,\hat a_2^\dagger, \qquad \dot{\hat a}_2=g\,\hat a_1^\dagger
\quad\Rightarrow\quad
\hat a_1(t)=\cosh r\,\hat a_1+\sinh r\,\hat a_2^\dagger, \qquad \hat a_2(t)=\cosh r\,\hat a_2+\sinh r\,\hat a_1^\dagger, \qquad r=gt .$$

**Depleted pump.** If the pump is also quantised, add $\hbar\omega_p(\hat n_p+\frac12)$ and replace $g\to g\,\hat a_p$:

$$H_I= i\hbar\big(g\,\hat a_p\hat a_1^\dagger \hat a_2^\dagger - g^*\,\hat a_p^\dagger\hat a_1 \hat a_2\big).$$

One pump photon is converted into a signal–idler pair:

<div style="text-align:center"><svg width="400" height="230" viewBox="0 0 400 230" xmlns="http://www.w3.org/2000/svg" fill="none" stroke="currentColor" stroke-width="1.5" font-family="Times New Roman, serif" font-size="17"><defs><marker id="arrPV" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="7" markerHeight="7" orient="auto"><path d="M0,0 L10,5 L0,10 z" fill="currentColor" stroke="none"/></marker></defs><line x1="30" y1="210" x2="30" y2="25" stroke-width="1" marker-end="url(#arrPV)"/><polyline points="200.0,215.0 200.0,214.0 200.0,213.0 200.0,212.0 200.0,211.0 200.0,210.0 200.0,209.0 200.0,208.0 197.4,207.0 195.3,206.0 194.2,205.0 194.2,204.0 195.3,203.0 197.4,202.0 200.0,201.0 202.6,200.0 204.7,199.0 205.8,198.0 205.8,197.0 204.7,196.0 202.6,195.0 200.0,194.0 197.4,193.0 195.3,192.0 194.2,191.0 194.2,190.0 195.3,189.0 197.4,188.0 200.0,187.0 202.6,186.0 204.7,185.0 205.8,184.0 205.8,183.0 204.7,182.0 202.6,181.0 200.0,180.0 197.4,179.0 195.3,178.0 194.2,177.0 194.2,176.0 195.3,175.0 197.4,174.0 200.0,173.0 202.6,172.0 204.7,171.0 205.8,170.0 205.8,169.0 204.7,168.0 202.6,167.0 200.0,166.0 197.4,165.0 195.3,164.0 194.2,163.0 194.2,162.0 195.3,161.0 197.4,160.0 200.0,159.0 202.6,158.0 204.7,157.0 205.8,156.0 205.8,155.0 204.7,154.0 202.6,153.0 200.0,152.0 197.4,151.0 195.3,150.0 194.2,149.0 194.2,148.0 195.3,147.0 197.4,146.0 200.0,145.0 202.6,144.0 204.7,143.0 205.8,142.0 205.8,141.0 204.7,140.0 202.6,139.0 200.0,138.0 197.4,137.0 195.3,136.0 194.2,135.0 194.2,134.0 195.3,133.0 200.0,132.0 200.0,131.0 200.0,130.0 200.0,129.0 200.0,128.0 200.0,127.0 200.0,126.0 200.0,125.0 200.0,124.0" marker-end="url(#arrPV)"/><polyline points="200.0,120.0 199.3,119.3 198.5,118.7 197.8,118.0 197.0,117.3 196.3,116.6 195.6,116.0 193.1,117.2 191.2,117.8 190.0,117.7 189.7,116.5 190.2,114.5 191.1,111.9 192.0,109.4 192.5,107.4 192.2,106.2 191.0,106.1 189.1,106.7 186.7,107.9 184.2,109.1 182.3,109.8 181.1,109.6 180.8,108.5 181.3,106.4 182.2,103.9 183.1,101.4 183.6,99.3 183.3,98.2 182.1,98.0 180.2,98.7 177.8,99.9 175.3,101.1 173.4,101.7 172.2,101.6 171.9,100.4 172.4,98.4 173.3,95.8 174.2,93.3 174.7,91.3 174.4,90.1 173.2,90.0 171.3,90.6 168.9,91.8 166.4,93.0 164.5,93.7 163.3,93.5 163.0,92.3 163.5,90.3 164.4,87.8 165.3,85.3 165.8,83.2 165.5,82.1 164.3,81.9 162.4,82.6 160.0,83.8 157.5,85.0 155.6,85.6 154.4,85.5 154.1,84.3 154.6,82.3 155.5,79.7 156.4,77.2 156.9,75.2 156.6,74.0 155.4,73.9 153.5,74.5 151.1,75.7 148.6,76.9 146.7,77.6 145.5,77.4 145.2,76.2 145.7,74.2 146.6,71.7 147.5,69.2 148.0,67.1 147.7,66.0 146.5,65.8 144.6,66.5 142.2,67.7 139.7,68.9 137.8,69.5 136.6,69.4 136.3,68.2 136.8,66.2 137.7,63.6 138.6,61.1 139.1,59.1 138.8,57.9 137.6,57.7 135.7,58.4 133.3,59.6 130.8,60.8 128.9,61.5 127.7,61.3 127.4,60.1 127.9,58.1 128.8,55.6 129.7,53.1 130.2,51.0 129.9,49.9 128.8,49.7 126.8,50.4 124.4,51.6 121.9,52.7 120.0,53.4 118.8,53.3 118.5,52.1 119.0,50.1 119.9,47.5 120.8,45.0 121.3,43.0 121.0,41.8 119.9,41.6 117.9,42.3 115.5,43.5 113.0,44.7 111.1,45.4 109.9,45.2 109.6,44.0 110.1,42.0 111.0,39.5 112.0,37.0 112.4,34.9 112.1,33.8 111.0,33.6 109.0,34.3 106.6,35.5 104.1,36.6 102.2,37.3 101.0,37.2 100.7,36.0 101.2,34.0 102.1,31.4 103.1,28.9 100.6,30.1 99.9,29.4 99.2,28.8 98.4,28.1 97.7,27.4 96.9,26.7 96.2,26.1 95.4,25.4" marker-end="url(#arrPV)"/><polyline points="200.0,120.0 200.7,119.3 201.5,118.7 202.2,118.0 203.0,117.3 203.7,116.6 204.4,116.0 203.5,113.4 203.0,111.4 203.3,110.3 204.5,110.1 206.5,110.8 208.9,111.9 211.3,113.1 213.3,113.8 214.5,113.6 214.8,112.5 214.3,110.4 213.3,107.9 212.4,105.4 211.9,103.4 212.2,102.2 213.4,102.0 215.4,102.7 217.8,103.9 220.2,105.1 222.2,105.8 223.4,105.6 223.7,104.4 223.2,102.4 222.2,99.9 221.3,97.3 220.8,95.3 221.1,94.2 222.3,94.0 224.3,94.7 226.7,95.8 229.1,97.0 231.1,97.7 232.3,97.5 232.6,96.4 232.1,94.3 231.1,91.8 230.2,89.3 229.7,87.3 230.0,86.1 231.2,85.9 233.2,86.6 235.6,87.8 238.0,89.0 240.0,89.7 241.2,89.5 241.5,88.3 241.0,86.3 240.0,83.8 239.1,81.2 238.6,79.2 238.9,78.1 240.1,77.9 242.1,78.6 244.5,79.7 246.9,80.9 248.9,81.6 250.1,81.4 250.4,80.3 249.9,78.2 248.9,75.7 248.0,73.2 247.5,71.2 247.8,70.0 249.0,69.8 251.0,70.5 253.4,71.7 255.8,72.9 257.8,73.6 259.0,73.4 259.3,72.2 258.8,70.2 257.8,67.7 256.9,65.1 256.4,63.1 256.7,61.9 257.9,61.8 259.9,62.5 262.3,63.6 264.7,64.8 266.7,65.5 267.9,65.3 268.2,64.2 267.7,62.1 266.7,59.6 265.8,57.1 265.3,55.1 265.6,53.9 266.8,53.7 268.8,54.4 271.2,55.6 273.6,56.8 275.6,57.5 276.8,57.3 277.1,56.1 276.6,54.1 275.6,51.6 274.7,49.0 274.2,47.0 274.5,45.8 275.7,45.7 277.7,46.4 280.1,47.5 282.5,48.7 284.5,49.4 285.7,49.2 286.0,48.1 285.5,46.0 284.5,43.5 283.6,41.0 283.1,39.0 283.4,37.8 284.6,37.6 286.6,38.3 289.0,39.5 291.4,40.7 293.4,41.4 294.6,41.2 294.9,40.0 294.4,38.0 293.4,35.5 292.5,32.9 292.0,30.9 292.3,29.7 293.5,29.6 295.5,30.3 297.9,31.4 300.3,32.6 299.4,30.1 300.1,29.4 300.8,28.8 301.6,28.1 302.3,27.4 303.1,26.7 303.8,26.1 304.6,25.4" marker-end="url(#arrPV)"/><circle cx="200" cy="120" r="4.5" fill="currentColor" stroke="none"/><g fill="currentColor" stroke="none"><text x="36" y="34" font-size="13" font-style="italic">t</text><text x="212" y="200" font-style="italic">ω<tspan font-size="11" dy="4">p</tspan></text><text x="214" y="182" font-size="12">pump â<tspan font-size="10" dy="4">p</tspan></text><text x="70" y="24" font-style="italic">ω<tspan font-size="11" dy="4">1</tspan></text><text x="315" y="24" font-style="italic">ω<tspan font-size="11" dy="4">2</tspan></text><text x="118" y="82" font-size="12" text-anchor="end">signal â<tspan font-size="10" dy="-6">†</tspan><tspan font-size="10" dy="10">1</tspan></text><text x="284" y="82" font-size="12">idler â<tspan font-size="10" dy="-6">†</tspan><tspan font-size="10" dy="10">2</tspan></text><text x="212" y="125" font-size="13">χ<tspan font-size="10" dy="-6">(2)</tspan></text><text x="200" y="226" text-anchor="middle" font-size="12">ω<tspan font-size="9" dy="3">p</tspan><tspan dy="-3"> = ω</tspan><tspan font-size="9" dy="3">1</tspan><tspan dy="-3"> + ω</tspan><tspan font-size="9" dy="3">2</tspan></text></g></svg></div>

**Photon number.** Start from $\ket{\alpha_1}\ket{\alpha_2}$. With $\langle\hat a_2\hat a_2^\dagger\rangle=|\alpha_2|^2+1$,

$$\langle \hat n_1 \rangle = \langle \alpha_1 \alpha_2 | \hat a_1^\dagger(t) \hat a_1(t) | \alpha_1 \alpha_2 \rangle = |\alpha_1 \cosh r+\alpha_2^* \sinh r|^2 + \sinh^2 r .$$

The first term is the classical (phase-sensitive) amplification. The second, $\sinh^2r$, comes from the vacuum of the other mode, so for a vacuum input $\langle\hat n_1\rangle=\sinh^2r$.

### Correlations and the Cauchy–Schwarz inequality

$$g_{12}^{(2)}(0)=\frac{\langle \hat a_1^\dagger \hat a_1 \hat a_2^\dagger \hat a_2 \rangle}{\langle \hat a_1^\dagger \hat a_1 \rangle \langle \hat a_2^\dagger \hat a_2 \rangle}, \qquad \text{for } P\ge0:\quad \big(g_{12}^{(2)}(0)\big)^2 \leq g_1^{(2)}(0)\, g_2^{(2)}(0) .$$

**Conserved difference.** $\frac{d}{dt}(\hat n_1-\hat n_2)=\frac1{i\hbar}[\hat n_1-\hat n_2,H_I]=0$, because $\hat K_\pm$ change $n_1$ and $n_2$ by the same amount. Hence $\hat n_2(t)=\hat n_1(t)+\hat n_2(0)-\hat n_1(0)$ and

$$\langle \hat n_1\hat n_2 \rangle = \langle \hat n_1(t)^2 \rangle + \langle \hat n_1(t)\big(\hat n_2(0)-\hat n_1(0)\big)\rangle .$$

For the vacuum input the last term vanishes, since $\hat n_2(0)-\hat n_1(0)$ annihilates $\ket{0,0}$. With $\langle\hat n_1\rangle=\langle\hat n_2\rangle$ and $\langle\hat n_1^2\rangle=\langle\hat a_1^{\dagger2}\hat a_1^2\rangle+\langle\hat n_1\rangle$,

$$g_{12}^{(2)}= g_1^{(2)}(0)+ \frac{1}{\langle \hat n_1 \rangle}
\quad\Rightarrow\quad
\big(g_{12}^{(2)}\big)^2=\Big(g_1^{(2)}(0)+\frac{1}{\langle \hat n_1 \rangle}\Big)^2 >\big(g_1^{(2)}(0)\big)^2=g_1^{(2)}g_2^{(2)} .$$

The inequality is violated for every gain. With $g_1^{(2)}=2$ (see below), $g_{12}^{(2)}=2+1/\sinh^2r$. Its divergence for $r\to0$ is not a problem: at low gain almost every detected photon is accompanied by its partner.

**Why there is no (positive) $P$.** The violation already shows that no non-negative $P$ exists. In fact no regular $P$ exists at all: the joint quadrature of $\alpha_1-\alpha_2^*$ is squeezed below the vacuum (see $W$ below). A $P$ function would need a Gaussian of negative variance there, $e^{+c|\alpha_1-\alpha_2^*|^2}$, which is not normalisable. $P$ exists only as a highly singular distribution.

**Wigner function.** From $\hat a_1(t)\pm\hat a_2^\dagger(t)=e^{\pm r}(\hat a_1\pm\hat a_2^\dagger)$, the combination $\alpha_1+\alpha_2^*$ is amplified and $\alpha_1-\alpha_2^*$ is squeezed. Starting from the vacuum $W_0=\frac{4}{\pi^2}e^{-2|\alpha_1|^2-2|\alpha_2|^2}=\frac{4}{\pi^2}e^{-|\gamma_1|^2-|\gamma_2|^2}$,

$$W(\alpha_1,\alpha_2)=\frac{4}{\pi^2}\exp\Big(-e^{-2r}|\gamma_1|^2-e^{2r}|\gamma_2|^2\Big), \qquad \gamma_1 = \alpha_1+\alpha_2^*, \quad \gamma_2 = \alpha_1 -\alpha_2^* .$$

$W$ is positive (a Gaussian), even though the state is nonclassical.

### The two-mode squeezed vacuum and its reduced state

For the vacuum input, $\ket{\psi}=e^{r(\hat K_+-\hat K_-)}\ket{0,0}$. The su(1,1) disentangling formula splits the exponential into normally ordered factors:

$$e^{r(\hat K_+-\hat K_-)}=e^{\tanh r\,\hat K_+}\,e^{-2\ln\cosh r\,\hat K_0}\,e^{-\tanh r\,\hat K_-}.$$

Acting on $\ket{0,0}$ from the right: $e^{-\tanh r\,\hat K_-}\ket{0,0}=\ket{0,0}$, then $e^{-\ln\cosh r\,(\hat n_1+\hat n_2+1)}\ket{0,0}=\frac{1}{\cosh r}\ket{0,0}$, and finally $(\hat a_1^\dagger\hat a_2^\dagger)^n\ket{0,0}=n!\ket{n,n}$:

$$\ket{\psi} = \frac{1}{\cosh r}\sum_{n=0}^\infty \tanh^n r\, \ket{n,n} .$$

The photon numbers in the two modes are perfectly correlated. Tracing out mode 2,

$$\hat\rho_1=\mathrm{Tr}_2\ket\psi\bra\psi = \frac{1}{\cosh^2r}\sum_n \tanh^{2n}r\; \ket{n} \bra{n} .$$

This is a thermal state, $p_n=\frac{\bar n^n}{(1+\bar n)^{n+1}}$ with $\frac{\bar n}{1+\bar n}=\tanh^2r$, i.e. $\bar n = \sinh^2 r$, and therefore $g_1^{(2)}=2$. Each mode alone looks thermal; the nonclassicality is entirely in the correlations.

## Jaynes–Cummings model: dressed states

Atom levels $\ket e,\ket g$ with transition frequency $\omega_0$, cavity mode $\omega$, detuning $\Delta = \omega_0 -\omega$. In each closed pair $\{\ket{e,n},\ket{g,n+1}\}$ (Lecture 11) the Hamiltonian is

$$H_n=\hbar\omega\Big(n+\frac12\Big)\mathbb 1+\frac\hbar2\begin{pmatrix}\Delta&\Omega_n\\ \Omega_n&-\Delta\end{pmatrix}, \qquad \Omega_n=2g\sqrt{n+1}=\Omega_0\sqrt{n+1}$$

($g$ real; $\Omega_0=2g$ is the vacuum Rabi frequency). Its eigenvalues are

$$E_{n,\pm} = \Big(n+\frac{1}{2}\Big) \hbar \omega \pm \frac{\hbar}{ 2} \sqrt{\Delta^2 + \Omega_n^2},$$

and with the mixing angle $\tan\theta_n=\Omega_n/\Delta$ ($0\le\theta_n\le\pi$) the **dressed states** are

$$\ket{+,n}=\cos\frac{\theta_n}{2}\, \ket{e,n} + \sin\frac{\theta_n}{2}\, \ket{g,n+1}, \qquad
\ket{-,n}=-\sin\frac{\theta_n}{2}\,\ket{e,n}+ \cos\frac{\theta_n}{2}\, \ket{g,n+1} .$$

(With a complex coupling $g=|g|e^{i\phi}$ the $\ket{g,n+1}$ components pick up the phase $e^{-i\phi}$. The lecture's factors of $\pm i$ correspond to $g=-i|g|$.)

- **Resonance**, $\Delta=0$: $\theta_n=\pi/2$, so $\ket{\pm,n}=\frac{1}{\sqrt2}(\ket{e,n}\pm\ket{g,n+1})$, a 50/50 mixture. The levels are split by $\hbar\Omega_n$ (**vacuum Rabi splitting** $\hbar\Omega_0$ for $n=0$).
- **Far detuned**, $|\Delta| \gg \Omega_n$ (take $\Delta>0$): $\theta_n\to0$, so $\ket{+,n} \approx \ket{e,n}$ and $\ket{-,n} \approx \ket{g,n+1}$. Expanding the square root, $\sqrt{\Delta^2+\Omega_n^2}\approx\Delta+\Omega_n^2/2\Delta$:
$$E_{n,\pm} \approx \Big(n+\frac{1}{2}\Big) \hbar \omega \pm \hbar \Big(\frac{\Delta}{2} +\frac{\Omega_n^2}{4 \Delta}\Big), \qquad \Omega_n^2 = \Omega_0^2 (n+1).$$

### Light shifts (AC Stark and Lamb shift)

In the dispersive regime each level keeps its character but is shifted. With $s_0=\Omega_0^2/4\Delta=g^2/\Delta$:

$$\delta E_{e,n}=+\hbar s_0(n+1), \qquad \delta E_{g,n}=-\hbar s_0\,n$$

($\ket{g,n}$ is the lower level of the pair $n-1$, with $\Omega_{n-1}^2=\Omega_0^2n$). The shift grows with the number of photons, i.e. with the light intensity: this is the **AC Stark (light) shift**.

- **Lamb shift.** For $n=0$, $\ket{e,0}$ is still shifted by $\hbar s_0$, although there are no photons. $\ket{e,0}$ is coupled to $\ket{g,1}$: the atom virtually emits a photon into the empty mode and reabsorbs it. The excited state is dressed by the vacuum fluctuations of the mode, not by a real field. In the RWA $\ket{g,0}$ is not coupled to anything and is not shifted. Summed over all free-space modes, the same mechanism gives the atomic Lamb shift; here it is the single-mode "cavity Lamb shift".
- **Optical trap.** In a spatially varying field (e.g. a Gaussian beam or a cavity mode) the ground-state shift $-\hbar g^2(\mathbf r)\,n/\Delta$ follows the intensity. For red detuning ($\omega<\omega_0$, $\Delta>0$) the ground state is pulled down where the light is strongest, and atoms are attracted to the intensity maximum: the **optical dipole trap**. For blue detuning they are repelled.
- **Shifted atomic transition.**
$$E(\ket{e,n})-E(\ket{g,n}) = \hbar\omega_0+\hbar s_0\,(2n+1):$$
the transition frequency is shifted in proportion to $2n+1$.
- **The atom shifts the field.** The photon energy depends on the atomic state,
$$E(\ket{g,n+1})-E(\ket{g,n}) = \hbar (\omega -s_0), \qquad E(\ket{e,n+1})-E(\ket{e,n}) = \hbar (\omega +s_0).$$
The atom acts as a state-dependent refractive index for the cavity, which is the basis of the cat factory below.

**Interactive plot.** Top: $E_{n,\pm}-\hbar\omega(n+\frac12)$ against $\Delta$ for the pair $n$, showing the avoided crossing of width $\Omega_n$, the bare levels $\pm\Delta/2$, and the AC-Stark approximation. The approximation is accurate for $|\Delta|\gtrsim2\Omega_n$ and diverges at resonance. Bottom: the shift of the two branches along an atom's path through a mode with coupling $g(x)=g\,e^{-x^2/w^2}$. This is the potential of a dipole trap, and its integral is the cat-factory phase.

```dataviewjs
// ===== CONFIG =====
const CFG = { n: 0, nMax: 30, D: 6, Dmax: 15 };   // energies and detuning in units of g
// ==================
// ---- loader (leave as is) ----
const LIB = "FUW/lib/";
const load = (src) => new Promise((ok, no) => { const s = document.createElement("script"); s.src = src; s.onload = ok; s.onerror = () => no(new Error("could not load " + src)); document.head.append(s); });
const libPath = async (n) => { const here = dv.current().file.folder, up = here.includes("/") ? here.slice(0, here.lastIndexOf("/")) + "/" : ""; for (const p of [LIB + n, "lib/" + n, here + "/lib/" + n, up + "lib/" + n, ...app.vault.getFiles().filter((x) => x.path.endsWith("lib/" + n)).map((x) => x.path)]) if (await app.vault.adapter.exists(p)) return p; throw new Error("lib/" + n + " not found in this vault (is the lib folder synced to this computer?)"); };
if (!window.JXG) await (window.__jxg ??= libPath("jsxgraphcore.js").then((p) => load(app.vault.adapter.getResourcePath(p))).catch(() => load("https://cdn.jsdelivr.net/npm/jsxgraph@1.10.1/distrib/jsxgraphcore.js")).catch((e) => { window.__jxg = null; throw e; }));
if (!window.RL) await (window.__rl ??= libPath("rlti.js").then((p) => load(app.vault.adapter.getResourcePath(p))).catch((e) => { window.__rl = null; throw e; }));
const K = await RL.init(dv), { f, el, C } = K;
// ---- controls ----
const sN = K.slider("n", 0, CFG.nMax, 1, CFG.n, (v) => (+v).toFixed(0)), sD = K.slider("Δ / g", -CFG.Dmax, CFG.Dmax, 0.05, CFG.D);
const cbB = K.check("bare levels ±Δ/2"), cbA = K.check("AC-Stark (dispersive) approximation");
// ---- layout ----
const box = "background:#fff;border:1px solid #e5e7eb;border-radius:10px", H = Math.round(K.W * 0.48);
const d1 = el("div", `width:${K.W}px;height:${H}px;${box};touch-action:none;margin-top:6px`);
const d2 = el("div", `width:${K.W}px;height:${Math.round(H * 0.8)}px;${box};touch-action:none;margin-top:10px`);
const panel = el("div", "font-family:var(--font-monospace,monospace);font-size:0.8em;line-height:1.55;white-space:pre-wrap;color:var(--text-normal);margin-top:6px");
K.root.append(d1, d2, panel);
const ax = (n, pos, off) => ({ name: n, withLabel: true, strokeColor: "#9ca3af", label: { position: pos, offset: off, fontSize: 14, strokeColor: C.ink }, ticks: { minorTicks: 0, strokeColor: "#9ca3af", label: { fontSize: 10, strokeColor: C.muted } } });
const mk = (div, bb, xn, yn) => JXG.JSXGraph.initBoard(div, { boundingbox: bb, keepAspectRatio: false, axis: true, showCopyright: false, showNavigation: false, pan: { enabled: false }, zoom: { enabled: false }, defaultAxes: { x: ax(xn, "rt", [-14, 14]), y: ax(yn, "rt", [8, -6]) } });
const opt = (c, w, dash = 0, vis) => ({ fixed: true, highlight: false, strokeColor: c, strokeWidth: w, dash, ...(vis ? { visible: vis } : {}) });
// ---- 1) dressed-state energies of manifold n: (E − ħω(n+½))/ħg  vs  Δ/g ----
const b1 = mk(d1, [-CFG.Dmax, 10, CFG.Dmax, -10], "Δ / g", "(E − ħω(n+½)) / ħg");
const On2 = () => 4 * (+sN.value + 1);                                  // Ω_n² / g² = 4(n+1)
const Ep = (D) => 0.5 * Math.sqrt(D * D + On2()), disp = (D) => D / 2 + On2() / (4 * D);
b1.create("functiongraph", [Ep, -CFG.Dmax, CFG.Dmax], opt(C.obs, 2.6));
b1.create("functiongraph", [(D) => -Ep(D), -CFG.Dmax, CFG.Dmax], opt(C.sel, 2.6));
b1.create("functiongraph", [(D) => D / 2, -CFG.Dmax, CFG.Dmax], opt(C.muted, 1.2, 2, () => cbB.checked));
b1.create("functiongraph", [(D) => -D / 2, -CFG.Dmax, CFG.Dmax], opt(C.muted, 1.2, 2, () => cbB.checked));
const dOk = (D) => Math.abs(D) > 0.6 * Math.sqrt(On2());
b1.create("functiongraph", [(D) => (dOk(D) ? disp(D) : NaN), -CFG.Dmax, CFG.Dmax], opt("#16a34a", 1.6, 3, () => cbA.checked));
b1.create("functiongraph", [(D) => (dOk(D) ? -disp(D) : NaN), -CFG.Dmax, CFG.Dmax], opt("#16a34a", 1.6, 3, () => cbA.checked));
b1.create("line", [[() => +sD.value, 0], [() => +sD.value, 1]], opt(C.ink, 1, 1));
b1.create("point", [() => +sD.value, () => Ep(+sD.value)], { fixed: true, highlight: false, withLabel: false, size: 3.5, strokeColor: C.obs, fillColor: C.obs });
b1.create("point", [() => +sD.value, () => -Ep(+sD.value)], { fixed: true, highlight: false, withLabel: false, size: 3.5, strokeColor: C.sel, fillColor: C.sel });
let top1 = 9.5;
b1.create("text", [CFG.Dmax * 0.97, () => top1, () => `<span style='color:${C.obs}'>━</span> |+,n⟩ &nbsp;<span style='color:${C.sel}'>━</span> |−,n⟩` + (cbB.checked ? " &nbsp;┄ bare" : "") + (cbA.checked ? " &nbsp;<span style='color:#16a34a'>┅</span> ±(Δ/2 + Ω²ₙ/4Δ)" : "")], { fixed: true, highlight: false, fontSize: 12, strokeColor: C.ink, anchorX: "right", anchorY: "top" });
// ---- 2) energy of the two branches along the atom's path through the mode, g(x) = g e^{−x²/w²} ----
const b2 = mk(d2, [-2.2, 1, 2.2, -1], "x / w", "shift / g");
const g2 = (x) => Math.exp(-2 * x * x), N1 = () => +sN.value + 1;
const sg = () => Math.sign(+sD.value) || 1, aD = () => Math.abs(+sD.value);
const shG = (x) => -sg() * 0.5 * (Math.sqrt(aD() ** 2 + 4 * g2(x) * N1()) - aD());   // branch adiabatically connected to |g,n+1⟩
const shE = (x) => -shG(x);                                                          // branch connected to |e,n⟩
b2.create("functiongraph", [shE, -2.2, 2.2], opt(C.obs, 2.4));
b2.create("functiongraph", [shG, -2.2, 2.2], opt(C.sel, 2.4));
b2.create("functiongraph", [(x) => -g2(x) * N1() / (+sD.value || 1e-9), -2.2, 2.2], opt("#16a34a", 1.6, 3, () => cbA.checked));
let prof = 0.1;
b2.create("functiongraph", [(x) => prof * Math.exp(-2 * x * x), -2.2, 2.2], opt(C.muted, 1, 2));
let top2 = 0.95;
b2.create("text", [2.1, () => top2, () => `<span style='color:${C.obs}'>━</span> from |e,n⟩ &nbsp;<span style='color:${C.sel}'>━</span> from |g,n+1⟩` + (cbA.checked ? " &nbsp;<span style='color:#16a34a'>┅</span> −g(x)²(n+1)/Δ" : "") + " &nbsp;┄ g(x)²"], { fixed: true, highlight: false, fontSize: 12, strokeColor: C.ink, anchorX: "right", anchorY: "top" });
function update() {
  const n = +sN.value, D = +sD.value, R = Math.sqrt(D * D + On2());
  let m = 2; for (const D2 of [-CFG.Dmax, CFG.Dmax]) m = Math.max(m, Ep(D2)); top1 = m * 1.1; b1.setBoundingBox([-CFG.Dmax, m * 1.12, CFG.Dmax, -m * 1.12], false); b1.update();
  let s = 0.05; for (let i = 0; i <= 60; i++) { const x = -2.2 + (4.4 * i) / 60; s = Math.max(s, Math.abs(shG(x)), Math.abs(shE(x))); } prof = s; top2 = s * 1.32; b2.setBoundingBox([-2.2, s * 1.35, 2.2, -s * 1.35], false); b2.update();
  const exact = 0.5 * R - 0.5 * Math.abs(D), stark = Math.abs(D) > 1e-9 ? On2() / (4 * Math.abs(D)) : NaN, pe = 0.5 * (1 + D / R);
  panel.textContent =
`manifold n = ${n}: {|e,${n}⟩, |g,${n + 1}⟩}, Ω_n = 2g√(n+1) = ${f(Math.sqrt(On2()))} g;   at Δ = 0 the splitting is ħΩ_n (vacuum Rabi splitting for n = 0)
at Δ = ${f(D)} g:  E± − ħω(n+½) = ±${f(0.5 * R)} ħg;   shift of each level from ±Δ/2: ${f(exact)} ħg   AC-Stark estimate Ω²ₙ/4|Δ| = ${isNaN(stark) ? "—" : f(stark)} ħg   ${Math.abs(D) > Math.sqrt(On2()) * 2 ? "(dispersive regime: agree)" : "(near resonance: estimate fails)"}
|⟨e,n|+,n⟩|² = cos²(θ_n/2) = ${f(pe)}    lower panel: ${D > 0 ? "Δ > 0 (red detuned): the ground-like level is pushed down where the field is strong → trap" : D < 0 ? "Δ < 0 (blue detuned): the ground-like level is pushed up → repelled" : "resonance"}`;
}
for (const s of [sN, sD]) s.addEventListener("input", update);
for (const c of [cbB, cbA]) c.onchange = update;
update();
```

### Cavity QED with Rydberg atoms (Haroche)

Circular Rydberg states of Rb fly one at a time through a superconducting microwave cavity:

- $\ket e$ = principal quantum number 51 (51C) and $\ket g$ = 50C, with a 51.1 GHz transition resonant (or nearly so) with the cavity;
- 49C ($\ket i$) is used as a spectator level.

Circular states have long lifetimes (~30 ms) and huge dipoles (strong $g$). The cavity photon lifetime reached 0.13 s. The atomic state is prepared in B, rotated by classical microwave $\pi/2$ pulses in the Ramsey zones $R_1,R_2$, and measured by state-selective field ionisation in D. The interaction time is set by the atomic velocity $v$.

<div style="text-align:center"><svg width="600" height="210" viewBox="0 0 600 210" xmlns="http://www.w3.org/2000/svg" fill="none" stroke="currentColor" stroke-width="1.5" font-family="Times New Roman, serif" font-size="15"><defs><marker id="arrHR" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="7" markerHeight="7" orient="auto"><path d="M0,0 L10,5 L0,10 z" fill="currentColor" stroke="none"/></marker></defs><line x1="20" y1="100" x2="430" y2="100" stroke-dasharray="5 4" marker-end="url(#arrHR)"/><rect x="20" y="82" width="34" height="36" fill="currentColor" fill-opacity="0.1"/><rect x="72" y="78" width="40" height="44" fill="currentColor" fill-opacity="0.06"/><rect x="132" y="72" width="26" height="56" fill="currentColor" fill-opacity="0.06"/><path d="M216,55 Q196,100 216,145" stroke-width="4"/><path d="M284,55 Q304,100 284,145" stroke-width="4"/><path d="M216,100 Q235,70 250,100 T284,100" stroke-opacity="0.45"/><rect x="332" y="72" width="26" height="56" fill="currentColor" fill-opacity="0.06"/><rect x="384" y="76" width="44" height="48" fill="currentColor" fill-opacity="0.12"/><circle cx="180" cy="100" r="5" fill="currentColor" stroke="none"/><line x1="172" y1="86" x2="196" y2="86" stroke-width="1.2" marker-end="url(#arrHR)"/><g fill="currentColor" stroke="none" font-size="13" text-anchor="middle"><text x="37" y="140">O</text><text x="37" y="154" font-size="11">oven</text><text x="92" y="140">B</text><text x="92" y="154" font-size="11">circular-state</text><text x="92" y="166" font-size="11">preparation</text><text x="145" y="145">R<tspan font-size="9" dy="3">1</tspan></text><text x="250" y="165">C</text><text x="250" y="179" font-size="11">superconducting cavity</text><text x="250" y="192" font-size="11">(~51 GHz)</text><text x="345" y="145">R<tspan font-size="9" dy="3">2</tspan></text><text x="406" y="140">D</text><text x="406" y="154" font-size="11">field-ionisation</text><text x="406" y="166" font-size="11">detector (e or g)</text><text x="185" y="80" font-size="11">v</text><text x="145" y="60" font-size="11">π/2</text><text x="345" y="60" font-size="11">π/2</text></g><line x1="470" y1="40" x2="530" y2="40" stroke-width="2"/><line x1="470" y1="110" x2="530" y2="110" stroke-width="2"/><line x1="470" y1="170" x2="530" y2="170" stroke-width="2"/><line x1="500" y1="44" x2="500" y2="106" stroke-width="1" marker-end="url(#arrHR)"/><line x1="500" y1="114" x2="500" y2="166" stroke-width="1" stroke-dasharray="3 3"/><g fill="currentColor" stroke="none" font-size="13"><text x="536" y="44" font-style="italic">e</text><text x="550" y="44" font-size="11">51C</text><text x="536" y="114" font-style="italic">g</text><text x="550" y="114" font-size="11">50C</text><text x="536" y="174" font-style="italic">i</text><text x="550" y="174" font-size="11">49C</text><text x="506" y="80" font-size="11">51.1 GHz</text><text x="506" y="145" font-size="11">54.3 GHz</text><text x="500" y="200" font-size="11" text-anchor="middle">Rb circular Rydberg levels</text></g></svg></div>

**Entangling two atoms through the cavity.** Atom 1 in $\ket e$, atom 2 in $\ket g$, cavity in $\ket0$. While atom 1 passes (resonant, $\Delta=0$),

$$\ket{e_1,0} \rightarrow \cos(gt_1) \ket{e_1, 0}-i \sin(gt_1)\ket{g_1, 1}.$$

With $gt_1 = \pi /4$ (a "$\pi/2$ pulse"),

$$\frac{1}{\sqrt{2}}\big(\ket{e_1g_2, 0} - i \ket{g_1 g_2,1}\big).$$

Atom 2 then passes. It only interacts with the photon:

$$\ket{g_2, 1} \rightarrow \cos(g t_2) \ket{g_2, 1}-i \sin(g t_2) \ket{e_2, 0}, \qquad \ket{g_2, 0} \rightarrow \ket{g_2, 0}.$$

With $g t_2 = \pi/2$ (a "$\pi$ pulse"), $\ket{g_2,1}\to-i\ket{e_2,0}$ and

$$\frac{1}{\sqrt{2}}\big(\ket{e_1 g_2, 0} - \ket{g_1 e_2, 0}\big) = \frac{1}{\sqrt{2}}\big(\ket{e_1 g_2} - \ket{g_1 e_2}\big) \ket{0},$$

a Bell state of the two atoms. The cavity photon has acted as a quantum bus and is left in the vacuum.

### Cat factory

In the dispersive regime each photon shifts the energy of the atom by $\pm\hbar s_0$. Equivalently, the field frequency becomes $\omega\pm s_0$. During the interaction time $t_d$ the field accumulates a phase per photon

$$\phi=s_0 t_d = \frac{\Omega_0^2}{4 \Delta}\,t_d ,$$

of opposite sign for $\ket e$ and $\ket g$. Using $\delta E_{g,n}=-\hbar s_0n$,

$$\ket{g, \alpha} = e^{-|\alpha|^2/2} \sum_n \frac{\alpha^n}{\sqrt{n!}}\ket{g,n} \rightarrow e^{-|\alpha|^2/2}\sum_n \frac{\alpha^n e^{in \phi}}{\sqrt{n!}}\ket{g,n}=\ket{g,\alpha e^{i\phi}},$$

and likewise $\ket{e,\alpha}\to e^{-i\phi}\ket{e,\alpha e^{-i\phi}}$. This requires $|\Delta| \gg \Omega_n$ for all relevant $n$, so the phase per photon is small. An atom prepared by $R_1$ in $\frac{1}{\sqrt{2}}(\ket{g}+\ket{e})$ therefore gives

$$\frac{1}{\sqrt{2}}\big(\ket g+\ket e\big)\ket{\alpha}\;\to\;\frac{1}{\sqrt{2}}\Big(\ket g\ket{\alpha e^{i\phi}}+e^{-i\phi}\ket e\ket{\alpha e^{-i \phi}}\Big),$$

an atom–field entangled state. A second $\pi/2$ pulse in $R_2$ and detection of the atom in $\ket e$ or $\ket g$ project the field onto $\ket{\alpha e^{i\phi}}\pm e^{-i\phi}\ket{\alpha e^{-i\phi}}$ (up to normalisation): a Schrödinger cat state.

**Adiabatic following.** The coupling varies along the path, $\Omega_0(x)$. If the atom is slow enough, the state $\ket{g,n+1}$ adiabatically follows the dressed state $\ket{-,n}$. Its energy shift is the lower curve in the plot above, and the accumulated phase is

$$\phi_n =\int \frac{dx}{2v}\,\Big(\sqrt{\Delta^2 + (n+1)\, \Omega_0^2(x)} - \Delta\Big),$$

which reduces to $(n+1)\,s_0t_d$ in the dispersive limit. Adiabaticity requires the mixing angle to change slowly compared with the level splitting: $|\dot\theta_n|\ll\sqrt{\Delta^2+\Omega_n^2}$.

**Losses.** The Jaynes–Cummings model has none. Cavity decay ($\kappa$) and atomic spontaneous emission ($\gamma$) require a master equation. The coherent dynamics above needs the strong-coupling regime $g\gg\kappa,\gamma$, which the long Rydberg and photon lifetimes provide.

> [!note] Next lecture
> Multilevel atoms (with Michał).

**References.**
- E. Hagley et al., *Generation of Einstein–Podolsky–Rosen pairs of atoms*, PRL **79**, 1 (1997): the two-atom entanglement above.
- M. Brune et al., *Observing the progressive decoherence of the "meter" in a quantum measurement*, PRL **77**, 4887 (1996): the dispersive cat.
- J. M. Raimond, M. Brune, S. Haroche, *Manipulating quantum entanglement with atoms and photons in a cavity*, Rev. Mod. Phys. **73**, 565 (2001).
- S. Deléglise et al., *Reconstruction of non-classical cavity field states with snapshots of their decoherence*, Nature **455**, 510 (2008).
- S. Haroche, J. M. Raimond, *Exploring the Quantum: Atoms, Cavities and Photons* (Oxford, 2006).

---
[[QO - Lecture 11|← Previous: Lecture 11]] · [[QO - Lecture 13|Next: Lecture 13 →]]
