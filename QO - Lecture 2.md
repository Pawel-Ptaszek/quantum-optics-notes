← [[QO - Lecture 1|Lecture 1]] · [[QO - chapter I|Full chapter]]

# Lecture 2

## 3. Single photons and the phase of light

### 3.1 One-photon states

A single photon in mode $(\mathbf{k},\sigma)$:

$$\hat{a}_{\mathbf{k},\sigma}^\dagger \ket{0}$$

where $\mathbf{k}$ is the wavevector and $\sigma$ the polarization; its energy is $E=\hbar \omega = \hbar c k$.

In practice we have a **wavepacket** containing one photon:

$$\ket{1_\psi} = \sum_\sigma \int d^3k\; \psi_\sigma(\mathbf{k})\, \hat{a}^\dagger_{\mathbf{k},\sigma} \ket{0}$$

Normalization $\langle 1_\psi|1_\psi\rangle=1$:

$$\sum_\sigma \int d^3k\, |\psi_\sigma(\mathbf{k})|^2=1$$

> [!note] [Photon wave function (I. Białynicki-Birula)](https://arxiv.org/pdf/quant-ph/0508202)

> There is no good position operator for the photon, but we can still define a photon wave function $\psi(\mathbf{r})$ in position space built from the Riemann–Silberstein vector $\mathbf{F} = \frac{1}{\sqrt2}\left(\sqrt{\epsilon_0}\,\mathbf{E} + \frac{i}{\sqrt{\mu_0}}\mathbf{B}\right)$. It's modulus squared $|F|^2$ is the energy density (as opposed to a probability density function). Another source ["On the wave function of the photon"](https://www.researchgate.net/publication/251447766_On_the_Wave_Function_of_the_Photon) 


**Change of mode basis.** For any unitary matrix $\mathcal{U}$ we can define new modes

$$\hat b_{j,\sigma}=\sum_{\mathbf{k}} \mathcal{U}_{j,\mathbf{k}}\, \hat a_{\mathbf{k},\sigma}$$

They are again bosonic modes, because $[\hat b_{j},\hat b^\dagger_{j'}] = \sum_{\mathbf{k}}\mathcal{U}_{j\mathbf{k}}\mathcal{U}^*_{j'\mathbf{k}} = (\mathcal{U}\mathcal{U}^\dagger)_{jj'} = \delta_{jj'}$. A wavepacket photon is just a single photon in one of these new modes.

### 3.2 Plane wave and the phase

Classical plane wave:

$$\mathbf{E}= \mathbf{e}\, E_0 \cos(\mathbf{k}\cdot \mathbf{r}-\omega t + \phi)$$

This has the same form as $\langle \hat E \rangle$ for a coherent state. Measuring the intensity gives $\langle \hat n \rangle = |\alpha|^2$ — **can we also measure the phase of the field?**

### 3.3 Constructing a phase operator — Dirac's attempt

Try a polar decomposition of $\hat a$:

$$\hat{a}\overset{?}{=} e^{i \hat{\theta}} \sqrt{\hat{n}}, \qquad \hat{a}^\dagger = \sqrt{\hat{n}}\, e^{- i \hat{\theta}}$$

Inserting into the commutator:

$$1= [\hat a,\hat a^\dagger]=e^{i\hat\theta}\, \hat n\, e^{-i \hat\theta }-\hat n \quad\Rightarrow\quad e^{i \hat\theta} = e^{i \hat\theta}\hat n - \hat n\, e^{i \hat\theta} = -[\hat n, e^{i\hat\theta}]$$

which is satisfied if

$$[\hat{n}, \hat{\theta}]=i$$

This would give a number–phase uncertainty relation

$$\Delta n\, \Delta \theta \geq \frac{1}{2}$$

**But such a Hermitian $\hat\theta$ cannot exist.** Take matrix elements in the:

$$\bra{n}[\hat n,\hat \theta] \ket{n'}= \bra{n}(\hat n \hat \theta - \hat \theta \hat n) \ket{n'}=(n-n')\bra{n}\hat \theta \ket{n'}$$

The left-hand side is $\bra{n} i \ket{n'} = i\, \delta_{n,n'}$. For $n=n'$ we get $i = 0$ which is a contradiction. (The deeper reason: $\hat n$ is bounded from below, so $e^{i\hat\theta}$ cannot be unitary.) [**Wintner-Wielandt Theorem**](https://arxiv.org/pdf/1805.11131) - The identity operator cannot be expressed as the commutator of two bounded operators, and $\hat{n}$ is bounded from below.

### 3.4 [Susskind–Glogower phase operators](https://www.uobabylon.edu.iq/eprints/publication_12_7688_39.pdf)

Define the exponential-phase operator directly, without $\hat\theta$:

$$\widehat{e^{i\theta}} =(\hat{a} \hat{a}^\dagger)^{-1/2}\hat a =(\hat n+1)^{-1/2}\,\hat a = \sum_{n=0}^\infty \ket{n}\bra{n+1}, \qquad \widehat{e^{-i\theta}} = \big(\widehat{e^{i\theta}}\big)^\dagger = \hat a^\dagger (\hat n+1)^{-1/2}$$
The eigenstates $\ket{e^{i\theta}}$ are:

$$\ket{e^{i \theta}}= \sum_{n=1}^\infty e^{in\theta} \ket{n}$$
The eigenstates are not orthogonal, but they provide resolution of identity
It is only **one-sided unitary**:

$$\widehat{e^{i\theta}}\,\widehat{e^{-i\theta}} = \hat a\, (\hat n+1)^{-1}\hat a^\dagger = \hat 1, \qquad \widehat{e^{-i\theta}}\,\widehat{e^{i\theta}} = \hat 1 - \ket{0}\bra{0}$$
$$[\widehat{e^{i\theta}},\widehat{e^{-i\theta}}] = \ket{0}\bra{0}$$
(it's not "normal" $\rightarrow$ not unitary)

Hermitian combinations $\hat C = \frac12\big(\widehat{e^{i\theta}}+\widehat{e^{-i\theta}}\big)$, $\hat S = \frac{1}{2i}\big(\widehat{e^{i\theta}}-\widehat{e^{-i\theta}}\big)$ can be measured 

### 3.5 [Pegg-Barnett phase operator](https://iopscience.iop.org/article/10.1209/0295-5075/6/6/002/pdf)

---

## 4. Linear optics

### 4.1 What can we do with photons?

| Operation                         | Operator                                                |
| --------------------------------- | ------------------------------------------------------- |
| Production                        | $\hat a^\dagger$                                        |
| Detection                         | $\hat a$                                                |
| ==Linear optics==                 | $\hat a' = U\hat a$ (mixes only annihilation operators) |
| Active (amplification, squeezing) | mixes $\hat a$ and $\hat a^\dagger$                     |
| Nonlinear                         | higher powers of $\hat a, \hat a^\dagger$               |

### 4.2 Beam splitter

![[Pasted image 20261013105128.png|center|300]]

**Classical fields**: incoming $\mathcal{E}_1, \mathcal{E}_2$, outgoing $\mathcal{E}_3, \mathcal{E}_4$:

$$\begin{pmatrix} \mathcal{E}_3 \\ \mathcal{E}_4 \end{pmatrix} = B \begin{pmatrix} \mathcal{E}_1 \\ \mathcal{E}_2 \end{pmatrix}, \qquad B = \begin{pmatrix} r_1 & t_2 \\ t_1 & r_2 \end{pmatrix}$$

Energy conservation

$$|\mathcal{E}_1|^2 + |\mathcal{E}_2|^2 =|\mathcal{E}_3|^2 + |\mathcal{E}_4|^2$$

for all inputs means $B$ is **unitary**, $B^\dagger B = \hat 1$:

$$|r_1|^2+|t_1|^2 = |r_2|^2+|t_2|^2 = 1, \qquad r_1^* t_2 + t_1^* r_2 = 0$$

**Quantum version.** Two input modes $\hat a_1, \hat a_2$ and two output modes $\hat a_3, \hat a_4$:

$$\begin{pmatrix} \hat a_3 \\ \hat a_4 \end{pmatrix} = B \begin{pmatrix} \hat a_1 \\ \hat a_2 \end{pmatrix}$$

Unitarity of $B$ guarantees that the output operators obey $[\hat a_i,\hat a_j^\dagger]=\delta_{ij}$.

**Example: balanced (50:50) beam splitter with one photon.**

$$B = \frac{1}{\sqrt{2}}\begin{pmatrix} 1 & 1 \\ -1 & 1 \end{pmatrix}$$

Input: $\ket{\psi_\text{in}} = \hat a_1^\dagger \ket{0}$. Invert the relation, $\hat a_\text{in} = B^\dagger \hat a_\text{out}$:

$$\hat a_1 = \frac{1}{\sqrt2}(\hat a_3 - \hat a_4) \quad\Rightarrow\quad \hat a_1^\dagger = \frac{1}{\sqrt2}(\hat a_3^\dagger - \hat a_4^\dagger)$$

$$\ket{\psi_\text{out}} = \frac{1}{\sqrt{2}}\big(\hat a_3^\dagger -\hat a_4^\dagger\big) \ket{0} = \frac{1}{\sqrt2}\big(\ket{1_3 0_4} - \ket{0_3 1_4}\big)$$

The photon is in a superposition of both outputs. It is detected in either port with probability $\frac12$ (it does not split).

### 4.3 Phase shifter

A phase delay $\phi$ in one arm:

<div style="text-align:center"><svg width="380" height="120" viewBox="0 0 380 120" xmlns="http://www.w3.org/2000/svg" fill="none" stroke="currentColor" stroke-width="1.6" font-family="Times New Roman, serif" font-size="18"><defs><marker id="arrPS" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="7" markerHeight="7" orient="auto"><path d="M0,0 L10,5 L0,10 z" fill="currentColor" stroke="none"/></marker></defs><line x1="60" y1="40" x2="160" y2="40" marker-end="url(#arrPS)"/><rect x="160" y="22" width="60" height="36" rx="4"/><line x1="220" y1="40" x2="320" y2="40" marker-end="url(#arrPS)"/><line x1="60" y1="90" x2="320" y2="90" marker-end="url(#arrPS)"/><g fill="currentColor" stroke="none" font-style="italic"><text x="190" y="46" text-anchor="middle">φ</text><text x="50" y="46" text-anchor="end">â₁</text><text x="50" y="96" text-anchor="end">â₂</text><text x="330" y="46">â′₁</text><text x="330" y="96">â′₂</text></g></svg></div>

$$\begin{pmatrix} \hat a'_1 \\ \hat a'_2 \end{pmatrix} = \begin{pmatrix} e^{i \phi} & 0\\ 0 & 1 \end{pmatrix}\begin{pmatrix} \hat a_1 \\ \hat a_2 \end{pmatrix}$$

### 4.4 General linear optical element

Any passive linear network with $N$ input and $N$ output modes:

<div style="text-align:center"><svg width="400" height="190" viewBox="0 0 400 190" xmlns="http://www.w3.org/2000/svg" fill="none" stroke="currentColor" stroke-width="1.6" font-family="Times New Roman, serif" font-size="18"><defs><marker id="arrU" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="7" markerHeight="7" orient="auto"><path d="M0,0 L10,5 L0,10 z" fill="currentColor" stroke="none"/></marker></defs><rect x="150" y="15" width="100" height="160" rx="6"/><line x1="60" y1="40" x2="150" y2="40" marker-end="url(#arrU)"/><line x1="60" y1="75" x2="150" y2="75" marker-end="url(#arrU)"/><line x1="60" y1="150" x2="150" y2="150" marker-end="url(#arrU)"/><line x1="250" y1="40" x2="340" y2="40" marker-end="url(#arrU)"/><line x1="250" y1="75" x2="340" y2="75" marker-end="url(#arrU)"/><line x1="250" y1="150" x2="340" y2="150" marker-end="url(#arrU)"/><g fill="currentColor" stroke="none" font-style="italic"><text x="200" y="102" text-anchor="middle" font-size="26">U</text><text x="50" y="46" text-anchor="end">â₁</text><text x="50" y="81" text-anchor="end">â₂</text><text x="50" y="156" text-anchor="end">â<tspan font-size="13" dy="4">N</tspan></text><text x="350" y="46">â′₁</text><text x="350" y="81">â′₂</text><text x="350" y="156">â′<tspan font-size="13" dy="4">N</tspan></text><text x="105" y="118" text-anchor="middle" font-style="normal">⋮</text><text x="295" y="118" text-anchor="middle" font-style="normal">⋮</text></g></svg></div>

With the vector of modes $\hat{\mathbf{a}} = (\hat a_1,\dots,\hat a_N)^T$:

$$\hat{\mathbf{a}}'=U\, \hat{\mathbf{a}}, \qquad \hat a'_i = \sum_{j=1}^N U_{ij}\,\hat a_j, \qquad U^\dagger U = \hat 1$$

Unitarity of $U$ ⇔ energy (photon number) conservation ⇔ $[\hat a'_i,\hat a'^\dagger_j]=\delta_{ij}$. 

Any $N\times N$ unitary can be built from beam splitters and phase shifters [Reck, Zeillinger - "Experimental Realization of Any Discrete Unitary Operator". 1994](https://journals.aps.org/prl/pdf/10.1103/PhysRevLett.73.58).


### 4.5 Heisenberg picture — the beam-splitter Hamiltonian

In the Heisenberg picture the state is fixed and the mode operators transform:

$$\hat{\mathbf{a}}'=B\, \hat{\mathbf{a}} = \hat U_B^\dagger\, \hat{\mathbf{a}}\, \hat U_B$$

**How do we construct $\hat U_B$?** Write the unitary matrix as an exponential of a Hermitian matrix $\mathcal{H}$, and lift it to an operator quadratic in the modes:

$$B=e^{i \mathcal{H}}, \qquad \hat{\mathcal{H}}_B = \hat{\mathbf{a}}^\dagger \mathcal{H}\, \hat{\mathbf{a}} = \sum_{jk}\hat a_j^\dagger \mathcal{H}_{jk}\hat a_k, \qquad \hat U_B = e^{i\hat{\mathcal{H}}_B}$$

*Check:* $[\hat{\mathcal{H}}_B, \hat a_j] = -\sum_k \mathcal{H}_{jk}\hat a_k$, so $\hat U_B^\dagger \hat{\mathbf{a}}\, \hat U_B = e^{i\mathcal{H}}\hat{\mathbf{a}} = B\hat{\mathbf{a}}$.

For a real beam splitter $B = \begin{pmatrix} \cos\vartheta & \sin\vartheta \\ -\sin\vartheta & \cos\vartheta \end{pmatrix}$ (balanced: $\vartheta = \pi/4$):

$$\mathcal{H} = \vartheta\, \sigma_y = \vartheta\begin{pmatrix} 0 & -i \\ i & 0 \end{pmatrix}, \qquad e^{i\vartheta\sigma_y} = \cos\vartheta\, \hat 1 + i \sin\vartheta\,\sigma_y = B$$

$$\hat{\mathcal{H}}_B = i \vartheta \left(\hat a_2^\dagger \hat a_1 - \hat a_1^\dagger \hat a_2\right)$$

### 4.6 Schrödinger picture

Equivalently, the operators are fixed and the state transforms:

$$\ket{\psi} \rightarrow \ket{\psi'}=\hat U_B \ket{\psi}$$

Since $\hat U_B\ket{0}=\ket{0}$, it is enough to know how creation operators transform: $\hat U_B\, \hat a_k^\dagger\, \hat U_B^\dagger = \sum_j B_{jk}\, \hat a_j^\dagger$ — an input photon in mode $k$ goes to the outputs with amplitudes given by **column $k$ of $B$**.

### 4.7 Mach–Zehnder interferometer

![[Pasted image 20261013112403.png|center|420]]

<div style="text-align:center"><svg width="520" height="170" viewBox="0 0 520 170" xmlns="http://www.w3.org/2000/svg" fill="none" stroke="currentColor" stroke-width="1.6" font-family="Times New Roman, serif" font-size="18"><defs><marker id="arrMZ" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="7" markerHeight="7" orient="auto"><path d="M0,0 L10,5 L0,10 z" fill="currentColor" stroke="none"/></marker></defs><rect x="110" y="25" width="60" height="110" rx="5"/><rect x="350" y="25" width="60" height="110" rx="5"/><rect x="235" y="32" width="50" height="36" rx="4"/><line x1="50" y1="50" x2="110" y2="50" marker-end="url(#arrMZ)"/><line x1="50" y1="110" x2="110" y2="110" marker-end="url(#arrMZ)"/><line x1="170" y1="50" x2="235" y2="50" marker-end="url(#arrMZ)"/><line x1="285" y1="50" x2="350" y2="50" marker-end="url(#arrMZ)"/><line x1="170" y1="110" x2="350" y2="110" marker-end="url(#arrMZ)"/><line x1="410" y1="50" x2="465" y2="50" marker-end="url(#arrMZ)"/><line x1="410" y1="110" x2="465" y2="110" marker-end="url(#arrMZ)"/><path d="M466,38 h10 a12,12 0 0 1 0,24 h-10 z"/><path d="M466,98 h10 a12,12 0 0 1 0,24 h-10 z"/><g fill="currentColor" stroke="none"><g font-style="italic"><text x="140" y="87" text-anchor="middle" font-size="24">B</text><text x="380" y="87" text-anchor="middle" font-size="24">B</text><text x="260" y="56" text-anchor="middle">φ</text><text x="42" y="56" text-anchor="end">â₁</text><text x="42" y="116" text-anchor="end">â₂</text><text x="437" y="42" text-anchor="middle">â′₁</text><text x="437" y="102" text-anchor="middle">â′₂</text><text x="200" y="42" text-anchor="middle" font-size="14">arm 1</text><text x="260" y="102" text-anchor="middle" font-size="14">arm 2</text></g><text x="140" y="155" text-anchor="middle" font-size="14">BS 50:50</text><text x="260" y="155" text-anchor="middle" font-size="14">phase shift</text><text x="380" y="155" text-anchor="middle" font-size="14">BS 50:50</text><text x="478" y="30" text-anchor="middle" font-size="13">D₁: sin²(φ/2)</text><text x="478" y="142" text-anchor="middle" font-size="13">D₂: cos²(φ/2)</text></g></svg></div>

BS → phase shift $\varphi$ in arm 1 → BS (matrices act right to left):

$$\begin{pmatrix} \hat a'_1 \\ \hat a'_2 \end{pmatrix} = \frac{1}{2}\begin{pmatrix} 1 & 1\\ -1 & 1 \end{pmatrix}\begin{pmatrix} e^{i \varphi} & 0\\ 0 & 1 \end{pmatrix} \begin{pmatrix} 1 & 1\\ -1 & 1 \end{pmatrix}\begin{pmatrix} \hat a_1 \\ \hat a_2 \end{pmatrix}$$

Multiplying out and using $e^{i\varphi}-1 = 2i\,e^{i\varphi/2}\sin\frac{\varphi}{2}$, $\;e^{i\varphi}+1 = 2\,e^{i\varphi/2}\cos\frac{\varphi}{2}$:

$$\begin{pmatrix} \hat a'_1 \\ \hat a'_2 \end{pmatrix} = e^{i \varphi/2} \begin{pmatrix} i \sin(\varphi/2) & \cos(\varphi/2)\\ -\cos(\varphi/2) & -i \sin(\varphi/2) \end{pmatrix}\begin{pmatrix} \hat a_1 \\ \hat a_2 \end{pmatrix}$$

For a single photon at input 1, $\hat a_1^\dagger \ket{0}$ (column 1, global phase dropped):

$$\ket{\psi'}=i \sin(\varphi/2)\ket{1,0} - \cos(\varphi/2) \ket{0,1}$$

Detection probabilities: $P_1 = \sin^2(\varphi/2)$, $P_2 = \cos^2(\varphi/2)$. After many repetitions the intensity at output 1 is

$$I_1 \propto \sin^2(\varphi/2)$$


![[Pasted image 20261013122649.png|center|480]]

The fringes depend on $\varphi$ ⇒ the MZI enables **phase estimation**. With $N$ independent photons the precision is limited by the shot noise, $\Delta\varphi \sim 1/\sqrt{N}$.

### 4.8 Back to the beam splitter

$$B = \frac{1}{\sqrt{2}}\begin{pmatrix} 1&1\\ -1 & 1\end{pmatrix}$$

**Single photon in.** $\hat a_1^\dagger\ket{0,0}$ gives

$$\ket{\psi'}=\frac{1}{\sqrt{2}}\big(\ket{1,0} - \ket{0,1}\big)$$

which can be called a **mode-entangled** state (one excitation shared between two modes). An interpretation is that in the MZI the photon interferes with itself.

**Coherent state in.** $\ket{\psi} = \ket{\alpha}_1 \ket{0}_2 = \hat D_1(\alpha) \ket{0,0}$. Transforming the displacement like the creation operator, $\hat U_B \hat D_1(\alpha)\hat U_B^\dagger = \hat D_1\!\big(\tfrac{\alpha}{\sqrt2}\big)\hat D_2\!\big(\tfrac{-\alpha}{\sqrt2}\big)$:

$$\ket{\psi'}= \left|\tfrac{\alpha}{\sqrt{2}}\right\rangle_1 \left|-\tfrac{\alpha}{\sqrt{2}}\right\rangle_2$$

which is a **product state**: a coherent state is split like a classical wave, no entanglement.

### 4.9 Two photons — Hong–Ou–Mandel effect

Input one photon in each port, $\hat a_1^\dagger \hat a_2^\dagger \ket{0,0}=\ket{1,1}$. Using columns 1 and 2 of $B$:

$$\hat a_1^\dagger \to \frac{1}{\sqrt2}\big(\hat a_1^\dagger - \hat a_2^\dagger\big), \qquad \hat a_2^\dagger \to \frac{1}{\sqrt2}\big(\hat a_1^\dagger + \hat a_2^\dagger\big)$$

$$\ket{\psi'} = \frac{1}{2}\big(\hat a_1^{\dagger 2} - \hat a_2^{\dagger 2}\big)\ket{0,0} = \frac{1}{\sqrt{2}}\big(\ket{2,0}-\ket{0,2}\big)$$

(using $\hat a^{\dagger 2}\ket{0} = \sqrt2\ket{2}$). The $\ket{1,1}$ term cancels: "both transmitted" and "both reflected" interfere destructively. The photons always leave together (which is calledbunching) aka. the **Hong–Ou–Mandel effect**.

Check against (TO-DO):
- **Coherent states** $\ket{\alpha}_1\ket{\alpha}_2$
- **Distinguishable photons** (different polarization, frequency or arrival time): no interference
- **Particles vs modes:** bunching follows from the bosonic commutation relations of the modes while fermions behave differently (antibunching)

**Time delay.** Delaying one photon by $\tau$ makes them partially distinguishable. The coincidence probability is a function of the overlap between the wavefunction which for Gaussian wavepackets is a Gaussian **HOM dip** of width ≈ the coherence time.

![[Hong-Ou-Mandel-dip-between-two-Gaussian-shaped-photon-wave-packets.webp|center|320]]

### 4.10 Multimode generalization

For $N$ single photons ($\prod_k a_k^\dagger \ket{0}$) sent into an $N$-mode network $U$, the amplitude to detect one photon in each of a given set of outputs is the **permanent** (for $2\times 2$ matrices its the sum $ad+bc$) of the corresponding $N\times N$ submatrix of $U$ (for HOM  $\operatorname{perm}B = \frac12(1\cdot1 + 1\cdot(-1)) = 0$). This is the basis of boson sampling.

---
[[QO - Lecture 1|← Previous: Lecture 1]] · [[QO - Lecture 3|Next: Lecture 3 →]]
