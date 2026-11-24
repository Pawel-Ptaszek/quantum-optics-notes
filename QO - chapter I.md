> [!info] Course info
> **Midterm:** 03.12
> **Contact:** kajac@fuw.edu.pl

## Introduction — Nobel prizes in quantum optics

| Year | Laureates | Topic |
| ---- | --------- | ----- |
| 1964 | Townes, Basov, Prokhorov | Maser / laser |
| 1966 | Kastler | Optical pumping |
| 1981 | Schawlow, Bloembergen | Laser spectroscopy |
| 1989 | Ramsey | Separated oscillatory fields (Ramsey spectroscopy) |
| 1997 | Chu, Cohen-Tannoudji, Phillips | Laser cooling and trapping |
| 2001 | Ketterle, Cornell, Wieman | Bose–Einstein condensation |
| 2005 | Glauber | Quantum theory of optical coherence |
| 2012 | Haroche, Wineland | Cavity QED, control of single quantum systems |
| 2022 | Aspect, Clauser, Zeilinger | Bell inequality tests with entangled photons |
| 2023 | Agostini, Krausz, L'Huillier | Attosecond pulses |

---

# Lecture 1

## 1. Quantization of the free field

### 1.1 Maxwell's equations and the Coulomb gauge

$$\nabla \cdot \mathbf{B}=0, \qquad \nabla \times \mathbf{E} = -\partial_t \mathbf{B}, \qquad \nabla \cdot \mathbf{D} = \rho, \qquad \nabla \times \mathbf{H} = \partial_t \mathbf{D} +\mathbf{j}$$

In vacuum $\mathbf{D}=\epsilon_0 \mathbf{E}$, $\mathbf{H}=\mathbf{B}/\mu_0$. Potentials:

$$\mathbf{B}=\nabla \times \mathbf{A}, \qquad \mathbf{E}=-\nabla \phi- \partial_t \mathbf{A}$$

Inserting into the Ampère–Maxwell law (with $\mu_0\epsilon_0 = 1/c^2$):

$$\nabla \times \nabla \times \mathbf{A} = \frac{1}{c^2} \partial_t (-\nabla \phi - \partial_t \mathbf{A})+\mu_0 \mathbf{j}$$

**Gauge freedom** — the fields are unchanged under

$$\mathbf{A}'=\mathbf{A}+\nabla \Lambda, \qquad \phi'=\phi -\partial_t \Lambda$$

We choose the **Coulomb gauge** $\nabla \cdot \mathbf{A}=0$. Then Gauss's law gives $\nabla^2\phi = -\rho/\epsilon_0$, so with no charges $\phi=0$ (and $\mathbf{j}=0$). Using $\nabla\times\nabla\times\mathbf{A} = \nabla(\nabla\cdot\mathbf{A}) - \nabla^2\mathbf{A} = -\nabla^2\mathbf{A}$ we get the wave equation

$$\nabla^2 \mathbf{A}- \frac{1}{c^2}\partial_t^2 \mathbf{A}=0$$

### 1.2 Mode expansion

Ansatz (separation of variables): $\mathbf{A}(\mathbf{r},t)=\mathcal{A}\, q(t)\, \mathbf{v}(\mathbf{r})$. Inserting into the wave equation:

$$\frac{\nabla ^2 \mathbf{v}}{\mathbf{v}}=\frac{1}{c^2} \frac{\ddot{q}}{q}=-k^2$$

which gives the **Helmholtz equation** and a **harmonic oscillator** with $\Omega = ck$:

$$\nabla^2 \mathbf{v}+k^2 \mathbf{v}=0, \qquad \ddot{q}+\Omega^2 q=0$$

**Cavity:** cube $0\le x,y,z \le L$, $V=L^3$, perfectly conducting walls.
- Boundary condition: the tangential $\mathbf{E}$ (hence tangential $\mathbf{v}$) vanishes on the walls.
- Finite size: $k_i=\dfrac{l_i \pi}{L}$, $\; l_i\in \mathbb{N}_0$ (negative $l_i$ give the same mode).
- Coulomb gauge $\nabla\cdot\mathbf{v}=0$ ⇒ transversality $\mathbf{k}\cdot\mathbf{e}=e_x k_x+e_y k_y+e_z k_z =0$, where $\mathbf{e}$ is the polarization vector ⇒ 2 polarizations per $\mathbf{k}$.

Solutions:

$$v_x=N e_x \cos(k_x x) \sin(k_y y)\sin(k_z z), \quad v_y=N e_y \sin(k_x x) \cos(k_y y)\sin(k_z z), \quad v_z=N e_z \sin(k_x x) \sin(k_y y)\cos(k_z z)$$

with $N=\sqrt{8/V}$. Mode index $l=(l_x,l_y,l_z,\text{polarization})$. Orthonormality:

$$\int_V d^3 r\; \mathbf{v}_l \cdot \mathbf{v}_{l'}=\delta_{l,l'}$$

It is convenient to use dimensionless mode functions $\mathbf{u}_l = \sqrt{V}\,\mathbf{v}_l$, so that $\int_V d^3r\, \mathbf{u}_l\cdot\mathbf{u}_{l'} = V\delta_{ll'}$, and to write

$$\mathbf{A}(\mathbf{r},t)=\sum_l \frac{1}{\sqrt{\epsilon_0 V}}\, q_l(t)\, \mathbf{u}_l(\mathbf{r})$$

### 1.3 Energy of the field → harmonic oscillators

$$\mathcal{H}=\frac{1}{2}\int_V d^3 r\left(\epsilon_0 \mathbf{E}^2+ \mu_0 \mathbf{H}^2 \right) = \frac{1}{2}\int_V d^3 r\left(\epsilon_0 \mathbf{E}^2+ \frac{1}{\mu_0} \mathbf{B}^2 \right)$$

**Electric part.** $\mathbf{E} = -\partial_t\mathbf{A} = -\sum_l \frac{1}{\sqrt{\epsilon_0 V}}\dot q_l \mathbf{u}_l$, so

$$\frac{\epsilon_0}{2}\int_V \mathbf{E}^2\, d^3r = \frac{\epsilon_0}{2}\sum_{l,l'}\frac{\dot q_l \dot q_{l'}}{\epsilon_0 V}\int_V \mathbf{u}_l\cdot\mathbf{u}_{l'}\,d^3r = \frac{1}{2}\sum_l \dot q_l^2$$

**Magnetic part.** $\mathbf{H}=\frac{1}{\mu_0} \nabla \times \mathbf{A} = \sum_l \frac{1}{\mu_0 \sqrt{\epsilon_0 V}}\,q_l\, \nabla\times \mathbf{u}_l$, so

$$\frac{\mu_0}{2}\int_V \mathbf{H}^2\, d^3r = \frac{1}{2\mu_0\epsilon_0 V}\sum_{l,l'} q_l q_{l'} \int_V (\nabla\times\mathbf{u}_l)\cdot(\nabla\times\mathbf{u}_{l'})\,d^3r$$

Use the identity $\nabla\cdot\big(\mathbf{a}\times(\nabla\times\mathbf{b})\big) = (\nabla\times\mathbf{a})\cdot(\nabla\times\mathbf{b}) - \mathbf{a}\cdot(\nabla\times\nabla\times\mathbf{b})$ and the divergence (Gauss) theorem:

$$\int_V (\nabla\times\mathbf{u}_l)\cdot(\nabla\times\mathbf{u}_{l'})\,d^3r = \int_V \mathbf{u}_l\cdot(\nabla\times\nabla\times\mathbf{u}_{l'})\,d^3r + \oint_{\partial V} \big(\mathbf{n}\times\mathbf{u}_l\big)\cdot(\nabla\times\mathbf{u}_{l'})\,dS$$

- Surface term $=0$: $\mathbf{n}\times\mathbf{u}_l$ is the tangential field on the conducting wall, which vanishes.
- $\nabla\times\nabla\times\mathbf{u}_{l'} = \nabla(\nabla\cdot\mathbf{u}_{l'}) - \nabla^2\mathbf{u}_{l'} = k_{l'}^2\,\mathbf{u}_{l'}$ (transversality + Helmholtz).

Hence $\int_V (\nabla\times\mathbf{u}_l)\cdot(\nabla\times\mathbf{u}_{l'}) = k_l^2 V\delta_{ll'}$ and

$$\frac{\mu_0}{2}\int_V \mathbf{H}^2\, d^3r = \frac{1}{2}\sum_l c^2 k_l^2\, q_l^2 = \frac{1}{2}\sum_l \Omega_l^2\, q_l^2$$

> [!important] Result
> $$\mathcal{H}=\sum_l \left( \frac{1}{2} p_l^2 +\frac{1}{2} \Omega_l^2 q_l^2 \right), \qquad p_l = \dot q_l$$
> The free field is a set of independent **harmonic oscillators**, one per mode.

### 1.4 Quantization

Promote $q_l, p_l$ to operators with $[\hat q_l, \hat p_{l'}] = i\hbar\,\delta_{ll'}$:

$$\hat{\mathcal{H}}=\sum_l \left( \frac{1}{2} \hat{p}_l^2 +\frac{1}{2} \Omega_l^2 \hat{q}_l^2 \right)$$

Ladder operators:

$$\hat{q}_l = \sqrt{\frac{\hbar}{2 \Omega_l}}\,\big(\hat{a}_l+\hat{a}_l^\dagger\big), \qquad \hat{p}_l = -i\sqrt{\frac{\hbar \Omega_l}{2}}\,\big(\hat{a}_l-\hat{a}_l^\dagger\big), \qquad [\hat{a}_l,\hat{a}_{l'}^\dagger]=\delta_{ll'}$$

> [!important] Field Hamiltonian
> $$\hat{\mathcal{H}}=\sum_l \hbar \Omega_l \left(\hat{a}_l^\dagger \hat{a}_l+\frac{1}{2} \right)$$

Single photon in mode $l$: $\hat a_l^\dagger \ket{0}=\ket{1_l}$.

### 1.5 Field operators and time evolution

$$\hat{\mathbf{A}} = \sum_l \frac{1}{\sqrt{\epsilon_0 V}}\, \hat{q}_l\, \mathbf{u}_l(\mathbf{r}) = \sum_l \sqrt{\frac{\hbar}{2 \epsilon_0 V \Omega_l}}\; \mathbf{u}_l(\mathbf{r})\, \big(\hat{a}_l+\hat{a}_l^\dagger\big)$$

**Heisenberg equation of motion:**

$$\dot{\hat{a}}_l = \frac{i}{\hbar} [\hat{\mathcal{H}},\hat{a}_l], \qquad [\hat a^\dagger \hat a, \hat a]= \hat a^\dagger [\hat a,\hat a]+[\hat a^\dagger,\hat a]\hat a=-\hat a$$

$$\Rightarrow\quad \dot{\hat a}_l = -i\Omega_l \hat a_l \quad\Rightarrow\quad \hat a_l(t) = \hat a_l(0)\, e^{-i \Omega_l t}$$

**Electric field** $\hat{\mathbf{E}} = -\partial_t \hat{\mathbf{A}}$:

$$\hat{\mathbf{E}}=i\sum_l \sqrt{\frac{\hbar \Omega_l }{2 \epsilon_0 V}}\; \mathbf{u}_l(\mathbf{r})\,\big(\hat a_l(t)-\hat a_l^\dagger(t)\big)$$

Split into positive- and negative-frequency parts, $\hat{\mathbf{E}} = \hat{\mathbf{E}}^{(+)} + \hat{\mathbf{E}}^{(-)}$, $\hat{\mathbf{E}}^{(-)} = \big(\hat{\mathbf{E}}^{(+)}\big)^\dagger$:

$$\hat{\mathbf{E}}^{(+)}=\frac{i}{2} \sum_l \mathcal{E}_l\, \mathbf{u}_l(\mathbf{r})\, \hat a_l(0)\, e^{-i \Omega_l t}, \qquad \mathcal{E}_l=\sqrt{\frac{2\hbar \Omega_l}{\epsilon_0 V}}$$

---

## 2. Quantum states of light

### 2.1 Fock (number) states

- Vacuum: $\ket{0}$, with $\hat a\ket{0}=0$
- One photon: $\hat a^\dagger \ket{0}= \ket{1}$
- $n$ photons: $\ket{n}=\dfrac{(\hat a^\dagger)^n}{\sqrt{n!}}\ket{0}$
- Multimode: $\ket{n_1,n_2,\dots}$

**Mean field** (single mode, $\hat E \propto i(\hat a-\hat a^\dagger)$):

$$\langle \hat E \rangle = \bra{n}\hat E\ket{n}= 0$$

**Fluctuations:**

$$\bra{n} (\hat a+\hat a^\dagger)^2 \ket{n} = \bra{n}\big(\hat a\hat a+\hat a^\dagger \hat a^\dagger + \hat a^\dagger\hat a+\hat a \hat a^\dagger\big) \ket{n} = \bra{n} 1+ 2 \hat{N} \ket{n} =2n+1$$

and likewise $-\bra{n}(\hat a-\hat a^\dagger)^2\ket{n} = 2n+1$ (the $\hat a\hat a$, $\hat a^\dagger\hat a^\dagger$ terms change the photon number, so their expectation vanishes).

$$\Delta^2 E = \langle \hat E^2 \rangle -\langle \hat E \rangle^2 = \frac{\mathcal{E}^2}{4}(2n+1) \quad\Rightarrow\quad \Delta E = \frac{\mathcal{E}}{\sqrt2}\sqrt{n+\tfrac{1}{2}}$$

Even in vacuum $\Delta E = \mathcal{E}/2 \neq 0$ — **vacuum fluctuations**.

### 2.2 Coherent states

**Definition:** eigenstates of the annihilation operator

$$\hat{a} \ket{\alpha} = \alpha \ket{\alpha}, \qquad \alpha\in\mathbb{C}$$

**Fock expansion.** Write $\ket{\alpha} = \sum_n c_n\ket{n}$. Then

$$\hat a\ket{\alpha} = \sum_n c_n \sqrt{n}\, \ket{n-1} = \sum_n c_n\, \alpha\, \ket{n}$$

Projecting onto $\bra{m}$:

$$c_{m+1}\sqrt{m+1} = \alpha\, c_m \quad\Rightarrow\quad c_n = \frac{\alpha}{\sqrt n}c_{n-1} = \frac{\alpha^n}{\sqrt{n!}}\,c_0$$

Normalization: $1 = |c_0|^2\sum_n \frac{|\alpha|^{2n}}{n!} = |c_0|^2 e^{|\alpha|^2}$, so $c_0 = e^{-|\alpha|^2/2}$:

$$\ket{\alpha} = e^{-|\alpha|^2/2} \sum_{n=0}^{\infty} \frac{\alpha^n}{\sqrt{n!}}\ket{n}$$

**Photon-number distribution** $P(n) = |\langle n | \alpha \rangle|^2$:

$$P(n)=e^{-|\alpha|^2}\,\frac{|\alpha|^{2n}}{n!}$$

A **Poisson distribution** — the variance equals the mean:

$$\bar{n}=|\alpha|^2, \qquad \Delta^2 n = |\alpha|^2, \qquad \frac{\Delta n}{\bar n} = \frac{1}{|\alpha|}$$

**Displacement operator.**

$$\ket{\alpha}=\hat D(\alpha)\ket{0}, \qquad \hat D(\alpha)= e^{\alpha \hat a^\dagger - \alpha^* \hat a}$$

With BCH, $e^{\hat X+\hat Y}=e^{\hat X}e^{\hat Y}e^{-\frac12[\hat X,\hat Y]}$ for $[\hat X,\hat Y]$ a c-number; here $[\alpha\hat a^\dagger,-\alpha^*\hat a]=|\alpha|^2$:

$$\hat D(\alpha) = e^{-|\alpha|^2/2}\,e^{\alpha \hat a^\dagger}\, e^{-\alpha^* \hat a}$$

Acting on $\ket{0}$ ($e^{-\alpha^*\hat a}\ket0=\ket0$) reproduces the Fock expansion above. $\hat D$ displaces the field operators (Hadamard lemma):

$$\hat D^\dagger(\alpha)\, \hat a\, \hat D(\alpha) = \hat a+ \alpha$$

A coherent state is a **displaced vacuum**.

![[a7211c19-0634-454e-b748-8618a7ed9346.jpg|center|450]]

**Overlap** — coherent states are not orthogonal:

$$\langle \beta | \alpha \rangle = \bra{0} \hat D^\dagger(\beta)\hat D(\alpha) \ket{0} = e^{-\frac{1}{2}\left(|\alpha|^2+|\beta|^2\right)+\alpha \beta^*}, \qquad |\langle \beta | \alpha \rangle|^2 = e^{-|\alpha-\beta|^2}$$

**Completeness** — they form an *overcomplete* basis:

$$\frac{1}{\pi}\int d^2 \alpha\, \ket{\alpha} \bra{\alpha} = \hat{1}, \qquad d^2\alpha = d(\mathrm{Re}\,\alpha)\, d(\mathrm{Im}\,\alpha)$$

*Proof.* Insert the Fock expansion and use polar coordinates $\alpha = re^{i\theta}$, $d^2\alpha = r\,dr\,d\theta$:

$$\int d^2 \alpha\, \ket{\alpha} \bra{\alpha} = \sum_{n,m} \frac{\ket{n} \bra{m}}{\sqrt{n!\, m!}} \int d^2 \alpha\; e^{-|\alpha|^2} \alpha^n \alpha^{*m} = \sum_{n,m} \frac{\ket{n} \bra{m}}{\sqrt{n!\, m!}} \int_0^\infty dr\; r^{n+m+1} e^{-r^2} \int_0^{2\pi} d \theta\; e^{i \theta (n-m)}$$

Angular integral: $\int_0^{2\pi} d\theta\, e^{i\theta(n-m)} = 2\pi\,\delta_{nm}$.

Radial integral (for $n=m$), substituting $x=r^2$, $dx = 2r\,dr$:

$$\int_0^\infty dr\; r^{2n+1} e^{-r^2} = \frac{1}{2}\int_0^\infty dx\; x^n e^{-x} = \frac{1}{2}\Gamma(n+1) = \frac{n!}{2}$$

Therefore

$$\int d^2 \alpha\, \ket{\alpha} \bra{\alpha} = \sum_{n} \frac{\ket{n} \bra{n}}{n!}\cdot 2\pi\cdot\frac{n!}{2} = \pi\sum_n\ket{n}\bra{n} = \pi\,\hat 1 \qquad\blacksquare$$

**Mean field.** Single mode, $\hat E = \frac{i}{2}\mathcal{E}\big(\hat a\, e^{-i\Omega t} - \hat a^\dagger e^{i\Omega t}\big)$, $\alpha = |\alpha|e^{i\theta}$:

$$\langle \alpha | \hat E | \alpha \rangle = \frac{i}{2} \mathcal{E}\, |\alpha| \left(e^{-i (\Omega t- \theta)}-e^{i (\Omega t- \theta)}\right) = \mathcal{E}\,|\alpha| \sin(\Omega t - \theta)$$

**Fluctuations.** Using $\hat a\hat a^\dagger = \hat a^\dagger\hat a+1$:

$$\langle \hat E^2 \rangle = \frac{\mathcal{E}^2}{4}\Big(1+ 4 |\alpha|^2 \sin^2(\Omega t - \theta)\Big) \quad\Rightarrow\quad \Delta^2 E = \langle \hat E^2 \rangle - \langle \hat E \rangle^2 = \frac{\mathcal{E}^2}{4}$$

The noise is the same as for the vacuum — independent of $\alpha$ and of time.

![[ee91ba35-8143-4cdc-ac52-3211b31dc004.jpg|center|450]]

> [!summary]
> A coherent state behaves like a classical wave with Poissonian photon-number fluctuations. It is a **minimum-uncertainty state**: for the quadratures $\hat X_1 = \frac{1}{2}(\hat a+\hat a^\dagger)$, $\hat X_2 = \frac{1}{2i}(\hat a-\hat a^\dagger)$, $[\hat X_1,\hat X_2]=\frac{i}{2}$, it saturates $\Delta X_1\,\Delta X_2 = \frac14$ with $\Delta X_1=\Delta X_2=\frac12$.

**What is a typical light state?**

### 2.3 Thermal states

The number of photons is given by the Boltzmann distribution.

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

For $N$ single photons sent into an $N$-mode network $U$, the amplitude to detect one photon in each of a given set of outputs is the **permanent** of the corresponding $N\times N$ submatrix of $U$ (HOM is the $2\times2$ case: $\operatorname{perm}B = \frac12(1\cdot1 + 1\cdot(-1)) = 0$). This is the basis of boson sampling.


# Lecture 3

## 5. Operator identities and the displacement operator

### 5.1 BCH, Hadamard lemma, Weyl form

**Baker–Campbell–Hausdorff:**

$$e^{\hat A} e^{\hat B} = \exp\!\Big(\hat A+\hat B+\tfrac{1}{2}[\hat A,\hat B]+\tfrac{1}{12}\big([\hat A,[\hat A,\hat B]]-[\hat B,[\hat A,\hat B]]\big)+\dots\Big)$$

**Hadamard lemma** (used to transform operators):

$$e^{\hat X}\, \hat Y\, e^{-\hat X}=\hat Y+[\hat X,\hat Y]+\frac{1}{2!}[\hat X,[\hat X,\hat Y]]+\frac{1}{3!}[\hat X,[\hat X,[\hat X,\hat Y]]]+\dots$$

**Weyl case** — if $[\hat A,\hat B]$ is a c-number (e.g. $\hat A\propto\hat a^\dagger$, $\hat B\propto\hat a$), all higher commutators vanish and the series truncate:

$$e^{\hat A+\hat B} = e^{\hat A}\,e^{\hat B}\,e^{-\frac12[\hat A,\hat B]}$$

(The general product expansion $e^{\hat A+\hat B} = e^{\hat A}e^{\hat B}e^{-\frac12[\hat A,\hat B]}\cdots$ is the Zassenhaus formula.)

### 5.2 Displacement operator

$$\hat D(\alpha) = e^{\alpha \hat a^\dagger - \alpha^* \hat a}, \qquad \hat D(\alpha) \ket{0}= e^{-|\alpha|^2/2}\,e^{\alpha \hat a^\dagger}\,e^{-\alpha^* \hat a}\ket{0} = e^{-|\alpha|^2/2}\,e^{\alpha \hat a^\dagger}\ket{0} = \ket{\alpha}$$

(Weyl form with $[\alpha\hat a^\dagger, -\alpha^*\hat a] = |\alpha|^2$; $e^{-\alpha^*\hat a}\ket0 = \ket0$.)

**Composition.** With $\hat A = \alpha\hat a^\dagger-\alpha^*\hat a$, $\hat B = \beta\hat a^\dagger-\beta^*\hat a$:

$$[\hat A,\hat B] = \alpha\beta^* - \alpha^*\beta = 2i\,\mathrm{Im}(\alpha\beta^*)$$

$$\hat D(\alpha)\hat D(\beta)=e^{\hat A+\hat B}\,e^{\frac12[\hat A,\hat B]} = \hat D(\alpha+\beta)\; e^{i\,\mathrm{Im}(\alpha \beta^*)}$$

So $\hat D(\alpha)\hat D(\beta)\ket{0}=e^{i \phi}\ket{\alpha + \beta}$ with $\phi = \mathrm{Im}(\alpha\beta^*)$ — displacements add, up to a phase.

**Why "displacement".** Hadamard lemma with $\hat X = -(\alpha\hat a^\dagger-\alpha^*\hat a)$: $[\hat X,\hat a] = \alpha$, a c-number, so

$$\hat D^\dagger(\alpha)\,\hat{a}\,\hat D(\alpha) = \hat{a}+\alpha$$

---

## 6. Thermal states

Thermal light is in general multimode; here we treat a single mode of frequency $\omega$ in equilibrium at temperature $T$. It is a mixed state, described by a density matrix.

### 6.1 Density matrix and partition function

$$\hat\rho=\frac{1}{Z}\, e^{-\hat{\mathcal{H}}/k_B T}, \qquad \hat{\mathcal{H}} = \hbar\omega\left(\hat n+\tfrac12\right)$$

With $x \equiv \hbar\omega/k_BT$:

$$Z= \mathrm{Tr}\, e^{-\hat{\mathcal{H}}/k_BT} = \sum_{n=0}^\infty e^{-x(n+\frac{1}{2})} = \frac{e^{-x/2}}{1-e^{-x}}$$

In the Fock basis $\hat\rho$ is diagonal:

$$\hat\rho = \sum_{n}p_n \ket{n}\bra{n}, \qquad p_n=\frac{e^{-x(n+\frac{1}{2})}}{Z} = \left(1-e^{-x}\right)e^{-nx}$$

### 6.2 Mean photon number

Derivative trick: $\displaystyle\sum_n n\, e^{-nx}=-\frac{d}{dx} \sum_n e^{-nx}= -\frac{d}{dx}\frac{1}{1-e^{-x}} = \frac{e^{-x}}{(1-e^{-x})^2}$, so

$$\bar n = \langle \hat n \rangle = \sum_n n\, p_n=\frac{e^{-x}}{1-e^{-x}} = \frac{1}{e^{\hbar \omega /k_BT}-1}$$

the **Bose–Einstein** distribution. For $k_BT \gg \hbar \omega$: $\bar n \approx k_BT/\hbar \omega$. In terms of $\bar n$, $p_n = \dfrac{\bar n^{\,n}}{(1+\bar n)^{n+1}}$ (geometric distribution).

### 6.3 Photon-number fluctuations

Apply the derivative twice:

$$\sum_n n^2 e^{-nx} = \frac{d^2}{dx^2}\frac{1}{1-e^{-x}} = \frac{e^{-x}\left(1+e^{-x}\right)}{(1-e^{-x})^3} \quad\Rightarrow\quad \langle \hat n^2\rangle = \frac{e^{-x}\left(1+e^{-x}\right)}{(1-e^{-x})^2}$$

$$\Delta^2 n= \langle \hat n^2 \rangle - \bar n^2 = \frac{e^{-x}}{(1-e^{-x})^2} = \bar n^2+\bar n$$

> [!important] Thermal vs coherent light
> Coherent (Poissonian) light: $\Delta^2 n = \bar n$. Thermal light: $\Delta^2 n = \bar n + \bar n^2$ — **super-Poissonian**: the extra $\bar n^2$ (wave noise) dominates for $\bar n\gg1$. Equivalently $g^{(2)}(0) = \langle \hat n(\hat n-1)\rangle/\bar n^2 = 2$ for thermal light, $1$ for coherent light.

### 6.4 Interactive: Gaussian states, from thermal to pure

> Needs **Dataview** with *Enable JavaScript Queries* on (same setup as the RLTI notes; uses `FUW/lib/jsxgraphcore.js` and `FUW/lib/rlti.js`).

The most general single-mode Gaussian state is a **displaced squeezed thermal state**,

$$\hat\rho = \hat D(\alpha_0)\,\hat S(\xi)\,\hat\rho_{\rm th}\,\hat S^\dagger(\xi)\,\hat D^\dagger(\alpha_0), \qquad \xi = r\,e^{2i\varphi},$$

with free parameters $n_{\rm th}$ (temperature), $r,\varphi$ (squeezing) and $\alpha_0$ (displacement). Setting $k_BT\to0$ gives a **pure** state (coherent / squeezed); raising $k_BT$ mixes it.

> [!note] Is only $\hbar\omega/k_BT$ relevant?
> Yes. $\hat\rho_{\rm th} = e^{-\hbar\omega\hat n/k_BT}/Z$ depends on $k_BT$ and $\hbar\omega$ only through $x = \hbar\omega/k_BT$, i.e. through $n_{\rm th} = 1/(e^{x}-1)$. Both sliders are kept so you can check it: doubling both leaves every plot unchanged.

**Formulas used in the plot** ($\alpha = x+iy$, vacuum quadrature variance $\frac14$):
- Wigner function: Gaussian with mean $\boldsymbol\mu = (\mathrm{Re}\,\alpha_0, \mathrm{Im}\,\alpha_0)$ and covariance $V = \frac{2n_{\rm th}+1}{4}\,R_\varphi\,\mathrm{diag}(e^{-2r},e^{2r})\,R_\varphi^{T}$:
$$W(\alpha) = \frac{1}{2\pi\sqrt{\det V}}\exp\!\Big[-\tfrac12(\mathbf v-\boldsymbol\mu)^T V^{-1}(\mathbf v-\boldsymbol\mu)\Big].$$
- Photon statistics (exact, no Fock-space truncation error): from the generating function of §8.6, using the Weyl symbol of $z^{\hat n}$, $\frac{2}{1+z}e^{-2\frac{1-z}{1+z}|\alpha|^2}$, a Gaussian integral gives
$$G(z) = \frac{2}{\sqrt{A(z)}}\exp\frac{B(z)}{A(z)}, \quad A(z)=\det M(z),\quad B(z) = -2(1-z)\,\boldsymbol\mu^T\mathrm{adj}\,M(z)\,\boldsymbol\mu,\quad M(z)=(1+z)\mathbb 1+4(1-z)V,$$
and $P(n)$ are its Taylor coefficients.
- Reference: Poisson distribution with the same $\langle n\rangle$.

**Things to try:** thermal ($r=0$, $\alpha_0=0$) gives $g^{(2)}=2$ and the geometric $P(n)$ of §6.1. $k_BT=0$ with $|\alpha_0|>0$ is a coherent state, which is exactly Poissonian. Squeezing along the displacement ($\varphi = \arg\alpha_0$) makes it **sub-Poissonian**. Note that $W\ge0$ for every setting (Hudson, §8.9).

```dataviewjs
// ===== CONFIG =====
const CFG = {
  kT: 1.0, kTMax: 5,               // k_B T  [E0]  (0 = pure state)
  hw: 1.0, hwMin: 0.2, hwMax: 3,   // ħω     [E0]
  r: 0, rMax: 1.2,                 // squeezing parameter r
  phi: 0,                          // squeezing angle φ [deg]: X_φ is squeezed
  amp: 0, ampMax: 3,               // displacement |α0|
  arg: 0,                          // arg α0 [deg]
  L: 4.5,                          // Wigner plot range: Re α, Im α ∈ [−L, L]
  N: 220,                          // Fock cutoff for P(n)
};
// ==================
// ---- loader (leave as is) ----
const LIB = "FUW/lib/";
const load = (src) => new Promise((ok, no) => { const s = document.createElement("script"); s.src = src; s.onload = ok; s.onerror = () => no(new Error("could not load " + src)); document.head.append(s); });
const libPath = async (n) => { const here = dv.current().file.folder, up = here.includes("/") ? here.slice(0, here.lastIndexOf("/")) + "/" : ""; for (const p of [LIB + n, "lib/" + n, here + "/lib/" + n, up + "lib/" + n, ...app.vault.getFiles().filter((x) => x.path.endsWith("lib/" + n)).map((x) => x.path)]) if (await app.vault.adapter.exists(p)) return p; throw new Error("lib/" + n + " not found in this vault (is the FUW/lib folder synced to this computer?)"); };
if (!window.JXG) await (window.__jxg ??= libPath("jsxgraphcore.js").then((p) => load(app.vault.adapter.getResourcePath(p))).catch(() => load("https://cdn.jsdelivr.net/npm/jsxgraph@1.10.1/distrib/jsxgraphcore.js")).catch((e) => { window.__jxg = null; throw e; }));
if (!window.RL) await (window.__rl ??= libPath("rlti.js").then((p) => load(app.vault.adapter.getResourcePath(p))).catch((e) => { window.__rl = null; throw e; }));
const K = await RL.init(dv), { f, el, C } = K;

// ---- controls ----
const deg = (v) => (+v).toFixed(0) + "°";
const sT = K.slider("k_BT", 0, CFG.kTMax, 0.01, CFG.kT);
const sH = K.slider("ħω", CFG.hwMin, CFG.hwMax, 0.01, CFG.hw);
const sR = K.slider("r", 0, CFG.rMax, 0.01, CFG.r);
const sP = K.slider("φ", 0, 180, 1, CFG.phi, deg);
const sA = K.slider("|α₀|", 0, CFG.ampMax, 0.01, CFG.amp);
const sG = K.slider("arg α₀", 0, 360, 1, CFG.arg, deg);
const cbV = K.check("vacuum-noise circle"), cbP = K.check("Poisson, same mean");

// ---- layout ----
const GAP = 12, WS = Math.min(320, Math.floor((K.W - GAP) / 2)), WP = K.W - WS - GAP;
const row = el("div", `display:flex;gap:${GAP}px;align-items:flex-start;margin-top:6px`);
const box = "background:#fff;border:1px solid #e5e7eb;border-radius:10px";
const cv = el("canvas", `width:${WS}px;height:${WS}px;${box}`);
const dpr = window.devicePixelRatio || 1; cv.width = Math.round(WS * dpr); cv.height = Math.round(WS * dpr);
const pdiv = el("div", `width:${WP}px;height:${WS}px;${box};touch-action:none`);
row.append(cv, pdiv);
const panel = el("div", "font-family:var(--font-monospace,monospace);font-size:0.8em;line-height:1.55;white-space:pre-wrap;color:var(--text-normal);margin-top:6px");
K.root.append(row, panel);

// ---- state: covariance V (vacuum = I/4) and mean μ, with α = x + i y ----
function state() {
  const kT = +sT.value, hw = +sH.value, x = kT > 0 ? hw / kT : Infinity;
  const nth = x === Infinity ? 0 : 1 / Math.expm1(x);
  const r = +sR.value, ph = (+sP.value * Math.PI) / 180, A = +sA.value, ag = (+sG.value * Math.PI) / 180;
  const s = (2 * nth + 1) / 4, c = Math.cos(ph), sn = Math.sin(ph), e1 = Math.exp(-2 * r), e2 = Math.exp(2 * r);
  const V = [s * (c * c * e1 + sn * sn * e2), s * c * sn * (e1 - e2), s * (sn * sn * e1 + c * c * e2)]; // [Vxx, Vxy, Vyy]
  return { kT, hw, x, nth, r, ph, V, mu: [A * Math.cos(ag), A * Math.sin(ag)] };
}

// ---- P(n) exactly, from the generating function G(z) = Tr(ρ z^n) = 2 A(z)^(-1/2) exp(B(z)/A(z)) ----
function photonStats({ V, mu }) {
  const N = CFG.N, [vxx, vxy, vyy] = V;
  // M(z) = (1+z) I + 4(1−z) V = M0 + z M1
  const M0 = [1 + 4 * vxx, 4 * vxy, 1 + 4 * vyy], M1 = [1 - 4 * vxx, -4 * vxy, 1 - 4 * vyy];
  const a = [M0[0] * M0[2] - M0[1] ** 2, M0[0] * M1[2] + M1[0] * M0[2] - 2 * M0[1] * M1[1], M1[0] * M1[2] - M1[1] ** 2];
  const q = (M) => M[2] * mu[0] ** 2 - 2 * M[1] * mu[0] * mu[1] + M[0] * mu[1] ** 2; // μᵀ adj(M) μ
  const q0 = q(M0), q1 = q(M1), b = [-2 * q0, 2 * q0 - 2 * q1, 2 * q1];
  const pow = (p) => { const h = new Float64Array(N); h[0] = a[0] ** p; for (let n = 1; n < N; n++) { let s = 0; for (let k = 1; k <= Math.min(2, n); k++) s += (p * k - (n - k)) * a[k] * h[n - k]; h[n] = s / (n * a[0]); } return h; };
  const inv = pow(-1), half = pow(-0.5), g = new Float64Array(N), e = new Float64Array(N), P = new Float64Array(N);
  for (let n = 0; n < N; n++) for (let k = 0; k <= Math.min(2, n); k++) g[n] += b[k] * inv[n - k];
  e[0] = Math.exp(g[0]);
  for (let n = 1; n < N; n++) { let s = 0; for (let k = 1; k <= n; k++) s += k * g[k] * e[n - k]; e[n] = s / n; }
  for (let n = 0; n < N; n++) { let s = 0; for (let k = 0; k <= n; k++) s += half[k] * e[n - k]; P[n] = Math.max(0, 2 * s); }
  let m1 = 0, m2 = 0, tot = 0; P.forEach((p, n) => { tot += p; m1 += n * p; m2 += n * n * p; });
  return { P, tot, mean: m1, varn: m2 - m1 * m1, fact2: m2 - m1 };
}

// ---- Wigner function on the canvas ----
const ctx = cv.getContext("2d"), L = CFG.L, VMAX = 2 / Math.PI;
const stops = [[-1, [31, 95, 168]], [-0.5, [127, 166, 212]], [0, [248, 248, 248]], [0.5, [240, 164, 106]], [1, [194, 65, 12]]];
const cmap = (t) => { t = Math.max(-1, Math.min(1, t)); let i = 0; while (i < stops.length - 2 && t > stops[i + 1][0]) i++; const [t0, c0] = stops[i], [t1, c1] = stops[i + 1], u = (t - t0) / (t1 - t0); return c0.map((v, j) => Math.round(v + u * (c1[j] - v))); };
const X = (px) => -L + (2 * L * px) / cv.width, Y = (py) => L - (2 * L * py) / cv.height;
const toPx = (x) => ((x + L) / (2 * L)) * cv.width, toPy = (y) => ((L - y) / (2 * L)) * cv.height;
function drawW(st) {
  const [vxx, vxy, vyy] = st.V, det = vxx * vyy - vxy * vxy, ixx = vyy / det, ixy = -vxy / det, iyy = vxx / det, norm = 1 / (2 * Math.PI * Math.sqrt(det));
  const img = ctx.createImageData(cv.width, cv.height), d = img.data;
  for (let py = 0; py < cv.height; py++) {
    const dy = Y(py) - st.mu[1];
    for (let px = 0; px < cv.width; px++) {
      const dx = X(px) - st.mu[0], w = norm * Math.exp(-0.5 * (ixx * dx * dx + 2 * ixy * dx * dy + iyy * dy * dy));
      const [R, G, B] = cmap(w / VMAX), o = 4 * (py * cv.width + px); d[o] = R; d[o + 1] = G; d[o + 2] = B; d[o + 3] = 255;
    }
  }
  ctx.putImageData(img, 0, 0);
  ctx.save(); ctx.scale(dpr, dpr); const S = WS, sx = (x) => toPx(x) / dpr, sy = (y) => toPy(y) / dpr;
  ctx.strokeStyle = "#9ca3af"; ctx.lineWidth = 1; ctx.beginPath(); ctx.moveTo(0, sy(0)); ctx.lineTo(S, sy(0)); ctx.moveTo(sx(0), 0); ctx.lineTo(sx(0), S); ctx.stroke();
  ctx.fillStyle = "#6b7280"; ctx.font = "10px sans-serif";
  for (let t = -Math.floor(L); t <= Math.floor(L); t++) if (t) { ctx.fillRect(sx(t) - 0.5, sy(0) - 3, 1, 6); ctx.fillRect(sx(0) - 3, sy(t) - 0.5, 6, 1); ctx.fillText(t, sx(t) - 3, sy(0) + 13); }
  ctx.fillStyle = C.ink; ctx.font = "italic 13px serif"; ctx.fillText("Re α", S - 34, sy(0) - 6); ctx.fillText("Im α", sx(0) + 6, 13);
  // 1σ ellipse of W  (axes = eigenvectors of V)
  const tr = vxx + vyy, dd = Math.sqrt(((vxx - vyy) / 2) ** 2 + vxy * vxy), l1 = tr / 2 + dd, l2 = tr / 2 - dd, th = 0.5 * Math.atan2(2 * vxy, vxx - vyy);
  ctx.strokeStyle = C.ink; ctx.lineWidth = 1.5; ctx.beginPath(); ctx.ellipse(sx(st.mu[0]), sy(st.mu[1]), (Math.sqrt(l1) * S) / (2 * L), (Math.sqrt(l2) * S) / (2 * L), -th, 0, 2 * Math.PI); ctx.stroke();
  if (cbV.checked) { ctx.setLineDash([4, 3]); ctx.strokeStyle = C.obs; ctx.beginPath(); ctx.arc(sx(st.mu[0]), sy(st.mu[1]), (0.5 * S) / (2 * L), 0, 2 * Math.PI); ctx.stroke(); ctx.setLineDash([]); }
  ctx.fillStyle = C.muted; ctx.font = "11px sans-serif"; ctx.fillText("W(α), colour scale ±2/π", 6, S - 6);
  ctx.restore();
}

// ---- P(n) board ----
const bP = JXG.JSXGraph.initBoard(pdiv, { boundingbox: [-1.5, 1, 20, -0.08], keepAspectRatio: false, axis: true, showCopyright: false, showNavigation: false, pan: { enabled: false }, zoom: { enabled: false },
  defaultAxes: { x: { name: "n", withLabel: true, strokeColor: "#9ca3af", label: { position: "rt", offset: [-14, 14], fontSize: 14, strokeColor: C.ink }, ticks: { minorTicks: 0, strokeColor: "#9ca3af", label: { fontSize: 10, strokeColor: C.muted } } },
                 y: { name: "P(n)", withLabel: true, strokeColor: "#9ca3af", label: { position: "rt", offset: [8, -6], fontSize: 14, strokeColor: C.ink }, ticks: { minorTicks: 0, strokeColor: "#9ca3af", label: { fontSize: 10, strokeColor: C.muted } } } } });
let ST = state(), PS = photonStats(ST), nShow = 20;
const bars = bP.create("curve", [[0], [0]], { fixed: true, highlight: false, strokeColor: "#c2410c", strokeWidth: 1, fillColor: "#f0a46a", fillOpacity: 0.85 });
bars.updateDataArray = function () { const xs = [], ys = []; for (let n = 0; n <= nShow; n++) { xs.push(n - 0.38, n - 0.38, n + 0.38, n + 0.38, NaN); ys.push(0, PS.P[n], PS.P[n], 0, NaN); } this.dataX = xs; this.dataY = ys; };
const pois = (n, m) => Math.exp(n * Math.log(Math.max(m, 1e-300)) - m - lgamma(n + 1));
function lgamma(x) { let s = 0; for (let k = 2; k < x; k++) s += Math.log(k); return s; }
const poisLine = bP.create("curve", [[0], [0]], { fixed: true, highlight: false, strokeColor: C.obs, strokeWidth: 2, dash: 2, visible: () => cbP.checked });
poisLine.updateDataArray = function () { const xs = [], ys = []; for (let n = 0; n <= nShow; n++) { xs.push(n); ys.push(pois(n, PS.mean)); } this.dataX = xs; this.dataY = ys; };
const poisPts = [];
for (let n = 0; n <= 80; n++) poisPts.push(bP.create("point", [n, () => pois(n, PS.mean)], { fixed: true, highlight: false, withLabel: false, size: 2.5, strokeColor: C.obs, fillColor: "#fff", visible: () => cbP.checked && n <= nShow }));
const legend = bP.create("text", [0, 0, () => cbP.checked ? "<span style='color:#c2410c'>■</span> state &nbsp; <span style='color:" + C.obs + "'>○</span> Poisson, same ⟨n⟩" : "<span style='color:#c2410c'>■</span> state"], { fixed: true, highlight: false, fontSize: 12, strokeColor: C.ink, anchorX: "right", anchorY: "top" });

function update() {
  ST = state(); PS = photonStats(ST);
  let cum = 0, nEnd = 0; for (let n = 0; n < CFG.N; n++) { cum += PS.P[n]; if (cum > 0.999) { nEnd = n; break; } }
  nShow = Math.min(80, Math.max(10, Math.ceil(Math.max(nEnd, PS.mean + 4 * Math.sqrt(PS.varn)))));
  let ymax = 0; for (let n = 0; n <= nShow; n++) ymax = Math.max(ymax, PS.P[n], cbP.checked ? pois(n, PS.mean) : 0);
  ymax *= 1.18;
  bP.setBoundingBox([-0.06 * nShow - 1, ymax, nShow + 1, -0.08 * ymax], false);
  legend.setPosition(JXG.COORDS_BY_USER, [nShow + 0.6, ymax * 0.97]);
  bP.update(); drawW(ST);
  const m = PS.mean, Q = m > 1e-9 ? (PS.varn - m) / m : 0, g2 = m > 1e-9 ? PS.fact2 / (m * m) : NaN;
  const x = ST.x === Infinity ? "∞" : f(ST.x);
  panel.textContent =
`ħω/k_BT = ${x}  ⇒  n_th = ${f(ST.nth)}    purity Tr ρ² = 1/(2n_th+1) = ${f(1 / (2 * ST.nth + 1))}   (only the ratio matters)
⟨n⟩ = ${f(m)}   Var(n) = ${f(PS.varn)}   Q = ${f(Q)}   g⁽²⁾(0) = ${isNaN(g2) ? "—" : f(g2)}   ${Q < -1e-6 ? "sub-Poissonian (nonclassical)" : Q > 1e-6 ? "super-Poissonian" : "Poissonian"}
Var(X_φ) = ${f(Math.exp(-2 * ST.r) * (2 * ST.nth + 1) / 4)}, Var(X_φ+π/2) = ${f(Math.exp(2 * ST.r) * (2 * ST.nth + 1) / 4)}  (vacuum 0.250)${Math.exp(-2 * ST.r) * (2 * ST.nth + 1) < 1 - 1e-9 ? "  squeezed!" : ""}   W ≥ 0 (Gaussian)`;
}
for (const s of [sT, sH, sR, sP, sA, sG]) s.addEventListener("input", update);
for (const c of [cbV, cbP]) c.onchange = update;
update();
```

---

## 7. Hong–Ou–Mandel effect revisited

Convention in this lecture: inputs $\hat a, \hat b$, outputs $\hat c, \hat d$, balanced BS

$$\begin{pmatrix} \hat c \\ \hat d \end{pmatrix} = B \begin{pmatrix} \hat a \\ \hat b \end{pmatrix}, \qquad B = \frac{1}{\sqrt2}\begin{pmatrix} 1 & 1 \\ 1 & -1 \end{pmatrix} = B^{-1} \quad\Rightarrow\quad \hat a=\frac{1}{\sqrt{2}}(\hat c+\hat d), \quad \hat b=\frac{1}{\sqrt{2}}(\hat c-\hat d)$$

<div style="text-align:center"><svg width="560" height="330" viewBox="0 0 560 330" xmlns="http://www.w3.org/2000/svg" fill="none" stroke="currentColor" stroke-width="1.6" font-family="Times New Roman, serif" font-size="18"><defs><marker id="arrHOM" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="7" markerHeight="7" orient="auto"><path d="M0,0 L10,5 L0,10 z" fill="currentColor" stroke="none"/></marker></defs><line x1="40" y1="170" x2="282" y2="170" stroke-dasharray="4 4" opacity="0.6"/><line x1="300" y1="320" x2="300" y2="188" stroke-dasharray="4 4" opacity="0.6"/><rect x="282" y="152" width="36" height="36"/><line x1="282" y1="188" x2="318" y2="152" stroke-width="2.4"/><line x1="318" y1="170" x2="455" y2="170" marker-end="url(#arrHOM)"/><line x1="300" y1="152" x2="300" y2="60" marker-end="url(#arrHOM)"/><g stroke-width="1.8"><polyline points="100.0,170.0 101.0,170.0 102.0,170.0 103.0,170.0 104.0,170.0 105.0,170.0 106.0,170.0 107.0,170.0 108.0,170.0 109.0,170.0 110.0,170.0 111.0,170.0 112.0,170.0 113.0,170.0 114.0,170.0 115.0,170.0 116.0,170.0 117.0,170.0 118.0,170.0 119.0,170.0 120.0,170.0 121.0,170.0 122.0,170.0 123.0,170.0 124.0,170.1 125.0,170.1 126.0,170.0 127.0,169.9 128.0,169.8 129.0,169.8 130.0,170.0 131.0,170.2 132.0,170.3 133.0,170.4 134.0,170.1 135.0,169.7 136.0,169.3 137.0,169.2 138.0,169.6 139.0,170.4 140.0,171.2 141.0,171.6 142.0,171.0 143.0,169.6 144.0,168.0 145.0,167.2 146.0,167.9 147.0,170.1 148.0,172.9 149.0,174.5 150.0,173.8 151.0,170.6 152.0,166.4 153.0,163.4 154.0,163.9 155.0,168.0 156.0,174.0 157.0,178.6 158.0,178.8 159.0,174.0 160.0,166.2 161.0,159.8 162.0,158.6 163.0,163.7 164.0,172.7 165.0,180.8 166.0,183.3 167.0,178.6 168.0,169.0 169.0,159.8 170.0,156.0 171.0,159.8 172.0,169.0 173.0,178.6 174.0,183.3 175.0,180.8 176.0,172.7 177.0,163.7 178.0,158.6 179.0,159.8 180.0,166.2 181.0,174.0 182.0,178.8 183.0,178.6 184.0,174.0 185.0,168.0 186.0,163.9 187.0,163.4 188.0,166.4 189.0,170.6 190.0,173.8 191.0,174.5 192.0,172.9 193.0,170.1 194.0,167.9 195.0,167.2 196.0,168.0 197.0,169.6 198.0,171.0 199.0,171.6 200.0,171.2 201.0,170.4 202.0,169.6 203.0,169.2 204.0,169.3 205.0,169.7 206.0,170.1 207.0,170.4 208.0,170.3 209.0,170.2 210.0,170.0 211.0,169.8 212.0,169.8 213.0,169.9 214.0,170.0 215.0,170.1 216.0,170.1 217.0,170.0 218.0,170.0 219.0,170.0 220.0,170.0 221.0,170.0 222.0,170.0 223.0,170.0 224.0,170.0 225.0,170.0 226.0,170.0 227.0,170.0 228.0,170.0 229.0,170.0 230.0,170.0 231.0,170.0 232.0,170.0 233.0,170.0 234.0,170.0 235.0,170.0 236.0,170.0 237.0,170.0 238.0,170.0 239.0,170.0 240.0,170.0"/><polyline points="300.0,310.0 300.0,309.4 300.0,308.7 300.0,308.1 300.0,307.4 300.0,306.8 300.0,306.1 300.0,305.5 300.0,304.9 300.0,304.2 300.0,303.6 300.0,302.9 300.0,302.3 300.0,301.6 300.0,301.0 300.0,300.4 300.0,299.7 300.0,299.1 300.0,298.4 300.0,297.8 300.0,297.1 300.0,296.5 300.0,295.9 300.0,295.2 299.9,294.6 299.9,293.9 299.9,293.3 300.0,292.6 300.0,292.0 300.1,291.4 300.2,290.7 300.3,290.1 300.3,289.4 300.2,288.8 300.0,288.1 299.8,287.5 299.4,286.9 299.1,286.2 299.0,285.6 299.1,284.9 299.5,284.3 300.3,283.6 301.1,283.0 302.0,282.4 302.5,281.7 302.5,281.1 301.8,280.4 300.3,279.8 298.5,279.1 296.5,278.5 295.1,277.9 294.6,277.2 295.5,276.6 297.8,275.9 301.0,275.3 304.6,274.6 307.6,274.0 309.1,273.4 308.5,272.7 305.7,272.1 301.2,271.4 295.8,270.8 291.0,270.1 288.0,269.5 287.6,268.9 290.2,268.2 295.3,267.6 301.7,266.9 307.9,266.3 312.4,265.6 314.0,265.0 312.4,264.4 307.9,263.7 301.7,263.1 295.3,262.4 290.2,261.8 287.6,261.1 288.0,260.5 291.0,259.9 295.8,259.2 301.2,258.6 305.7,257.9 308.5,257.3 309.1,256.6 307.6,256.0 304.6,255.4 301.0,254.7 297.8,254.1 295.5,253.4 294.6,252.8 295.1,252.1 296.5,251.5 298.5,250.9 300.3,250.2 301.8,249.6 302.5,248.9 302.5,248.3 302.0,247.6 301.1,247.0 300.3,246.4 299.5,245.7 299.1,245.1 299.0,244.4 299.1,243.8 299.4,243.1 299.8,242.5 300.0,241.9 300.2,241.2 300.3,240.6 300.3,239.9 300.2,239.3 300.1,238.6 300.0,238.0 300.0,237.4 299.9,236.7 299.9,236.1 299.9,235.4 300.0,234.8 300.0,234.1 300.0,233.5 300.0,232.9 300.0,232.2 300.0,231.6 300.0,230.9 300.0,230.3 300.0,229.6 300.0,229.0 300.0,228.4 300.0,227.7 300.0,227.1 300.0,226.4 300.0,225.8 300.0,225.1 300.0,224.5 300.0,223.9 300.0,223.2 300.0,222.6 300.0,221.9 300.0,221.3 300.0,220.6 300.0,220.0"/></g><path d="M456,156 h12 a14,14 0 0 1 0,28 h-12 z"/><path d="M286,58 v-12 a14,14 0 0 1 28,0 v12 z"/><rect x="420" y="20" width="110" height="40" rx="5"/><line x1="482" y1="156" x2="482" y2="62" marker-end="url(#arrHOM)"/><line x1="316" y1="40" x2="418" y2="40" marker-end="url(#arrHOM)"/><g fill="currentColor" stroke="none"><g font-style="italic"><text x="30" y="160">â (Ũ)</text><text x="312" y="312">b̂ (Ṽ)</text><text x="380" y="162">ĉ</text><text x="308" y="110">d̂</text><text x="282" y="270" text-anchor="end" font-size="15">delayed by τ</text></g><text x="475" y="200" text-anchor="middle" font-size="14">D<tspan font-size="10" dy="3">c</tspan></text><text x="270" y="40" text-anchor="end" font-size="14">D<tspan font-size="10" dy="3">d</tspan></text><text x="475" y="45" text-anchor="middle" font-size="14">coincidences</text><text x="300" y="140" text-anchor="start" font-size="13" dx="24">BS 50:50</text></g></svg></div>

### 7.1 Classical reference

Two distinguishable particles, each going to either output with probability $\frac12$: outcomes $(2,0), (0,2), (1,1), (1,1)$ are equally likely ⇒ coincidence probability $P_{cc} = \frac12$.

### 7.2 Coherent states

$$\ket{\psi}=\hat D_a(\alpha)\, \hat D_b(\beta) \ket{0}$$

Substitute $\hat a^\dagger = (\hat c^\dagger+\hat d^\dagger)/\sqrt2$ into the exponent:

$$\hat D_a(\alpha) = \exp\!\Big[\tfrac{\alpha}{\sqrt{2}}\big(\hat c^\dagger + \hat d^\dagger\big)-\tfrac{\alpha^*}{\sqrt{2}}\big(\hat c + \hat d\big)\Big] = \hat D_c\!\big(\tfrac{\alpha}{\sqrt2}\big)\hat D_d\!\big(\tfrac{\alpha}{\sqrt2}\big), \qquad \hat D_b(\beta) = \hat D_c\!\big(\tfrac{\beta}{\sqrt2}\big)\hat D_d\!\big(\tfrac{-\beta}{\sqrt2}\big)$$

Combining with §5.2 (the two phases $\pm\frac12\mathrm{Im}(\alpha\beta^*)$ cancel):

$$\ket{\psi}_{\rm out} = \left|\tfrac{\alpha+\beta}{\sqrt{2}}\right\rangle_c\left|\tfrac{\alpha-\beta}{\sqrt{2}}\right\rangle_d$$

If $\alpha = \beta$: $\ket{\sqrt{2} \alpha}_c \ket{0}_d$ — no coincidences, but only because of ordinary interference at a fixed relative phase.

**Random phases.** Take $\alpha= |\alpha|e^{i\theta_1}$, $\beta = |\alpha|e^{i \theta_2}$ with $\theta_{1,2}$ random in each run. Coincidence rate:

$$\langle \hat c^\dagger \hat c\, \hat d^\dagger \hat d \rangle = \left|\tfrac{\alpha+\beta}{\sqrt{2}}\right|^2 \left|\tfrac{\alpha - \beta}{\sqrt{2}}\right|^2 = \frac{1}{4} \left|\alpha^2 - \beta^2\right|^2 = \frac{1}{4} |\alpha|^4\left|1-e^{2i(\theta_2 - \theta_1)}\right|^2 = |\alpha|^4 \sin^2(\theta_2 - \theta_1)$$

Averaging over $\theta_2-\theta_1$: $\langle\, \cdot\,\rangle_\theta = |\alpha|^4/2$. Each detector receives on average $\langle \hat n_c\rangle_\theta = \langle \hat n_d\rangle_\theta = |\alpha|^2$, so the normalized coincidence rate is

$$\frac{\langle \hat n_c \hat n_d\rangle_\theta}{\langle \hat n_c\rangle_\theta\langle \hat n_d\rangle_\theta} = \frac{1}{2}$$

compared with $1$ for non-interfering (e.g. delayed) pulses. Classical light gives a dip of at most **50% visibility**; single photons give **100%** (coincidences vanish) ⇒ the HOM dip is a nonclassical effect.

### 7.3 Polarization and entangled inputs

Identical photons:

$$\hat a^\dagger \hat b^\dagger \ket{0} \rightarrow \frac{1}{2}\big(\hat c^\dagger \hat c^\dagger - \hat c^\dagger \hat d^\dagger + \hat d^\dagger \hat c^\dagger - \hat d^\dagger \hat d^\dagger\big)\ket{0} = \frac{1}{2}\big(\hat c^{\dagger2} - \hat d^{\dagger2}\big)\ket0$$

Now let each photon also carry polarization ($\hat a_H, \hat a_V, \dots$; the BS acts the same on both polarizations). Input the polarization-entangled states

$$\ket{\Psi^\pm} = \frac{1}{\sqrt{2}}\big(\ket{H}_a\ket{V}_b\pm\ket{V}_a\ket{H}_b\big) = \frac{1}{\sqrt2}\big(\hat a_H^\dagger \hat b_V^\dagger \pm \hat a_V^\dagger \hat b_H^\dagger\big)\ket0$$

Expanding as above:

$$\ket{\Psi^+} \rightarrow \frac{1}{\sqrt2}\big(\hat c_H^\dagger \hat c_V^\dagger - \hat d_H^\dagger \hat d_V^\dagger\big)\ket0 \qquad \text{(bunching, no coincidences)}$$

$$\ket{\Psi^-} \rightarrow \frac{1}{\sqrt2}\big(\hat c_V^\dagger \hat d_H^\dagger - \hat c_H^\dagger \hat d_V^\dagger\big)\ket0 \qquad \text{(always coincidences)}$$

The total state must be symmetric under exchange of the photons: a symmetric polarization part ($\Psi^+$) forces a symmetric spatial part (bunching), the antisymmetric singlet $\Psi^-$ forces an antisymmetric spatial part (antibunching). A coincidence therefore identifies $\ket{\Psi^-}$ — the basis of a linear-optics **Bell-state measurement**.

### 7.4 Partial distinguishability — the HOM dip

Photons in wavepacket modes with spectral amplitudes $\tilde U(\omega)$, $\tilde V(\omega)$, normalized $\int d\omega\, |\tilde U|^2 = \int d\omega\, |\tilde V|^2 = 1$:

$$\hat A^\dagger= \int d \omega\, \tilde U(\omega)\, \hat a^\dagger_\omega, \qquad \hat B^\dagger= \int d \omega\, \tilde V(\omega)\, \hat b^\dagger_\omega, \qquad [\hat a_\omega, \hat a^\dagger_{\omega'}] = \delta(\omega-\omega')$$

$$\hat A^\dagger \hat B^\dagger \ket{0} = \iint d \omega\, d\omega'\; \tilde U(\omega)\tilde V(\omega')\; \hat a^\dagger_{\omega} \hat b^\dagger_{\omega'} \ket{0}$$

A perfect (frequency-independent) BS acts on each frequency separately, $\hat a^\dagger_\omega \to \frac{1}{\sqrt2}(\hat c^\dagger_\omega+\hat d^\dagger_\omega)$, $\hat b^\dagger_\omega \to \frac{1}{\sqrt2}(\hat c^\dagger_\omega-\hat d^\dagger_\omega)$:

$$\hat A^\dagger \hat B^\dagger\ket{0} \to \frac12\iint d \omega\, d\omega'\; \tilde U(\omega)\tilde V(\omega') \big(\hat c^\dagger_\omega + \hat d^\dagger_\omega\big)\big(\hat c^\dagger_{\omega'}-\hat d^\dagger_{\omega'}\big)\ket{0}$$

**Coincidence part** (one photon in $c$, one in $d$):

$$\frac12\iint d \omega\, d\omega'\; \tilde U(\omega)\tilde V(\omega')\big(\hat d^\dagger_\omega \hat c^\dagger_{\omega'} - \hat c^\dagger_\omega \hat d^\dagger_{\omega'}\big)\ket{0} = \iint d \omega\, d\omega'\; f(\omega,\omega')\, \hat c^\dagger_\omega \hat d^\dagger_{\omega'}\ket0$$

where we relabeled $\omega\leftrightarrow\omega'$ in the first term:

$$f(\omega,\omega') = \frac12\Big[\tilde U(\omega')\tilde V(\omega) - \tilde U(\omega)\tilde V(\omega')\Big]$$

The states $\hat c^\dagger_\omega \hat d^\dagger_{\omega'}\ket0$ are orthonormal (δ-normalized), so

$$P_{cc} = \iint d \omega\, d\omega'\, |f(\omega,\omega')|^2 = \frac{1}{4}\iint d\omega\, d\omega' \Big(|\tilde U(\omega')|^2|\tilde V(\omega)|^2 + |\tilde U(\omega)|^2|\tilde V(\omega')|^2 - 2\,\mathrm{Re}\big[\tilde U(\omega')\tilde V(\omega)\tilde U^*(\omega)\tilde V^*(\omega')\big]\Big)$$

The first two terms give $1$ each; the cross term factorizes into $\left|\int d\omega\, \tilde U^*(\omega)\tilde V(\omega)\right|^2$:

> [!important] HOM coincidence probability
> $$P_{cc} = \frac{1}{4} \left(1+1-2\left| \int d \omega\, \tilde U^*(\omega)\, \tilde V(\omega)\right|^2\right) = \frac{1}{2} \left(1-\left|\int d \omega\, \tilde U^*(\omega)\, \tilde V(\omega)\right|^2\right)$$

The integral is the **overlap** of the two modes:
- identical modes (overlap 1): $P_{cc} = 0$ — perfect HOM;
- orthogonal modes (overlap 0): $P_{cc} = \frac12$ — the classical (distinguishable) result.

**Delay $\tau$.** Delaying photon $b$ multiplies its spectrum by a phase, $\tilde V(\omega) = \tilde U(\omega)\, e^{i\omega\tau}$. For a Gaussian spectrum $|\tilde U(\omega)|^2 = \frac{1}{\sqrt{2\pi}\sigma}e^{-(\omega-\omega_0)^2/2\sigma^2}$:

$$\int d\omega\, |\tilde U(\omega)|^2 e^{i\omega\tau} = e^{i\omega_0\tau}\,e^{-\sigma^2\tau^2/2} \quad\Rightarrow\quad P_{cc}(\tau) = \frac12\left(1-e^{-\sigma^2\tau^2}\right)$$

— the **HOM dip**, of width $\sim 1/\sigma$ (the coherence time).

### 7.5 Do the photons have to meet at the BS?

T. B. Pittman *et al.* (Shih group), [Can Two-Photon Interference be Considered the Interference of Two Photons?](https://journals.aps.org/prl/pdf/10.1103/PhysRevLett.77.1917), *Phys. Rev. Lett.* **77**, 1917 (1996).

![[Pasted image 20261015154718.png|center|450]]

In this experiment the two photons **never meet at the BS** — one passes long before the other — yet the dip is still observed. The interference is between the two *two-photon amplitudes* (both reflected, $r_x r_y$, vs both transmitted), not between two photons overlapping in time.

Timing of the two amplitudes, as noted in the lecture:
- $D_2$ clicks, then $D_1$ clicks after $\tau_{a,y}$;
- $D_1$ clicks $\tau_{1,x}$ after the start.

Setting $\tau_{1,x} = 2\tau_{a,y}$ makes both delays the same, so the two amplitudes give the same detection-time difference and become indistinguishable ⇒ they interfere and the coincidences vanish.

![[Pasted image 20261015155408.png|center|450]]

> [!todo] Unfinished in lecture notes
> $\Delta t = $ …


# Lecture 4

## 8. Photodetection and photon statistics

### 8.1 Recap: coherent states

$$\ket{\alpha}=e^{-|\alpha|^2/2}\sum_{n=0}^\infty \frac{\alpha^n}{\sqrt{n!}}\ket{n}, \qquad \bar n = |\alpha|^2$$

Overlap of coherent states (§2.2):

$$|\langle \alpha | \beta \rangle|^2=e^{-|\alpha-\beta|^2}$$

### 8.2 How a detector works

A photon is absorbed and produces an electrical signal:
- **Semiconductor** (photodiode, APD, CCD): the photon excites an electron from the valence band to the conduction band.
- **Atomic transitions**: the photon drives a transition (e.g. photoionization) and we register the energy absorbed.

### 8.3 Semiclassical model of counting

Light with intensity $\mathcal{I}$ falls on the detector for a total time $\Delta t$. Split it into $N$ short intervals $\delta t = \Delta t/N$:

<div style="text-align:center"><svg width="560" height="170" viewBox="0 0 560 170" xmlns="http://www.w3.org/2000/svg" fill="none" stroke="currentColor" stroke-width="1.6" font-family="Times New Roman, serif" font-size="17"><defs><marker id="arrDet" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="6" markerHeight="6" orient="auto"><path d="M0,0 L10,5 L0,10 z" fill="currentColor" stroke="none"/></marker></defs><rect x="60" y="60" width="440" height="30"/><line x1="87.5" y1="60" x2="87.5" y2="90" stroke-width="0.8" opacity="0.6"/><line x1="115.0" y1="60" x2="115.0" y2="90" stroke-width="0.8" opacity="0.6"/><line x1="142.5" y1="60" x2="142.5" y2="90" stroke-width="0.8" opacity="0.6"/><line x1="170.0" y1="60" x2="170.0" y2="90" stroke-width="0.8" opacity="0.6"/><line x1="197.5" y1="60" x2="197.5" y2="90" stroke-width="0.8" opacity="0.6"/><line x1="225.0" y1="60" x2="225.0" y2="90" stroke-width="0.8" opacity="0.6"/><line x1="252.5" y1="60" x2="252.5" y2="90" stroke-width="0.8" opacity="0.6"/><line x1="280.0" y1="60" x2="280.0" y2="90" stroke-width="0.8" opacity="0.6"/><line x1="307.5" y1="60" x2="307.5" y2="90" stroke-width="0.8" opacity="0.6"/><line x1="335.0" y1="60" x2="335.0" y2="90" stroke-width="0.8" opacity="0.6"/><line x1="362.5" y1="60" x2="362.5" y2="90" stroke-width="0.8" opacity="0.6"/><line x1="390.0" y1="60" x2="390.0" y2="90" stroke-width="0.8" opacity="0.6"/><line x1="417.5" y1="60" x2="417.5" y2="90" stroke-width="0.8" opacity="0.6"/><line x1="445.0" y1="60" x2="445.0" y2="90" stroke-width="0.8" opacity="0.6"/><line x1="472.5" y1="60" x2="472.5" y2="90" stroke-width="0.8" opacity="0.6"/><rect x="115.0" y="60" width="27.5" height="30" fill="currentColor" fill-opacity="0.18" stroke="none"/><line x1="128.8" y1="56" x2="128.8" y2="30" marker-end="url(#arrDet)"/><rect x="197.5" y="60" width="27.5" height="30" fill="currentColor" fill-opacity="0.18" stroke="none"/><line x1="211.2" y1="56" x2="211.2" y2="30" marker-end="url(#arrDet)"/><rect x="225.0" y="60" width="27.5" height="30" fill="currentColor" fill-opacity="0.18" stroke="none"/><line x1="238.8" y1="56" x2="238.8" y2="30" marker-end="url(#arrDet)"/><rect x="362.5" y="60" width="27.5" height="30" fill="currentColor" fill-opacity="0.18" stroke="none"/><line x1="376.2" y1="56" x2="376.2" y2="30" marker-end="url(#arrDet)"/><rect x="445.0" y="60" width="27.5" height="30" fill="currentColor" fill-opacity="0.18" stroke="none"/><line x1="458.8" y1="56" x2="458.8" y2="30" marker-end="url(#arrDet)"/><path d="M280.0,96 v6 h27.5 v-6" stroke-width="1.2"/><path d="M60,122 v6 H500 v-6" stroke-width="1.2"/><g fill="currentColor" stroke="none"><text x="293.8" y="118" text-anchor="middle" font-style="italic">δt</text><text x="280.0" y="148" text-anchor="middle"><tspan font-style="italic">Δt</tspan> = <tspan font-style="italic">N δt</tspan></text><text x="508" y="20" text-anchor="end" font-size="14">clicks (prob. <tspan font-style="italic">p</tspan> = <tspan font-style="italic">C𝓘 δt</tspan> each)</text></g></svg></div>

- $\Delta t$ — total measurement time
- $\delta t$ — single interval, short enough that at most one click happens in it

Probability of a click in one interval ($C$ includes the quantum efficiency and $1/\hbar\omega$):

$$p=C\, \mathcal{I}\, \delta t \ll 1$$

Mean number of counts in the whole window:

$$W= C\, \mathcal{I}\, \Delta t = Np \qquad\Rightarrow\qquad p=\frac{W}{N} \ll 1$$

**Probability of $n$ counts.** The intervals are independent, so $n$ is binomially distributed. For $N\to\infty$ at fixed $W$:

$$p_n = \binom{N}{n}\left(\frac{W}{N}\right)^n \left(1-\frac{W}{N}\right)^{N-n}$$

- $\binom{N}{n} = \frac{N(N-1)\cdots(N-n+1)}{n!} \to \frac{N^n}{n!}$, which cancels the $N^{-n}$;
- $\left(1-\frac{W}{N}\right)^{N-n} \to e^{-W}$.

$$p_n \;\to\; \frac{W^n}{n!}\,e^{-W}$$

A **Poisson** distribution: $\langle n\rangle = W$ and $\mathrm{Var}(n) = \langle n\rangle$ — the same statistics as a coherent state.

### 8.4 Fluctuating intensity: Mandel's formula

If the intensity fluctuates from shot to shot, $W$ is a random variable with distribution $P(W)$. Averaging the Poisson law over it gives **Mandel's formula**:

$$p_n = \int_0^\infty dW\, P(W)\, \frac{W^n}{n!}e^{-W}$$

**Variance.** For a Poisson distribution with mean $W$: $\sum_n n\, \frac{W^n}{n!}e^{-W} = W$ and $\sum_n n(n-1)\frac{W^n}{n!}e^{-W} = W^2$. Averaging over $P(W)$:

$$\langle n\rangle = \langle W\rangle, \qquad \langle n(n-1)\rangle = \langle W^2\rangle$$

$$\mathrm{Var}(n) = \langle n(n-1)\rangle + \langle n\rangle - \langle n\rangle^2 = \langle W^2\rangle + \langle W\rangle - \langle W\rangle^2$$

> [!important] Counting statistics of classical light
> $$\mathrm{Var}(n)=\langle n \rangle + \mathrm{Var}(W)$$
> Shot noise (Poisson) plus the classical intensity noise. Since $\mathrm{Var}(W)\ge 0$, any classical field gives $\mathrm{Var}(n) \ge \langle n\rangle$. **Sub-Poissonian** counts, $\mathrm{Var}(n) < \langle n\rangle$ (e.g. Fock states), cannot be explained classically.

**Example: thermal light.** The intensity of chaotic light has an exponential distribution, $P(W) = \frac{1}{\bar W}e^{-W/\bar W}$, with $\mathrm{Var}(W) = \bar W^2$. Then

$$p_n = \frac{1}{\bar W}\int_0^\infty dW\, \frac{W^n}{n!}e^{-W(1+1/\bar W)} = \frac{\bar W^{\,n}}{(1+\bar W)^{n+1}}, \qquad \mathrm{Var}(n) = \bar W + \bar W^2$$

— the Bose–Einstein distribution of §6, now obtained from classical intensity fluctuations.

### 8.5 Glauber–Sudarshan $P$-representation

Every state (pure or mixed) can be written as a "mixture" of coherent states:

$$\hat\rho = \int d^2 \alpha\; P(\alpha)\, \ket{\alpha} \bra{\alpha}$$

$P(\alpha)$ is the **Glauber–Sudarshan $P$-function**. Since $\mathrm{Tr}\,\hat\rho = 1$ and $\langle\alpha|\alpha\rangle = 1$:

$$\int d^2 \alpha\; P(\alpha)=1$$

$P$ is only a **quasi-probability**: it is real and normalized, but it can be negative or more singular than a δ-function (derivatives of $\delta^{2}(\alpha)$).

**Normally ordered moments** are averages over $P$, because $\hat a\ket\alpha = \alpha\ket\alpha$ and $\bra\alpha\hat a^\dagger = \alpha^*\bra\alpha$:

$$\big\langle (\hat a^\dagger)^k \hat a^l \big\rangle = \mathrm{Tr}\Big[\hat\rho\, (\hat a^\dagger)^k \hat a^l\Big] = \int d^2 \alpha\; P(\alpha)\, \bra{\alpha}(\hat a^\dagger)^k \hat a^l\ket{\alpha} = \int d^2 \alpha\; P(\alpha)\, \alpha^{*k} \alpha^l$$

**Examples.**
- Coherent state $\ket{\alpha_0}$: $P(\alpha) = \delta^{2}(\alpha-\alpha_0)$.
- Thermal state with mean photon number $N$ — a Gaussian mixture of coherent states, i.e. a coherent state "smeared out" around $\alpha=0$:

$$\hat\rho_{\rm th} = \sum_n \frac{N^n}{(1+N)^{n+1}} \ket{n} \bra{n}, \qquad P(\alpha)= \frac{1}{\pi N}\,e^{-|\alpha|^2/N}$$

*Check* — photon-number distribution, using $|\langle n|\alpha\rangle|^2 = e^{-|\alpha|^2}|\alpha|^{2n}/n!$, polar coordinates and $\int_0^\infty dr\, r^{2n+1}e^{-ar^2} = \frac{n!}{2a^{n+1}}$ (as in §2.2) with $a = 1+\frac1N$:

$$\bra{n} \hat\rho_{\rm th} \ket{n} = \int d^2 \alpha\; P(\alpha)\, |\langle n|\alpha\rangle|^2 = \frac{2\pi}{\pi N\, n!}\int_0^\infty dr\; r^{2n+1}\, e^{-r^2(1+1/N)} = \frac{1}{N}\frac{1}{(1+1/N)^{n+1}} = \frac{N^n}{(1+N)^{n+1}} \;\checkmark$$

This is exactly Mandel's formula (§8.4) with $W = |\alpha|^2$: a state with a genuine, nonnegative $P$ behaves like classical light with a fluctuating amplitude.

**Nonclassicality.** The photon-number variance is $\mathrm{Var}(n) = \langle (\hat a^\dagger \hat a)^2 \rangle - \langle \hat a^\dagger \hat a \rangle^2$. Normal ordering, $(\hat a^\dagger\hat a)^2 = \hat a^\dagger(\hat a^\dagger\hat a+1)\hat a = \hat a^{\dagger2}\hat a^2 + \hat a^\dagger\hat a$, gives $\langle \hat n^2\rangle - \langle\hat n\rangle = \langle \hat a^{\dagger2}\hat a^2\rangle = \int d^2\alpha\, P(\alpha)|\alpha|^4$, so

$$\mathrm{Var}(n) - \langle \hat n\rangle = \int d^2\alpha\; P(\alpha)\,\big(|\alpha|^2 - \langle\hat n\rangle\big)^2$$

If $P\ge 0$ this is $\ge 0$. Hence **sub-Poissonian** light requires a $P$-function that is negative or more singular than δ.

**Example — Fock state** $\ket{n}$: $\mathrm{Var}(n) = 0 < \langle\hat n\rangle = n$ for $n\ge1$ — sub-Poissonian, hence nonclassical: no nonnegative $P(\alpha)$ can describe it.

> [!important] Classical vs nonclassical states
> A state is **classical** if $P(\alpha)$ is a genuine probability distribution (nonnegative, no worse than a δ-function): coherent states and their mixtures, thermal light. Otherwise it is **nonclassical**: e.g. Fock states, whose $P$ contains derivatives of $\delta^{2}(\alpha)$, and squeezed states.

### 8.6 Photon-number generating function

$$G(x)=\sum_{n=0}^\infty p_n\, x^n = \mathrm{Tr}\big(\hat\rho\, x^{\hat{n}}\big)$$

All of the photon statistics can be read off from $G$:

| Quantity | From $G$ |
| --- | --- |
| Normalization | $G(1)=1$ |
| Probabilities | $p_n = \frac{1}{n!}G^{(n)}(0)$ |
| Mean | $G'(1)=\langle \hat n \rangle$ |
| Factorial moments | $G''(1)=\langle \hat n(\hat n-1) \rangle$, in general $G^{(k)}(1) = \langle \hat n(\hat n-1)\cdots(\hat n-k+1)\rangle$ |
| Variance | $\mathrm{Var}(n) = G''(1) + G'(1) - G'(1)^2$ |

**Coherent state.** Using the Fock expansion of $\ket\alpha$:

$$\bra{\alpha} x^{\hat n} \ket{\alpha}= e^{-|\alpha|^2}\sum_n \frac{|\alpha|^{2n}}{n!}x^n = e^{-(1-x)|\alpha|^2}$$

Hence for any state, via the $P$-representation,

$$G(x) = \int d^2\alpha\; P(\alpha)\, e^{-(1-x)|\alpha|^2}$$

**Examples.**

| State | $G(x)$ |
| --- | --- |
| Fock $\ket n$ | $x^n$ |
| Coherent $\ket\alpha$ | $e^{-(1-x)\vert\alpha\vert^2}$ |
| Thermal, mean $N$ | $\dfrac{1}{1+N(1-x)}$ |

(Thermal: $\sum_n \frac{N^n}{(1+N)^{n+1}}x^n = \frac{1}{1+N}\,\frac{1}{1-\frac{Nx}{1+N}} = \frac{1}{1+N-Nx}$.)

**Losses.** Model a loss (or a detector with efficiency $\eta$) as a beam splitter with transmission $\eta$ and vacuum in the other port; a coherent state is attenuated, $\ket{\alpha} \rightarrow \ket{\sqrt{\eta}\, \alpha}$. Then

$$G_{\rm out}(x) = \int d^2 \alpha\; P(\alpha)\, e^{-(1-x)\eta |\alpha|^2}=G(1- \eta + \eta x)$$

since $\eta(1-x) = 1-(1-\eta+\eta x)$. It holds for **every** state. Consequences:
- $\langle \hat n\rangle_{\rm out} = \eta\,\langle \hat n\rangle$;
- Fock state: $G_{\rm out} = (1-\eta+\eta x)^n$ → a **binomial** distribution, $p_k = \binom{n}{k}\eta^k(1-\eta)^{n-k}$ (each photon survives independently);
- coherent states stay coherent ($|\alpha|^2\to\eta|\alpha|^2$), thermal states stay thermal ($N\to\eta N$).

**Two modes.** For modes $a$, $b$:

$$G(x,y)= \mathrm{Tr}\big(\hat\rho\, x^{\hat n_a} y^{\hat n_b}\big) = \sum_{m,n} p_{mn}\, x^m y^n$$

Correlations follow from mixed derivatives:

$$\langle \hat n_a \hat n_b\rangle = \partial_x\partial_y G\big|_{x=y=1}, \qquad \mathrm{Cov}(n_a,n_b) = \Big(\partial_x\partial_y G - \partial_x G\, \partial_y G\Big)\Big|_{x=y=1}$$

- Product of coherent states $\ket{\alpha}\bra{\alpha} \otimes \ket{\beta}\bra{\beta}$: $G(x,y) = e^{-(1-x)|\alpha|^2}\,e^{-(1-y)|\beta|^2}$ factorizes ⇒ no correlations.
- HOM output $\frac{1}{\sqrt2}(\ket{2,0}-\ket{0,2})$: $G(x,y) = \frac12(x^2+y^2)$ ⇒ $\langle \hat n_a\hat n_b\rangle = 0$, no coincidences.

### 8.7 Second-order correlation function $g^{(2)}$

$$g^{(2)}(0) = \frac{\langle (\hat a^\dagger)^2 \hat a^2 \rangle}{\langle \hat a^\dagger \hat a \rangle^2}= \frac{G''(1)}{G'(1)^2}$$

It is measured in a **Hanbury Brown–Twiss** setup: the light is split on a 50:50 BS and the coincidence rate of the two detectors is normalized by the product of their single rates. Since $\langle(\hat a^\dagger)^2\hat a^2\rangle = \langle \hat n^2\rangle - \langle \hat n\rangle$:

$$g^{(2)}(0) - 1 = \frac{\mathrm{Var}(n) - \langle \hat n\rangle}{\langle \hat n\rangle^2}$$

so $g^{(2)}<1$ ⇔ sub-Poissonian statistics.

**Examples** (from the generating functions in §8.6):

| State | $G(x)$ | $g^{(2)}(0)$ | |
| --- | --- | --- | --- |
| Coherent | $e^{-(1-x)\vert\alpha\vert^2}$ | $1$ | uncorrelated (Poissonian) |
| Thermal | $\frac{1}{1+N(1-x)}$, $G'(1)=N$, $G''(1)=2N^2$ | $2$ | bunching |
| Fock $\ket n$ | $x^n$, $G'(1)=n$, $G''(1)=n(n-1)$ | $1-\frac{1}{n}$ | antibunching ($0$ for one photon) |

**Classical bound.** With the $P$-representation, $g^{(2)}(0) = \dfrac{\int P\,|\alpha|^4}{\left(\int P\,|\alpha|^2\right)^2}$. If $P\ge0$, Cauchy–Schwarz gives $\int P|\alpha|^4 \ge \left(\int P|\alpha|^2\right)^2$:

$$g^{(2)}(0) \geq 1 \quad\text{for any classical state}$$

(Strictly, "bunching/antibunching" refers to how $g^{(2)}(\tau)$ behaves with delay $\tau$; for a single mode $g^{(2)}(0)<1$ is the sub-Poissonian condition.)

### 8.8 Other witnesses of nonclassicality — quadrature squeezing

Quadrature $\hat X_\theta = \frac12\left(\hat a\, e^{-i\theta} + \hat a^\dagger e^{i\theta}\right)$, vacuum (and coherent-state) variance $\frac14$. By the argument of §8.5,

$$\Delta^2 X_\theta = \tfrac14 + \int d^2\alpha\; P(\alpha)\,\big(\mathrm{Re}(\alpha e^{-i\theta}) - \langle \hat X_\theta\rangle\big)^2 \;\geq\; \tfrac14 \quad \text{if } P\ge 0$$

so **squeezing**, $\Delta^2 X_\theta < \frac14$ for some $\theta$, is a nonclassicality witness (it catches squeezed states, which $g^{(2)}$ may miss).

**Balanced homodyne detection** measures $\hat X_\theta$: the signal $\hat a$ is mixed on a 50:50 BS with a strong coherent **local oscillator** (LO) $\ket\beta$, $\beta = |\beta|e^{i\theta}$, and the two photocurrents are subtracted.

<div style="text-align:center"><svg width="620" height="300" viewBox="0 0 620 300" xmlns="http://www.w3.org/2000/svg" fill="none" stroke="currentColor" stroke-width="1.6" font-family="Times New Roman, serif" font-size="18"><defs><marker id="arrBHD" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="7" markerHeight="7" orient="auto"><path d="M0,0 L10,5 L0,10 z" fill="currentColor" stroke="none"/></marker></defs><g transform="translate(40,0)"><line x1="60" y1="160" x2="222" y2="160" marker-end="url(#arrBHD)"/><line x1="240" y1="290" x2="240" y2="178" marker-end="url(#arrBHD)"/><rect x="222" y="142" width="36" height="36"/><line x1="222" y1="178" x2="258" y2="142" stroke-width="2.4"/><line x1="258" y1="160" x2="385" y2="160" marker-end="url(#arrBHD)"/><line x1="240" y1="142" x2="240" y2="62" marker-end="url(#arrBHD)"/><path d="M386,146 h12 a14,14 0 0 1 0,28 h-12 z"/><path d="M226,60 v-12 a14,14 0 0 1 28,0 v12 z"/><line x1="268" y1="34" x2="452" y2="34"/><line x1="412" y1="160" x2="470" y2="160"/><line x1="452" y1="34" x2="470" y2="34"/><line x1="470" y1="34" x2="470" y2="70" marker-end="url(#arrBHD)"/><circle cx="470" cy="88" r="16"/><line x1="470" y1="160" x2="470" y2="106" marker-end="url(#arrBHD)"/><line x1="486" y1="88" x2="530" y2="88" marker-end="url(#arrBHD)"/><g fill="currentColor" stroke="none"><g font-style="italic"><text x="54" y="152" text-anchor="end">signal â</text><text x="252" y="282">LO |β⟩, β = |β|e<tspan dy="-7" font-size="12">iθ</tspan></text><text x="320" y="152">ĉ</text><text x="250" y="110">d̂</text><text x="500" y="116" font-size="15">i₋ ∝ |β| X̂<tspan dy="5" font-size="11">θ</tspan></text></g><text x="470" y="95" text-anchor="middle" font-size="22">−</text><text x="400" y="196" text-anchor="middle" font-size="14">D<tspan dy="3" font-size="10">c</tspan></text><text x="214" y="30" text-anchor="end" font-size="14">D<tspan dy="3" font-size="10">d</tspan></text><text x="284" y="136" font-size="13">BS 50:50</text></g></g></svg></div>

With $\hat c = \frac{1}{\sqrt2}(\hat a+\hat b)$, $\hat d = \frac{1}{\sqrt2}(\hat a-\hat b)$:

$$\hat n_c - \hat n_d = \hat a^\dagger \hat b + \hat b^\dagger \hat a \;\approx\; \beta\,\hat a^\dagger + \beta^*\hat a = 2|\beta|\,\hat X_\theta$$

(replacing the strong LO mode $\hat b$ by the number $\beta$). The LO intensity amplifies the signal quadrature above the detector noise; the LO phase $\theta$ selects which quadrature is measured.

Summary of witnesses: $g^{(2)}(0)<1$ (sub-Poissonian), $\Delta^2 X_\theta<\frac14$ (squeezing), negative Wigner function (§8.9). Each is **sufficient** for nonclassicality, none is necessary.

### 8.9 Wigner function

> [!abstract] In one sentence
> The Wigner function $W(\alpha)$ is a phase-space "quasi-probability" distribution: it behaves like a joint probability for the two quadratures, except that it **can be negative** — and negativity is a signature of nonclassical light.

Notation: $\alpha = x + iy$, quadratures $\hat X_\theta = \frac12\big(\hat a\,e^{-i\theta} + \hat a^\dagger e^{i\theta}\big)$, so $\hat X_0 \leftrightarrow x$ and $\hat X_{\pi/2} \leftrightarrow y$; vacuum variance $\frac14$.

#### Definition

**(a) Fourier form.** Define the symmetrically ordered characteristic function and Fourier-transform it:

$$\chi_W(\beta) = \mathrm{Tr}\big[\hat\rho\, \hat D(\beta)\big] \qquad\Longrightarrow\qquad W(\alpha) = \frac{1}{\pi^2}\int d^2\beta\; e^{\alpha\beta^* - \alpha^*\beta}\, \chi_W(\beta)$$

**(b) Parity form** — usually the easiest to compute with:

$$W(\alpha) = \frac{2}{\pi}\,\Big\langle \hat D(\alpha)\,(-1)^{\hat n}\,\hat D^\dagger(\alpha)\Big\rangle$$

$W$ at the point $\alpha$ is the mean **parity** of the state displaced back to the origin.

**(c) Position form** — with $\hat x = (\hat a+\hat a^\dagger)/\sqrt2$, $\hat p = (\hat a-\hat a^\dagger)/i\sqrt2$, $[\hat x,\hat p]=i$:

$$W(x,p) = \frac{1}{2\pi}\int dy\; e^{ipy}\,\big\langle x-\tfrac{y}{2}\big|\hat\rho\big|x+\tfrac{y}{2}\big\rangle$$

(same function, rescaled: $\alpha = (x+ip)/\sqrt2$ and $W(x,p)\,dx\,dp = W(\alpha)\,d^2\alpha$).

---

#### Properties

**① Real and normalized**

$$W(\alpha)\in\mathbb R, \qquad \int d^2\alpha\; W(\alpha) = \chi_W(0) = 1$$

**② Marginals are true probability distributions**

$$\int dy\; W(x+iy) = \text{probability density of } \hat X_0 \text{ at } x$$

and the same holds along every rotated axis for $\hat X_\theta$.
→ Homodyne detection (§8.8) measures exactly these marginals. Measuring them for all $\theta$ and inverting (inverse Radon transform) reconstructs $W$: **homodyne tomography**.

**③ Symmetrically ordered moments**

$$\big\langle \{(\hat a^\dagger)^k \hat a^l\}_{\rm sym}\big\rangle = \int d^2\alpha\; W(\alpha)\,\alpha^{*k}\alpha^l$$

e.g. $\langle \hat X_\theta\rangle$ and $\langle \hat X_\theta^2\rangle$ are ordinary averages over $W$.

**④ Bounded**

$$|W(\alpha)| \le \frac{2}{\pi}$$

because the parity operator has eigenvalues $\pm1$ (parity form). Unlike $P$, $W$ is never singular.

**⑤ Overlaps**

$$\mathrm{Tr}(\hat\rho_1\hat\rho_2) = \pi\int d^2\alpha\; W_1(\alpha)\,W_2(\alpha)$$

For orthogonal states the left side is $0$, so at least one of $W_1, W_2$ must be negative somewhere — negativity is unavoidable in quantum mechanics.

**⑥ Can be negative** → $W$ is a quasi-probability, not a probability.

---

#### Relation to $P$ and $Q$

Both $W$ and $Q$ are Gaussian smoothings of $P$:

$$W(\alpha) = \frac{2}{\pi}\int d^2\beta\; P(\beta)\, e^{-2|\alpha-\beta|^2}, \qquad Q(\alpha) = \frac{1}{\pi}\langle\alpha|\hat\rho|\alpha\rangle = \frac{1}{\pi}\int d^2\beta\; P(\beta)\, e^{-|\alpha-\beta|^2}$$

| | $P$ (Glauber–Sudarshan) | $W$ (Wigner) | $Q$ (Husimi) |
| --- | --- | --- | --- |
| Operator ordering | normal | symmetric | antinormal |
| Smoothing of $P$ | — | half the vacuum noise | full vacuum noise |
| Can be negative? | yes | yes | **no**, $Q\ge0$ |
| Can be singular? | yes (δ and worse) | no, $\vert W\vert\le\frac{2}{\pi}$ | no |
| Marginals = measured quadrature distributions | no | **yes** | no (extra noise) |

> [!important] Consequence
> $P\ge0 \;\Rightarrow\; W\ge0$. So a **negative Wigner function proves nonclassicality**.

---

#### Examples

| State | $W(\alpha)$, $\;\alpha = x+iy$ | Negative? |
| --- | --- | --- |
| Coherent $\ket{\alpha_0}$ (vacuum: $\alpha_0=0$) | $\frac{2}{\pi}\,e^{-2\vert\alpha-\alpha_0\vert^2}$ | no |
| Thermal, mean $N$ | $\frac{2}{\pi(2N+1)}\,e^{-2\vert\alpha\vert^2/(2N+1)}$ | no |
| Squeezed vacuum $\hat S(r)\ket0$ | $\frac{2}{\pi}\,e^{-2e^{2r}x^2 - 2e^{-2r}y^2}$ | no |
| Fock $\ket n$ | $\frac{2}{\pi}(-1)^n\, e^{-2\vert\alpha\vert^2}\, L_n\!\big(4\vert\alpha\vert^2\big)$ | yes, for $n\ge1$ |
| Cat $\ket{\alpha_0}+\ket{-\alpha_0}$ ($\alpha_0$ real, normalized) | $\frac{2}{\pi\mathcal N'}\Big[e^{-2\vert\alpha-\alpha_0\vert^2} + e^{-2\vert\alpha+\alpha_0\vert^2} + 2e^{-2\vert\alpha\vert^2}\cos(4\alpha_0 y)\Big]$ | yes (fringes) |

Notation: $L_n$ = Laguerre polynomial ($L_0 = 1$, $L_1(u) = 1-u$); $\hat S(r) = e^{\frac{r}{2}(\hat a^2 - \hat a^{\dagger 2})}$ squeezes $\hat X_0$ to variance $e^{-2r}/4$; $\mathcal N' = 2\big(1+e^{-2\alpha_0^2}\big)$.

![[QO - Wigner functions.png|center|700]]

**How to read the examples:**
- **Coherent** — a Gaussian blob of vacuum width, displaced to $\alpha_0$.
- **Thermal** — the same blob, broadened by the factor $2N+1$. (Derivation: convolve $P = \frac{1}{\pi N}e^{-|\alpha|^2/N}$ with $\frac{2}{\pi}e^{-2|\alpha|^2}$; the variances per quadrature add, $\frac{N}{2}+\frac14 = \frac{2N+1}{4}$.)
- **Squeezed** — an ellipse: narrower than vacuum in $x$, wider in $y$. Still positive.
- **Fock** — rings. At the origin, by the parity form, $W(0) = \frac{2}{\pi}\bra n(-1)^{\hat n}\ket n = \frac{2}{\pi}(-1)^n$; for $\ket1$ this is the minimum allowed value $-\frac{2}{\pi}$.
- **Cat** — two coherent blobs plus interference fringes between them; the fringes are what make it quantum.

> [!important] Hudson's theorem
> A **pure** state has $W\ge0$ **iff** it is Gaussian (coherent or squeezed). So for pure states, Wigner negativity ⇔ non-Gaussianity.
> Squeezed states are nonclassical ($P$ too singular) yet have $W\ge0$: negativity of $W$ is **sufficient, not necessary**, for nonclassicality.

---

# Lecture 5

## 9. Glauber's theory of photodetection and correlation functions

### 9.1 What a detector measures — click probabilities

A photodetector does not measure "the field"; it produces **clicks**. The experimentally accessible quantities are click probabilities (per unit time):

| Quantity | Meaning |
| --- | --- |
| $P_1(\mathbf r,t)\,\delta t$ | probability of a click at $\mathbf r$ in $[t, t+\delta t]$ |
| $P_2(\mathbf r,t;\mathbf r',t')\,\delta t\,\delta t'$ | joint probability of clicks at $(\mathbf r,t)$ and at $(\mathbf r',t')$ |
| $P_n(\mathbf r_1,t_1;\dots;\mathbf r_n,t_n)$ | $n$-fold coincidences |

Goal: express them through the state of the field.

### 9.2 Detector–field interaction

Model the detector as an atom (or semiconductor) in its ground state $\ket g$ that is excited by the light into one of a **continuum** of states $\ket{\epsilon}$ (e.g. photoionization, or the conduction band). The electron is then detected → click.

Electric-dipole coupling:

$$\hat H' = -\hat{\mathbf d}\cdot\mathbf E(\mathbf r,t)$$

For a two-level atom this is $\hat H' = -d\,E\,\hat\sigma_x$, with the dipole matrix element $d = d_{01} = \bra{1}\hat d\ket{0}$ (projected on the field polarization).

<div style="text-align:center"><svg width="590" height="250" viewBox="0 0 590 250" xmlns="http://www.w3.org/2000/svg" fill="none" stroke="currentColor" stroke-width="1.6" font-family="Times New Roman, serif" font-size="18"><defs><marker id="arrLev" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="7" markerHeight="7" orient="auto"><path d="M0,0 L10,5 L0,10 z" fill="currentColor" stroke="none"/></marker></defs><rect x="170" y="30" width="200" height="90" fill="currentColor" fill-opacity="0.08" stroke-width="1"/><line x1="170" y1="34" x2="370" y2="34" stroke-width="0.7" opacity="0.45"/><line x1="170" y1="40" x2="370" y2="40" stroke-width="0.7" opacity="0.45"/><line x1="170" y1="46" x2="370" y2="46" stroke-width="0.7" opacity="0.45"/><line x1="170" y1="52" x2="370" y2="52" stroke-width="0.7" opacity="0.45"/><line x1="170" y1="58" x2="370" y2="58" stroke-width="0.7" opacity="0.45"/><line x1="170" y1="64" x2="370" y2="64" stroke-width="0.7" opacity="0.45"/><line x1="170" y1="70" x2="370" y2="70" stroke-width="0.7" opacity="0.45"/><line x1="170" y1="76" x2="370" y2="76" stroke-width="0.7" opacity="0.45"/><line x1="170" y1="82" x2="370" y2="82" stroke-width="0.7" opacity="0.45"/><line x1="170" y1="88" x2="370" y2="88" stroke-width="0.7" opacity="0.45"/><line x1="170" y1="94" x2="370" y2="94" stroke-width="0.7" opacity="0.45"/><line x1="170" y1="100" x2="370" y2="100" stroke-width="0.7" opacity="0.45"/><line x1="170" y1="106" x2="370" y2="106" stroke-width="0.7" opacity="0.45"/><line x1="170" y1="112" x2="370" y2="112" stroke-width="0.7" opacity="0.45"/><line x1="170" y1="70" x2="370" y2="70" stroke-width="2.2"/><line x1="170" y1="215" x2="370" y2="215" stroke-width="2.6"/><line x1="270" y1="213" x2="270" y2="74" marker-end="url(#arrLev)"/><polyline points="40,150.0 41,152.6 42,154.7 43,155.9 44,155.8 45,154.7 46,152.6 47,149.9 48,147.3 49,145.3 50,144.1 51,144.2 52,145.4 53,147.5 54,150.1 55,152.7 56,154.8 57,155.9 58,155.8 59,154.6 60,152.5 61,149.8 62,147.3 63,145.2 64,144.1 65,144.2 66,145.4 67,147.6 68,150.2 69,152.8 70,154.8 71,155.9 72,155.8 73,154.5 74,152.4 75,149.7 76,147.2 77,145.1 78,144.1 79,144.2 80,145.5 81,147.7 82,150.3 83,152.9 84,154.9 85,155.9 86,155.8 87,154.5 88,152.3 89,149.6 90,147.1 91,145.1 92,144.1 93,144.2 94,145.6 95,147.8 96,150.4 97,153.0 98,154.9 99,155.9 100,155.7 101,154.4 102,152.2 103,149.5 104,147.0 105,145.0 106,144.1 107,144.3 108,145.6 109,147.9 110,150.5 111,153.1 112,155.0 113,155.9 114,155.7 115,154.3 116,152.1 117,149.4 118,146.9 119,145.0 120,144.0 121,144.3 122,145.7 123,147.9 124,150.6 125,153.1 126,155.1 127,156.0 128,155.7 129,154.3 130,152.0 131,149.3 132,146.8 133,144.9 134,144.0 135,144.3 136,145.8 137,148.0 138,150.7 139,153.2 140,155.1 141,156.0 142,155.6 143,154.2 144,151.9 145,149.2 146,146.7 147,144.9 148,144.0 149,144.4 150,145.8 151,148.1 152,150.8 153,153.3 154,155.2 155,156.0 156,155.6 157,154.1 158,151.8 159,149.1 160,146.6"/><line x1="160" y1="150" x2="262" y2="150" stroke-dasharray="3 3" marker-end="url(#arrLev)" opacity="0.7"/><line x1="380" y1="70" x2="460" y2="70" marker-end="url(#arrLev)"/><g fill="currentColor" stroke="none"><g font-style="italic"><text x="160" y="221" text-anchor="end">|g⟩, ε<tspan dy="4" font-size="12">g</tspan></text><text x="160" y="76" text-anchor="end" font-size="16">ε = ε<tspan dy="4" font-size="11">g</tspan><tspan dy="-4"> + ħω</tspan></text><text x="278" y="160">ħω</text><text x="70" y="140" font-size="15">photon</text></g><text x="270" y="22" text-anchor="middle" font-size="15">continuum |ε⟩, density ρ(ε)</text><text x="466" y="66" font-size="14">electron</text><text x="466" y="84" font-size="14">detected → click</text><text x="278" y="196" font-size="14" font-style="italic">d<tspan dy="4" font-size="10">εg</tspan></text></g></svg></div>

*Ground state $\ket g$ coupled by $d_{\epsilon g}$ to a continuum of excited states $\ket\epsilon$; a photon $\hbar\omega$ drives the transition to $\epsilon \approx \epsilon_g+\hbar\omega$, and the excited electron gives a click.*

### 9.3 Semiclassical derivation: classical field, quantum detector

Detector state $\ket{\psi(t)}$, initially $\ket{\psi(t_0)} = \ket g$. In the **interaction picture**, $\hat H_I(t) = e^{i\hat H_0 t/\hbar}\hat H' e^{-i\hat H_0 t/\hbar}$ and

$$i \hbar\, \partial_t \ket{\psi_I(t)} = \hat H_I(t) \ket{\psi_I(t)}$$

**First-order perturbation theory:**

$$\ket{\psi_I(t+\Delta t)} \approx \ket{g} + \frac{1}{i \hbar} \int_t^{t+\Delta t} dt'\, \hat H_I(t') \ket{g}$$

so the amplitude to end in the excited state $\ket\epsilon$ is

$$\langle\epsilon|\psi_I(t+\Delta t) \rangle = \frac{1}{i \hbar} \int_t^{t+\Delta t} dt'\, \bra{\epsilon} \hat H_I(t') \ket{g} = -\frac{1}{i\hbar}\int_t^{t+\Delta t} dt'\; d_{\epsilon g}\,E(t')\, e^{i(\epsilon-\epsilon_g)t'/\hbar}$$

**Rotating-wave approximation.** Write $E(t) = E^{(+)}e^{-i\omega t} + E^{(-)}e^{i\omega t}$. Only $E^{(+)}$ (absorption) oscillates slowly when $\epsilon - \epsilon_g \approx \hbar\omega$; the $E^{(-)}$ term averages out. Then

$$|\langle \epsilon| \psi_I(t+\Delta t) \rangle|^2= |d_{\epsilon g}|^2\, |E^{(+)}|^2\; \left|\frac{1}{\hbar} \int_t^{t+\Delta t} dt'\, e^{i(\epsilon - \epsilon_g -\hbar \omega)t'/\hbar}\right|^2$$

**Sum over the continuum** of final states with density $\rho(\epsilon)$. For $\Delta t$ long compared with $\hbar/(\text{width of the continuum})$,

$$\left|\frac{1}{\hbar}\int_t^{t+\Delta t} dt'\, e^{i\Delta E\, t'/\hbar}\right|^2 = \frac{\sin^2(\Delta E\,\Delta t/2\hbar)}{(\Delta E/2)^2} \;\longrightarrow\; \frac{2\pi}{\hbar}\,\Delta t\;\delta(\Delta E)$$

![[QO - transition amplitude.png|center|650]]

*The time integral (here without the $1/\hbar^2$ prefactor, as in §9.4) for three interaction times: the peak grows as $\Delta t^2$ and narrows as $1/\Delta t$, so the area grows only linearly, $2\pi\hbar\,\Delta t$. For long $\Delta t$ it becomes $2\pi\hbar\,\Delta t\,\delta(\Delta E)$, which is why the click **rate** is constant.*

(Fermi's golden rule). The excitation probability grows linearly in $\Delta t$, so the **click rate** is

$$P_1 = \frac{1}{\Delta t}\int d\epsilon\,\rho(\epsilon)\,|\langle \epsilon| \psi_I(t+\Delta t) \rangle|^2 = \underbrace{\frac{2\pi}{\hbar}\,\rho(\epsilon_g+\hbar\omega)\,|d|^2}_{s\;=\;\text{sensitivity}}\;|E^{(+)}(\mathbf r,t)|^2$$

> [!important] Semiclassical result
> $P_1(\mathbf r,t) = s\,|E^{(+)}(\mathbf r,t)|^2 \propto$ intensity. The detector responds to the **positive-frequency** part of the field.

### 9.4 Quantum field

Now the field is an operator:

$$\hat H'=-\hat{\mathbf d} \cdot \hat{\mathbf E}$$

We propagate $\ket{\psi_I(t)}$ of detector + field, starting from $\ket{\psi_I(t_0)}=\ket{g,\psi_0}$, where $\ket{\psi_0}$ is the field state.

We look for the amplitude to find the detector excited, $\ket\epsilon$, and the field in **some** state $\ket\Phi$:

$$\langle \epsilon, \Phi | \psi_I (t_0 +\Delta t) \rangle$$

but we don't measure $\Phi$ → at the end we sum over it.

**1st-order perturbation theory:**

$$\langle \epsilon,\Phi | \psi_I \rangle \approx \frac{1}{i \hbar} \int dt'\, \bra{\epsilon, \Phi} \hat H_I(t') \ket{g ,\psi_0} = -\frac{1}{i \hbar} \int dt'\, e^{i (\epsilon - \epsilon_g) t'/\hbar}\, d_{\epsilon g}\, \bra{\Phi} \hat{E}(t') \ket{\psi_0}$$

> [!note] Comment
> Same as §9.3, but the field amplitude $E(t')$ is replaced by the matrix element $\bra\Phi\hat E(t')\ket{\psi_0}$ between field states.

Split $\hat E = \hat E^{(+)} + \hat E^{(-)}$, with

$$\hat E^{(+)}(t') \propto \int d\omega\; e^{-i \omega t'}\, \hat a(\omega), \qquad \hat E^{(-)} = \big(\hat E^{(+)}\big)^\dagger$$

**RWA.** Each frequency component gives a time integral

$$\int dt'\; e^{i (\Delta \mp \hbar \omega)t'/\hbar}, \qquad \Delta \equiv \epsilon - \epsilon_g$$

- $\hat E^{(-)}$ (sign $+$): $\Delta + \hbar\omega$ is large, the integrand oscillates quickly and integrates to zero.
- $\hat E^{(+)}$ (sign $-$): $\Delta - \hbar \omega \approx 0$ (resonance) survives.

If $\ket{\psi_0}$ is close to monochromatic (centred at $\omega_0$):

$$\langle \epsilon,\Phi | \psi_I \rangle \approx \frac{i}{\hbar}\, d_{\epsilon g}\, \bra{\Phi} \hat E^{(+)} \ket{\psi_0} \int dt'\; e^{i(\Delta - \hbar \omega_0)t'/\hbar}$$

and the squared time integral gives, exactly as in §9.3,

$$\left|\int dt'\; e^{i(\Delta - \hbar \omega_0)t'/\hbar}\right|^2 = \frac{\sin^2\!\big((\Delta -\hbar \omega_0)\,\Delta t/2\hbar\big)}{\big((\Delta-\hbar\omega_0)/2\hbar\big)^2} \;\longrightarrow\; 2\pi\hbar\,\Delta t\;\delta(\Delta-\hbar\omega_0)$$

**Total click probability** — sum over the unobserved $\Phi$ (and the continuum of $\epsilon$), using $\sum_\Phi \ket\Phi\bra\Phi = \hat 1$:

$$P\propto \sum_{\epsilon,\Phi} |\langle \epsilon, \Phi | \psi_I \rangle|^2 \;\propto\; \sum_\Phi \bra{\psi_0}\hat E^{(-)} \ket{\Phi} \bra{\Phi}\hat E^{(+)} \ket{\psi_0}= \bra{\psi_0}\hat E^{(-)}\hat E^{(+)} \ket{\psi_0} \;\propto\; \langle \hat a^\dagger \hat a \rangle$$

For a mixed state: $P_1(\mathbf r,t) = s\;\mathrm{Tr}\big[\hat\rho\;\hat E^{(-)}(\mathbf r,t)\,\hat E^{(+)}(\mathbf r,t)\big]$.

> [!note] Comment
> - Kinda the same as classically: $|E^{(+)}|^2 \to \langle\hat E^{(-)}\hat E^{(+)}\rangle$.
> - The sign is $+$: with $\hat E^{(+)} \propto i\hat a$ and $\hat E^{(-)} \propto -i\hat a^\dagger$, the product is $\propto +\hat a^\dagger\hat a \ge 0$.
> - **Normal order** ($\hat E^{(-)}$ on the left) means the vacuum gives **no clicks**, $\hat E^{(+)}\ket0 = 0$: vacuum fluctuations are not detected.

This is the **first-order correlation function** at a single point, $P_1 \propto G^{(1)}(x,x)$, with $x \equiv (\mathbf r,t)$ and

$$G^{(1)}(x,x') = \big\langle \hat E^{(-)}(x)\,\hat E^{(+)}(x')\big\rangle$$

### 9.5 Two detectors and higher orders

With two detectors each absorbing one photon (time- and normal-ordered):

$$P_{2}(x_1,x_2) \propto G^{(2)}(x_1,x_2) = \Big\langle \hat E^{(-)}(x_1)\,\hat E^{(-)}(x_2)\,\hat E^{(+)}(x_2)\,\hat E^{(+)}(x_1)\Big\rangle$$

This is different from the classical result

$$P_2 \propto \big\langle I(x_1)\, I(x_2)\big\rangle$$

(averaged over the classical fluctuations of the field).

> [!note] Comment
> - For a **coherent state**, $\hat E^{(+)}\ket\alpha = \mathcal E(\alpha)\ket\alpha$, so $G^{(2)}$ factorizes into $I(x_1)I(x_2)$ exactly.
> - More generally, the quantum and classical results agree whenever the $P$-function is a genuine probability distribution (§8.5). The classical formula is then just the average over $P$.

**The quantum case can differ.** One photon:

$$P_2\big(\ket{\psi}=\hat a^\dagger \ket{0}\big)=0$$

because $\hat E^{(+)}\hat E^{(+)}$ must annihilate two photons and there is only one. Classically, $\langle I_1 I_2\rangle > 0$ for any nonzero intensity.

**General $n$:**

$$P_n \propto G^{(n)}(x_1,\dots,x_n) = \Big\langle \hat E^{(-)}(x_1)\cdots\hat E^{(-)}(x_n)\,\hat E^{(+)}(x_n)\cdots\hat E^{(+)}(x_1)\Big\rangle$$

These are **Glauber's correlation functions**.

### 9.6 Normalized correlation functions

$$g^{(1)}(x_1,x_2) = \frac{G^{(1)}(x_1,x_2)}{\sqrt{G^{(1)}(x_1,x_1)\,G^{(1)}(x_2,x_2)}}$$

— first-order coherence; $|g^{(1)}|$ is the **fringe visibility** in an interferometer.

$$g^{(2)}(\tau) = \frac{\langle \hat E^{(-)}(t)\,\hat E^{(-)}(t+\tau)\,\hat E^{(+)}(t+\tau)\,\hat E^{(+)}(t)\rangle}{\langle \hat E^{(-)}(t)\hat E^{(+)}(t)\rangle^2}$$

— intensity correlations (HBT). For a single mode at $\tau=0$ it reduces to $\langle(\hat a^\dagger)^2\hat a^2\rangle/\langle\hat a^\dagger\hat a\rangle^2$ of §8.7. Bunching: $g^{(2)}(0) > g^{(2)}(\tau)$; antibunching: $g^{(2)}(0) < g^{(2)}(\tau)$.

### 9.7 Question: the $g^{(2)}$ bound vs the Wigner bound — which is more general?

We can show a bound separating classical from nonclassical light from $g^{(2)}$ ($g^{(2)}(0)\ge1$, §8.7). How is it related to the bound from the Wigner function ($W\ge0$, §8.9)? Which one is more general?

> [!note] Comment — answer
> **Neither is more general.** Both follow from the same statement, "$P(\alpha)$ is a genuine probability distribution" (§8.5), but they test different things and neither implies the other:
>
> | State | $g^{(2)}(0)$ | $W<0$ somewhere? | Caught by |
> | --- | --- | --- | --- |
> | Fock $\ket1$ | $0$ | yes | both |
> | Mixture $p\ket1\bra1 + (1-p)\ket0\bra0$, $p<\frac12$ | $0$ | no ($W(0)=\frac{2}{\pi}(1-2p)>0$; minimum at origin) | only $g^{(2)}$ |
> | Even cat $\ket{\alpha_0}+\ket{-\alpha_0}$ | $1/\tanh^2\vert\alpha_0\vert^2 > 1$ | yes (fringes) | only $W$ |
> | Squeezed vacuum | $3 + 1/\sinh^2 r > 1$ | no (Gaussian) | neither: needs the squeezing witness (§8.8) |
>
> The general criterion is the one on $P$; $g^{(2)}<1$, $W<0$ and $\Delta^2X_\theta<\frac14$ are separate, sufficient-only tests of it.

---

# Lecture 6

> [!info] Midterm
> The midterm was announced in this lecture for **26 November** (26.XI). The course-information box at the top of the chapter still says 03.12; one of the two dates is out of date.

## 10. Optical coherence: first- and second-order correlation functions

In Lecture 5 we showed that an ideal photodetector placed at the space-time point $x=(\mathbf r,t)$ clicks with a probability per unit time proportional to $\langle \hat E^{(-)}(x)\hat E^{(+)}(x)\rangle$, and that a pair of detectors records coincidences at a rate proportional to $\langle \hat E^{(-)}(x_1)\hat E^{(-)}(x_2)\hat E^{(+)}(x_2)\hat E^{(+)}(x_1)\rangle$. In this lecture we study these quantities systematically. The first-order function describes interference of amplitudes, as in Young's experiment; the second-order function describes correlations of intensities, as in the experiment of Hanbury Brown and Twiss. The comparison of the two leads to a sharp criterion separating classical from nonclassical light. Throughout, $\hat E^{(\pm)}$ denotes the positive- and negative-frequency parts of one polarization component of the field, and averages are taken in the state $\hat\rho$ of the field.

### 10.1 The first-order correlation function

The **first-order correlation function** of the field is defined as

$$G^{(1)}(x,x') = \mathrm{Tr}\big[\hat\rho\,\hat E^{(-)}(x)\,\hat E^{(+)}(x')\big] = \big\langle \hat E^{(-)}(x)\,\hat E^{(+)}(x')\big\rangle. \tag{10.1}$$

Its diagonal value $G^{(1)}(x,x)$ is, up to the detector sensitivity, the intensity registered by a detector at $x$. The off-diagonal values $x\neq x'$ are not measured by a single detector; we shall see in §10.2 that they determine the visibility of interference fringes. The definition generalizes to order $n$:

$$G^{(n)}(x_1,\dots,x_n;\,x_{n+1},\dots,x_{2n}) = \big\langle \hat E^{(-)}(x_1)\cdots\hat E^{(-)}(x_n)\,\hat E^{(+)}(x_{n+1})\cdots\hat E^{(+)}(x_{2n})\big\rangle, \tag{10.2}$$

and for $x_{n+k}=x_{n+1-k}$ it reduces to the $n$-fold coincidence rate of Lecture 5. Since the absolute scale of $G^{(1)}$ depends on the intensity, it is convenient to introduce the **normalized first-order correlation function**, or degree of first-order coherence,

$$g^{(1)}(x,x') = \frac{G^{(1)}(x,x')}{\sqrt{G^{(1)}(x,x)\,G^{(1)}(x',x')}}. \tag{10.3}$$

**Vacuum.** For $\hat\rho=\ket0\bra0$ every correlation function vanishes, because $\hat E^{(+)}(x')\ket0 = 0$ for every $x'$. This is the formal statement that a detector of the type described in Lecture 5 does not respond to vacuum fluctuations.

**Coherent states.** Let the field be in a multimode coherent state $\ket{\{\alpha_l\}} = \bigotimes_l\ket{\alpha_l}$. Using the mode expansion of §1.5, $\hat E^{(+)}(\mathbf r,t) = \frac{i}{2}\sum_l \mathcal E_l\,\mathbf u_l(\mathbf r)\,\hat a_l\,e^{-i\Omega_l t}$, and the eigenvalue equation $\hat a_l\ket{\alpha_l}=\alpha_l\ket{\alpha_l}$, we obtain

$$\hat E^{(+)}(x)\,\ket{\{\alpha_l\}} = \mathcal E(x)\,\ket{\{\alpha_l\}}, \qquad \mathcal E(x) = \frac{i}{2}\sum_l \mathcal E_l\,\mathbf u_l(\mathbf r)\,\alpha_l\,e^{-i\Omega_l t}. \tag{10.4}$$

The coherent state is an eigenstate of the positive-frequency field operator at every point, and the eigenvalue $\mathcal E(x)$ is the classical field with the same mode amplitudes. Taking the adjoint of (10.4) gives $\bra{\{\alpha_l\}}\hat E^{(-)}(x) = \mathcal E^*(x)\bra{\{\alpha_l\}}$, and therefore

$$G^{(1)}(x,x') = \mathcal E^*(x)\,\mathcal E(x'), \qquad |g^{(1)}(x,x')| = \frac{|\mathcal E^*(x)\,\mathcal E(x')|}{\sqrt{|\mathcal E(x)|^2\,|\mathcal E(x')|^2}} = 1. \tag{10.5}$$

The correlation function of a coherent state factorizes into a product of a function of $x$ and a function of $x'$. Following Glauber, a field whose $G^{(1)}$ factorizes in this way, or equivalently whose $|g^{(1)}|$ equals one for all pairs of points, is called **first-order coherent**. The analogous factorization of $G^{(n)}$ defines coherence of order $n$; by (10.4), coherent states are coherent to all orders.

**General properties.** Two properties of $G^{(1)}$ hold for every state. First, $G^{(1)}(x',x) = G^{(1)}(x,x')^*$, which follows from $\hat E^{(-)} = (\hat E^{(+)})^\dagger$ and the hermiticity of $\hat\rho$. Second, $G^{(1)}$ is a positive semidefinite kernel. To prove it, choose arbitrary points $x_1,\dots,x_N$ and complex numbers $\lambda_1,\dots,\lambda_N$, and define the operator $\hat A = \sum_j \lambda_j\,\hat E^{(+)}(x_j)$. The operator $\hat A^\dagger\hat A$ is positive and so is $\hat\rho$, hence $\mathrm{Tr}(\hat\rho\,\hat A^\dagger\hat A)\ge0$. Writing this out,

$$\mathrm{Tr}\big(\hat\rho\,\hat A^\dagger\hat A\big) = \sum_{i,j}\lambda_i^*\lambda_j\,G^{(1)}(x_i,x_j) \;\ge\; 0 \quad\text{for all } \lambda_j. \tag{10.6}$$

Thus the $N\times N$ matrix $G^{(1)}(x_i,x_j)$ is positive semidefinite. For $N=1$ this gives $G^{(1)}(x,x)\ge0$, i.e. intensities are non-negative. For $N=2$ the determinant of the $2\times2$ matrix must be non-negative, which is the Cauchy–Schwarz inequality

$$G^{(1)}(x_1,x_1)\,G^{(1)}(x_2,x_2) \;\ge\; \big|G^{(1)}(x_1,x_2)\big|^2, \qquad\text{hence}\qquad 0\le|g^{(1)}(x_1,x_2)|\le1. \tag{10.7}$$

The coherent state saturates the upper bound. The physical meaning of the intermediate values is clarified by the double-slit experiment.

### 10.2 Young's double-slit experiment

<div style="text-align:center"><svg width="560" height="280" viewBox="0 0 560 280" xmlns="http://www.w3.org/2000/svg" fill="none" stroke="currentColor" stroke-width="1.6" font-family="Times New Roman, serif" font-size="17"><defs><marker id="arrY" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="7" markerHeight="7" orient="auto"><path d="M0,0 L10,5 L0,10 z" fill="currentColor" stroke="none"/></marker></defs><path d="M40,140 q8,-10 16,0 t16,0 t16,0" /><line x1="90" y1="140" x2="140" y2="140" marker-end="url(#arrY)"/><line x1="160" y1="20" x2="160" y2="100"/><line x1="160" y1="112" x2="160" y2="168"/><line x1="160" y1="180" x2="160" y2="250"/><line x1="440" y1="30" x2="440" y2="250" stroke-width="2.2"/><line x1="160" y1="106" x2="440" y2="90" stroke-dasharray="5 4"/><line x1="160" y1="174" x2="440" y2="90" stroke-dasharray="5 4"/><circle cx="440" cy="90" r="3.5" fill="currentColor"/><polyline points="470.3,40.0 470.0,41.2 470.0,42.5 470.3,43.8 470.9,45.0 471.8,46.2 473.0,47.5 474.5,48.8 476.1,50.0 478.0,51.2 479.9,52.5 482.0,53.8 483.9,55.0 485.8,56.2 487.5,57.5 489.0,58.8 490.1,60.0 490.9,61.2 491.3,62.5 491.2,63.8 490.7,65.0 489.8,66.2 488.4,67.5 486.8,68.8 484.8,70.0 482.6,71.2 480.3,72.5 478.0,73.8 475.9,75.0 473.9,76.2 472.2,77.5 471.0,78.8 470.2,80.0 470.0,81.2 470.4,82.5 471.4,83.8 472.9,85.0 475.1,86.2 477.7,87.5 480.8,88.8 484.1,90.0 487.7,91.2 491.3,92.5 494.9,93.8 498.2,95.0 501.2,96.2 503.7,97.5 505.6,98.8 506.8,100.0 507.3,101.2 507.1,102.5 506.1,103.8 504.3,105.0 502.0,106.2 499.0,107.5 495.6,108.8 491.9,110.0 488.0,111.2 484.2,112.5 480.5,113.8 477.2,115.0 474.4,116.2 472.2,117.5 470.7,118.8 470.0,120.0 470.2,121.2 471.3,122.5 473.1,123.8 475.7,125.0 479.0,126.2 482.9,127.5 487.1,128.8 491.6,130.0 496.1,131.2 500.4,132.5 504.5,133.8 508.1,135.0 511.0,136.2 513.2,137.5 514.5,138.8 515.0,140.0 514.5,141.2 513.2,142.5 511.0,143.8 508.1,145.0 504.5,146.2 500.4,147.5 496.1,148.8 491.6,150.0 487.1,151.2 482.9,152.5 479.0,153.8 475.7,155.0 473.1,156.2 471.3,157.5 470.2,158.8 470.0,160.0 470.7,161.2 472.2,162.5 474.4,163.8 477.2,165.0 480.5,166.2 484.2,167.5 488.0,168.8 491.9,170.0 495.6,171.2 499.0,172.5 502.0,173.8 504.3,175.0 506.1,176.2 507.1,177.5 507.3,178.8 506.8,180.0 505.6,181.2 503.7,182.5 501.2,183.8 498.2,185.0 494.9,186.2 491.3,187.5 487.7,188.8 484.1,190.0 480.8,191.2 477.7,192.5 475.1,193.8 472.9,195.0 471.4,196.2 470.4,197.5 470.0,198.8 470.2,200.0 471.0,201.2 472.2,202.5 473.9,203.8 475.9,205.0 478.0,206.2 480.3,207.5 482.6,208.8 484.8,210.0 486.8,211.2 488.4,212.5 489.8,213.8 490.7,215.0 491.2,216.2 491.3,217.5 490.9,218.8 490.1,220.0 489.0,221.2 487.5,222.5 485.8,223.8 483.9,225.0 482.0,226.2 479.9,227.5 478.0,228.8 476.1,230.0 474.5,231.2 473.0,232.5 471.8,233.8 470.9,235.0 470.3,236.2 470.0,237.5 470.0,238.8 470.3,240.0" stroke-width="1.4"/><g fill="currentColor" stroke="none" font-style="italic"><text x="150" y="104" text-anchor="end">r₁</text><text x="150" y="180" text-anchor="end">r₂</text><text x="300" y="88" text-anchor="middle">s₁</text><text x="300" y="150" text-anchor="middle">s₂</text><text x="448" y="80">r</text><text x="500" y="42" font-size="14" font-style="normal">I(r)</text><text x="440" y="270" text-anchor="middle" font-size="14" font-style="normal">screen</text><text x="160" y="16" text-anchor="middle" font-size="14" font-style="normal">two slits</text></g></svg></div>

Light illuminates an opaque screen with two small apertures at positions $\mathbf r_1$ and $\mathbf r_2$, and is detected at the point $\mathbf r$ of a distant observation screen. Let $s_i = |\mathbf r-\mathbf r_i|$ be the distances from the apertures to the point of observation. Each aperture acts as a source of a spherical wave, and by the superposition principle the positive-frequency field at $\mathbf r$ is the sum of the two contributions,

$$\hat E^{(+)}(\mathbf r,t) = \frac{1}{s_1}\,\hat E^{(+)}\!\Big(\mathbf r_1,\,t-\frac{s_1}{c}\Big) + \frac{1}{s_2}\,\hat E^{(+)}\!\Big(\mathbf r_2,\,t-\frac{s_2}{c}\Big), \tag{10.8}$$

where an overall geometrical factor has been absorbed into the field. The propagation phase $e^{iks_i}$ does not appear explicitly in (10.8), because it is already contained in the retarded time: for a quasi-monochromatic field of carrier frequency $\omega=ck$ we have $\hat E^{(+)}(\mathbf r_i,t-s_i/c) = \hat{\mathcal E}_i(t-s_i/c)\,e^{-i\omega t}\,e^{iks_i}$ with a slowly varying envelope $\hat{\mathcal E}_i$. In the far field the distances differ by much less than their magnitude, $s_1\approx s_2\approx R$, so we may set $1/s_1\approx1/s_2\approx1/R$ in the amplitudes. The difference $s_1-s_2$ must not be neglected in the phase, because it is comparable to the wavelength. With the shorthand $x_i = (\mathbf r_i,\,t-s_i/c)$ the field at the screen becomes

$$\hat E^{(+)}(\mathbf r,t) = \frac{1}{R}\Big[\hat E^{(+)}(x_1)+\hat E^{(+)}(x_2)\Big]. \tag{10.9}$$

The intensity recorded at $\mathbf r$ is $I(\mathbf r,t)=\eta\,\langle\hat E^{(-)}(\mathbf r,t)\hat E^{(+)}(\mathbf r,t)\rangle$, where $\eta$ contains the detector sensitivity and the factor $1/R^2$. Inserting (10.9) produces four terms:

$$I(\mathbf r,t) = \eta\Big[G^{(1)}(x_1,x_1)+G^{(1)}(x_2,x_2)+G^{(1)}(x_1,x_2)+G^{(1)}(x_2,x_1)\Big] = \eta\Big[G^{(1)}(x_1,x_1)+G^{(1)}(x_2,x_2)+2\,\mathrm{Re}\,G^{(1)}(x_1,x_2)\Big]. \tag{10.10}$$

The first two terms are the intensities that each aperture would produce alone; the third is the **interference term**. Writing $G^{(1)}(x_1,x_2) = |G^{(1)}(x_1,x_2)|\,e^{i\psi}$, equivalently $g^{(1)}(x_1,x_2) = |g^{(1)}(x_1,x_2)|\,e^{i\psi}$, we obtain

$$I(\mathbf r,t) = \eta\Big[G^{(1)}(x_1,x_1)+G^{(1)}(x_2,x_2)+2\,\big|G^{(1)}(x_1,x_2)\big|\cos\psi\Big]. \tag{10.11}$$

By the remark below (10.8), the phase $\psi$ contains the term $k(s_2-s_1)$ and therefore varies rapidly as the point $\mathbf r$ moves across the screen, while the moduli vary slowly. The intensity oscillates between $I_{\max,\min}=\eta\big[G^{(1)}(x_1,x_1)+G^{(1)}(x_2,x_2)\pm2|G^{(1)}(x_1,x_2)|\big]$, and the **visibility** of the fringes is

$$\mathcal V = \frac{I_{\max}-I_{\min}}{I_{\max}+I_{\min}} = \frac{2\,|G^{(1)}(x_1,x_2)|}{G^{(1)}(x_1,x_1)+G^{(1)}(x_2,x_2)} = \frac{2\sqrt{G^{(1)}(x_1,x_1)\,G^{(1)}(x_2,x_2)}}{G^{(1)}(x_1,x_1)+G^{(1)}(x_2,x_2)}\;\big|g^{(1)}(x_1,x_2)\big|. \tag{10.12}$$

The prefactor is the ratio of the geometric to the arithmetic mean of the two intensities and does not exceed one; it equals one when the apertures are equally illuminated. In that case $\mathcal V = |g^{(1)}(x_1,x_2)|$: **the modulus of the normalized first-order correlation function is the fringe visibility**, and its phase $\psi$ determines the position of the fringes.

**Two-mode description.** To compare specific quantum states it is convenient to describe the light emerging from the two apertures by two modes with annihilation operators $\hat a_1$ and $\hat a_2$. For quasi-monochromatic light, (10.9) becomes $\hat E^{(+)}(\mathbf r,t)\propto\big(\hat a_1 e^{iks_1}+\hat a_2 e^{iks_2}\big)e^{-i\omega t}$, and (10.10) becomes

$$\frac{I(\mathbf r)}{\eta} = \langle\hat a_1^\dagger\hat a_1\rangle + \langle\hat a_2^\dagger\hat a_2\rangle + 2\,\big|\langle\hat a_1^\dagger\hat a_2\rangle\big|\cos\psi, \qquad \psi = k(s_2-s_1)+\arg\langle\hat a_1^\dagger\hat a_2\rangle, \tag{10.13}$$

where the cross term has been obtained from $\langle\hat a_1^\dagger\hat a_2\rangle e^{ik(s_2-s_1)}$ and its complex conjugate. The sign convention for $\psi$ is immaterial, since only $\cos\psi$ enters. We now evaluate (10.13) for three states.

*(a) Coherent light in both apertures,* $\ket{\alpha_1}\ket{\alpha_2}$. The expectation values are $\langle\hat a_i^\dagger\hat a_i\rangle = |\alpha_i|^2$ and $\langle\hat a_1^\dagger\hat a_2\rangle = \alpha_1^*\alpha_2$. For equal amplitudes $\alpha_1=\alpha_2=\alpha$,

$$\frac{I}{\eta} = 2|\alpha|^2\,(1+\cos\psi), \qquad \mathcal V = 1. \tag{10.14}$$

The interference is perfect, and the result coincides with that of classical wave optics for two mutually coherent waves of equal amplitude.

*(b) A single photon.* Let a single photon be prepared in the superposition mode $\hat b = (\hat a_1+\hat a_2)/\sqrt2$, i.e. in the state $\ket\psi = \hat b^\dagger\ket0 = \frac{1}{\sqrt2}\big(\ket{1}_1\ket{0}_2+\ket{0}_1\ket{1}_2\big)$. The annihilation operators act as $\hat a_1\ket\psi = \hat a_2\ket\psi = \frac{1}{\sqrt2}\ket{0}_1\ket{0}_2$, from which $\langle\hat a_1^\dagger\hat a_1\rangle = \langle\hat a_2^\dagger\hat a_2\rangle = \|\hat a_i\ket\psi\|^2 = \frac12$ and $\langle\hat a_1^\dagger\hat a_2\rangle = (\hat a_1\ket\psi)^\dagger(\hat a_2\ket\psi) = \frac12$. Therefore

$$\frac{I}{\eta} = \frac12+\frac12+\cos\psi = 1+\cos\psi, \qquad \mathcal V = 1. \tag{10.15}$$

The visibility is again unity, although the field contains exactly one photon. Here $I(\mathbf r)$ is the probability per unit time that the detector at $\mathbf r$ clicks; in a single run the photon produces one click at a random point, and the fringe pattern (10.15) emerges as the histogram of many runs. In Dirac's words, each photon interferes only with itself: the interfering objects are the two probability amplitudes for the photon to have passed through either aperture.

*(c) Independent Fock states,* $\ket{n_1}_1\ket{n_2}_2$. Now $\langle\hat a_1^\dagger\hat a_2\rangle = \bra{n_1}\hat a_1^\dagger\ket{n_1}\,\bra{n_2}\hat a_2\ket{n_2} = 0$, since $\hat a$ and $\hat a^\dagger$ change the photon number. Hence

$$\frac{I}{\eta} = n_1+n_2, \qquad G^{(1)}(x_1,x_2)=0, \qquad \mathcal V=0. \tag{10.16}$$

A product of two Fock states produces no interference at all, regardless of the photon numbers. A Fock state has a completely undetermined phase, so there is no fixed phase relation between the two apertures. Note that two coherent states with independent random phases give the same ensemble average, but for a different reason: each single realization shows fringes, and only the average over the random relative phase washes them out.

### 10.3 The second-order correlation function

First-order coherence is insensitive to a large class of differences between states: a stable laser and a filtered thermal source of the same spectrum have the same $g^{(1)}$. The two are distinguished by intensity correlations. For a stationary field observed at a single point, the second-order correlation function at time delay $\tau$ is

$$G^{(2)}(\tau) = \big\langle\hat E^{(-)}(t)\,\hat E^{(-)}(t+\tau)\,\hat E^{(+)}(t+\tau)\,\hat E^{(+)}(t)\big\rangle, \tag{10.17}$$

which by Lecture 5 is proportional to the probability density of detecting one photon at time $t$ and another at time $t+\tau$. Its normalized form is

$$g^{(2)}(\tau) = \frac{G^{(2)}(\tau)}{\big[G^{(1)}(0)\big]^2}, \qquad G^{(1)}(0) = \big\langle\hat E^{(-)}(t)\,\hat E^{(+)}(t)\big\rangle, \tag{10.18}$$

where stationarity makes $G^{(1)}(0)$, the mean intensity, independent of $t$. The value $g^{(2)}(\tau)=1$ means that the two detection events are statistically independent; $g^{(2)}>1$ means that a detection at $t$ increases the probability of another detection at $t+\tau$; $g^{(2)}<1$ means that it decreases it.

For a coherent state, (10.4) gives $G^{(2)}(\tau) = |\mathcal E(t)|^2\,|\mathcal E(t+\tau)|^2$. For a single-mode stationary field $|\mathcal E|$ is constant, so $g^{(2)}(\tau)=1$ for all $\tau$, together with $|g^{(1)}|=1$. Photodetections in coherent light are uncorrelated, which is the time-domain counterpart of the Poisson statistics found in Lecture 4.

### 10.4 Classical fields: statistical mixtures of coherent states

Consider next a field that is classical in the sense of §8.5: an ensemble of coherent states in which the complex amplitude $\mathcal E$ occurs with a probability density $P(\mathcal E)$,

$$\hat\rho = \int d^2\mathcal E\;P(\mathcal E)\,\ket{\mathcal E}\bra{\mathcal E}, \qquad P(\mathcal E)\ge0, \qquad \int d^2\mathcal E\;P(\mathcal E) = 1. \tag{10.19}$$

This describes, for example, a classical light source whose amplitude fluctuates from shot to shot. The intensity in each realization is $\sum_f|\langle f|\hat E^{(+)}|\mathcal E\rangle|^2 = \langle\hat E^{(-)}\hat E^{(+)}\rangle = |\mathcal E|^2$. Because the operators in $G^{(1)}$ and $G^{(2)}$ are normally ordered, each coherent state in the mixture contributes the corresponding product of eigenvalues, and at $\tau=0$

$$g^{(2)}(0) = \frac{\int d^2\mathcal E\;P(\mathcal E)\,\mathcal E^*\mathcal E^*\mathcal E\,\mathcal E}{\Big(\int d^2\mathcal E\;P(\mathcal E)\,\mathcal E^*\mathcal E\Big)^2} = \frac{\langle|\mathcal E|^4\rangle}{\langle|\mathcal E|^2\rangle^2}, \tag{10.20}$$

where $\langle\cdot\rangle$ now denotes the average over $P$. The numerator can be rewritten by completing the square. Since

$$\Big\langle\big(|\mathcal E|^2-\langle|\mathcal E|^2\rangle\big)^2\Big\rangle = \langle|\mathcal E|^4\rangle - 2\,\langle|\mathcal E|^2\rangle^2 + \langle|\mathcal E|^2\rangle^2 = \langle|\mathcal E|^4\rangle - \langle|\mathcal E|^2\rangle^2, \tag{10.21}$$

we may write $\langle|\mathcal E|^4\rangle = \langle|\mathcal E|^2\rangle^2 + \langle(|\mathcal E|^2-\langle|\mathcal E|^2\rangle)^2\rangle$, and therefore

$$g^{(2)}(0) = 1 + \frac{\int d^2\mathcal E\;P(\mathcal E)\,\big(|\mathcal E|^2-\langle|\mathcal E|^2\rangle\big)^2}{\langle|\mathcal E|^2\rangle^2} = 1+\frac{\mathrm{Var}(I)}{\langle I\rangle^2} \;\ge\; 1. \tag{10.22}$$

The inequality follows because the integrand is a square multiplied by the non-negative weight $P$. **For every classical field $g^{(2)}(0)\ge1$**, with equality only if the intensity does not fluctuate.

A remark on the single-mode form is in order. With $\hat E^{(+)}\propto\hat a$ the numerator of $g^{(2)}(0)$ is $\langle\hat a^\dagger\hat a^\dagger\hat a\hat a\rangle$, and the commutator $\hat a\hat a^\dagger = \hat a^\dagger\hat a+1$ gives the operator identity $\langle\hat a^\dagger\hat a^\dagger\hat a\hat a\rangle = \langle\hat a^\dagger(\hat a\hat a^\dagger-1)\hat a\rangle = \langle\hat n^2\rangle-\langle\hat n\rangle$. For the mixture (10.19) the normally ordered moment equals $\langle|\alpha|^4\rangle$ directly, whereas $\langle\hat n^2\rangle = \langle|\alpha|^4\rangle+\langle|\alpha|^2\rangle$; the term $-\langle\hat n\rangle$ is cancelled exactly by the shot noise contained in $\langle\hat n^2\rangle$. It would therefore be incorrect to identify $\langle\hat n^2\rangle$ with $\langle|\alpha|^4\rangle$.

The physical content of (10.22) is **photon bunching**. A photodetector clicks with a probability proportional to the instantaneous intensity. When the intensity fluctuates, the clicks are concentrated in the intervals of high intensity, and the detection of one photon makes it more probable that the light is momentarily bright and hence that a second photon follows. In the figure below the upper trace shows the intensity of chaotic light and the clicks it produces; the lower trace shows the same mean rate for light of constant intensity.

![[QO - bunching.png|center|620]]

**Nonclassical light.** For a single photon, $\hat a\hat a\ket1 = 0$, hence $\bra1\hat a^\dagger\hat a^\dagger\hat a\hat a\ket1 = 0$ and $g^{(2)}(0)=0$. No mixture of the form (10.19) can produce this value. More generally, a value $g^{(2)}(0)<1$ cannot be written as (10.22) with a non-negative $P$ and therefore signals a **nonclassical** state. In terms of the photon-number distribution of a single mode, using $\Delta^2n = \langle\hat n^2\rangle-\bar n^2$ with $\bar n = \langle\hat n\rangle$,

$$g^{(2)}(0) = \frac{\langle\hat a^\dagger\hat a^\dagger\hat a\hat a\rangle}{\langle\hat a^\dagger\hat a\rangle^2} = \frac{\langle\hat n^2\rangle-\langle\hat n\rangle}{\langle\hat n\rangle^2} = \frac{\Delta^2n+\bar n^2-\bar n}{\bar n^2} = 1+\frac{\Delta^2n-\bar n}{\bar n^2}. \tag{10.23}$$

Light with Poissonian statistics, $\Delta^2n=\bar n$, has $g^{(2)}(0)=1$; sub-Poissonian light, $\Delta^2n<\bar n$, has $g^{(2)}(0)<1$; super-Poissonian light has $g^{(2)}(0)>1$. For a Fock state $\ket n$ the variance vanishes, and (10.23) gives

$$g^{(2)}(0) = 1+\frac{0-n}{n^2} = 1-\frac1n, \tag{10.24}$$

which equals zero for a single photon and approaches the coherent value as $n\to\infty$.

### 10.5 Chaotic light, the Siegert relation and the Hanbury Brown–Twiss experiment

Light emitted by many independent atoms, such as thermal light or the light of a discharge lamp, is called **chaotic**. Its field is a sum of a large number of statistically independent contributions with random phases. By the central limit theorem the complex amplitude $\mathcal E(t)$ is then a complex Gaussian random process with zero mean. The random phases also imply circular symmetry: averages containing unequal numbers of $\mathcal E$ and $\mathcal E^*$, such as $\langle\mathcal E(t)\,\mathcal E(t')\rangle$, vanish. For such a process all higher moments are determined by the second moments through the Gaussian moment theorem,

$$\big\langle\mathcal E^*_1\,\mathcal E^*_2\,\mathcal E_3\,\mathcal E_4\big\rangle = \big\langle\mathcal E^*_1\mathcal E_3\big\rangle\big\langle\mathcal E^*_2\mathcal E_4\big\rangle + \big\langle\mathcal E^*_1\mathcal E_4\big\rangle\big\langle\mathcal E^*_2\mathcal E_3\big\rangle, \tag{10.25}$$

where $\mathcal E_j$ is shorthand for $\mathcal E(t_j)$. We apply (10.25) to the numerator of $g^{(2)}(\tau)$, with $t_1=t_4=t$ and $t_2=t_3=t+\tau$. Using stationarity, $\langle\mathcal E^*(t)\mathcal E(t)\rangle = \langle\mathcal E^*(t+\tau)\mathcal E(t+\tau)\rangle = G^{(1)}(0)$ and $\langle\mathcal E^*(t)\mathcal E(t+\tau)\rangle = G^{(1)}(\tau)$, we find

$$G^{(2)}(\tau) = \big\langle\mathcal E^*(t)\mathcal E(t+\tau)\big\rangle\big\langle\mathcal E^*(t+\tau)\mathcal E(t)\big\rangle + \big\langle\mathcal E^*(t)\mathcal E(t)\big\rangle\big\langle\mathcal E^*(t+\tau)\mathcal E(t+\tau)\big\rangle = |G^{(1)}(\tau)|^2+\big[G^{(1)}(0)\big]^2. \tag{10.26}$$

Dividing by $[G^{(1)}(0)]^2$ gives the **Siegert relation**

$$g^{(2)}(\tau) = 1+\big|g^{(1)}(\tau)\big|^2 \qquad\text{(chaotic light)}. \tag{10.27}$$

At $\tau=0$ we have $g^{(1)}(0)=1$, hence $g^{(2)}(0)=2$, in agreement with the thermal value obtained from the photon-number distribution in §8.7. For delays long compared with the coherence time $\tau_c$, the field loses memory of its phase, $g^{(1)}(\tau)\to0$, and $g^{(2)}(\tau)\to1$. For example, a collision-broadened line with a Lorentzian spectrum has $g^{(1)}(\tau) = e^{-i\omega_0\tau-|\tau|/\tau_c}$ and therefore $g^{(2)}(\tau) = 1+e^{-2|\tau|/\tau_c}$. The width of the bunching peak measures the coherence time of the light. It must be stressed that (10.27) holds only for chaotic light: a stable laser has $|g^{(1)}(\tau)|=1$ and $g^{(2)}(\tau)=1$, not 2.

The limit $g^{(2)}(\tau)\to1$ for $\tau\to\infty$ is more general than (10.27). For any stationary field whose fluctuations have a finite correlation time, intensities at very distant times are statistically independent, so $\langle I(t)I(t+\tau)\rangle\to\langle I\rangle^2$. A second general property of classical fields follows from the Cauchy–Schwarz inequality and stationarity, $\langle I(t)I(t+\tau)\rangle \le \sqrt{\langle I(t)^2\rangle\langle I(t+\tau)^2\rangle} = \langle I^2\rangle$, which gives

$$g^{(2)}(\tau)\le g^{(2)}(0) \qquad\text{(classical fields)}. \tag{10.28}$$

The light of a single emitter, for instance one atom or one quantum dot, violates (10.28). After emitting a photon the emitter is in its ground state and must be re-excited before it can emit again, so $g^{(2)}(0)=0$ and $g^{(2)}(\tau)$ rises towards one. This is **photon antibunching**, a nonclassical effect.

![[QO - g2 of tau.png|center|620]]

**The Hanbury Brown–Twiss experiment.** The function $g^{(2)}(\tau)$ is measured by dividing the light on a 50:50 beam splitter between two detectors and recording the rate of coincidences as a function of an electronic delay $\tau$ inserted in one of the channels.

<div style="text-align:center"><svg width="650" height="230" viewBox="0 0 650 230" xmlns="http://www.w3.org/2000/svg" fill="none" stroke="currentColor" stroke-width="1.6" font-family="Times New Roman, serif" font-size="17"><defs><marker id="arrH" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="7" markerHeight="7" orient="auto"><path d="M0,0 L10,5 L0,10 z" fill="currentColor" stroke="none"/></marker></defs><path d="M30,120 q7,-9 14,0 t14,0 t14,0 t14,0"/><line x1="90" y1="120" x2="202" y2="120" marker-end="url(#arrH)"/><rect x="202" y="102" width="36" height="36"/><line x1="202" y1="138" x2="238" y2="102" stroke-width="2.4"/><line x1="238" y1="120" x2="330" y2="120" marker-end="url(#arrH)"/><path d="M332,106 h12 a14,14 0 0 1 0,28 h-12 z"/><line x1="220" y1="138" x2="220" y2="188" marker-end="url(#arrH)"/><path d="M206,190 h28 v12 a14,14 0 0 1 -28,0 z"/><line x1="360" y1="120" x2="400" y2="120"/><rect x="400" y="106" width="56" height="28" rx="4"/><line x1="456" y1="120" x2="490" y2="120" marker-end="url(#arrH)"/><line x1="248" y1="210" x2="512" y2="210"/><line x1="512" y1="210" x2="512" y2="140" marker-end="url(#arrH)"/><circle cx="512" cy="120" r="18"/><g fill="currentColor" stroke="none"><text x="512" y="127" text-anchor="middle" font-size="20">×</text><text x="428" y="126" text-anchor="middle" font-size="15" font-style="italic">delay τ</text><text x="345" y="100" text-anchor="middle" font-size="14">D₁</text><text x="190" y="205" text-anchor="end" font-size="14">D₂</text><text x="252" y="96" font-size="13">BS 50:50</text><text x="60" y="104" text-anchor="middle" font-size="14" font-style="italic">light</text><text x="538" y="112" font-size="14" font-style="italic">⟨I₁(t+τ) I₂(t)⟩</text><text x="538" y="134" font-size="13">coincidences</text></g></svg></div>

Two detectors are used, rather than one, because a real detector cannot register two photons arriving within its dead time. The beam splitter does not alter $g^{(2)}$. Indeed, let the input mode $\hat a$ be mixed with a vacuum mode $\hat v$, so that the outputs are $\hat c = (\hat a+\hat v)/\sqrt2$ and $\hat d = (\hat a-\hat v)/\sqrt2$. In the normally ordered averages $\langle\hat c^\dagger\hat d^\dagger\hat d\hat c\rangle$ and $\langle\hat c^\dagger\hat c\rangle$ every term containing $\hat v$ or $\hat v^\dagger$ vanishes, since $\hat v$ acts on the vacuum on the right and $\hat v^\dagger$ on the vacuum on the left. Consequently $\langle\hat c^\dagger\hat d^\dagger\hat d\hat c\rangle = \frac14\langle\hat a^{\dagger2}\hat a^2\rangle$ and $\langle\hat c^\dagger\hat c\rangle = \langle\hat d^\dagger\hat d\rangle = \frac12\langle\hat a^\dagger\hat a\rangle$, so the normalized coincidence rate equals the $g^{(2)}(0)$ of the input. Hanbury Brown and Twiss (1956) first observed the bunching of chaotic light in this arrangement with a mercury lamp. In the same year they applied the method to starlight, correlating the intensities recorded by two separated telescopes: the spatial version of (10.27), $g^{(2)}(\mathbf r_1,\mathbf r_2) = 1+|g^{(1)}(\mathbf r_1,\mathbf r_2)|^2$, decays as the separation of the telescopes exceeds roughly $\lambda/\theta$, which yielded the angular diameter $\theta$ of Sirius. Because only intensities are correlated, this **intensity interferometry** is insensitive to the random phase distortions introduced by atmospheric turbulence, which limit amplitude (Michelson) interferometers.

### 10.6 Realistic detectors with efficiency $\eta<1$

A real detector registers each incident photon only with probability $\eta<1$. It may be modelled as an ideal detector preceded by a beam splitter of transmission $\eta$, whose reflected output is lost. Since each photon is transmitted independently, the probability of $k$ clicks when $n$ photons arrive is binomial, and for a state $\ket\psi$ the probability of $k$ clicks is

$$P_k = \sum_{n=k}^{\infty}\binom{n}{k}\eta^k(1-\eta)^{n-k}\,\big|\langle n|\psi\rangle\big|^2 = \langle\psi|\hat\Pi_k|\psi\rangle, \qquad \hat\Pi_k = \sum_{n=k}^{\infty}\binom{n}{k}\eta^k(1-\eta)^{n-k}\,\ket n\bra n. \tag{10.29}$$

The operators $\hat\Pi_k$ are positive, and by the binomial theorem $\sum_k\hat\Pi_k = \sum_n\big[\eta+(1-\eta)\big]^n\ket n\bra n = \hat 1$; they form the positive operator-valued measure that describes the inefficient detector. For a mixed state $|\langle n|\psi\rangle|^2$ is replaced by $p_n = \bra n\hat\rho\ket n$.

**Coherent state.** For $\ket\psi=\ket\alpha$ we have $|\langle n|\alpha\rangle|^2 = e^{-|\alpha|^2}|\alpha|^{2n}/n!$, so

$$P_k = \sum_{n=k}^\infty e^{-|\alpha|^2}\frac{|\alpha|^{2n}}{n!}\,\frac{n!}{k!\,(n-k)!}\,\eta^k(1-\eta)^{n-k}.$$

The factor $n!$ cancels. Changing the summation index to $m=n-k$ and writing $|\alpha|^{2n} = |\alpha|^{2k}|\alpha|^{2m}$, we obtain

$$P_k = e^{-|\alpha|^2}\frac{\big(\eta|\alpha|^2\big)^k}{k!}\sum_{m=0}^\infty\frac{\big[|\alpha|^2(1-\eta)\big]^m}{m!} = e^{-|\alpha|^2}\frac{\big(\eta|\alpha|^2\big)^k}{k!}\,e^{|\alpha|^2(1-\eta)} = \frac{\big(\eta|\alpha|^2\big)^k}{k!}\,e^{-\eta|\alpha|^2}. \tag{10.30}$$

The click statistics of a coherent state remain Poissonian, with the mean reduced from $|\alpha|^2$ to $\eta|\alpha|^2$. An imperfect detector does not change the form of the distribution; this is expected, because the beam splitter transforms a coherent state into a coherent state of amplitude $\sqrt\eta\,\alpha$.

**General states.** The effect of $\eta$ on an arbitrary distribution is most easily found with the generating function of §8.6. Multiplying (10.29) by $x^k$ and summing over $k$ with the binomial theorem gives

$$G_{\rm clicks}(x) = \sum_k P_k\,x^k = \sum_n p_n\sum_{k=0}^n\binom nk(\eta x)^k(1-\eta)^{n-k} = \sum_n p_n\,(1-\eta+\eta x)^n = G(1-\eta+\eta x). \tag{10.31}$$

Each derivative with respect to $x$ produces a factor $\eta$, so the factorial moments are scaled as $\langle k(k-1)\cdots(k-r+1)\rangle = \eta^r\langle n(n-1)\cdots(n-r+1)\rangle$. In particular $\bar k = \eta\bar n$ and $\langle k(k-1)\rangle = \eta^2\langle n(n-1)\rangle$. Two consequences follow. First, the measured second-order correlation function is independent of the efficiency,

$$g^{(2)}_{\rm clicks}(0) = \frac{\langle k(k-1)\rangle}{\bar k^2} = \frac{\eta^2\langle n(n-1)\rangle}{\eta^2\bar n^2} = g^{(2)}(0), \tag{10.32}$$

which is why $g^{(2)}$ is the preferred measure of nonclassicality in experiments with lossy detectors. Second, since $\Delta^2k-\bar k = \langle k(k-1)\rangle-\bar k^2 = \eta^2\big(\Delta^2n-\bar n\big)$, the Mandel parameter $Q = (\Delta^2n-\bar n)/\bar n$ is reduced by the efficiency,

$$Q_{\rm clicks} = \frac{\Delta^2k-\bar k}{\bar k} = \frac{\eta^2(\Delta^2n-\bar n)}{\eta\bar n} = \eta\,Q. \tag{10.33}$$

Losses drive every distribution towards the Poisson distribution. They preserve the sign of $Q$, so a super-Poissonian distribution stays super-Poissonian, but the departure from the Poisson value shrinks in proportion to $\eta$. In particular an inefficient detector cannot make the observed distribution narrower than the Poisson distribution; the sub-Poissonian character of a nonclassical state, $Q<0$, is diluted and disappears completely as $\eta\to0$.

**Mixtures of coherent states.** For the classical state $\hat\rho = \int d^2\alpha\,P(\alpha)\ket\alpha\bra\alpha$ with $P\ge0$, applying (10.30) to each member of the mixture gives

$$P_k = \int d^2\alpha\;P(\alpha)\,\frac{\big(\eta|\alpha|^2\big)^k}{k!}\,e^{-\eta|\alpha|^2}, \tag{10.34}$$

which is Mandel's formula of §8.4 with $W=\eta|\alpha|^2$. By the result of §8.4, $\Delta^2k = \bar k+\mathrm{Var}(W) = \bar k+\eta^2\,\mathrm{Var}(|\alpha|^2)\ge\bar k$. A classical field, observed with any detector efficiency, never yields sub-Poissonian counting statistics.

---

# Lecture 7

## 11. Phase-sensitive detection and phase-space representations

### 11.1 Counting photons does not see the phase

Photon counting gives access to photon statistics, and for classical states the number of clicks satisfies (Lecture 6)

$$\frac{\Delta^2 k}{\bar k}\;\ge\;1 \qquad\text{(classical states)}. \tag{11.1}$$

But a photodetector measures only functions of $\hat n = \hat a^\dagger\hat a$, which commutes with the phase rotation $e^{-i\phi\hat n}$: the states $\ket\alpha$ and $\ket{\alpha e^{i\phi}}$ give identical click statistics. How, then, can we measure the phase? We must make the signal interfere with a reference field of known phase.

### 11.2 Balanced homodyne detection

<div style="text-align:center"><svg width="620" height="300" viewBox="0 0 620 300" xmlns="http://www.w3.org/2000/svg" fill="none" stroke="currentColor" stroke-width="1.6" font-family="Times New Roman, serif" font-size="18"><defs><marker id="arrBHD7" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="7" markerHeight="7" orient="auto"><path d="M0,0 L10,5 L0,10 z" fill="currentColor" stroke="none"/></marker></defs><g transform="translate(40,0)"><line x1="60" y1="160" x2="222" y2="160" marker-end="url(#arrBHD7)"/><line x1="240" y1="290" x2="240" y2="178" marker-end="url(#arrBHD7)"/><rect x="222" y="142" width="36" height="36"/><line x1="222" y1="178" x2="258" y2="142" stroke-width="2.4"/><line x1="258" y1="160" x2="385" y2="160" marker-end="url(#arrBHD7)"/><line x1="240" y1="142" x2="240" y2="62" marker-end="url(#arrBHD7)"/><path d="M386,146 h12 a14,14 0 0 1 0,28 h-12 z"/><path d="M226,60 v-12 a14,14 0 0 1 28,0 v12 z"/><line x1="268" y1="34" x2="452" y2="34"/><line x1="412" y1="160" x2="470" y2="160"/><line x1="452" y1="34" x2="470" y2="34"/><line x1="470" y1="34" x2="470" y2="70" marker-end="url(#arrBHD7)"/><circle cx="470" cy="88" r="16"/><line x1="470" y1="160" x2="470" y2="106" marker-end="url(#arrBHD7)"/><line x1="486" y1="88" x2="530" y2="88" marker-end="url(#arrBHD7)"/><g fill="currentColor" stroke="none"><g font-style="italic"><text x="54" y="152" text-anchor="end">signal â</text><text x="252" y="282">LO |β⟩, β = |β|e<tspan dy="-7" font-size="12">iθ</tspan></text><text x="320" y="152">ĉ</text><text x="250" y="110">d̂</text><text x="500" y="116" font-size="15">n₋ ≈ √2|β| x̂<tspan dy="5" font-size="11">θ</tspan></text></g><text x="470" y="95" text-anchor="middle" font-size="22">−</text><text x="400" y="196" text-anchor="middle" font-size="14">D<tspan dy="3" font-size="10">c</tspan></text><text x="214" y="30" text-anchor="end" font-size="14">D<tspan dy="3" font-size="10">d</tspan></text><text x="284" y="136" font-size="13">BS 50:50</text></g></g></svg></div>

The signal mode $\hat a$ is combined on a 50:50 beam splitter with a **local oscillator** (LO) $\hat b$ in the coherent state $\ket\beta$, $\beta = |\beta|e^{i\theta}$. With output modes $\hat c = (\hat b+\hat a)/\sqrt2$ and $\hat d = (\hat b-\hat a)/\sqrt2$, the difference of the photocurrents measures

$$\hat n_- = \hat c^\dagger\hat c-\hat d^\dagger\hat d = \frac12\Big[(\hat a^\dagger+\hat b^\dagger)(\hat a+\hat b)-(\hat b^\dagger-\hat a^\dagger)(\hat b-\hat a)\Big] = \hat a^\dagger\hat b+\hat b^\dagger\hat a. \tag{11.2}$$

The terms $\hat b^\dagger\hat b$ cancel, so the intensity noise of the LO does not reach the signal; (11.2) is exact.

**Mean value.** Tracing out the LO, $\hat\rho_b = \ket\beta\bra\beta$, with $\hat b\ket\beta = \beta\ket\beta$:

$$\mathrm{Tr}_b\big[\hat\rho_b\,\hat n_-\big] = \beta\,\hat a^\dagger+\beta^*\hat a = \sqrt2\,|\beta|\,\hat x_\theta, \tag{11.3}$$

where we use quadratures normalized to $[\hat q,\hat p]=i$ (vacuum variance $\frac12$, twice the value of the earlier lectures):

$$\hat q = \frac{\hat a+\hat a^\dagger}{\sqrt2},\qquad \hat p = \frac{\hat a-\hat a^\dagger}{i\sqrt2},\qquad \hat x_\theta = \frac{\hat a\,e^{-i\theta}+\hat a^\dagger e^{i\theta}}{\sqrt2} = \hat q\cos\theta+\hat p\sin\theta. \tag{11.4}$$

Hence $\langle\hat n_-\rangle = \sqrt2\,|\beta|\,\langle\hat x_\theta\rangle$ exactly, for every $\beta$.

**The strong-LO limit.** To *measure* $\hat x_\theta$, all moments of $X = n_-/(\sqrt2|\beta|)$ must agree with those of $\hat x_\theta$, and the partial trace of $\hat n_-^2$ is not the square of (11.3). Using $\langle\hat b^2\rangle = \beta^2$, $\langle\hat b^\dagger\hat b\rangle = |\beta|^2$, $\langle\hat b\hat b^\dagger\rangle = |\beta|^2+1$,

$$\mathrm{Tr}_b\big[\hat\rho_b\,\hat n_-^2\big] = \big(\beta\hat a^\dagger+\beta^*\hat a\big)^2+\hat a^\dagger\hat a, \qquad \mathrm{Var}(X) = \mathrm{Var}(\hat x_\theta)+\frac{\langle\hat a^\dagger\hat a\rangle}{2|\beta|^2}. \tag{11.5}$$

The excess comes from $[\hat b,\hat b^\dagger]=1$: the vacuum fluctuations of the LO beat with the signal. Moreover, $\hat n_-$ has integer eigenvalues, so the measurement on the signal is a POVM $\hat E_k = \langle\beta|\hat\Pi_k|\beta\rangle$ ($\hat\Pi_k$ the eigenprojectors of $\hat n_-$) rather than a projective one. It tends to the projectors $\ket{x_\theta}\bra{x_\theta}$ only when

$$|\beta|^2\;\gg\;\langle\hat a^\dagger\hat a\rangle , \qquad\text{where}\qquad \frac{\hat n_-}{\sqrt2\,|\beta|}\;\longrightarrow\;\hat x_\theta = \hat q\cos\theta+\hat p\sin\theta. \tag{11.6}$$

Balanced homodyne detection with a strong LO thus measures the quadrature selected by the LO phase. Its outcome distribution is a one-dimensional projection of the Wigner function (§11.5); to reconstruct the state, the measurement is repeated for many $\theta$.

**Quadrature noise of classical states.** A coherent state has $\Delta^2x_\theta = \frac12$ for every $\theta$. For a mixture with $P\ge0$, as in §8.8,

$$\Delta^2x_\theta = \frac12+\int d^2\alpha\;P(\alpha)\Big(x_\theta(\alpha)-\langle\hat x_\theta\rangle\Big)^2\;\ge\;\frac12, \qquad x_\theta(\alpha) = \sqrt2\,\mathrm{Re}\big(\alpha\,e^{-i\theta}\big). \tag{11.7}$$

Quantum mechanics requires only $\Delta q\,\Delta p\ge\frac12$; the region between the two bounds belongs to squeezed, nonclassical states.

<div style="text-align:center"><svg width="440" height="410" viewBox="0 0 440 410" xmlns="http://www.w3.org/2000/svg" fill="none" stroke="currentColor" stroke-width="1.6" font-family="Times New Roman, serif" font-size="16"><defs><marker id="arrU7" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="7" markerHeight="7" orient="auto"><path d="M0,0 L10,5 L0,10 z" fill="currentColor" stroke="none"/></marker></defs><path d="M70,360 L70,31.0 L99.8,31.0 L99.8,31.0 L101.2,45.8 L102.6,59.3 L104.0,71.7 L105.4,83.1 L106.8,93.6 L108.2,103.4 L109.6,112.4 L111.0,120.9 L112.4,128.8 L113.8,136.2 L115.2,143.1 L116.6,149.6 L118.0,155.8 L119.4,161.6 L120.8,167.0 L122.2,172.2 L123.6,177.1 L125.0,181.8 L126.4,186.2 L127.8,190.4 L129.2,194.4 L130.6,198.2 L132.0,201.9 L133.4,205.4 L134.8,208.7 L136.2,211.9 L137.6,215.0 L139.0,217.9 L140.4,220.8 L141.8,223.5 L143.2,226.1 L144.6,228.6 L146.0,231.0 L147.4,233.4 L148.8,235.6 L150.2,237.8 L151.6,239.9 L153.0,241.9 L154.4,243.9 L155.8,245.8 L157.2,247.6 L158.6,249.4 L160.0,251.1 L161.4,252.8 L162.8,254.4 L164.2,256.0 L165.6,257.5 L167.0,259.0 L168.4,260.4 L169.8,261.8 L171.2,263.1 L172.6,264.5 L174.0,265.8 L175.4,267.0 L176.8,268.2 L178.2,269.4 L179.6,270.6 L181.0,271.7 L182.4,272.8 L183.8,273.9 L185.2,274.9 L186.6,275.9 L188.0,276.9 L189.4,277.9 L190.8,278.9 L192.2,279.8 L193.6,280.7 L195.0,281.6 L196.4,282.5 L197.8,283.3 L199.2,284.1 L200.6,285.0 L202.0,285.8 L203.4,286.5 L204.8,287.3 L206.2,288.0 L207.6,288.8 L209.0,289.5 L210.4,290.2 L211.8,290.9 L213.2,291.6 L214.6,292.2 L216.0,292.9 L217.4,293.5 L218.8,294.1 L220.2,294.7 L221.6,295.4 L223.0,295.9 L224.4,296.5 L225.8,297.1 L227.2,297.7 L228.6,298.2 L230.0,298.7 L231.4,299.3 L232.8,299.8 L234.2,300.3 L235.6,300.8 L237.0,301.3 L238.4,301.8 L239.8,302.3 L241.2,302.8 L242.6,303.2 L244.0,303.7 L245.4,304.1 L246.8,304.6 L248.2,305.0 L249.6,305.4 L251.0,305.9 L252.4,306.3 L253.8,306.7 L255.2,307.1 L256.6,307.5 L258.0,307.9 L259.4,308.3 L260.8,308.6 L262.2,309.0 L263.6,309.4 L265.0,309.7 L266.4,310.1 L267.8,310.5 L269.2,310.8 L270.6,311.1 L272.0,311.5 L273.4,311.8 L274.8,312.1 L276.2,312.5 L277.6,312.8 L279.0,313.1 L280.4,313.4 L281.8,313.7 L283.2,314.0 L284.6,314.3 L286.0,314.6 L287.4,314.9 L288.8,315.2 L290.2,315.5 L291.6,315.8 L293.0,316.1 L294.4,316.3 L295.8,316.6 L297.2,316.9 L298.6,317.1 L300.0,317.4 L301.4,317.6 L302.8,317.9 L304.2,318.2 L305.6,318.4 L307.0,318.6 L308.4,318.9 L309.8,319.1 L311.2,319.4 L312.6,319.6 L314.0,319.8 L315.4,320.1 L316.8,320.3 L318.2,320.5 L319.6,320.7 L321.0,321.0 L322.4,321.2 L323.8,321.4 L325.2,321.6 L326.6,321.8 L328.0,322.0 L329.4,322.2 L330.8,322.4 L332.2,322.6 L333.6,322.8 L335.0,323.0 L336.4,323.2 L337.8,323.4 L339.2,323.6 L340.6,323.8 L342.0,324.0 L343.4,324.2 L344.8,324.3 L346.2,324.5 L347.6,324.7 L349.0,324.9 L350.4,325.0 L351.8,325.2 L353.2,325.4 L354.6,325.6 L356.0,325.7 L357.4,325.9 L358.8,326.1 L360.2,326.2 L361.6,326.4 L363.0,326.6 L364.4,326.7 L365.8,326.9 L367.2,327.0 L368.6,327.2 L370.0,327.3 L371.4,327.5 L372.8,327.6 L374.2,327.8 L375.6,327.9 L377.0,328.1 L378.4,328.2 L379.8,328.4 L381.2,328.5 L382.6,328.6 L384.0,328.8 L385.4,328.9 L386.8,329.1 L388.2,329.2 L389.6,329.3 L391.0,329.5 L392.0,360 Z" fill="currentColor" fill-opacity="0.26" stroke="none"/><rect x="169.0" y="31.0" width="223.0" height="230.0" fill="currentColor" fill-opacity="0.06" stroke="none"/><line x1="169.0" y1="261.0" x2="169.0" y2="31.0" stroke-dasharray="4 4"/><line x1="169.0" y1="261.0" x2="392.0" y2="261.0" stroke-dasharray="4 4"/><polyline points="103.6,68.3 105.0,80.0 106.4,90.8 107.8,100.7 109.2,110.0 110.6,118.6 112.0,126.7 113.4,134.2 114.8,141.2 116.2,147.9 117.6,154.1 119.0,160.0 120.4,165.6 121.8,170.8 123.2,175.8 124.6,180.5 126.0,185.0 127.4,189.3 128.8,193.3 130.2,197.2 131.6,200.9 133.0,204.4 134.4,207.8 135.8,211.1 137.2,214.2 138.6,217.1 140.0,220.0 141.4,222.7 142.8,225.4 144.2,227.9 145.6,230.4 147.0,232.7 148.4,235.0 149.8,237.2 151.2,239.3 152.6,241.4 154.0,243.3 155.4,245.2 156.8,247.1 158.2,248.9 159.6,250.6 161.0,252.3 162.4,253.9 163.8,255.5 165.2,257.1 166.6,258.6 168.0,260.0 169.4,261.4 170.8,262.8 172.2,264.1 173.6,265.4 175.0,266.7 176.4,267.9 177.8,269.1 179.2,270.3 180.6,271.4 182.0,272.5 183.4,273.6 184.8,274.6 186.2,275.7 187.6,276.7 189.0,277.6 190.4,278.6 191.8,279.5 193.2,280.5 194.6,281.3 196.0,282.2 197.4,283.1 198.8,283.9 200.2,284.7 201.6,285.5 203.0,286.3 204.4,287.1 205.8,287.8 207.2,288.6 208.6,289.3 210.0,290.0 211.4,290.7 212.8,291.4 214.2,292.0 215.6,292.7 217.0,293.3 218.4,294.0 219.8,294.6 221.2,295.2 222.6,295.8 224.0,296.4 225.4,296.9 226.8,297.5 228.2,298.1 229.6,298.6 231.0,299.1 232.4,299.7 233.8,300.2 235.2,300.7 236.6,301.2 238.0,301.7 239.4,302.1 240.8,302.6 242.2,303.1 243.6,303.5 245.0,304.0 246.4,304.4 247.8,304.9 249.2,305.3 250.6,305.7 252.0,306.2 253.4,306.6 254.8,307.0 256.2,307.4 257.6,307.8 259.0,308.1 260.4,308.5 261.8,308.9 263.2,309.3 264.6,309.6 266.0,310.0 267.4,310.4 268.8,310.7 270.2,311.0 271.6,311.4 273.0,311.7 274.4,312.1 275.8,312.4 277.2,312.7 278.6,313.0 280.0,313.3 281.4,313.6 282.8,313.9 284.2,314.2 285.6,314.5 287.0,314.8 288.4,315.1 289.8,315.4 291.2,315.7 292.6,316.0 294.0,316.2 295.4,316.5 296.8,316.8 298.2,317.1 299.6,317.3 301.0,317.6 302.4,317.8 303.8,318.1 305.2,318.3 306.6,318.6 308.0,318.8 309.4,319.1 310.8,319.3 312.2,319.5 313.6,319.8 315.0,320.0 316.4,320.2 317.8,320.5 319.2,320.7 320.6,320.9 322.0,321.1 323.4,321.3 324.8,321.5 326.2,321.7 327.6,322.0 329.0,322.2 330.4,322.4 331.8,322.6 333.2,322.8 334.6,323.0 336.0,323.2 337.4,323.4 338.8,323.5 340.2,323.7 341.6,323.9 343.0,324.1 344.4,324.3 345.8,324.5 347.2,324.6 348.6,324.8 350.0,325.0 351.4,325.2 352.8,325.3 354.2,325.5 355.6,325.7 357.0,325.9 358.4,326.0 359.8,326.2 361.2,326.3 362.6,326.5 364.0,326.7 365.4,326.8 366.8,327.0 368.2,327.1 369.6,327.3 371.0,327.4 372.4,327.6 373.8,327.7 375.2,327.9 376.6,328.0 378.0,328.2 379.4,328.3 380.8,328.5 382.2,328.6" stroke-width="2.2"/><circle cx="169.0" cy="261.0" r="4.5" fill="currentColor"/><line x1="70" y1="360" x2="408.8" y2="360" marker-end="url(#arrU7)"/><line x1="70" y1="360" x2="70" y2="17.0" marker-end="url(#arrU7)"/><g fill="currentColor" stroke="none" font-size="14"><text x="408.8" y="380" text-anchor="end" font-style="italic" font-size="16">Δq</text><text x="60" y="21.19999999999999" text-anchor="end" font-style="italic" font-size="16">Δp</text><text x="168.99494936611666" y="378" text-anchor="middle">1/√2</text><text x="64" y="266.00505063388334" text-anchor="end">1/√2</text><text x="116.2" y="301.2">forbidden</text><text x="116.2" y="317.2" font-size="12">Δq Δp &lt; ½</text><text x="259.0" y="136.0" text-anchor="middle">classical states</text><text x="259.0" y="152.0" text-anchor="middle" font-size="12">(mixtures of coherent states)</text><text x="176.99494936611666" y="279.00505063388334" font-size="12">coherent states</text><text x="128.8" y="94.0" text-anchor="middle" font-size="12">squeezed</text><text x="128.8" y="108.0" text-anchor="middle" font-size="12">in q</text><text x="329.0" y="276.0" text-anchor="middle" font-size="12">squeezed in p</text><text x="385.0" y="346.0" font-size="12" font-style="italic" text-anchor="end">Δq Δp = ½</text></g></svg></div>

### 11.3 Phase-space representations

The $P$-function represents a coherent state by $\delta^2(\alpha-\alpha_0)$ and is singular for nonclassical states. The Wigner function exists for every state:

$$W(x,p) = \frac{1}{2\pi\hbar}\int_{-\infty}^{\infty}d\xi\;e^{-ip\xi/\hbar}\,\Big\langle x+\frac\xi2\Big|\,\hat\rho\,\Big|x-\frac\xi2\Big\rangle. \tag{11.8}$$

It is the density matrix in the center coordinate $x$ and relative coordinate $\xi$, Fourier transformed in $\xi$. (For optical quadratures, $\hbar = 1$ and $x\to q$.) For a pure state,

$$W(x,p) = \frac{1}{2\pi\hbar}\int d\xi\;e^{-ip\xi/\hbar}\,\psi\Big(x+\frac\xi2\Big)\,\psi^*\Big(x-\frac\xi2\Big). \tag{11.9}$$

**Marginals.** With $\int dp\,e^{-ip\xi/\hbar} = 2\pi\hbar\,\delta(\xi)$,

$$\int dp\;W(x,p) = \langle x|\hat\rho|x\rangle. \tag{11.10}$$

With $\langle p|x\rangle = (2\pi\hbar)^{-1/2}e^{-ipx/\hbar}$, $\langle p|\hat\rho|p\rangle = \frac{1}{2\pi\hbar}\int dx'\,dx''\,e^{-ip(x'-x'')/\hbar}\langle x'|\hat\rho|x''\rangle$; the substitution $x = (x'+x'')/2$, $\xi = x'-x''$ (unit Jacobian) gives

$$\int dx\;W(x,p) = \langle p|\hat\rho|p\rangle, \qquad \int dx\int dp\;W = 1. \tag{11.11}$$

**Overlaps.** Inserting (11.8) for two states, the $p$-integral gives $2\pi\hbar\,\delta(\xi+\xi')$ and the rest is a trace:

$$\mathrm{Tr}(\hat\rho_1\hat\rho_2) = 2\pi\hbar\int dx\int dp\;W_1(x,p)\,W_2(x,p). \tag{11.12}$$

Since $\mathrm{Tr}\,\hat\rho^2\le1$, $\int dx\,dp\,W^2\le1/2\pi\hbar$: no state occupies less than about $2\pi\hbar$ of phase space. For orthogonal states, $0 = \int dx\,dp\,W_\phi W_{\phi_\perp}$. Since $W_{\ket0}$ is a positive Gaussian, $W_{\ket1}$ must be negative somewhere. **The Wigner function may be negative.**

### 11.4 Time evolution and expectation values

Insert $\partial_t\hat\rho = -\frac i\hbar[\hat H,\hat\rho]$, $\hat H = \hat p^2/2m+U(\hat x)$, into (11.8).

*Kinetic term.* $\langle x'|[\hat p^2,\hat\rho]|x''\rangle = -\hbar^2(\partial_{x'}^2-\partial_{x''}^2)\rho$, and with $\partial_{x'} = \frac12\partial_x+\partial_\xi$, $\partial_{x''} = \frac12\partial_x-\partial_\xi$ this is $-2\hbar^2\partial_x\partial_\xi\rho$. Under the Fourier transform $\partial_\xi\to ip/\hbar$, so $\partial_tW|_{\rm kin} = -\frac pm\,\partial_xW$.

*Potential term.* $U(x+\frac\xi2)-U(x-\frac\xi2) = 2\sum_{n\ge0}\frac{U^{(2n+1)}(x)}{(2n+1)!}\big(\frac\xi2\big)^{2n+1}$, and $\xi\to i\hbar\,\partial_p$. Since $-\frac i\hbar\cdot i^{2n+1}\hbar^{2n+1}2^{-2n} = (-1)^n(\hbar/2)^{2n}$,

$$\Big(\partial_t+\frac pm\,\partial_x-U'(x)\,\partial_p\Big)W = \sum_{n=1}^{\infty}\frac{(-1)^n}{(2n+1)!}\Big(\frac\hbar2\Big)^{2n}U^{(2n+1)}(x)\,\partial_p^{2n+1}W. \tag{11.13}$$

The left side is the classical Liouville equation; the right side holds the quantum corrections, which vanish for $U'''=0$. **For quadratic Hamiltonians $W$ evolves like a classical phase-space density**; a free-field mode rotates $W$ rigidly about the origin.

**Expectation values.** With the Weyl symbol

$$A(x,p) = \int d\xi\;e^{-ip\xi/\hbar}\,\Big\langle x+\frac\xi2\Big|\,\hat A\,\Big|x-\frac\xi2\Big\rangle, \tag{11.14}$$

which is $2\pi\hbar$ times the "Wigner function" of $\hat A$, (11.12) gives

$$\langle\hat A\rangle = \int dx\int dp\;A(x,p)\,W(x,p). \tag{11.15}$$

This is the Wigner–Weyl representation; products of $x$ and $p$ correspond to symmetrically ordered operators.

### 11.5 Quantum state tomography

Let $\hat x_\theta\ket{x_\theta} = x_\theta\ket{x_\theta}$. A position eigenstate has $W_{\ket{x_0}} = \frac{1}{2\pi\hbar}\delta(x-x_0)$, and $\ket{x_\theta}$ is obtained from it by the oscillator rotation, which by §11.4 rotates $W$ rigidly. (The same result follows from the Gaussian integral (11.9).) Hence

$$W_{\ket{x_\theta}}(x,p) = \frac{1}{2\pi\hbar}\,\delta\big(x_\theta-x\cos\theta-p\sin\theta\big), \tag{11.16}$$

a line in phase space. By (11.12), the homodyne distribution is

$$\mathrm{pr}(x_\theta;\theta) = \mathrm{Tr}\big(\hat\rho\,\ket{x_\theta}\bra{x_\theta}\big) = \int dx\,dp\;\delta\big(x_\theta-x\cos\theta-p\sin\theta\big)\,W(x,p), \tag{11.17}$$

the integral of $W$ along lines perpendicular to the $x_\theta$ axis: the **Radon transform** of $W$.

<div style="text-align:center"><svg width="470" height="400" viewBox="0 0 470 400" xmlns="http://www.w3.org/2000/svg" fill="none" stroke="currentColor" stroke-width="1.6" font-family="Times New Roman, serif" font-size="16"><defs><marker id="arrT7" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="7" markerHeight="7" orient="auto"><path d="M0,0 L10,5 L0,10 z" fill="currentColor" stroke="none"/></marker></defs><g transform="translate(30,40)"><ellipse cx="200" cy="200" rx="70" ry="38" transform="rotate(-60 200 200)" fill="currentColor" fill-opacity="0.18"/><ellipse cx="200" cy="200" rx="40" ry="20" transform="rotate(-60 200 200)" fill="currentColor" fill-opacity="0.22" stroke="none"/><line x1="48.8" y1="114.1" x2="183.8" y2="347.9" stroke-width="0.8" opacity="0.45" stroke-dasharray="3 4"/><line x1="67.8" y1="103.1" x2="202.8" y2="336.9" stroke-width="0.8" opacity="0.45" stroke-dasharray="3 4"/><line x1="86.9" y1="92.1" x2="221.9" y2="325.9" stroke-width="0.8" opacity="0.45" stroke-dasharray="3 4"/><line x1="105.9" y1="81.1" x2="240.9" y2="314.9" stroke-width="0.8" opacity="0.45" stroke-dasharray="3 4"/><line x1="125.0" y1="70.1" x2="260.0" y2="303.9" stroke-width="0.8" opacity="0.45" stroke-dasharray="3 4"/><line x1="144.1" y1="59.1" x2="279.1" y2="292.9" stroke-width="0.8" opacity="0.45" stroke-dasharray="3 4"/><line x1="163.1" y1="48.1" x2="298.1" y2="281.9" stroke-width="0.8" opacity="0.45" stroke-dasharray="3 4"/><line x1="182.2" y1="37.1" x2="317.2" y2="270.9" stroke-width="0.8" opacity="0.45" stroke-dasharray="3 4"/><line x1="201.2" y1="26.1" x2="336.2" y2="259.9" stroke-width="0.8" opacity="0.45" stroke-dasharray="3 4"/><line x1="70.1" y1="275.0" x2="329.9" y2="125.0" marker-end="url(#arrT7)" stroke-width="1.8"/><line x1="50" y1="200" x2="360" y2="200" stroke-width="1" opacity="0.6" marker-end="url(#arrT7)"/><line x1="200" y1="350" x2="200" y2="40" stroke-width="1" opacity="0.6" marker-end="url(#arrT7)"/><line x1="25.4" y1="127.6" x2="224.6" y2="12.6" stroke-width="1"/><polyline points="29.7,125.0 33.1,122.9 36.5,120.8 39.9,118.7 43.2,116.5 46.6,114.2 49.8,111.9 53.0,109.4 56.1,106.8 59.1,103.9 62.0,100.9 64.7,97.6 67.2,94.0 69.6,90.1 71.8,85.9 73.7,81.3 75.5,76.4 77.2,71.2 78.6,65.8 80.0,60.2 81.4,54.6 82.8,49.0 84.3,43.6 86.0,38.5 87.9,33.9 90.2,29.8 92.8,26.3 95.8,23.6 99.3,21.6 103.2,20.3 107.5,19.8 112.2,19.9 117.2,20.5 122.4,21.6 127.8,23.0 133.4,24.6 138.9,26.2 144.5,27.8 149.9,29.2 155.2,30.4 160.3,31.3 165.3,31.9 170.0,32.1 174.6,32.0 179.0,31.6 183.2,30.9 187.3,29.9 191.2,28.8 195.0,27.4 198.8,25.9 202.4,24.2 206.1,22.5 209.6,20.7 213.2,18.8 216.7,16.9 220.2,15.0" stroke-width="2"/><path d="M260,200 A60,60 0 0 0 252.0,170.0" stroke-width="1"/><g fill="currentColor" stroke="none" font-style="italic"><text x="333.9" y="119.0">x<tspan font-size="11" dy="4">θ</tspan></text><text x="365" y="205">q</text><text x="206" y="40">p</text><text x="266" y="188" font-size="14">θ</text><text x="95" y="330" font-size="14">W(q,p)</text><text x="124.6" y="-10.5" font-size="14">pr(x<tspan font-size="10" dy="3">θ</tspan><tspan dy="-3">)</tspan></text></g></g></svg></div>

**Inversion.** Fourier transforming (11.17) in $x_\theta$ removes the delta function and gives a slice of the two-dimensional Fourier transform of $W$:

$$\int dx_\theta\;e^{itx_\theta}\,\mathrm{pr}(x_\theta;\theta) = \int dx\,dp\;e^{it(x\cos\theta+p\sin\theta)}\,W(x,p). \tag{11.18}$$

Inverting the 2D Fourier transform in polar coordinates ($dk_x\,dk_p = |t|\,dt\,d\theta$, $t\in\mathbb R$, $\theta\in[0,\pi)$) gives the inverse Radon transform (filtered back-projection),

$$W(x,p) = \frac{1}{(2\pi)^2}\int_{-\infty}^{\infty}dt\;|t|\int_0^{\pi}d\theta\int dx_\theta\;\mathrm{pr}(x_\theta;\theta)\;e^{it(x_\theta-x\cos\theta-p\sin\theta)}. \tag{11.19}$$

From homodyne data at all phases one reconstructs $W$, and through (11.8) the density matrix: optical homodyne tomography.

### 11.6 Beyond the Wigner function: $P$, $W$ and $Q$

All three representations follow one scheme: a quasi-probability distribution $F_\rho$ and an operator–function correspondence $\hat A\mapsto A_F(x,p)$ with

$$\langle \hat A\rangle = \int dx\int dp\;A_F(x,p)\,F_\rho(x,p). \tag{11.20}$$

$P$ gives normally ordered moments, $W$ symmetrically ordered ones, and the **Husimi $Q$-function** antinormally ordered ones. With $\alpha = \alpha_R+i\alpha_I$,

$$Q(\alpha_R,\alpha_I) = \frac1\pi\,\langle\alpha|\hat\rho|\alpha\rangle, \qquad \int d\alpha_R\,d\alpha_I\;Q = 1, \qquad \big\langle \hat a^l(\hat a^\dagger)^k\big\rangle = \int d^2\alpha\;Q(\alpha)\,\alpha^l\alpha^{*k}. \tag{11.21}$$

The normalization follows from the coherent-state completeness relation (§2.2). In the quadratures of (11.4), $\alpha = (q+ip)/\sqrt2$, so $Q(q,p) = \langle\alpha|\hat\rho|\alpha\rangle/2\pi$, and by (11.12) with the vacuum Wigner function $W_{\ket\alpha}(q',p') = \frac1\pi e^{-(q'-q)^2-(p'-p)^2}$,

$$Q(q,p) = \frac1\pi\int dq'\,dp'\;W(q',p')\;e^{-(q-q')^2-(p-p')^2}: \tag{11.22}$$

$Q$ is $W$ smoothed by one vacuum Gaussian. Being an expectation value of the positive operator $\ket\alpha\bra\alpha$, $Q$ satisfies $0\le Q\le 1/\pi$ for every state. Examples: $Q = \frac1\pi e^{-|\alpha-\alpha_0|^2}$ for $\ket{\alpha_0}$, $Q = \frac{1}{\pi}\frac{|\alpha|^{2n}}{n!}e^{-|\alpha|^2}$ for $\ket n$ (a ring, positive despite the nonclassicality of $\ket n$), and $Q = \frac{1}{\pi(\bar n+1)}e^{-|\alpha|^2/(\bar n+1)}$ for thermal light. In short: $P$ may be singular, $W$ is bounded but may be negative, $Q$ is always a smooth probability density.

> [!question]- Questions (not from the lecture)
> **"What if my state is multimode - is it possible to go below uncertainty on a subsystem"**
> No: the reduced state of a subsystem is a valid state and obeys $\Delta q_1\Delta p_1\ge\frac12$. A multimode state can, however, reduce the noise of **joint** observables: $\hat q_1-\hat q_2$ and $\hat p_1+\hat p_2$ commute, and in the two-mode squeezed vacuum both variances tend to zero, while each mode alone is thermal. The inferred (conditional) variances of $q_1$ and $p_1$ then have a product below $\frac14$ (EPR paradox, Reid criterion).
>
> **"What is the wigner function representaion of a Sussking glogowe operator?"**
> The Weyl symbol of $\sum_n\ket n\bra{n+1}$ is a sum of Gaussian-times-Laguerre terms with no simple closed form. Far from the origin it approaches the classical phase factor $e^{i\varphi}$ of $\alpha=|\alpha|e^{i\varphi}$; near the origin it deviates strongly, since the phase of a weak field is ill-defined. (Not checked against a reference.)
>
> **"Squeezed state in homodyne detection - can it increase phase estimation - what is its wigenr function"**
> Its Wigner function is a Gaussian ellipse (§8.9). A phase-squeezed state (ellipse narrow in the angular direction) has smaller phase uncertainty than a coherent state of the same mean photon number. Squeezed vacuum injected into the unused port of an interferometer (Caves, 1981) lowers the phase uncertainty below the shot-noise limit $1/\sqrt{\bar n}$ by about $e^{-r}$; this is used in gravitational-wave detectors.
>
> **"what is the projective measurmetn of a real coherent state with finite amplitude"**
> With a finite LO the measurement is not projective: it is the POVM $\hat E_k = \langle\beta|\hat\Pi_k|\beta\rangle$ with integer outcomes, the correct mean, and excess variance $\langle\hat a^\dagger\hat a\rangle/2|\beta|^2$ (11.5). For $|\beta|\to0$ it reduces to photon counting with no phase information.
>
> **"What are the terms arizing as a derivatives of wigner function for the simplest possible non quadriatic hamiltonian"**
> For $U=\lambda x^3$ only $U'''=6\lambda$ survives in (11.13): $\big(\partial_t+\frac pm\partial_x-3\lambda x^2\partial_p\big)W = -\frac{\lambda\hbar^2}{4}\partial_p^3W$. For $U=\lambda x^4$ the right side is $-\lambda\hbar^2x\,\partial_p^3W$. This third-derivative term has no classical counterpart and lets $W$ develop negative regions.
>
> **"How to measure non classicality in a general gaussian state"**
> A Gaussian state with covariance matrix $V$ (vacuum $V=\frac12\mathbb 1$ here) has a non-negative Gaussian $P$-function iff $V-\frac12\mathbb 1\ge0$. It is nonclassical exactly when the smallest eigenvalue of $V$ is below $\frac12$, i.e. when some (possibly joint) quadrature is squeezed; homodyne measurements of the second moments suffice.


# Lecture 8

## Calculating $W(x,p)$ from the definition

We evaluate the Wigner function directly from its definition,

$$W(x,p)=\frac{1}{2\pi}\int d\xi\, e^{-ip\xi}\,\bra{x+\xi/2}\hat\rho\ket{x-\xi/2}, \qquad \hat\rho=\ket\psi\bra\psi:\quad \bra{x+\xi/2}\hat\rho\ket{x-\xi/2}=\psi(x+\xi/2)\,\psi^*(x-\xi/2).$$

### Coherent state

For real $\alpha$ the coherent state is the vacuum Gaussian displaced by $\sqrt2\alpha$ in $x$ (recall $\langle\hat x\rangle=\sqrt2\,\mathrm{Re}\,\alpha$):

$$\psi_\alpha(x)=\Big(\frac{1}{\pi}\Big)^{1/4} e^{-\frac{1}{2}(x-\sqrt{2} \alpha)^2}.$$

The product $\psi_\alpha(x+\xi/2)\psi_\alpha(x-\xi/2)=\pi^{-1/2}e^{-(x-\sqrt2\alpha)^2-\xi^2/4}$, and $\int d\xi\,e^{-ip\xi}e^{-\xi^2/4}=2\sqrt\pi\,e^{-p^2}$, so

$$W_{\alpha}(x,p)=\frac{1}{\pi}\, e^{-(x-\sqrt{2}\alpha)^2 -p^2}.$$

### Fock state

**Husimi function.** Using $\langle\alpha|n\rangle=e^{-|\alpha|^2/2}\alpha^{*n}/\sqrt{n!}$,

$$Q_n(\alpha)= \frac{1}{\pi} |\langle \alpha | n \rangle |^2 = \frac{1}{\pi} e^{-|\alpha|^2} \frac{|\alpha|^{2n}}{n!}.$$

It is rotationally symmetric (a Fock state has no phase), peaks on the ring $|\alpha|=\sqrt n$, and for $n\ge1$ vanishes at the origin, $Q_n(0)=|\langle0|n\rangle|^2/\pi=0$: a "hole" in the centre. $Q$ is non-negative for every state, so this hole is the only trace of nonclassicality it shows.

**Wigner function.** The wavefunctions are

$$\psi_n(x)=\frac{1}{\sqrt{2^n n! \sqrt{\pi}}}\,e^{-x^2/2}H_n(x),$$

so, with $\xi=2y$,

$$W_n(x,p)=\frac{1}{\pi}\,\frac{1}{2^n n! \sqrt{\pi}} \int dy\; e^{-2ipy}\, e^{-x^2-y^2}\,H_n(x+y)\,H_n(x-y).$$

Instead of integrating the product of two Hermite polynomials directly, we use the generating function

$$e^{2ut-t^2} = \sum_{m} H_m(u)\frac{t^m}{m!}
\quad\Rightarrow\quad
e^{2(x+y)t-t^2}\, e^{2(x-y)s-s^2}=\sum_{m,n}H_m(x+y)\,H_n(x-y)\, \frac{t^m s^n}{m!\, n!}.$$

Multiplying by $e^{-2ipy-y^2}$ and integrating over $y$ is a Gaussian integral, $\int dy\,e^{-y^2+by}=\sqrt\pi\,e^{b^2/4}$ with $b=2(t-s-ip)$:

$$\int dy\; e^{-2ipy-y^2}\,e^{2(x+y)t-t^2+2(x-y)s-s^2} = \sqrt{\pi}\, e^{-p^2}\,e^{2(x-ip)t+2(x+ip)s-2ts}
\\ = \sqrt{\pi}\, e^{-p^2} \sum_{j,k,l} \frac{2^{j+k+l}(-1)^l (x-ip)^j (x+ip)^k\, t^{j+l}s^{k+l}}{j!\,k!\,l!}.$$

The diagonal term $W_n$ is $n!^2$ times the coefficient of $t^ns^n$, i.e. $j=k=n-l$, and $(x-ip)(x+ip)=x^2+p^2$:

$$W_n(x,p)=\frac{n!}{2^n\pi}\,e^{-(x^2+p^2)} \sum_{l=0}^{n} \frac{2^{2n-l}(-1)^l(x^2 +p^2)^{n-l}}{l!\, ((n-l)!)^2}
= \frac{(-1)^n}{\pi}\, e^{-(x^2+p^2)}\,L_n\big(2(x^2+p^2)\big),$$

where in the last step $k=n-l$ and $L_n(u)=\sum_k\binom nk\frac{(-u)^k}{k!}$ is the Laguerre polynomial. On the $\alpha$-plane ($x^2+p^2=2|\alpha|^2$, normalised in $d^2\alpha$) this reads $W_n(\alpha)=\frac{2}{\pi}(-1)^n e^{-2|\alpha|^2}L_n(4|\alpha|^2)$. $W_n(0)=(-1)^n\frac{2}{\pi}$ is the most negative value any Wigner function can take, and $W_n$ has $n$ circular nodes. The generating function in $t,s$ thus gives the Wigner functions of all Fock states at once (and, through the off-diagonal $t^ms^n$ terms, of $\ket m\bra n$).

**Interactive plot.** Left: $Q_n$ or $W_n$ on the $\alpha$-plane (dashed ring $|\alpha|=\sqrt n$). Right: radial cuts of both. Compare the single smooth ring of $Q$ with the $n$ sign changes of $W$.

```dataviewjs
// ===== CONFIG =====
const CFG = { n: 1, nMax: 15, L: 4.5 };
// ==================
// ---- loader (leave as is) ----
const LIB = "FUW/lib/";
const load = (src) => new Promise((ok, no) => { const s = document.createElement("script"); s.src = src; s.onload = ok; s.onerror = () => no(new Error("could not load " + src)); document.head.append(s); });
const libPath = async (n) => { const here = dv.current().file.folder, up = here.includes("/") ? here.slice(0, here.lastIndexOf("/")) + "/" : ""; for (const p of [LIB + n, "lib/" + n, here + "/lib/" + n, up + "lib/" + n, ...app.vault.getFiles().filter((x) => x.path.endsWith("lib/" + n)).map((x) => x.path)]) if (await app.vault.adapter.exists(p)) return p; throw new Error("lib/" + n + " not found in this vault (is the FUW/lib folder synced to this computer?)"); };
if (!window.JXG) await (window.__jxg ??= libPath("jsxgraphcore.js").then((p) => load(app.vault.adapter.getResourcePath(p))).catch(() => load("https://cdn.jsdelivr.net/npm/jsxgraph@1.10.1/distrib/jsxgraphcore.js")).catch((e) => { window.__jxg = null; throw e; }));
if (!window.RL) await (window.__rl ??= libPath("rlti.js").then((p) => load(app.vault.adapter.getResourcePath(p))).catch((e) => { window.__rl = null; throw e; }));
const K = await RL.init(dv), { f, el, C } = K;
// ---- shared plotting helpers ----
const GAP = 12, WS = Math.min(320, Math.floor((K.W - GAP) / 2)), WP = K.W - WS - GAP, dpr = window.devicePixelRatio || 1;
const box = "background:#fff;border:1px solid #e5e7eb;border-radius:10px";
const row = el("div", `display:flex;gap:${GAP}px;align-items:flex-start;margin-top:6px;flex-wrap:wrap`);
const cv = el("canvas", `width:${WS}px;height:${WS}px;${box}`); cv.width = Math.round(WS * dpr); cv.height = Math.round(WS * dpr);
const pdiv = el("div", `width:${WP}px;height:${WS}px;${box};touch-action:none`);
row.append(cv, pdiv); K.root.append(row);
const panel = el("div", "font-family:var(--font-monospace,monospace);font-size:0.8em;line-height:1.55;white-space:pre-wrap;color:var(--text-normal);margin-top:6px");
const stops = [[-1, [31, 95, 168]], [-0.5, [127, 166, 212]], [0, [248, 248, 248]], [0.5, [240, 164, 106]], [1, [194, 65, 12]]];
const cmap = (t) => { t = Math.max(-1, Math.min(1, t)); let i = 0; while (i < stops.length - 2 && t > stops[i + 1][0]) i++; const [t0, c0] = stops[i], [t1, c1] = stops[i + 1], u = (t - t0) / (t1 - t0); return c0.map((v, j) => Math.round(v + u * (c1[j] - v))); };
function heat(fun, L, vmax, label, overlay) {   // fun(x, y) on the α-plane, x = Re α, y = Im α
  const ctx = cv.getContext("2d"), Wd = cv.width, Hd = cv.height, img = ctx.createImageData(Wd, Hd), d = img.data;
  for (let py = 0; py < Hd; py++) { const y = L - (2 * L * py) / Hd;
    for (let px = 0; px < Wd; px++) { const x = -L + (2 * L * px) / Wd, [R, G, B] = cmap(fun(x, y) / vmax), o = 4 * (py * Wd + px); d[o] = R; d[o + 1] = G; d[o + 2] = B; d[o + 3] = 255; } }
  ctx.putImageData(img, 0, 0); ctx.save(); ctx.scale(dpr, dpr);
  const sx = (x) => ((x + L) / (2 * L)) * WS, sy = (y) => ((L - y) / (2 * L)) * WS;
  ctx.strokeStyle = "#9ca3af"; ctx.lineWidth = 1; ctx.beginPath(); ctx.moveTo(0, sy(0)); ctx.lineTo(WS, sy(0)); ctx.moveTo(sx(0), 0); ctx.lineTo(sx(0), WS); ctx.stroke();
  ctx.fillStyle = "#6b7280"; ctx.font = "10px sans-serif";
  for (let t = -Math.floor(L); t <= Math.floor(L); t++) if (t) { ctx.fillRect(sx(t) - 0.5, sy(0) - 3, 1, 6); ctx.fillRect(sx(0) - 3, sy(t) - 0.5, 6, 1); ctx.fillText(t, sx(t) - 3, sy(0) + 13); }
  ctx.fillStyle = C.ink; ctx.font = "italic 13px serif"; ctx.fillText("Re α", WS - 34, sy(0) - 6); ctx.fillText("Im α", sx(0) + 6, 13);
  if (overlay) overlay(ctx, sx, sy, WS / (2 * L));
  ctx.fillStyle = C.muted; ctx.font = "11px sans-serif"; ctx.fillText(label, 6, WS - 6); ctx.restore();
}
const axes = (xn, yn) => ({ x: { name: xn, withLabel: true, strokeColor: "#9ca3af", label: { position: "rt", offset: [-14, 14], fontSize: 14, strokeColor: C.ink }, ticks: { minorTicks: 0, strokeColor: "#9ca3af", label: { fontSize: 10, strokeColor: C.muted } } },
  y: { name: yn, withLabel: true, strokeColor: "#9ca3af", label: { position: "rt", offset: [8, -6], fontSize: 14, strokeColor: C.ink }, ticks: { minorTicks: 0, strokeColor: "#9ca3af", label: { fontSize: 10, strokeColor: C.muted } } } });
const board = (div, bb, xn, yn) => JXG.JSXGraph.initBoard(div, { boundingbox: bb, keepAspectRatio: false, axis: true, showCopyright: false, showNavigation: false, pan: { enabled: false }, zoom: { enabled: false }, defaultAxes: axes(xn, yn) });
const LF = [0]; for (let n = 1; n <= 400; n++) LF[n] = LF[n - 1] + Math.log(n);
const pois = (n, m) => (m <= 0 ? (n === 0 ? 1 : 0) : Math.exp(n * Math.log(m) - m - LF[n]));
// P(n) bars + Poisson reference with the same mean; returns an update function
function countsPlot(bP, cbP) {
  let P = [1], nShow = 10, mean = 0;
  const bars = bP.create("curve", [[0], [0]], { fixed: true, highlight: false, strokeColor: "#c2410c", strokeWidth: 1, fillColor: "#f0a46a", fillOpacity: 0.85 });
  bars.updateDataArray = function () { const xs = [], ys = []; for (let n = 0; n <= nShow; n++) { xs.push(n - 0.38, n - 0.38, n + 0.38, n + 0.38, NaN); ys.push(0, P[n], P[n], 0, NaN); } this.dataX = xs; this.dataY = ys; };
  const pl = bP.create("curve", [[0], [0]], { fixed: true, highlight: false, strokeColor: C.obs, strokeWidth: 2, dash: 2, visible: () => cbP.checked });
  pl.updateDataArray = function () { const xs = [], ys = []; for (let n = 0; n <= nShow; n++) { xs.push(n); ys.push(pois(n, mean)); } this.dataX = xs; this.dataY = ys; };
  for (let n = 0; n <= 80; n++) bP.create("point", [n, () => pois(n, mean)], { fixed: true, highlight: false, withLabel: false, size: 2.5, strokeColor: C.obs, fillColor: "#fff", visible: () => cbP.checked && n <= nShow });
  const leg = bP.create("text", [0, 0, () => "<span style='color:#c2410c'>■</span> state" + (cbP.checked ? " &nbsp; <span style='color:" + C.obs + "'>○</span> Poisson, same ⟨n⟩" : "")], { fixed: true, highlight: false, fontSize: 12, strokeColor: C.ink, anchorX: "right", anchorY: "top" });
  return (Pnew) => {
    P = Pnew; mean = 0; let m2 = 0, cum = 0, nEnd = 0; P.forEach((p, n) => { mean += n * p; m2 += n * n * p; });
    for (let n = 0; n < P.length; n++) { cum += P[n]; if (cum > 0.999) { nEnd = n; break; } }
    const varn = m2 - mean * mean; nShow = Math.min(80, Math.max(10, Math.ceil(Math.max(nEnd, mean + 4 * Math.sqrt(varn)))));
    let ymax = 0; for (let n = 0; n <= nShow; n++) ymax = Math.max(ymax, P[n], cbP.checked ? pois(n, mean) : 0); ymax *= 1.18;
    bP.setBoundingBox([-0.06 * nShow - 1, ymax, nShow + 1, -0.08 * ymax], false); leg.setPosition(JXG.COORDS_BY_USER, [nShow + 0.6, ymax * 0.97]); bP.update();
    return { mean, varn };
  };
}
const sN = K.slider("n", 0, CFG.nMax, 1, CFG.n, (v) => (+v).toFixed(0));
const sel = K.select([["Q", "Husimi Q"], ["W", "Wigner W"]]);
K.root.append(panel);
// Q(α) = e^{−|α|²}|α|^{2n}/(π n!),   W(α) = (2/π)(−1)ⁿ e^{−2|α|²} Lₙ(4|α|²)   (both normalised in d²α)
const lag = (n, u) => { let a = 1, b = 1 - u; if (n === 0) return 1; for (let k = 1; k < n; k++) { const c = ((2 * k + 1 - u) * b - k * a) / (k + 1); a = b; b = c; } return b; };
const Qr = (n, r) => Math.exp(-r * r + (n ? 2 * n * Math.log(r) : 0) - LF[n]) / Math.PI;
const Wr = (n, r) => (2 / Math.PI) * (n % 2 ? -1 : 1) * Math.exp(-2 * r * r) * lag(n, 4 * r * r);
const bR = board(pdiv, [-0.5, 0.7, CFG.L, -0.75], "|α|", "");
bR.create("line", [[0, 0], [1, 0]], { fixed: true, highlight: false, strokeColor: C.muted, strokeWidth: 0.5 });
const cQ = bR.create("functiongraph", [(r) => Qr(+sN.value, Math.max(r, 1e-9)), 0, CFG.L], { fixed: true, highlight: false, strokeColor: "#c2410c", strokeWidth: 2.4 });
const cW = bR.create("functiongraph", [(r) => Wr(+sN.value, r), 0, CFG.L], { fixed: true, highlight: false, strokeColor: "#1f5fa8", strokeWidth: 2.4 });
const vr = bR.create("line", [[() => Math.sqrt(+sN.value), 0], [() => Math.sqrt(+sN.value), 1]], { fixed: true, highlight: false, strokeColor: C.muted, dash: 2, strokeWidth: 1 });
bR.create("text", [CFG.L - 0.1, 0.66, "<span style='color:#c2410c'>━</span> Q(|α|) &nbsp; <span style='color:#1f5fa8'>━</span> W(|α|) &nbsp; ┆ |α| = √n"], { fixed: true, highlight: false, fontSize: 12, strokeColor: C.ink, anchorX: "right", anchorY: "top" });
function update() {
  const n = +sN.value, isQ = sel.value === "Q";
  cQ.setAttribute({ strokeWidth: isQ ? 2.8 : 1.4 }); cW.setAttribute({ strokeWidth: isQ ? 1.4 : 2.8 }); bR.update();
  const qmax = Qr(n, Math.sqrt(Math.max(n, 1e-9)));
  if (isQ) heat((x, y) => Qr(n, Math.max(Math.hypot(x, y), 1e-9)), CFG.L, qmax, `Q(α) for |${n}⟩, colour scale 0 … ${f(qmax)}`,
      (ctx, sx, sy, s) => { ctx.strokeStyle = C.muted; ctx.setLineDash([3, 3]); ctx.beginPath(); ctx.arc(sx(0), sy(0), Math.sqrt(n) * s, 0, 2 * Math.PI); ctx.stroke(); ctx.setLineDash([]); });
  else heat((x, y) => Wr(n, Math.hypot(x, y)), CFG.L, 2 / Math.PI, `W(α) for |${n}⟩, colour scale ±2/π`);
  panel.textContent =
`Q(0) = ${n ? "0  (⟨0|n⟩ = 0: the hole)" : "1/π"}    max Q = ${f(qmax)} on the ring |α| = √n = ${f(Math.sqrt(n))}
W(0) = (−1)ⁿ 2/π = ${f(Wr(n, 0))}    W has ${n} radial nodes; it is negative somewhere for every n ≥ 1, Q never is`;
}
sN.addEventListener("input", update); sel.onchange = update;
update();
```

**Creation and annihilation operators as derivatives in phase space.** In general, multiplying $\hat\rho$ by $\hat a$ or $\hat a^\dagger$ acts on the Wigner function as a first-order differential operator:

$$\hat a\hat\rho \leftrightarrow \Big(\alpha+\frac12\frac{\partial}{\partial\alpha^*}\Big)W, \qquad
\hat\rho\hat a \leftrightarrow \Big(\alpha-\frac12\frac{\partial}{\partial\alpha^*}\Big)W, \qquad
\hat a^\dagger\hat\rho \leftrightarrow \Big(\alpha^*-\frac12\frac{\partial}{\partial\alpha}\Big)W, \qquad
\hat\rho\hat a^\dagger \leftrightarrow \Big(\alpha^*+\frac12\frac{\partial}{\partial\alpha}\Big)W.$$

A check: for the vacuum, $W_0=\frac2\pi e^{-2|\alpha|^2}$ and $\partial_{\alpha^*}W_0=-2\alpha W_0$, so $\hat a\ket0\bra0\leftrightarrow(\alpha-\alpha)W_0=0$, as it must be. For example, applying $\hat a^\dagger(\cdot)\hat a$ once gives $(\alpha^*-\frac12\partial_\alpha)(\alpha-\frac12\partial_{\alpha^*})W_0=(4|\alpha|^2-1)W_0=W_1$, and $n$ applications give $n!\,W_n$; master equations become Fokker–Planck-type equations for $W$ in the same way.

### Squeezing

Let's take other states saturating uncertainty principle
<div style="text-align:center"><svg width="440" height="410" viewBox="0 0 440 410" xmlns="http://www.w3.org/2000/svg" fill="none" stroke="currentColor" stroke-width="1.6" font-family="Times New Roman, serif" font-size="16"><defs><marker id="arrU7" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="7" markerHeight="7" orient="auto"><path d="M0,0 L10,5 L0,10 z" fill="currentColor" stroke="none"/></marker></defs><path d="M70,360 L70,31.0 L99.8,31.0 L99.8,31.0 L101.2,45.8 L102.6,59.3 L104.0,71.7 L105.4,83.1 L106.8,93.6 L108.2,103.4 L109.6,112.4 L111.0,120.9 L112.4,128.8 L113.8,136.2 L115.2,143.1 L116.6,149.6 L118.0,155.8 L119.4,161.6 L120.8,167.0 L122.2,172.2 L123.6,177.1 L125.0,181.8 L126.4,186.2 L127.8,190.4 L129.2,194.4 L130.6,198.2 L132.0,201.9 L133.4,205.4 L134.8,208.7 L136.2,211.9 L137.6,215.0 L139.0,217.9 L140.4,220.8 L141.8,223.5 L143.2,226.1 L144.6,228.6 L146.0,231.0 L147.4,233.4 L148.8,235.6 L150.2,237.8 L151.6,239.9 L153.0,241.9 L154.4,243.9 L155.8,245.8 L157.2,247.6 L158.6,249.4 L160.0,251.1 L161.4,252.8 L162.8,254.4 L164.2,256.0 L165.6,257.5 L167.0,259.0 L168.4,260.4 L169.8,261.8 L171.2,263.1 L172.6,264.5 L174.0,265.8 L175.4,267.0 L176.8,268.2 L178.2,269.4 L179.6,270.6 L181.0,271.7 L182.4,272.8 L183.8,273.9 L185.2,274.9 L186.6,275.9 L188.0,276.9 L189.4,277.9 L190.8,278.9 L192.2,279.8 L193.6,280.7 L195.0,281.6 L196.4,282.5 L197.8,283.3 L199.2,284.1 L200.6,285.0 L202.0,285.8 L203.4,286.5 L204.8,287.3 L206.2,288.0 L207.6,288.8 L209.0,289.5 L210.4,290.2 L211.8,290.9 L213.2,291.6 L214.6,292.2 L216.0,292.9 L217.4,293.5 L218.8,294.1 L220.2,294.7 L221.6,295.4 L223.0,295.9 L224.4,296.5 L225.8,297.1 L227.2,297.7 L228.6,298.2 L230.0,298.7 L231.4,299.3 L232.8,299.8 L234.2,300.3 L235.6,300.8 L237.0,301.3 L238.4,301.8 L239.8,302.3 L241.2,302.8 L242.6,303.2 L244.0,303.7 L245.4,304.1 L246.8,304.6 L248.2,305.0 L249.6,305.4 L251.0,305.9 L252.4,306.3 L253.8,306.7 L255.2,307.1 L256.6,307.5 L258.0,307.9 L259.4,308.3 L260.8,308.6 L262.2,309.0 L263.6,309.4 L265.0,309.7 L266.4,310.1 L267.8,310.5 L269.2,310.8 L270.6,311.1 L272.0,311.5 L273.4,311.8 L274.8,312.1 L276.2,312.5 L277.6,312.8 L279.0,313.1 L280.4,313.4 L281.8,313.7 L283.2,314.0 L284.6,314.3 L286.0,314.6 L287.4,314.9 L288.8,315.2 L290.2,315.5 L291.6,315.8 L293.0,316.1 L294.4,316.3 L295.8,316.6 L297.2,316.9 L298.6,317.1 L300.0,317.4 L301.4,317.6 L302.8,317.9 L304.2,318.2 L305.6,318.4 L307.0,318.6 L308.4,318.9 L309.8,319.1 L311.2,319.4 L312.6,319.6 L314.0,319.8 L315.4,320.1 L316.8,320.3 L318.2,320.5 L319.6,320.7 L321.0,321.0 L322.4,321.2 L323.8,321.4 L325.2,321.6 L326.6,321.8 L328.0,322.0 L329.4,322.2 L330.8,322.4 L332.2,322.6 L333.6,322.8 L335.0,323.0 L336.4,323.2 L337.8,323.4 L339.2,323.6 L340.6,323.8 L342.0,324.0 L343.4,324.2 L344.8,324.3 L346.2,324.5 L347.6,324.7 L349.0,324.9 L350.4,325.0 L351.8,325.2 L353.2,325.4 L354.6,325.6 L356.0,325.7 L357.4,325.9 L358.8,326.1 L360.2,326.2 L361.6,326.4 L363.0,326.6 L364.4,326.7 L365.8,326.9 L367.2,327.0 L368.6,327.2 L370.0,327.3 L371.4,327.5 L372.8,327.6 L374.2,327.8 L375.6,327.9 L377.0,328.1 L378.4,328.2 L379.8,328.4 L381.2,328.5 L382.6,328.6 L384.0,328.8 L385.4,328.9 L386.8,329.1 L388.2,329.2 L389.6,329.3 L391.0,329.5 L392.0,360 Z" fill="currentColor" fill-opacity="0.26" stroke="none"/><rect x="169.0" y="31.0" width="223.0" height="230.0" fill="currentColor" fill-opacity="0.06" stroke="none"/><line x1="169.0" y1="261.0" x2="169.0" y2="31.0" stroke-dasharray="4 4"/><line x1="169.0" y1="261.0" x2="392.0" y2="261.0" stroke-dasharray="4 4"/><polyline points="103.6,68.3 105.0,80.0 106.4,90.8 107.8,100.7 109.2,110.0 110.6,118.6 112.0,126.7 113.4,134.2 114.8,141.2 116.2,147.9 117.6,154.1 119.0,160.0 120.4,165.6 121.8,170.8 123.2,175.8 124.6,180.5 126.0,185.0 127.4,189.3 128.8,193.3 130.2,197.2 131.6,200.9 133.0,204.4 134.4,207.8 135.8,211.1 137.2,214.2 138.6,217.1 140.0,220.0 141.4,222.7 142.8,225.4 144.2,227.9 145.6,230.4 147.0,232.7 148.4,235.0 149.8,237.2 151.2,239.3 152.6,241.4 154.0,243.3 155.4,245.2 156.8,247.1 158.2,248.9 159.6,250.6 161.0,252.3 162.4,253.9 163.8,255.5 165.2,257.1 166.6,258.6 168.0,260.0 169.4,261.4 170.8,262.8 172.2,264.1 173.6,265.4 175.0,266.7 176.4,267.9 177.8,269.1 179.2,270.3 180.6,271.4 182.0,272.5 183.4,273.6 184.8,274.6 186.2,275.7 187.6,276.7 189.0,277.6 190.4,278.6 191.8,279.5 193.2,280.5 194.6,281.3 196.0,282.2 197.4,283.1 198.8,283.9 200.2,284.7 201.6,285.5 203.0,286.3 204.4,287.1 205.8,287.8 207.2,288.6 208.6,289.3 210.0,290.0 211.4,290.7 212.8,291.4 214.2,292.0 215.6,292.7 217.0,293.3 218.4,294.0 219.8,294.6 221.2,295.2 222.6,295.8 224.0,296.4 225.4,296.9 226.8,297.5 228.2,298.1 229.6,298.6 231.0,299.1 232.4,299.7 233.8,300.2 235.2,300.7 236.6,301.2 238.0,301.7 239.4,302.1 240.8,302.6 242.2,303.1 243.6,303.5 245.0,304.0 246.4,304.4 247.8,304.9 249.2,305.3 250.6,305.7 252.0,306.2 253.4,306.6 254.8,307.0 256.2,307.4 257.6,307.8 259.0,308.1 260.4,308.5 261.8,308.9 263.2,309.3 264.6,309.6 266.0,310.0 267.4,310.4 268.8,310.7 270.2,311.0 271.6,311.4 273.0,311.7 274.4,312.1 275.8,312.4 277.2,312.7 278.6,313.0 280.0,313.3 281.4,313.6 282.8,313.9 284.2,314.2 285.6,314.5 287.0,314.8 288.4,315.1 289.8,315.4 291.2,315.7 292.6,316.0 294.0,316.2 295.4,316.5 296.8,316.8 298.2,317.1 299.6,317.3 301.0,317.6 302.4,317.8 303.8,318.1 305.2,318.3 306.6,318.6 308.0,318.8 309.4,319.1 310.8,319.3 312.2,319.5 313.6,319.8 315.0,320.0 316.4,320.2 317.8,320.5 319.2,320.7 320.6,320.9 322.0,321.1 323.4,321.3 324.8,321.5 326.2,321.7 327.6,322.0 329.0,322.2 330.4,322.4 331.8,322.6 333.2,322.8 334.6,323.0 336.0,323.2 337.4,323.4 338.8,323.5 340.2,323.7 341.6,323.9 343.0,324.1 344.4,324.3 345.8,324.5 347.2,324.6 348.6,324.8 350.0,325.0 351.4,325.2 352.8,325.3 354.2,325.5 355.6,325.7 357.0,325.9 358.4,326.0 359.8,326.2 361.2,326.3 362.6,326.5 364.0,326.7 365.4,326.8 366.8,327.0 368.2,327.1 369.6,327.3 371.0,327.4 372.4,327.6 373.8,327.7 375.2,327.9 376.6,328.0 378.0,328.2 379.4,328.3 380.8,328.5 382.2,328.6" stroke-width="2.2"/><circle cx="169.0" cy="261.0" r="4.5" fill="currentColor"/><line x1="70" y1="360" x2="408.8" y2="360" marker-end="url(#arrU7)"/><line x1="70" y1="360" x2="70" y2="17.0" marker-end="url(#arrU7)"/><g fill="currentColor" stroke="none" font-size="14"><text x="408.8" y="380" text-anchor="end" font-style="italic" font-size="16">Δq</text><text x="60" y="21.19999999999999" text-anchor="end" font-style="italic" font-size="16">Δp</text><text x="168.99494936611666" y="378" text-anchor="middle">1/√2</text><text x="64" y="266.00505063388334" text-anchor="end">1/√2</text><text x="116.2" y="301.2">forbidden</text><text x="116.2" y="317.2" font-size="12">Δq Δp &lt; ½</text><text x="259.0" y="136.0" text-anchor="middle">classical states</text><text x="259.0" y="152.0" text-anchor="middle" font-size="12">(mixtures of coherent states)</text><text x="176.99494936611666" y="279.00505063388334" font-size="12">coherent states</text><text x="128.8" y="94.0" text-anchor="middle" font-size="12">squeezed</text><text x="128.8" y="108.0" text-anchor="middle" font-size="12">in q</text><text x="329.0" y="276.0" text-anchor="middle" font-size="12">squeezed in p</text><text x="385.0" y="346.0" font-size="12" font-style="italic" text-anchor="end">Δq Δp = ½</text></g></svg></div>
$$x_\theta = \frac{1}{2} (a e^{-i\theta} + a^\dagger e^{i \theta})$$
measure of squeezing:
$$s(\theta) = 4 \Delta^2 x_\theta -1$$
Class of states: squeezed coherent states:
$$S(\xi)=e^{\frac{1}{2}(\xi^*a^2 -\xi {a^\dagger}^2)}$$
$$S^\dagger a S=a+\frac{1}{2}[a,()] + \frac{1}{3!}[a,...]$$
The nested commutators only involve $[a,\tfrac12\xi (a^\dagger)^2]=\xi a^\dagger$ and $[a^\dagger,\tfrac12\xi^* a^2]=-\xi^* a$, so the series resums to cosh and sinh: $S^\dagger a S = a \cosh r-a^\dagger e^{i\theta}\sinh r$, where $\xi=re^{i \theta}$
$$S^\dagger a^\dagger S = a^{\dagger}\cosh(r)-a \sinh(r) e^{-i \theta}$$
$$\bra{\psi_\xi}a\ket{\psi_\xi}=\bra{0}S^\dagger a S \ket{0}=0$$
Now we can calculate the variance of quadratures
$$\Delta^2 X_1 =\bra{0}S^\dagger (\frac{1}{2}(a+a^\dagger))^2 S \ket{0} - \bra{0} S^\dagger \frac{1}{2}(a+a^\dagger)S \ket{0}^2$$
if we insert $S S^\dagger$
$$=\frac{1}{4} (\cosh^2(r)+\sinh^2(r)-2 \sinh(r)\cosh(r) \cos(\theta))$$
for $\theta=0$
$$\Delta^2 X_1=\frac{1}{4}(\cosh r-\sinh r)^2  = \frac{1}{4}e^{-2r}$$
as $r \rightarrow \infty $, the quadrature $\Delta^2 X_1 \rightarrow 0$
The second quadrature is:
$$\Delta^2 X_2 = \frac{1}{4}e^{2r}$$
$$\Delta X_1 \Delta X_2 =\frac{1}{4}$$

### Squeezed coherent states

A **squeezed coherent state** is obtained by squeezing the vacuum and then displacing it,

$$\ket{\alpha,\xi} = \hat D(\alpha)\,\hat S(\xi)\ket0, \qquad \xi = re^{i\theta}.$$

We abbreviate $\mu = \cosh r$ and $\nu = e^{i\theta}\sinh r$, so that $\hat S^\dagger\hat a\hat S = \mu\hat a-\nu\hat a^\dagger$, and use $\hat D^\dagger\hat a\hat D = \hat a+\alpha$.

**Mean photon number.** Inserting $\hat D\hat D^\dagger = \hat 1$ between $\hat a^\dagger$ and $\hat a$,

$$\langle\hat a^\dagger\hat a\rangle_{\alpha,\xi} = \bra0\hat S^\dagger\hat D^\dagger\hat a^\dagger\hat D\hat D^\dagger\hat a\hat D\hat S\ket0 = \bra0\hat S^\dagger(\hat a^\dagger+\alpha^*)(\hat a+\alpha)\hat S\ket0 = |\alpha|^2+\sinh^2r .$$

The cross terms vanish because $\bra0\hat S^\dagger\hat a\hat S\ket0 = 0$, and the last term is $\|\hat S^\dagger\hat a\hat S\ket0\|^2 = \|-\nu\hat a^\dagger\ket0\|^2 = \sinh^2r$. The coherent part contributes $|\alpha|^2$ and the squeezing adds $\sinh^2r$ photons.

**Eigenvalue equation.** Start from $\hat a\ket0 = 0$ and insert $\hat S^\dagger\hat D^\dagger\hat D\hat S = \hat 1$:

$$0 = \hat D\hat S\,\hat a\,\hat S^\dagger\hat D^\dagger\;\hat D\hat S\ket0 .$$

The inverse transformations are $\hat S\hat a\hat S^\dagger = \mu\hat a+\nu\hat a^\dagger$ (replace $\xi\to-\xi$) and $\hat D\hat a\hat D^\dagger = \hat a-\alpha$. Hence $\hat D\hat S\hat a\hat S^\dagger\hat D^\dagger = \mu(\hat a-\alpha)+\nu(\hat a^\dagger-\alpha^*)$, and

$$\big(\mu\,\hat a+\nu\,\hat a^\dagger\big)\ket{\alpha,\xi} = \gamma\,\ket{\alpha,\xi}, \qquad \gamma = \alpha\cosh r+\alpha^*e^{i\theta}\sinh r .$$

For $\alpha = 0$ this reduces to $(\mu\hat a+\nu\hat a^\dagger)\ket\xi = 0$, the equation used for the squeezed vacuum below. In terms of the quadratures $\hat X_{1,2}$ ($\hat a = \hat X_1+i\hat X_2$) and for $\theta = 0$, the operator is $\mu\hat a+\nu\hat a^\dagger = (\mu+\nu)\hat X_1+i(\mu-\nu)\hat X_2$, so the equation can also be written as

$$\big(\hat X_1+i\lambda\hat X_2\big)\ket{\alpha,\xi} = \chi\,\ket{\alpha,\xi}, \qquad \lambda = \frac{\mu-\nu}{\mu+\nu} = e^{-2r}, \qquad \chi = \frac{\gamma}{\mu+\nu}.$$

For real $\alpha$, $\gamma = \alpha(\mu+\nu)$ and $\chi = \alpha$. Eigenstates of $\hat X_1+i\lambda\hat X_2$ are minimum-uncertainty states with $\Delta X_1/\Delta X_2 = \lambda$; the squeezed coherent states are exactly these.

## Photon number distribution of squeezed states

Expand the squeezed vacuum in the Fock basis, $\ket{\xi}=\sum_{n} c_n \ket{n}$. Setting $\alpha=0$ in the eigenvalue equation above,
$$(\mu\hat a + \nu\hat a^\dagger)\ket{\xi}=0 .$$
Projecting onto $\bra n$ gives $\mu\sqrt{n+1}\,c_{n+1}+\nu\sqrt n\,c_{n-1}=0$, i.e.
$$c_{n+1}=-\frac{\nu}{\mu}\sqrt{\frac{n}{n+1}}\,c_{n-1}.$$
Since $c_1 = 0$ (the $n=0$ equation), all odd amplitudes vanish. Iterating from $c_0$,
$$c_{2m}=(-1)^m (e^{i \theta} \tanh r)^m \sqrt{\frac{(2m-1)!!}{(2m)!!}}\,c_0 .$$
Normalization:
$$|c_0|^2 \Big(1+\sum_{m\ge1} \frac{(2m-1)!!}{(2m)!!}\tanh^{2m}r\Big)=|c_0|^2\,(1-\tanh^2 r)^{-1/2}=|c_0|^2\cosh r=1,$$
using $(1-z)^{-1/2}=\sum_m \frac{(2m-1)!!}{(2m)!!}z^m$. Hence $c_0=1/\sqrt{\cosh r}$ and, with $\frac{(2m-1)!!}{(2m)!!}=\frac{(2m)!}{4^m (m!)^2}$,
$$P(2m)=|c_{2m}|^2=\frac{(2m)!}{4^m (m!)^2} \frac{(\tanh r)^{2m}}{\cosh r}, \qquad P(2m+1)=0 .$$

**Things to try:** thermal ($r=0$, $\alpha_0=0$) gives $g^{(2)}=2$ and the geometric $P(n)$ of §6.1. $k_BT=0$ with $|\alpha_0|>0$ is a coherent state, which is exactly Poissonian. Squeezing along the displacement ($\varphi = \arg\alpha_0$) makes it **sub-Poissonian**. Note that $W\ge0$ for every setting (Hudson, §8.9).

```dataviewjs
// ===== CONFIG =====
const CFG = {
  kT: 1.0, kTMax: 5,               // k_B T  [E0]  (0 = pure state)
  hw: 1.0, hwMin: 0.2, hwMax: 3,   // ħω     [E0]
  r: 0, rMax: 1.2,                 // squeezing parameter r
  phi: 0,                          // squeezing angle φ [deg]: X_φ is squeezed
  amp: 0, ampMax: 3,               // displacement |α0|
  arg: 0,                          // arg α0 [deg]
  L: 4.5,                          // Wigner plot range: Re α, Im α ∈ [−L, L]
  N: 220,                          // Fock cutoff for P(n)
};
// ==================
// ---- loader (leave as is) ----
const LIB = "FUW/lib/";
const load = (src) => new Promise((ok, no) => { const s = document.createElement("script"); s.src = src; s.onload = ok; s.onerror = () => no(new Error("could not load " + src)); document.head.append(s); });
const libPath = async (n) => { const here = dv.current().file.folder, up = here.includes("/") ? here.slice(0, here.lastIndexOf("/")) + "/" : ""; for (const p of [LIB + n, "lib/" + n, here + "/lib/" + n, up + "lib/" + n, ...app.vault.getFiles().filter((x) => x.path.endsWith("lib/" + n)).map((x) => x.path)]) if (await app.vault.adapter.exists(p)) return p; throw new Error("lib/" + n + " not found in this vault (is the FUW/lib folder synced to this computer?)"); };
if (!window.JXG) await (window.__jxg ??= libPath("jsxgraphcore.js").then((p) => load(app.vault.adapter.getResourcePath(p))).catch(() => load("https://cdn.jsdelivr.net/npm/jsxgraph@1.10.1/distrib/jsxgraphcore.js")).catch((e) => { window.__jxg = null; throw e; }));
if (!window.RL) await (window.__rl ??= libPath("rlti.js").then((p) => load(app.vault.adapter.getResourcePath(p))).catch((e) => { window.__rl = null; throw e; }));
const K = await RL.init(dv), { f, el, C } = K;

// ---- controls ----
const deg = (v) => (+v).toFixed(0) + "°";
const sT = K.slider("k_BT", 0, CFG.kTMax, 0.01, CFG.kT);
const sH = K.slider("ħω", CFG.hwMin, CFG.hwMax, 0.01, CFG.hw);
const sR = K.slider("r", 0, CFG.rMax, 0.01, CFG.r);
const sP = K.slider("φ", 0, 180, 1, CFG.phi, deg);
const sA = K.slider("|α₀|", 0, CFG.ampMax, 0.01, CFG.amp);
const sG = K.slider("arg α₀", 0, 360, 1, CFG.arg, deg);
const cbV = K.check("vacuum-noise circle"), cbP = K.check("Poisson, same mean");

// ---- layout ----
const GAP = 12, WS = Math.min(320, Math.floor((K.W - GAP) / 2)), WP = K.W - WS - GAP;
const row = el("div", `display:flex;gap:${GAP}px;align-items:flex-start;margin-top:6px`);
const box = "background:#fff;border:1px solid #e5e7eb;border-radius:10px";
const cv = el("canvas", `width:${WS}px;height:${WS}px;${box}`);
const dpr = window.devicePixelRatio || 1; cv.width = Math.round(WS * dpr); cv.height = Math.round(WS * dpr);
const pdiv = el("div", `width:${WP}px;height:${WS}px;${box};touch-action:none`);
row.append(cv, pdiv);
const panel = el("div", "font-family:var(--font-monospace,monospace);font-size:0.8em;line-height:1.55;white-space:pre-wrap;color:var(--text-normal);margin-top:6px");
K.root.append(row, panel);

// ---- state: covariance V (vacuum = I/4) and mean μ, with α = x + i y ----
function state() {
  const kT = +sT.value, hw = +sH.value, x = kT > 0 ? hw / kT : Infinity;
  const nth = x === Infinity ? 0 : 1 / Math.expm1(x);
  const r = +sR.value, ph = (+sP.value * Math.PI) / 180, A = +sA.value, ag = (+sG.value * Math.PI) / 180;
  const s = (2 * nth + 1) / 4, c = Math.cos(ph), sn = Math.sin(ph), e1 = Math.exp(-2 * r), e2 = Math.exp(2 * r);
  const V = [s * (c * c * e1 + sn * sn * e2), s * c * sn * (e1 - e2), s * (sn * sn * e1 + c * c * e2)]; // [Vxx, Vxy, Vyy]
  return { kT, hw, x, nth, r, ph, V, mu: [A * Math.cos(ag), A * Math.sin(ag)] };
}

// ---- P(n) exactly, from the generating function G(z) = Tr(ρ z^n) = 2 A(z)^(-1/2) exp(B(z)/A(z)) ----
function photonStats({ V, mu }) {
  const N = CFG.N, [vxx, vxy, vyy] = V;
  // M(z) = (1+z) I + 4(1−z) V = M0 + z M1
  const M0 = [1 + 4 * vxx, 4 * vxy, 1 + 4 * vyy], M1 = [1 - 4 * vxx, -4 * vxy, 1 - 4 * vyy];
  const a = [M0[0] * M0[2] - M0[1] ** 2, M0[0] * M1[2] + M1[0] * M0[2] - 2 * M0[1] * M1[1], M1[0] * M1[2] - M1[1] ** 2];
  const q = (M) => M[2] * mu[0] ** 2 - 2 * M[1] * mu[0] * mu[1] + M[0] * mu[1] ** 2; // μᵀ adj(M) μ
  const q0 = q(M0), q1 = q(M1), b = [-2 * q0, 2 * q0 - 2 * q1, 2 * q1];
  const pow = (p) => { const h = new Float64Array(N); h[0] = a[0] ** p; for (let n = 1; n < N; n++) { let s = 0; for (let k = 1; k <= Math.min(2, n); k++) s += (p * k - (n - k)) * a[k] * h[n - k]; h[n] = s / (n * a[0]); } return h; };
  const inv = pow(-1), half = pow(-0.5), g = new Float64Array(N), e = new Float64Array(N), P = new Float64Array(N);
  for (let n = 0; n < N; n++) for (let k = 0; k <= Math.min(2, n); k++) g[n] += b[k] * inv[n - k];
  e[0] = Math.exp(g[0]);
  for (let n = 1; n < N; n++) { let s = 0; for (let k = 1; k <= n; k++) s += k * g[k] * e[n - k]; e[n] = s / n; }
  for (let n = 0; n < N; n++) { let s = 0; for (let k = 0; k <= n; k++) s += half[k] * e[n - k]; P[n] = Math.max(0, 2 * s); }
  let m1 = 0, m2 = 0, tot = 0; P.forEach((p, n) => { tot += p; m1 += n * p; m2 += n * n * p; });
  return { P, tot, mean: m1, varn: m2 - m1 * m1, fact2: m2 - m1 };
}

// ---- Wigner function on the canvas ----
const ctx = cv.getContext("2d"), L = CFG.L, VMAX = 2 / Math.PI;
const stops = [[-1, [31, 95, 168]], [-0.5, [127, 166, 212]], [0, [248, 248, 248]], [0.5, [240, 164, 106]], [1, [194, 65, 12]]];
const cmap = (t) => { t = Math.max(-1, Math.min(1, t)); let i = 0; while (i < stops.length - 2 && t > stops[i + 1][0]) i++; const [t0, c0] = stops[i], [t1, c1] = stops[i + 1], u = (t - t0) / (t1 - t0); return c0.map((v, j) => Math.round(v + u * (c1[j] - v))); };
const X = (px) => -L + (2 * L * px) / cv.width, Y = (py) => L - (2 * L * py) / cv.height;
const toPx = (x) => ((x + L) / (2 * L)) * cv.width, toPy = (y) => ((L - y) / (2 * L)) * cv.height;
function drawW(st) {
  const [vxx, vxy, vyy] = st.V, det = vxx * vyy - vxy * vxy, ixx = vyy / det, ixy = -vxy / det, iyy = vxx / det, norm = 1 / (2 * Math.PI * Math.sqrt(det));
  const img = ctx.createImageData(cv.width, cv.height), d = img.data;
  for (let py = 0; py < cv.height; py++) {
    const dy = Y(py) - st.mu[1];
    for (let px = 0; px < cv.width; px++) {
      const dx = X(px) - st.mu[0], w = norm * Math.exp(-0.5 * (ixx * dx * dx + 2 * ixy * dx * dy + iyy * dy * dy));
      const [R, G, B] = cmap(w / VMAX), o = 4 * (py * cv.width + px); d[o] = R; d[o + 1] = G; d[o + 2] = B; d[o + 3] = 255;
    }
  }
  ctx.putImageData(img, 0, 0);
  ctx.save(); ctx.scale(dpr, dpr); const S = WS, sx = (x) => toPx(x) / dpr, sy = (y) => toPy(y) / dpr;
  ctx.strokeStyle = "#9ca3af"; ctx.lineWidth = 1; ctx.beginPath(); ctx.moveTo(0, sy(0)); ctx.lineTo(S, sy(0)); ctx.moveTo(sx(0), 0); ctx.lineTo(sx(0), S); ctx.stroke();
  ctx.fillStyle = "#6b7280"; ctx.font = "10px sans-serif";
  for (let t = -Math.floor(L); t <= Math.floor(L); t++) if (t) { ctx.fillRect(sx(t) - 0.5, sy(0) - 3, 1, 6); ctx.fillRect(sx(0) - 3, sy(t) - 0.5, 6, 1); ctx.fillText(t, sx(t) - 3, sy(0) + 13); }
  ctx.fillStyle = C.ink; ctx.font = "italic 13px serif"; ctx.fillText("Re α", S - 34, sy(0) - 6); ctx.fillText("Im α", sx(0) + 6, 13);
  // 1σ ellipse of W  (axes = eigenvectors of V)
  const tr = vxx + vyy, dd = Math.sqrt(((vxx - vyy) / 2) ** 2 + vxy * vxy), l1 = tr / 2 + dd, l2 = tr / 2 - dd, th = 0.5 * Math.atan2(2 * vxy, vxx - vyy);
  ctx.strokeStyle = C.ink; ctx.lineWidth = 1.5; ctx.beginPath(); ctx.ellipse(sx(st.mu[0]), sy(st.mu[1]), (Math.sqrt(l1) * S) / (2 * L), (Math.sqrt(l2) * S) / (2 * L), -th, 0, 2 * Math.PI); ctx.stroke();
  if (cbV.checked) { ctx.setLineDash([4, 3]); ctx.strokeStyle = C.obs; ctx.beginPath(); ctx.arc(sx(st.mu[0]), sy(st.mu[1]), (0.5 * S) / (2 * L), 0, 2 * Math.PI); ctx.stroke(); ctx.setLineDash([]); }
  ctx.fillStyle = C.muted; ctx.font = "11px sans-serif"; ctx.fillText("W(α), colour scale ±2/π", 6, S - 6);
  ctx.restore();
}

// ---- P(n) board ----
const bP = JXG.JSXGraph.initBoard(pdiv, { boundingbox: [-1.5, 1, 20, -0.08], keepAspectRatio: false, axis: true, showCopyright: false, showNavigation: false, pan: { enabled: false }, zoom: { enabled: false },
  defaultAxes: { x: { name: "n", withLabel: true, strokeColor: "#9ca3af", label: { position: "rt", offset: [-14, 14], fontSize: 14, strokeColor: C.ink }, ticks: { minorTicks: 0, strokeColor: "#9ca3af", label: { fontSize: 10, strokeColor: C.muted } } },
                 y: { name: "P(n)", withLabel: true, strokeColor: "#9ca3af", label: { position: "rt", offset: [8, -6], fontSize: 14, strokeColor: C.ink }, ticks: { minorTicks: 0, strokeColor: "#9ca3af", label: { fontSize: 10, strokeColor: C.muted } } } } });
let ST = state(), PS = photonStats(ST), nShow = 20;
const bars = bP.create("curve", [[0], [0]], { fixed: true, highlight: false, strokeColor: "#c2410c", strokeWidth: 1, fillColor: "#f0a46a", fillOpacity: 0.85 });
bars.updateDataArray = function () { const xs = [], ys = []; for (let n = 0; n <= nShow; n++) { xs.push(n - 0.38, n - 0.38, n + 0.38, n + 0.38, NaN); ys.push(0, PS.P[n], PS.P[n], 0, NaN); } this.dataX = xs; this.dataY = ys; };
const pois = (n, m) => Math.exp(n * Math.log(Math.max(m, 1e-300)) - m - lgamma(n + 1));
function lgamma(x) { let s = 0; for (let k = 2; k < x; k++) s += Math.log(k); return s; }
const poisLine = bP.create("curve", [[0], [0]], { fixed: true, highlight: false, strokeColor: C.obs, strokeWidth: 2, dash: 2, visible: () => cbP.checked });
poisLine.updateDataArray = function () { const xs = [], ys = []; for (let n = 0; n <= nShow; n++) { xs.push(n); ys.push(pois(n, PS.mean)); } this.dataX = xs; this.dataY = ys; };
const poisPts = [];
for (let n = 0; n <= 80; n++) poisPts.push(bP.create("point", [n, () => pois(n, PS.mean)], { fixed: true, highlight: false, withLabel: false, size: 2.5, strokeColor: C.obs, fillColor: "#fff", visible: () => cbP.checked && n <= nShow }));
const legend = bP.create("text", [0, 0, () => cbP.checked ? "<span style='color:#c2410c'>■</span> state &nbsp; <span style='color:" + C.obs + "'>○</span> Poisson, same ⟨n⟩" : "<span style='color:#c2410c'>■</span> state"], { fixed: true, highlight: false, fontSize: 12, strokeColor: C.ink, anchorX: "right", anchorY: "top" });

function update() {
  ST = state(); PS = photonStats(ST);
  let cum = 0, nEnd = 0; for (let n = 0; n < CFG.N; n++) { cum += PS.P[n]; if (cum > 0.999) { nEnd = n; break; } }
  nShow = Math.min(80, Math.max(10, Math.ceil(Math.max(nEnd, PS.mean + 4 * Math.sqrt(PS.varn)))));
  let ymax = 0; for (let n = 0; n <= nShow; n++) ymax = Math.max(ymax, PS.P[n], cbP.checked ? pois(n, PS.mean) : 0);
  ymax *= 1.18;
  bP.setBoundingBox([-0.06 * nShow - 1, ymax, nShow + 1, -0.08 * ymax], false);
  legend.setPosition(JXG.COORDS_BY_USER, [nShow + 0.6, ymax * 0.97]);
  bP.update(); drawW(ST);
  const m = PS.mean, Q = m > 1e-9 ? (PS.varn - m) / m : 0, g2 = m > 1e-9 ? PS.fact2 / (m * m) : NaN;
  const x = ST.x === Infinity ? "∞" : f(ST.x);
  panel.textContent =
`ħω/k_BT = ${x}  ⇒  n_th = ${f(ST.nth)}    purity Tr ρ² = 1/(2n_th+1) = ${f(1 / (2 * ST.nth + 1))}   (only the ratio matters)
⟨n⟩ = ${f(m)}   Var(n) = ${f(PS.varn)}   Q = ${f(Q)}   g⁽²⁾(0) = ${isNaN(g2) ? "—" : f(g2)}   ${Q < -1e-6 ? "sub-Poissonian (nonclassical)" : Q > 1e-6 ? "super-Poissonian" : "Poissonian"}
Var(X_φ) = ${f(Math.exp(-2 * ST.r) * (2 * ST.nth + 1) / 4)}, Var(X_φ+π/2) = ${f(Math.exp(2 * ST.r) * (2 * ST.nth + 1) / 4)}  (vacuum 0.250)${Math.exp(-2 * ST.r) * (2 * ST.nth + 1) < 1 - 1e-9 ? "  squeezed!" : ""}   W ≥ 0 (Gaussian)`;
}
for (const s of [sT, sH, sR, sP, sA, sG]) s.addEventListener("input", update);
for (const c of [cbV, cbP]) c.onchange = update;
update();
```



### Photon number distribution of squeezed coherent states

Projecting the eigenvalue equation onto $\bra n$, with $\ket{\alpha,\xi} = \sum_nc_n\ket n$, gives the three-term recurrence

$$\mu\sqrt{n+1}\;c_{n+1}+\nu\sqrt n\;c_{n-1} = \gamma\,c_n .$$

We try $c_n = c_0\,t^n f_n/\sqrt{n!}$. Substituting and multiplying by $\sqrt{n!}/(c_0t^{n-1})$ gives $\mu t^2f_{n+1}+\nu nf_{n-1} = \gamma tf_n$. This is the Hermite recurrence $H_{n+1}(z) = 2zH_n(z)-2nH_{n-1}(z)$ provided $\nu = 2\mu t^2$ and $\gamma t = 2\mu t^2z$, i.e.

$$t^2 = \frac\nu{2\mu} = \frac12e^{i\theta}\tanh r, \qquad z = \frac{\gamma}{2\mu t} = \frac{\gamma}{\sqrt{e^{i\theta}\sinh2r}} .$$

Fixing $c_0 = \langle0|\alpha,\xi\rangle$ by normalization, the amplitudes are

$$c_n = \frac{1}{\sqrt{\cosh r}}\,\exp\Big[-\frac12|\alpha|^2-\frac12\alpha^{*2}e^{i\theta}\tanh r\Big]\Big(\frac12e^{i\theta}\tanh r\Big)^{n/2}\frac{H_n(z)}{\sqrt{n!}}, \qquad P(n) = |c_n|^2 .$$

For $r\to0$ this reduces to the Poisson distribution of $\ket\alpha$. For $\alpha = 0$, $z = 0$ and $H_n(0) = 0$ for odd $n$, which reproduces the even-only distribution of the squeezed vacuum derived above.

> [!example] Homework (from the board)
> Solve $(\mu\hat a+\nu\hat a^\dagger)\ket\xi = 0$ in the position representation $\langle x|\cdot\rangle$ and find the wavefunction of the squeezed vacuum.

**Interactive plot.** The bars are $P(n)$ computed from the recurrence above; the Wigner function is the Gaussian with mean $\alpha$ and covariance $\frac14R(\theta/2)\,\mathrm{diag}(e^{-2r},e^{2r})\,R(\theta/2)^T$ (the quadrature $\hat X_{\theta/2}$ is squeezed); the Husimi $Q$ (switch above the plot) is the same Gaussian with the vacuum noise added, covariance $+\frac14\mathbb 1$, so it is never narrower than the vacuum in any direction. Squeezing along the displacement ($\theta = 2\arg\alpha$) gives sub-Poissonian statistics; squeezing across it gives super-Poissonian statistics with oscillations in $P(n)$.

```dataviewjs
// ===== CONFIG =====
const CFG = { amp: 2, ampMax: 3.5, arg: 0, r: 0.5, rMax: 1.2, th: 0, L: 4.5, N: 260 };
// ==================
// ---- loader (leave as is) ----
const LIB = "FUW/lib/";
const load = (src) => new Promise((ok, no) => { const s = document.createElement("script"); s.src = src; s.onload = ok; s.onerror = () => no(new Error("could not load " + src)); document.head.append(s); });
const libPath = async (n) => { const here = dv.current().file.folder, up = here.includes("/") ? here.slice(0, here.lastIndexOf("/")) + "/" : ""; for (const p of [LIB + n, "lib/" + n, here + "/lib/" + n, up + "lib/" + n, ...app.vault.getFiles().filter((x) => x.path.endsWith("lib/" + n)).map((x) => x.path)]) if (await app.vault.adapter.exists(p)) return p; throw new Error("lib/" + n + " not found in this vault (is the FUW/lib folder synced to this computer?)"); };
if (!window.JXG) await (window.__jxg ??= libPath("jsxgraphcore.js").then((p) => load(app.vault.adapter.getResourcePath(p))).catch(() => load("https://cdn.jsdelivr.net/npm/jsxgraph@1.10.1/distrib/jsxgraphcore.js")).catch((e) => { window.__jxg = null; throw e; }));
if (!window.RL) await (window.__rl ??= libPath("rlti.js").then((p) => load(app.vault.adapter.getResourcePath(p))).catch((e) => { window.__rl = null; throw e; }));
const K = await RL.init(dv), { f, el, C } = K;
// ---- shared plotting helpers ----
const GAP = 12, WS = Math.min(320, Math.floor((K.W - GAP) / 2)), WP = K.W - WS - GAP, dpr = window.devicePixelRatio || 1;
const box = "background:#fff;border:1px solid #e5e7eb;border-radius:10px";
const row = el("div", `display:flex;gap:${GAP}px;align-items:flex-start;margin-top:6px;flex-wrap:wrap`);
const cv = el("canvas", `width:${WS}px;height:${WS}px;${box}`); cv.width = Math.round(WS * dpr); cv.height = Math.round(WS * dpr);
const pdiv = el("div", `width:${WP}px;height:${WS}px;${box};touch-action:none`);
row.append(cv, pdiv); K.root.append(row);
const panel = el("div", "font-family:var(--font-monospace,monospace);font-size:0.8em;line-height:1.55;white-space:pre-wrap;color:var(--text-normal);margin-top:6px");
const stops = [[-1, [31, 95, 168]], [-0.5, [127, 166, 212]], [0, [248, 248, 248]], [0.5, [240, 164, 106]], [1, [194, 65, 12]]];
const cmap = (t) => { t = Math.max(-1, Math.min(1, t)); let i = 0; while (i < stops.length - 2 && t > stops[i + 1][0]) i++; const [t0, c0] = stops[i], [t1, c1] = stops[i + 1], u = (t - t0) / (t1 - t0); return c0.map((v, j) => Math.round(v + u * (c1[j] - v))); };
function heat(fun, L, vmax, label, overlay) {   // fun(x, y) on the α-plane, x = Re α, y = Im α
  const ctx = cv.getContext("2d"), Wd = cv.width, Hd = cv.height, img = ctx.createImageData(Wd, Hd), d = img.data;
  for (let py = 0; py < Hd; py++) { const y = L - (2 * L * py) / Hd;
    for (let px = 0; px < Wd; px++) { const x = -L + (2 * L * px) / Wd, [R, G, B] = cmap(fun(x, y) / vmax), o = 4 * (py * Wd + px); d[o] = R; d[o + 1] = G; d[o + 2] = B; d[o + 3] = 255; } }
  ctx.putImageData(img, 0, 0); ctx.save(); ctx.scale(dpr, dpr);
  const sx = (x) => ((x + L) / (2 * L)) * WS, sy = (y) => ((L - y) / (2 * L)) * WS;
  ctx.strokeStyle = "#9ca3af"; ctx.lineWidth = 1; ctx.beginPath(); ctx.moveTo(0, sy(0)); ctx.lineTo(WS, sy(0)); ctx.moveTo(sx(0), 0); ctx.lineTo(sx(0), WS); ctx.stroke();
  ctx.fillStyle = "#6b7280"; ctx.font = "10px sans-serif";
  for (let t = -Math.floor(L); t <= Math.floor(L); t++) if (t) { ctx.fillRect(sx(t) - 0.5, sy(0) - 3, 1, 6); ctx.fillRect(sx(0) - 3, sy(t) - 0.5, 6, 1); ctx.fillText(t, sx(t) - 3, sy(0) + 13); }
  ctx.fillStyle = C.ink; ctx.font = "italic 13px serif"; ctx.fillText("Re α", WS - 34, sy(0) - 6); ctx.fillText("Im α", sx(0) + 6, 13);
  if (overlay) overlay(ctx, sx, sy, WS / (2 * L));
  ctx.fillStyle = C.muted; ctx.font = "11px sans-serif"; ctx.fillText(label, 6, WS - 6); ctx.restore();
}
const axes = (xn, yn) => ({ x: { name: xn, withLabel: true, strokeColor: "#9ca3af", label: { position: "rt", offset: [-14, 14], fontSize: 14, strokeColor: C.ink }, ticks: { minorTicks: 0, strokeColor: "#9ca3af", label: { fontSize: 10, strokeColor: C.muted } } },
  y: { name: yn, withLabel: true, strokeColor: "#9ca3af", label: { position: "rt", offset: [8, -6], fontSize: 14, strokeColor: C.ink }, ticks: { minorTicks: 0, strokeColor: "#9ca3af", label: { fontSize: 10, strokeColor: C.muted } } } });
const board = (div, bb, xn, yn) => JXG.JSXGraph.initBoard(div, { boundingbox: bb, keepAspectRatio: false, axis: true, showCopyright: false, showNavigation: false, pan: { enabled: false }, zoom: { enabled: false }, defaultAxes: axes(xn, yn) });
const LF = [0]; for (let n = 1; n <= 400; n++) LF[n] = LF[n - 1] + Math.log(n);
const pois = (n, m) => (m <= 0 ? (n === 0 ? 1 : 0) : Math.exp(n * Math.log(m) - m - LF[n]));
// P(n) bars + Poisson reference with the same mean; returns an update function
function countsPlot(bP, cbP) {
  let P = [1], nShow = 10, mean = 0;
  const bars = bP.create("curve", [[0], [0]], { fixed: true, highlight: false, strokeColor: "#c2410c", strokeWidth: 1, fillColor: "#f0a46a", fillOpacity: 0.85 });
  bars.updateDataArray = function () { const xs = [], ys = []; for (let n = 0; n <= nShow; n++) { xs.push(n - 0.38, n - 0.38, n + 0.38, n + 0.38, NaN); ys.push(0, P[n], P[n], 0, NaN); } this.dataX = xs; this.dataY = ys; };
  const pl = bP.create("curve", [[0], [0]], { fixed: true, highlight: false, strokeColor: C.obs, strokeWidth: 2, dash: 2, visible: () => cbP.checked });
  pl.updateDataArray = function () { const xs = [], ys = []; for (let n = 0; n <= nShow; n++) { xs.push(n); ys.push(pois(n, mean)); } this.dataX = xs; this.dataY = ys; };
  for (let n = 0; n <= 80; n++) bP.create("point", [n, () => pois(n, mean)], { fixed: true, highlight: false, withLabel: false, size: 2.5, strokeColor: C.obs, fillColor: "#fff", visible: () => cbP.checked && n <= nShow });
  const leg = bP.create("text", [0, 0, () => "<span style='color:#c2410c'>■</span> state" + (cbP.checked ? " &nbsp; <span style='color:" + C.obs + "'>○</span> Poisson, same ⟨n⟩" : "")], { fixed: true, highlight: false, fontSize: 12, strokeColor: C.ink, anchorX: "right", anchorY: "top" });
  return (Pnew) => {
    P = Pnew; mean = 0; let m2 = 0, cum = 0, nEnd = 0; P.forEach((p, n) => { mean += n * p; m2 += n * n * p; });
    for (let n = 0; n < P.length; n++) { cum += P[n]; if (cum > 0.999) { nEnd = n; break; } }
    const varn = m2 - mean * mean; nShow = Math.min(80, Math.max(10, Math.ceil(Math.max(nEnd, mean + 4 * Math.sqrt(varn)))));
    let ymax = 0; for (let n = 0; n <= nShow; n++) ymax = Math.max(ymax, P[n], cbP.checked ? pois(n, mean) : 0); ymax *= 1.18;
    bP.setBoundingBox([-0.06 * nShow - 1, ymax, nShow + 1, -0.08 * ymax], false); leg.setPosition(JXG.COORDS_BY_USER, [nShow + 0.6, ymax * 0.97]); bP.update();
    return { mean, varn };
  };
}
const sA = K.slider("|α|", 0, CFG.ampMax, 0.01, CFG.amp), sG = K.slider("arg α", 0, 360, 1, CFG.arg, (v) => v + "°");
const sR = K.slider("r", 0, CFG.rMax, 0.01, CFG.r), sT = K.slider("θ", 0, 360, 1, CFG.th, (v) => v + "°");
const sel = K.select([["W", "Wigner W"], ["Q", "Husimi Q"]]), cbV = K.check("vacuum circle"), cbP = K.check("Poisson, same mean");
K.root.append(panel);
const bP = board(pdiv, [-1, 1, 20, -0.08], "n", "P(n)"), upd = countsPlot(bP, cbP);
// c_n from (μ a + ν a†)|α,ξ⟩ = γ|α,ξ⟩:  μ√(n+1) c_{n+1} = γ c_n − ν √n c_{n−1}
function amplitudes(al, r, th) {
  const mu = Math.cosh(r), nu = [Math.cos(th) * Math.sinh(r), Math.sin(th) * Math.sinh(r)];
  const mul = (p, q) => [p[0] * q[0] - p[1] * q[1], p[0] * q[1] + p[1] * q[0]], ac = [al[0], -al[1]];
  const g = [al[0] * mu + mul(ac, nu)[0], al[1] * mu + mul(ac, nu)[1]];
  const t = Math.tanh(r), a2c = mul(ac, ac), e = mul(a2c, [Math.cos(th) * t, Math.sin(th) * t]);   // α*² e^{iθ} tanh r
  const amp0 = Math.exp(-(al[0] ** 2 + al[1] ** 2) / 2 - e[0] / 2) / Math.sqrt(mu), ph0 = -e[1] / 2;
  const c = [[amp0 * Math.cos(ph0), amp0 * Math.sin(ph0)]];
  c[1] = [mul(g, c[0])[0] / mu, mul(g, c[0])[1] / mu];
  for (let n = 1; n < CFG.N - 1; n++) { const a1 = mul(g, c[n]), b1 = mul(nu, c[n - 1]), s = Math.sqrt(n);
    c[n + 1] = [(a1[0] - s * b1[0]) / (mu * Math.sqrt(n + 1)), (a1[1] - s * b1[1]) / (mu * Math.sqrt(n + 1))]; }
  return { P: c.map((z) => z[0] ** 2 + z[1] ** 2), g };
}
function update() {
  const A = +sA.value, ag = (+sG.value * Math.PI) / 180, r = +sR.value, th = (+sT.value * Math.PI) / 180, al = [A * Math.cos(ag), A * Math.sin(ag)];
  const { P, g } = amplitudes(al, r, th), st = upd(P);
  // Wigner function: Gaussian, mean α, covariance ¼ R(θ/2) diag(e^{-2r}, e^{2r}) R(θ/2)^T  (X_{θ/2} is squeezed)
  const c = Math.cos(th / 2), s = Math.sin(th / 2), e1 = Math.exp(-2 * r) / 4, e2 = Math.exp(2 * r) / 4;
  // Husimi Q: the same Gaussian smoothed by the vacuum, covariance + ¼·1
  const isQ = sel.value === "Q", q = isQ ? 0.25 : 0;
  const vxx = c * c * e1 + s * s * e2 + q, vxy = c * s * (e1 - e2), vyy = s * s * e1 + c * c * e2 + q, det = vxx * vyy - vxy * vxy, nrm = 1 / (2 * Math.PI * Math.sqrt(det));
  heat((x, y) => { const dx = x - al[0], dy = y - al[1]; return nrm * Math.exp(-0.5 * (vyy * dx * dx - 2 * vxy * dx * dy + vxx * dy * dy) / det); }, CFG.L, isQ ? 1 / Math.PI : 2 / Math.PI, isQ ? "Q(α), colour scale 0 … 1/π" : "W(α), colour scale ±2/π",
    (ctx, sx, sy, k) => { if (!cbV.checked) return; ctx.setLineDash([4, 3]); ctx.strokeStyle = C.obs; ctx.beginPath(); ctx.arc(sx(al[0]), sy(al[1]), 0.5 * k, 0, 7); ctx.stroke(); ctx.setLineDash([]); });
  const nbar = A * A + Math.sinh(r) ** 2, F = st.varn / st.mean;
  panel.textContent =
`γ = α cosh r + α* e^{iθ} sinh r = ${f(g[0])} ${g[1] < 0 ? "−" : "+"} ${f(Math.abs(g[1]))}i
⟨n⟩ = ${f(st.mean)}  (|α|² + sinh²r = ${f(nbar)})   Δ²n = ${f(st.varn)}   Fano Δ²n/⟨n⟩ = ${f(F)}   ${F < 1 - 1e-6 ? "sub-Poissonian" : F > 1 + 1e-6 ? "super-Poissonian" : "Poissonian"}
Var(X_{θ/2}) = ${f(e1)},  Var(X_{θ/2+π/2}) = ${f(e2)}   (vacuum 0.250)`;
}
for (const x of [sA, sG, sR, sT]) x.addEventListener("input", update);
for (const x of [sel, cbV, cbP]) x.onchange = update;
update();
```

### Cat states

A **cat state** is a superposition of two coherent states of equal amplitude $\alpha$ (real) and opposite phases $\pm\varphi$,

$$\ket{\rm CAT} = \frac{N}{\sqrt2}\Big(\ket{\alpha e^{i\varphi}}+\ket{\alpha e^{-i\varphi}}\Big).$$

**Normalization.** The overlap of the two components is $\langle\alpha e^{-i\varphi}|\alpha e^{i\varphi}\rangle = \exp\big(-\alpha^2+\alpha^2e^{2i\varphi}\big) = e^{-2\alpha^2\sin^2\varphi}\,e^{i\alpha^2\sin2\varphi}$. Requiring $\langle{\rm CAT}|{\rm CAT}\rangle = N^2\big(1+\mathrm{Re}\,\langle\alpha e^{-i\varphi}|\alpha e^{i\varphi}\rangle\big) = 1$ gives

$$N^2(\varphi) = \frac{1}{1+\cos\big(\alpha^2\sin2\varphi\big)\,e^{-p_\varphi^2}}, \qquad p_\varphi = \sqrt2\,\alpha\sin\varphi .$$

The two components sit at the same position $x = \sqrt2\alpha\cos\varphi$ and at momenta $\pm p_\varphi$; for $p_\varphi\gg1$ they no longer overlap and $N^2\to1$.

**Photon number distribution.** With $\langle m|\beta\rangle = e^{-|\beta|^2/2}\beta^m/\sqrt{m!}$,

$$P_m = |\langle m|{\rm CAT}\rangle|^2 = \frac{N^2}{2}\Big|\langle m|\alpha e^{i\varphi}\rangle+\langle m|\alpha e^{-i\varphi}\rangle\Big|^2 = \Big|A_m^{1/2}e^{im\varphi}+A_m^{1/2}e^{-im\varphi}\Big|^2 = 4A_m\cos^2(m\varphi), \qquad A_m = \frac12N^2\frac{\alpha^{2m}}{m!}e^{-\alpha^2}.$$

The Poisson distribution of a coherent state is modulated by $\cos^2(m\varphi)$. For $\varphi = \pi/2$ (the even cat $\ket{i\alpha}+\ket{-i\alpha}$) only even $m$ survive; for $\varphi\to0$ the two components merge into $\ket\alpha$ and the statistics become Poissonian again. The **Fano factor** $\Delta^2n/\bar n$ as a function of $\varphi$ (bottom panel of the plot below) therefore starts at one, oscillates between sub- and super-Poissonian values, and returns to one at $\varphi = \pi$.

**Wigner function.** Writing the coherent-state wavefunctions as $\psi_\beta(x) = \pi^{-1/4}e^{\frac12(\beta^2-|\beta|^2)}e^{-\frac12(x-\sqrt2\beta)^2}$,

$$\psi_{\rm CAT}(x) = \frac{1}{\pi^{1/4}}\frac{N}{\sqrt2}\,e^{-\alpha^2\sin^2\varphi}\,e^{\frac i2\alpha^2\sin2\varphi}\Big(e^{-\frac12(x-\sqrt2\alpha e^{i\varphi})^2}+e^{-i\alpha^2\sin2\varphi}\,e^{-\frac12(x-\sqrt2\alpha e^{-i\varphi})^2}\Big).$$

Inserting this into the definition of $W$, the Wigner function is the sum of the two coherent-state Gaussians and an interference term,

$$W_{\rm CAT} = \frac{N^2}{2}\Big(W_{\ket{\alpha e^{i\varphi}}}+W_{\ket{\alpha e^{-i\varphi}}}+W_I\Big), \qquad W_I = \frac2\pi\cos\Big(2\sqrt2\,\alpha\sin\varphi\,\big(x-\tfrac{1}{\sqrt2}\alpha\cos\varphi\big)\Big)\,e^{-(x-\sqrt2\alpha\cos\varphi)^2-p^2},$$

with $W_{\ket\beta} = \frac1\pi e^{-(x-\sqrt2\,\mathrm{Re}\beta)^2-(p-\sqrt2\,\mathrm{Im}\beta)^2}$. The interference term sits midway between the two components; its fringes run perpendicular to the line joining them, with period $\pi/(\sqrt2\alpha\sin\varphi)$ in $x$. Because $W_I$ takes negative values, the cat state is nonclassical.

**$Q$ function.** From $\langle\beta|\gamma\rangle = e^{-\frac12|\beta-\gamma|^2}e^{i\,\mathrm{Im}(\beta^*\gamma)}$,

$$Q(\beta) = \frac1\pi\,\bigg|\langle\beta|\,\frac{N}{\sqrt2}\Big(\ket{\alpha e^{i\varphi}}+\ket{\alpha e^{-i\varphi}}\Big)\bigg|^2 .$$

$Q$ shows two smooth humps; the interference survives only as a weak modulation in the overlap region, since the Gaussian smoothing washes out the fringes.

```dataviewjs
// ===== CONFIG =====
const CFG = { amp: 2, ampMax: 3.5, phi: 90, L: 4.5, N: 200 };
// ==================
// ---- loader (leave as is) ----
const LIB = "FUW/lib/";
const load = (src) => new Promise((ok, no) => { const s = document.createElement("script"); s.src = src; s.onload = ok; s.onerror = () => no(new Error("could not load " + src)); document.head.append(s); });
const libPath = async (n) => { const here = dv.current().file.folder, up = here.includes("/") ? here.slice(0, here.lastIndexOf("/")) + "/" : ""; for (const p of [LIB + n, "lib/" + n, here + "/lib/" + n, up + "lib/" + n, ...app.vault.getFiles().filter((x) => x.path.endsWith("lib/" + n)).map((x) => x.path)]) if (await app.vault.adapter.exists(p)) return p; throw new Error("lib/" + n + " not found in this vault (is the FUW/lib folder synced to this computer?)"); };
if (!window.JXG) await (window.__jxg ??= libPath("jsxgraphcore.js").then((p) => load(app.vault.adapter.getResourcePath(p))).catch(() => load("https://cdn.jsdelivr.net/npm/jsxgraph@1.10.1/distrib/jsxgraphcore.js")).catch((e) => { window.__jxg = null; throw e; }));
if (!window.RL) await (window.__rl ??= libPath("rlti.js").then((p) => load(app.vault.adapter.getResourcePath(p))).catch((e) => { window.__rl = null; throw e; }));
const K = await RL.init(dv), { f, el, C } = K;
// ---- shared plotting helpers ----
const GAP = 12, WS = Math.min(320, Math.floor((K.W - GAP) / 2)), WP = K.W - WS - GAP, dpr = window.devicePixelRatio || 1;
const box = "background:#fff;border:1px solid #e5e7eb;border-radius:10px";
const row = el("div", `display:flex;gap:${GAP}px;align-items:flex-start;margin-top:6px;flex-wrap:wrap`);
const cv = el("canvas", `width:${WS}px;height:${WS}px;${box}`); cv.width = Math.round(WS * dpr); cv.height = Math.round(WS * dpr);
const pdiv = el("div", `width:${WP}px;height:${WS}px;${box};touch-action:none`);
row.append(cv, pdiv); K.root.append(row);
const panel = el("div", "font-family:var(--font-monospace,monospace);font-size:0.8em;line-height:1.55;white-space:pre-wrap;color:var(--text-normal);margin-top:6px");
const stops = [[-1, [31, 95, 168]], [-0.5, [127, 166, 212]], [0, [248, 248, 248]], [0.5, [240, 164, 106]], [1, [194, 65, 12]]];
const cmap = (t) => { t = Math.max(-1, Math.min(1, t)); let i = 0; while (i < stops.length - 2 && t > stops[i + 1][0]) i++; const [t0, c0] = stops[i], [t1, c1] = stops[i + 1], u = (t - t0) / (t1 - t0); return c0.map((v, j) => Math.round(v + u * (c1[j] - v))); };
function heat(fun, L, vmax, label, overlay) {   // fun(x, y) on the α-plane, x = Re α, y = Im α
  const ctx = cv.getContext("2d"), Wd = cv.width, Hd = cv.height, img = ctx.createImageData(Wd, Hd), d = img.data;
  for (let py = 0; py < Hd; py++) { const y = L - (2 * L * py) / Hd;
    for (let px = 0; px < Wd; px++) { const x = -L + (2 * L * px) / Wd, [R, G, B] = cmap(fun(x, y) / vmax), o = 4 * (py * Wd + px); d[o] = R; d[o + 1] = G; d[o + 2] = B; d[o + 3] = 255; } }
  ctx.putImageData(img, 0, 0); ctx.save(); ctx.scale(dpr, dpr);
  const sx = (x) => ((x + L) / (2 * L)) * WS, sy = (y) => ((L - y) / (2 * L)) * WS;
  ctx.strokeStyle = "#9ca3af"; ctx.lineWidth = 1; ctx.beginPath(); ctx.moveTo(0, sy(0)); ctx.lineTo(WS, sy(0)); ctx.moveTo(sx(0), 0); ctx.lineTo(sx(0), WS); ctx.stroke();
  ctx.fillStyle = "#6b7280"; ctx.font = "10px sans-serif";
  for (let t = -Math.floor(L); t <= Math.floor(L); t++) if (t) { ctx.fillRect(sx(t) - 0.5, sy(0) - 3, 1, 6); ctx.fillRect(sx(0) - 3, sy(t) - 0.5, 6, 1); ctx.fillText(t, sx(t) - 3, sy(0) + 13); }
  ctx.fillStyle = C.ink; ctx.font = "italic 13px serif"; ctx.fillText("Re α", WS - 34, sy(0) - 6); ctx.fillText("Im α", sx(0) + 6, 13);
  if (overlay) overlay(ctx, sx, sy, WS / (2 * L));
  ctx.fillStyle = C.muted; ctx.font = "11px sans-serif"; ctx.fillText(label, 6, WS - 6); ctx.restore();
}
const axes = (xn, yn) => ({ x: { name: xn, withLabel: true, strokeColor: "#9ca3af", label: { position: "rt", offset: [-14, 14], fontSize: 14, strokeColor: C.ink }, ticks: { minorTicks: 0, strokeColor: "#9ca3af", label: { fontSize: 10, strokeColor: C.muted } } },
  y: { name: yn, withLabel: true, strokeColor: "#9ca3af", label: { position: "rt", offset: [8, -6], fontSize: 14, strokeColor: C.ink }, ticks: { minorTicks: 0, strokeColor: "#9ca3af", label: { fontSize: 10, strokeColor: C.muted } } } });
const board = (div, bb, xn, yn) => JXG.JSXGraph.initBoard(div, { boundingbox: bb, keepAspectRatio: false, axis: true, showCopyright: false, showNavigation: false, pan: { enabled: false }, zoom: { enabled: false }, defaultAxes: axes(xn, yn) });
const LF = [0]; for (let n = 1; n <= 400; n++) LF[n] = LF[n - 1] + Math.log(n);
const pois = (n, m) => (m <= 0 ? (n === 0 ? 1 : 0) : Math.exp(n * Math.log(m) - m - LF[n]));
// P(n) bars + Poisson reference with the same mean; returns an update function
function countsPlot(bP, cbP) {
  let P = [1], nShow = 10, mean = 0;
  const bars = bP.create("curve", [[0], [0]], { fixed: true, highlight: false, strokeColor: "#c2410c", strokeWidth: 1, fillColor: "#f0a46a", fillOpacity: 0.85 });
  bars.updateDataArray = function () { const xs = [], ys = []; for (let n = 0; n <= nShow; n++) { xs.push(n - 0.38, n - 0.38, n + 0.38, n + 0.38, NaN); ys.push(0, P[n], P[n], 0, NaN); } this.dataX = xs; this.dataY = ys; };
  const pl = bP.create("curve", [[0], [0]], { fixed: true, highlight: false, strokeColor: C.obs, strokeWidth: 2, dash: 2, visible: () => cbP.checked });
  pl.updateDataArray = function () { const xs = [], ys = []; for (let n = 0; n <= nShow; n++) { xs.push(n); ys.push(pois(n, mean)); } this.dataX = xs; this.dataY = ys; };
  for (let n = 0; n <= 80; n++) bP.create("point", [n, () => pois(n, mean)], { fixed: true, highlight: false, withLabel: false, size: 2.5, strokeColor: C.obs, fillColor: "#fff", visible: () => cbP.checked && n <= nShow });
  const leg = bP.create("text", [0, 0, () => "<span style='color:#c2410c'>■</span> state" + (cbP.checked ? " &nbsp; <span style='color:" + C.obs + "'>○</span> Poisson, same ⟨n⟩" : "")], { fixed: true, highlight: false, fontSize: 12, strokeColor: C.ink, anchorX: "right", anchorY: "top" });
  return (Pnew) => {
    P = Pnew; mean = 0; let m2 = 0, cum = 0, nEnd = 0; P.forEach((p, n) => { mean += n * p; m2 += n * n * p; });
    for (let n = 0; n < P.length; n++) { cum += P[n]; if (cum > 0.999) { nEnd = n; break; } }
    const varn = m2 - mean * mean; nShow = Math.min(80, Math.max(10, Math.ceil(Math.max(nEnd, mean + 4 * Math.sqrt(varn)))));
    let ymax = 0; for (let n = 0; n <= nShow; n++) ymax = Math.max(ymax, P[n], cbP.checked ? pois(n, mean) : 0); ymax *= 1.18;
    bP.setBoundingBox([-0.06 * nShow - 1, ymax, nShow + 1, -0.08 * ymax], false); leg.setPosition(JXG.COORDS_BY_USER, [nShow + 0.6, ymax * 0.97]); bP.update();
    return { mean, varn };
  };
}
const sA = K.slider("α", 0.05, CFG.ampMax, 0.01, CFG.amp), sF = K.slider("φ", 0, 180, 1, CFG.phi, (v) => v + "°");
const sel = K.select([["W", "Wigner W"], ["Q", "Husimi Q"]]), cbP = K.check("Poisson, same mean");
const fdiv = el("div", `width:${K.W}px;height:${Math.round(WS * 0.75)}px;${box};touch-action:none;margin-top:${GAP}px`);
K.root.append(fdiv, panel);
const bP = board(pdiv, [-1, 1, 20, -0.08], "m", "P(m)"), upd = countsPlot(bP, cbP);
// photon statistics:  P_m = 2 N² e^{−α²} α^{2m}/m! cos²(mφ)
const N2 = (a, ph) => 1 / (1 + Math.cos(a * a * Math.sin(2 * ph)) * Math.exp(-2 * a * a * Math.sin(ph) ** 2));
const Pm = (a, ph) => { const n2 = N2(a, ph), out = []; for (let m = 0; m < CFG.N; m++) out.push(2 * n2 * Math.exp(-a * a + 2 * m * Math.log(a) - LF[m]) * Math.cos(m * ph) ** 2); return out; };
const fano = (a, ph) => { const P = Pm(a, ph); let m1 = 0, m2 = 0; P.forEach((p, m) => { m1 += m * p; m2 += m * m * p; }); return (m2 - m1 * m1) / m1; };
// Fano factor vs φ
const bF = board(fdiv, [-8, 3, 188, -0.2], "φ°", "Δ²n / n̄");
bF.create("line", [[0, 1], [1, 1]], { fixed: true, highlight: false, strokeColor: C.muted, dash: 2 });
const fcur = bF.create("functiongraph", [(d) => fano(+sA.value, (d * Math.PI) / 180), 0.5, 179.5], { fixed: true, highlight: false, strokeColor: C.obs, strokeWidth: 2.2 });
const fdot = bF.create("point", [() => +sF.value, () => fano(+sA.value, (Math.max(0.5, Math.min(179.5, +sF.value)) * Math.PI) / 180)], { fixed: true, highlight: false, withLabel: false, size: 4, strokeColor: C.sel, fillColor: C.sel });
// complex helpers
const cm = (p, q) => [p[0] * q[0] - p[1] * q[1], p[0] * q[1] + p[1] * q[0]], cexp = (z) => { const e = Math.exp(z[0]); return [e * Math.cos(z[1]), e * Math.sin(z[1])]; };
function update() {
  const a = +sA.value, ph = (+sF.value * Math.PI) / 180, n2 = N2(a, ph), b1 = [a * Math.cos(ph), a * Math.sin(ph)], b2 = [a * Math.cos(ph), -a * Math.sin(ph)];
  const st = upd(Pm(a, ph));
  // ⟨β2|β1⟩ = e^{−2α² sin²φ} e^{iα² sin 2φ}
  const ov = cexp([-2 * a * a * Math.sin(ph) ** 2, a * a * Math.sin(2 * ph)]);
  if (sel.value === "W") heat((x, y) => {
      const d1 = (x - b1[0]) ** 2 + (y - b1[1]) ** 2, d2 = (x - b2[0]) ** 2 + (y - b2[1]) ** 2;
      const zz = cm([x - b1[0], y - b1[1]], [x - b2[0], -y + b2[1]]) /* (α − β1)(α* − β2*) */, cr = cm(ov, cexp([-2 * zz[0], -2 * zz[1]]));
      return (n2 / 2) * (2 / Math.PI) * (Math.exp(-2 * d1) + Math.exp(-2 * d2) + 2 * cr[0]);
    }, CFG.L, 2 / Math.PI, "W(α), colour scale ±2/π");
  else heat((x, y) => {   // Q(α) = (N²/2π) |⟨α|β1⟩ + ⟨α|β2⟩|²,   ⟨α|β⟩ = e^{−|α−β|²/2} e^{i Im(α*β)}
      const t = (b) => cexp([-((x - b[0]) ** 2 + (y - b[1]) ** 2) / 2, x * b[1] - y * b[0]]), s1 = t(b1), s2 = t(b2);
      return (n2 / (2 * Math.PI)) * ((s1[0] + s2[0]) ** 2 + (s1[1] + s2[1]) ** 2);
    }, CFG.L, 1 / Math.PI, "Q(α), colour scale 0 … 1/π");
  let fmax = 0; for (let d = 1; d < 180; d += 1) fmax = Math.max(fmax, fano(a, (d * Math.PI) / 180));
  bF.setBoundingBox([-8, Math.max(2, fmax * 1.12), 188, -0.12 * Math.max(2, fmax * 1.12)], false); bF.update();
  const F = st.varn / st.mean;
  panel.textContent =
`N² = 1/(1 + cos(α² sin 2φ) e^{−2α² sin²φ}) = ${f(n2)}     p_φ = ±√2 α sin φ = ±${f(Math.SQRT2 * a * Math.sin(ph))}
⟨n⟩ = ${f(st.mean)}   Δ²n = ${f(st.varn)}   Fano Δ²n/⟨n⟩ = ${f(F)}   ${F < 1 - 1e-6 ? "sub-Poissonian" : F > 1 + 1e-6 ? "super-Poissonian" : "Poissonian"}`;
}
for (const x of [sA, sF]) x.addEventListener("input", update);
sel.onchange = update; cbP.onchange = update;
update();
```



**Further reading**

- [Properties of squeezed number states and squeezed thermal states](https://journals.aps.org/pra/pdf/10.1103/PhysRevA.40.2494)
- W. P. Schleich, *Quantum Optics in Phase Space* (Wiley-VCH, 2001)
- [Oscillations in photon distribution of squeezed states and interference in phase space](https://sci-hub.pl/storage/2024/1035/07d7a00c2dd7648a0b842a38071397b3/schleich1987.pdf)
- [Area of overlap and interference in phase space versus Wigner pseudoprobabilities](https://sci-hub.pl/10.1103/PhysRevA.38.1177)
- [Sub-Planck Structure in Phase Space and Its Relevance for Quantum Decoherence](https://sci-hub.pl/10.1038/35089017)

# Lecture 9

## Quantum state tomography

Balanced homodyne detection with local-oscillator phase $\theta$ measures the rotated quadrature

$$\hat x_\theta = \hat x\cos\theta+\hat p\sin\theta = \frac{1}{\sqrt2}\big(\hat a e^{-i\theta}+\hat a^\dagger e^{i\theta}\big),$$

and repeating the measurement gives its probability distribution $w_\theta(x_\theta)$. Since the marginals of $W$ are the quadrature distributions, $w_\theta$ is the integral of $W$ along the lines perpendicular to the $x_\theta$ axis,

$$w_\theta(x_\theta) = \int dx\,dp\;\delta(x_\theta-x\cos\theta-p\sin\theta)\,W(x,p).$$

This is the **Radon transform** of $W$. Quantum state tomography inverts it: from $w_\theta$ for all $\theta\in[-\pi/2,\pi/2)$ we reconstruct $W$, and therefore $\hat\rho$.

**Fourier slice theorem.** The one-dimensional Fourier transform of a marginal is a slice through the two-dimensional Fourier transform of $W$:

$$\int dx_\theta\, e^{it x_\theta}\,w_\theta(x_\theta) = \int dx\int dp\; e^{it(x\cos\theta+p\sin\theta)}\,W(x,p) = \tilde W(\zeta,\eta)\Big|_{\zeta=t\cos\theta,\ \eta=t\sin\theta}, \qquad \\ \tilde W(\zeta,\eta)=\int dx\int dp\; e^{i(\zeta x+\eta p)}W(x,p).$$

As $\theta$ runs over $[-\pi/2,\pi/2)$ and $t$ over $\mathbb R$, the point $(\zeta,\eta)$ covers the whole Fourier plane once, with $d\zeta\,d\eta = |t|\,dt\,d\theta$.

**Inversion.** Inverting the two-dimensional Fourier transform in these polar coordinates,

$$W(x',p') = \frac{1}{(2\pi)^2}\int_{-\pi/2}^{\pi/2}d\theta\int_{-\infty}^{\infty}dt\,|t|\; e^{-it(x'\cos\theta+p'\sin\theta)}\int dx_\theta\, e^{it x_\theta}\,w_\theta(x_\theta).$$

To check it, insert the Fourier slice theorem and exchange the order of integration:

$$\frac{1}{(2\pi)^2}\int dx\int dp\;W(x,p)\underbrace{\int dt\,|t|\int d\theta\; e^{i(x-x')\zeta+i(p-p')\eta}}_{(2\pi)^2\,\delta(x-x')\,\delta(p-p')} = W(x',p').$$

Doing the $t$-integral first gives the **filtered back-projection** used in practice,

$$W(x',p') = \frac{1}{(2\pi)^2}\int_{-\pi/2}^{\pi/2}d\theta\int dx_\theta\; w_\theta(x_\theta)\,K\big(x_\theta-x'\cos\theta-p'\sin\theta\big), \qquad K(u) = \int dt\,|t|\,e^{itu}.$$

$K$ diverges and has to be regularised by a cutoff $|t|<k_c$. Each measured value $x_\theta$ is smeared ("back-projected") along the line $x'\cos\theta+p'\sin\theta = x_\theta$ with the filter $K$, and the contributions from all phases are summed. The negative regions of $W$ appear only after summing over $\theta$; no single marginal is negative.

**Radon transform of a cat state.** Below, the left panel shows $W$ of $\frac{N}{\sqrt2}(\ket{\alpha e^{i\varphi}}+\ket{\alpha e^{-i\varphi}})$ with the $x_\theta$ axis dashed. The right panel shows the marginal $w_\theta$, and the bottom panel is the **sinogram**: all marginals stacked against $\theta$. Each coherent component traces a sinusoid $x_\theta = \sqrt2\,\mathrm{Re}(\beta e^{-i\theta})$. When the $x_\theta$ axis is perpendicular to the line joining the components, both project onto the same $x_\theta$ and the marginal shows interference fringes, with period $\pi/(\sqrt2\alpha\sin\varphi)$ for $\theta=0$. At other angles the two peaks are separated and the fringes are invisible.

```dataviewjs
// ===== CONFIG =====
const CFG = { amp: 2, ampMax: 3.5, phi: 90, th: 0, L: 4.5 };
// ==================
// ---- loader (leave as is) ----
const LIB = "FUW/lib/";
const load = (src) => new Promise((ok, no) => { const s = document.createElement("script"); s.src = src; s.onload = ok; s.onerror = () => no(new Error("could not load " + src)); document.head.append(s); });
const libPath = async (n) => { const here = dv.current().file.folder, up = here.includes("/") ? here.slice(0, here.lastIndexOf("/")) + "/" : ""; for (const p of [LIB + n, "lib/" + n, here + "/lib/" + n, up + "lib/" + n, ...app.vault.getFiles().filter((x) => x.path.endsWith("lib/" + n)).map((x) => x.path)]) if (await app.vault.adapter.exists(p)) return p; throw new Error("lib/" + n + " not found in this vault (is the FUW/lib folder synced to this computer?)"); };
if (!window.JXG) await (window.__jxg ??= libPath("jsxgraphcore.js").then((p) => load(app.vault.adapter.getResourcePath(p))).catch(() => load("https://cdn.jsdelivr.net/npm/jsxgraph@1.10.1/distrib/jsxgraphcore.js")).catch((e) => { window.__jxg = null; throw e; }));
if (!window.RL) await (window.__rl ??= libPath("rlti.js").then((p) => load(app.vault.adapter.getResourcePath(p))).catch((e) => { window.__rl = null; throw e; }));
const K = await RL.init(dv), { f, el, C } = K;
// ---- shared plotting helpers ----
const GAP = 12, WS = Math.min(320, Math.floor((K.W - GAP) / 2)), WP = K.W - WS - GAP, dpr = window.devicePixelRatio || 1;
const box = "background:#fff;border:1px solid #e5e7eb;border-radius:10px";
const row = el("div", `display:flex;gap:${GAP}px;align-items:flex-start;margin-top:6px;flex-wrap:wrap`);
const cv = el("canvas", `width:${WS}px;height:${WS}px;${box}`); cv.width = Math.round(WS * dpr); cv.height = Math.round(WS * dpr);
const pdiv = el("div", `width:${WP}px;height:${WS}px;${box};touch-action:none`);
row.append(cv, pdiv); K.root.append(row);
const panel = el("div", "font-family:var(--font-monospace,monospace);font-size:0.8em;line-height:1.55;white-space:pre-wrap;color:var(--text-normal);margin-top:6px");
const stops = [[-1, [31, 95, 168]], [-0.5, [127, 166, 212]], [0, [248, 248, 248]], [0.5, [240, 164, 106]], [1, [194, 65, 12]]];
const cmap = (t) => { t = Math.max(-1, Math.min(1, t)); let i = 0; while (i < stops.length - 2 && t > stops[i + 1][0]) i++; const [t0, c0] = stops[i], [t1, c1] = stops[i + 1], u = (t - t0) / (t1 - t0); return c0.map((v, j) => Math.round(v + u * (c1[j] - v))); };
function heat(fun, L, vmax, label, overlay) {   // fun(x, y) on the α-plane, x = Re α, y = Im α
  const ctx = cv.getContext("2d"), Wd = cv.width, Hd = cv.height, img = ctx.createImageData(Wd, Hd), d = img.data;
  for (let py = 0; py < Hd; py++) { const y = L - (2 * L * py) / Hd;
    for (let px = 0; px < Wd; px++) { const x = -L + (2 * L * px) / Wd, [R, G, B] = cmap(fun(x, y) / vmax), o = 4 * (py * Wd + px); d[o] = R; d[o + 1] = G; d[o + 2] = B; d[o + 3] = 255; } }
  ctx.putImageData(img, 0, 0); ctx.save(); ctx.scale(dpr, dpr);
  const sx = (x) => ((x + L) / (2 * L)) * WS, sy = (y) => ((L - y) / (2 * L)) * WS;
  ctx.strokeStyle = "#9ca3af"; ctx.lineWidth = 1; ctx.beginPath(); ctx.moveTo(0, sy(0)); ctx.lineTo(WS, sy(0)); ctx.moveTo(sx(0), 0); ctx.lineTo(sx(0), WS); ctx.stroke();
  ctx.fillStyle = "#6b7280"; ctx.font = "10px sans-serif";
  for (let t = -Math.floor(L); t <= Math.floor(L); t++) if (t) { ctx.fillRect(sx(t) - 0.5, sy(0) - 3, 1, 6); ctx.fillRect(sx(0) - 3, sy(t) - 0.5, 6, 1); ctx.fillText(t, sx(t) - 3, sy(0) + 13); }
  ctx.fillStyle = C.ink; ctx.font = "italic 13px serif"; ctx.fillText("Re α", WS - 34, sy(0) - 6); ctx.fillText("Im α", sx(0) + 6, 13);
  if (overlay) overlay(ctx, sx, sy, WS / (2 * L));
  ctx.fillStyle = C.muted; ctx.font = "11px sans-serif"; ctx.fillText(label, 6, WS - 6); ctx.restore();
}
const axes = (xn, yn) => ({ x: { name: xn, withLabel: true, strokeColor: "#9ca3af", label: { position: "rt", offset: [-14, 14], fontSize: 14, strokeColor: C.ink }, ticks: { minorTicks: 0, strokeColor: "#9ca3af", label: { fontSize: 10, strokeColor: C.muted } } },
  y: { name: yn, withLabel: true, strokeColor: "#9ca3af", label: { position: "rt", offset: [8, -6], fontSize: 14, strokeColor: C.ink }, ticks: { minorTicks: 0, strokeColor: "#9ca3af", label: { fontSize: 10, strokeColor: C.muted } } } });
const board = (div, bb, xn, yn) => JXG.JSXGraph.initBoard(div, { boundingbox: bb, keepAspectRatio: false, axis: true, showCopyright: false, showNavigation: false, pan: { enabled: false }, zoom: { enabled: false }, defaultAxes: axes(xn, yn) });
const LF = [0]; for (let n = 1; n <= 400; n++) LF[n] = LF[n - 1] + Math.log(n);
const sA = K.slider("α", 0.05, CFG.ampMax, 0.01, CFG.amp), sF = K.slider("φ", 0, 180, 1, CFG.phi, (v) => v + "°");
const sT = K.slider("θ", 0, 180, 1, CFG.th, (v) => v + "°");
// sinogram canvas: horizontal x_θ, vertical θ ∈ [0, π)
const HS = Math.round(WS * 0.7), sg = el("canvas", `width:${K.W}px;height:${HS}px;${box};margin-top:${GAP}px`);
sg.width = Math.round(K.W * dpr); sg.height = Math.round(HS * dpr);
K.root.append(sg, panel);
const XM = Math.SQRT2 * CFG.L;                       // x_θ range [−XM, XM]
const bM = board(pdiv, [-XM, 1, XM, -0.08], "x_θ", "w_θ");
// complex helpers
const cm = (p, q) => [p[0] * q[0] - p[1] * q[1], p[0] * q[1] + p[1] * q[0]], cexp = (z) => { const e = Math.exp(z[0]); return [e * Math.cos(z[1]), e * Math.sin(z[1])]; };
const N2 = (a, ph) => 1 / (1 + Math.cos(a * a * Math.sin(2 * ph)) * Math.exp(-2 * a * a * Math.sin(ph) ** 2));
// ψ_β(x) = π^{−1/4} exp[−½(x − √2 Re β)² + i(√2 Im β x − Re β Im β)]
const psi = (b, x) => cexp([-0.5 * (x - Math.SQRT2 * b[0]) ** 2 - 0.25 * Math.log(Math.PI), Math.SQRT2 * b[1] * x - b[0] * b[1]]);
const rot = (b, t) => [b[0] * Math.cos(t) + b[1] * Math.sin(t), -b[0] * Math.sin(t) + b[1] * Math.cos(t)];   // β e^{−iθ}
// marginal of x_θ = x cos θ + p sin θ:  |ψ_θ(x)|²,  ψ_θ = N/√2 (ψ_{β1 e^{−iθ}} + ψ_{β2 e^{−iθ}})
const marg = (a, ph, t, x) => { const b1 = rot([a * Math.cos(ph), a * Math.sin(ph)], t), b2 = rot([a * Math.cos(ph), -a * Math.sin(ph)], t), s1 = psi(b1, x), s2 = psi(b2, x);
  return (N2(a, ph) / 2) * ((s1[0] + s2[0]) ** 2 + (s1[1] + s2[1]) ** 2); };
bM.create("functiongraph", [(x) => marg(+sA.value, (+sF.value * Math.PI) / 180, (+sT.value * Math.PI) / 180, x), -XM, XM], { fixed: true, highlight: false, strokeColor: "#c2410c", strokeWidth: 2.4 });
function sinogram(a, ph, t0) {
  const ctx = sg.getContext("2d"), Wd = sg.width, Hd = sg.height, img = ctx.createImageData(Wd, Hd), d = img.data, M = [];
  let vmax = 0;
  for (let py = 0; py < Hd; py++) { const t = (Math.PI * py) / Hd, row = new Float32Array(Wd);
    for (let px = 0; px < Wd; px++) { row[px] = marg(a, ph, t, -XM + (2 * XM * px) / Wd); if (row[px] > vmax) vmax = row[px]; } M.push(row); }
  for (let py = 0; py < Hd; py++) for (let px = 0; px < Wd; px++) { const [R, G, B] = cmap(M[py][px] / vmax), o = 4 * (py * Wd + px); d[o] = R; d[o + 1] = G; d[o + 2] = B; d[o + 3] = 255; }
  ctx.putImageData(img, 0, 0); ctx.save(); ctx.scale(dpr, dpr);
  const yT = (t0 / Math.PI) * HS; ctx.strokeStyle = C.sel; ctx.lineWidth = 1.5; ctx.setLineDash([5, 3]); ctx.beginPath(); ctx.moveTo(0, yT); ctx.lineTo(K.W, yT); ctx.stroke(); ctx.setLineDash([]);
  ctx.fillStyle = C.muted; ctx.font = "11px sans-serif";
  ctx.fillText("sinogram w_θ(x_θ):  x_θ → from −" + f(XM) + " to " + f(XM) + ",   θ ↓ from 0° to 180°", 6, HS - 6); ctx.restore();
}
function update() {
  const a = +sA.value, ph = (+sF.value * Math.PI) / 180, t = (+sT.value * Math.PI) / 180, n2 = N2(a, ph);
  const b1 = [a * Math.cos(ph), a * Math.sin(ph)], b2 = [a * Math.cos(ph), -a * Math.sin(ph)];
  const ov = cexp([-2 * a * a * Math.sin(ph) ** 2, a * a * Math.sin(2 * ph)]);
  heat((x, y) => {
    const d1 = (x - b1[0]) ** 2 + (y - b1[1]) ** 2, d2 = (x - b2[0]) ** 2 + (y - b2[1]) ** 2;
    const zz = cm([x - b1[0], y - b1[1]], [x - b2[0], -y + b2[1]]), cr = cm(ov, cexp([-2 * zz[0], -2 * zz[1]]));
    return (n2 / 2) * (2 / Math.PI) * (Math.exp(-2 * d1) + Math.exp(-2 * d2) + 2 * cr[0]);
  }, CFG.L, 2 / Math.PI, "W(α); w_θ integrates W along lines ⊥ x_θ", (ctx, sx, sy) => {
    const c = Math.cos(t), s = Math.sin(t), R = 2 * CFG.L;
    ctx.strokeStyle = C.sel; ctx.lineWidth = 1.6; ctx.setLineDash([5, 3]); ctx.beginPath(); ctx.moveTo(sx(-R * c), sy(-R * s)); ctx.lineTo(sx(R * c), sy(R * s)); ctx.stroke(); ctx.setLineDash([]);
    ctx.fillStyle = C.sel; ctx.font = "italic 13px serif"; ctx.fillText("x_θ", sx(0.8 * CFG.L * c) + 4, sy(0.8 * CFG.L * s) - 4);
  });
  let ymax = 0; for (let i = 0; i <= 400; i++) ymax = Math.max(ymax, marg(a, ph, t, -XM + (2 * XM * i) / 400));
  bM.setBoundingBox([-XM, ymax * 1.18, XM, -0.08 * ymax * 1.18], false); bM.update();
  sinogram(a, ph, t);
  let norm = 0; for (let i = 0; i < 2000; i++) norm += marg(a, ph, t, -XM + (2 * XM * (i + 0.5)) / 2000) * (2 * XM / 2000);
  panel.textContent =
`x_θ = x cos θ + p sin θ = √2 Re(α e^{−iθ})     ∫ w_θ dx_θ = ${f(norm)}
w_θ(x_θ) = ∫ dp_θ W   is the Radon transform of W; homodyne detection measures it for every θ.
Fringes appear when both components project onto the same x_θ, i.e. when the x_θ axis is ⊥ to the line joining them.`;
}
for (const x of [sA, sF, sT]) x.addEventListener("input", update);
update();
```

## Phase-space functions and operator ordering

### The Husimi $Q$ function

$$Q(\alpha)=\frac{1}{\pi}\bra{\alpha}\hat\rho\ket{\alpha}, \qquad Q(\alpha)=\frac1\pi|\langle\alpha|\psi\rangle|^2 \ \text{ for } \hat\rho=\ket\psi\bra\psi, \qquad \alpha = \alpha_r+i\alpha_i .$$

$Q\ge0$ because $\hat\rho$ is positive, and $\int d^2\alpha\,Q=1$ by the completeness relation $\frac1\pi\int d^2\alpha\ket\alpha\bra\alpha=\hat 1$.

**$Q$ from a normally ordered $\hat\rho$.** Write the density operator in normal order, $\hat\rho = \sum_{kl}\rho^{(n)}_{kl}\,(\hat a^\dagger)^k\hat a^l$. Since $\hat a\ket\alpha=\alpha\ket\alpha$ and $\bra\alpha\hat a^\dagger=\alpha^*\bra\alpha$,

$$Q(\alpha)=\frac{1}{\pi}\sum_{kl}\rho^{(n)}_{kl}\,\alpha^{*k}\alpha^l :$$

$Q$ follows from the normally ordered $\hat\rho$ by the substitution $\hat a\to\alpha$, $\hat a^\dagger\to\alpha^*$.

**Expectation values of antinormally ordered observables.** Let $\hat A=\sum_{ij}A^{(a)}_{ij}\,\hat a^i(\hat a^\dagger)^j$ be antinormally ordered. Inserting the completeness relation between $\hat a^i$ and $(\hat a^\dagger)^j$,

$$\hat a^i(\hat a^\dagger)^j = \frac1\pi\int d^2\alpha\;\hat a^i\ket\alpha\bra\alpha(\hat a^\dagger)^j = \frac1\pi\int d^2\alpha\;\alpha^i\alpha^{*j}\ket\alpha\bra\alpha,$$

so $\hat A = \frac1\pi\int d^2\alpha\,A^{(a)}(\alpha)\ket\alpha\bra\alpha$ with $A^{(a)}(\alpha)=\sum_{ij}A^{(a)}_{ij}\alpha^i\alpha^{*j}$. Then

$$\langle\hat A\rangle = \mathrm{Tr}(\hat A\hat\rho) = \frac1\pi\int d^2\alpha\,A^{(a)}(\alpha)\bra\alpha\hat\rho\ket\alpha = \int d^2\alpha\;A^{(a)}(\alpha)\,Q(\alpha).$$

This is the same structure as for the Wigner function, where symmetrically (Weyl) ordered operators are averaged with $W$; here the ordering is antinormal. For example, $\langle\hat a\hat a^\dagger\rangle = \langle\hat n\rangle+1 = \int d^2\alpha\,|\alpha|^2Q$.

### The $P$ function

Now reverse the roles: put $\hat\rho$ in antinormal order and $\hat A$ in normal order,

$$\hat\rho=\sum_{kl}\rho^{(a)}_{kl}\,\hat a^k(\hat a^\dagger)^l, \qquad \hat A=\sum_{ij}A^{(n)}_{ij}\,(\hat a^\dagger)^i\hat a^j .$$

The same insertion of the completeness relation gives

$$\hat\rho = \frac{1}{\pi}\int d^2\alpha\sum_{kl}\rho^{(a)}_{kl}\,\hat a^k\ket\alpha\bra\alpha(\hat a^\dagger)^l = \int d^2\alpha\;\underbrace{\frac1\pi\sum_{kl}\rho^{(a)}_{kl}\,\alpha^k\alpha^{*l}}_{P(\alpha)}\;\ket\alpha\bra\alpha,$$

which is the Glauber–Sudarshan representation $\hat\rho=\int d^2\alpha\,P(\alpha)\ket\alpha\bra\alpha$ introduced earlier. Normally ordered observables are averaged with $P$, since $\mathrm{Tr}(\hat A\ket\alpha\bra\alpha)=\bra\alpha\hat A\ket\alpha = A^{(n)}(\alpha)$:

$$\langle\hat A\rangle = \int d^2\alpha\;A^{(n)}(\alpha)\,P(\alpha).$$

| function | $\hat\rho$ ordered | averages observables in | always a regular function? |
|---|---|---|---|
| $P$ | antinormally | normal order | no |
| $W$ | symmetrically | symmetric (Weyl) order | yes, but can be negative |
| $Q$ | normally | antinormal order | yes, $Q\ge0$ |

### The link between $P$ and $Q$

Inserting the $P$ representation into the definition of $Q$ and using $|\langle\alpha|\beta\rangle|^2=e^{-|\alpha-\beta|^2}$,

$$Q(\alpha) = \frac{1}{\pi}\bra{\alpha}\int d^2\beta\,P(\beta)\ket{\beta}\bra{\beta}\alpha\rangle = \frac{1}{\pi}\int d^2\beta\,P(\beta)\,e^{-|\alpha-\beta|^2}.$$

$Q$ is $P$ convolved with the normalised Gaussian $g(\alpha)=\frac1\pi e^{-|\alpha|^2}$, which is the $Q$ function of the vacuum. Smoothing with $g$ is why $Q$ is always a regular, non-negative function, and why it hides most signatures of nonclassicality.

**From $Q$ back to $P$.** Define the Fourier transform $\tilde f(\xi)=\int d^2\alpha\;e^{-i(\xi_r\alpha_r+\xi_i\alpha_i)}f(\alpha)$. By the **convolution theorem**, the Fourier transform of a convolution is the product of the transforms, $\tilde Q(\xi)=\tilde g(\xi)\,\tilde P(\xi)$. The transform of the Gaussian is

$$\tilde g(\xi)=\frac1\pi\int d\alpha_r\,e^{-\alpha_r^2-i\xi_r\alpha_r}\int d\alpha_i\,e^{-\alpha_i^2-i\xi_i\alpha_i} = e^{-(\xi_r^2+\xi_i^2)/4}.$$

Dividing by it and transforming back,

$$P(\alpha_r, \alpha_i)=\frac{1}{(2\pi)^2} \int d \xi_r \int d\xi_i\; \underbrace{e^{(\xi_r^2 +\xi_i^2)/4}}_{\text{anti-Gaussian}}\; \tilde Q(\xi_r, \xi_i)\; e^{i(\xi_r \alpha_r + \xi_i \alpha_i)} .$$

Deconvolution multiplies $\tilde Q$ by a growing Gaussian. $P$ is a regular function only if $\tilde Q$ decays faster than $e^{-|\xi|^2/4}$. Otherwise the integral diverges and $P$ is a distribution: derivatives of $\delta$ functions, or something even more singular.

### $P$ representation of a Fock state

We want $P$ such that $\ket{n}\bra{n}=\int d^2 \alpha\, P(\alpha) \ket{\alpha}\bra{\alpha}$, starting from

$$Q(\alpha)=\frac{1}{\pi}\frac{|\alpha|^{2n}}{n!}e^{-|\alpha|^2}.$$

Use polar coordinates in both planes, $\alpha_r = r\cos\varphi_\alpha$, $\alpha_i = r\sin\varphi_\alpha$ and $\xi_r = \xi\cos\psi$, $\xi_i = \xi\sin\psi$, so that $\xi_r\alpha_r+\xi_i\alpha_i=\xi r\cos(\varphi_\alpha-\psi)$. $Q$ does not depend on $\varphi_\alpha$, so we can shift $\varphi=\varphi_\alpha-\psi$:

$$\tilde Q(\xi)=\int_0^\infty r\,dr \int_{-\pi}^\pi d \varphi\; \frac{1}{\pi}\frac{r^{2n}}{n!}\, e^{-r^2}\, e^{-i \xi r\cos \varphi}.$$

The angular integral is a Bessel function, $\frac{1}{2 \pi}\int_{-\pi}^{\pi} d\varphi\; e^{-iz \cos \varphi} = J_{0}(z)$, so

$$\tilde Q(\xi) = \frac{2}{n!}\int_0^\infty dr\; r^{2n+1}e^{-r^2}J_0(\xi r).$$

With the tabulated integral

$$\int_0^\infty dx\; e^{-x^2}x^{2n+1}J_0(2x\sqrt{z}) = \frac{n!}{2}e^{-z}L_n(z)$$

at $2\sqrt z=\xi$, i.e. $z=\xi^2/4$,

$$\tilde Q(\xi) = e^{-\xi^2/4}\,L_n\Big(\frac{\xi^2}{4}\Big).$$

The Gaussian factor cancels exactly against the anti-Gaussian, leaving a polynomial:

$$P(\alpha)=\frac{1}{(2 \pi)^2} \int d \xi_r\int d\xi_i\; L_n\Big(\frac{\xi_r^2+\xi_i^2}{4}\Big)\,e^{i (\xi_r \alpha_r + \xi_i \alpha_i)} .$$

This integral diverges as an ordinary integral, but it is a well-defined distribution. Since $\xi_r^2\,e^{i(\xi_r\alpha_r+\xi_i\alpha_i)} = -\partial_{\alpha_r}^2e^{i(\xi_r\alpha_r+\xi_i\alpha_i)}$ (and likewise for $\xi_i$), the polynomial can be pulled out of the integral as a differential operator, and $\frac{1}{(2\pi)^2}\int d^2\xi\, e^{i(\xi_r\alpha_r+\xi_i\alpha_i)}=\delta(\alpha_r)\delta(\alpha_i)$:

$$P_n(\alpha)=L_n\Big(-\frac{1}{4}\big(\partial_{\alpha_r}^2+ \partial_{\alpha_i}^2\big)\Big)\,\delta^{(2)}(\alpha) = L_n\big(-\partial_\alpha\partial_{\alpha^*}\big)\,\delta^{(2)}(\alpha),$$

using $\partial_{\alpha_r}^2+\partial_{\alpha_i}^2=4\partial_\alpha\partial_{\alpha^*}$. For $n=1$, $L_1(u)=1-u$ gives $P_1 = \big(1+\partial_\alpha\partial_{\alpha^*}\big)\delta^{(2)}(\alpha)$. Check: convolving with $\frac1\pi e^{-|\alpha-\beta|^2}$ and integrating by parts gives $\frac1\pi\big[1+(|\alpha|^2-1)\big]e^{-|\alpha|^2}=Q_1$. The $P$ function of every Fock state $n\ge1$ is more singular than a $\delta$ function, so it cannot be a probability density. This is the $P$-function statement of their nonclassicality.

## The $P$ representation in practice

### Example 1: beam splitter and homodyne detection

A 50:50 beam splitter acts on the mode operators as

$$B=\frac{1}{\sqrt{2}} \begin{pmatrix} 1&-1 \\ 1 & 1 \end{pmatrix}, \qquad \ket{\beta}\otimes\ket{\gamma}\;\to\;\Big|\tfrac{\beta-\gamma}{\sqrt2}\Big\rangle\otimes\Big|\tfrac{\beta+\gamma}{\sqrt2}\Big\rangle .$$

Coherent states stay coherent, so an arbitrary input written in the $P$ representation is transformed term by term:

$$\rho_{\rm in} = \int d^2 \beta \int d^2 \gamma\; P_{12}(\beta, \gamma) \ket{\beta}\bra{\beta} \otimes \ket{\gamma}\bra{\gamma}
\quad\Rightarrow\quad
\rho_{\rm out}=\int d^2 \beta \int d^2 \gamma\; P_{12}(\beta, \gamma)\, \Big|\tfrac{\beta -\gamma}{\sqrt{2}}\Big\rangle \Big\langle\tfrac{\beta -\gamma}{\sqrt{2}}\Big|\otimes \Big|\tfrac{\beta +\gamma}{\sqrt{2}}\Big\rangle \Big\langle\tfrac{\beta +\gamma}{\sqrt{2}}\Big| .$$

In homodyne detection the second input is a local oscillator in the coherent state $\ket\alpha$, $P_{12} = P(\beta)\,\delta^{(2)}(\gamma -\alpha)$:

$$\rho_{\rm out}=\int d^2 \beta\; P(\beta)\, \Big|\tfrac{\beta -\alpha}{\sqrt{2}}\Big\rangle \Big\langle\tfrac{\beta -\alpha}{\sqrt{2}}\Big|\otimes \Big|\tfrac{\beta +\alpha}{\sqrt{2}}\Big\rangle \Big\langle\tfrac{\beta +\alpha}{\sqrt{2}}\Big| .$$

**Photon counting statistics.** For ideal detectors the joint distribution of counts is

$$K(n_1,n_2)=\int d^2 \beta \int d^2 \gamma\; P_{12}(\beta, \gamma)\, K_{n_1n_2}(\beta, \gamma),$$
$$K_{n_1n_2}(\beta,\gamma)=\Big|\Big\langle n_1\Big|\tfrac{\beta-\gamma}{\sqrt{2}}\Big\rangle\Big|^2\Big|\Big\langle n_2\Big|\tfrac{\beta+\gamma}{\sqrt{2}}\Big\rangle\Big|^2 = \frac{\mu_1^{n_1}\mu_2^{n_2}}{n_1!\, n_2!}\,e^{-(\mu_1+\mu_2)}, \qquad \mu_{1,2}=\tfrac12|\beta\mp\gamma|^2,$$

a product of two Poisson distributions ($\mu_1+\mu_2=|\beta|^2+|\gamma|^2$). Homodyne detection records only the difference $n_{21}=n_2-n_1$:

$$K(n_{21})=\sum_{n_2}K(n_1=n_2-n_{21},\,n_2) = \int d^2 \beta\; P(\beta)\, K_{n_{21}}(\alpha, \beta).$$

$K_{n_{21}}$ is the distribution of the difference of two independent Poisson variables (a Skellam distribution), with mean $\mu_2-\mu_1=2\,\mathrm{Re}(\alpha^*\beta)$. For a strong local oscillator, $\alpha=|\alpha|e^{i\theta}$, it becomes a narrow Gaussian centred at $2|\alpha|\,\mathrm{Re}(\beta e^{-i\theta})$, so $n_{21}/(\sqrt2|\alpha|)$ measures the quadrature $x_\theta$.

### Example 2: correlation functions

$P$ averages normally ordered products, so

$$\langle a^{\dagger n}a^m \rangle = \int d^2 \alpha\; P(\alpha)\, \alpha^{*n}\alpha^m, \qquad
g^{(2)}(0)=\frac{\langle a^{\dagger2} a^2 \rangle}{\langle a^\dagger a \rangle^2}= \frac{\int d^2 \alpha\,P(\alpha)\, |\alpha|^4}{\big(\int d^2\alpha\,P(\alpha)|\alpha|^2 \big)^2}.$$

If $P\ge0$, then $g^{(2)}(0)-1=\int d^2\alpha\,P\,(|\alpha|^2-\bar n)^2/\bar n^2\ge0$; antibunching therefore requires a non-positive $P$.

### Positive $P$ representation

The Glauber $P$ is often singular. The positive $P$ representation, which is numerically convenient, expands $\rho$ in non-diagonal coherent-state projectors:

$$\rho = \int d\mu(\alpha, \beta)\;P(\alpha,\beta)\,\Lambda(\alpha,\beta), \qquad \Lambda(\alpha,\beta)=\frac{\ket{\alpha}\bra{\beta^*}}{\langle \beta^* | \alpha \rangle}, \qquad \mathrm{Tr}\,\Lambda=1 .$$

- $d \mu = \delta^{(2)}(\alpha^* - \beta)\,d^2 \alpha\, d^2 \beta$ gives back the Glauber $P$ ($\Lambda=\ket\alpha\bra\alpha$).
- $d \mu = d^2 \alpha\, d^2 \beta$ gives the positive $P$. For every $\rho$ there is a real, non-negative, normalised choice,
$$P(\alpha,\beta)=\frac{1}{4\pi^2}\,e^{-|\alpha-\beta^*|^2/4}\,\Big\langle\tfrac{\alpha+\beta^*}{2}\Big|\rho\Big|\tfrac{\alpha+\beta^*}{2}\Big\rangle ,$$
so $P$ is a genuine probability distribution on the doubled phase space, and $\langle a^{\dagger n}a^m\rangle=\int d\mu\,P\,\beta^n\alpha^m$. Master equations then map to stochastic equations with positive diffusion.

## Parametric amplification

<div style="text-align:center"><svg width="520" height="170" viewBox="0 0 520 170" xmlns="http://www.w3.org/2000/svg" fill="none" stroke="currentColor" stroke-width="1.6" font-family="Times New Roman, serif" font-size="16"><defs><marker id="arrPA" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="7" markerHeight="7" orient="auto"><path d="M0,0 L10,5 L0,10 z" fill="currentColor" stroke="none"/></marker></defs><line x1="20" y1="85" x2="118" y2="85" marker-end="url(#arrPA)"/><rect x="120" y="55" width="80" height="60" fill="currentColor" fill-opacity="0.08"/><line x1="202" y1="85" x2="290" y2="45" marker-end="url(#arrPA)"/><line x1="202" y1="85" x2="290" y2="125" marker-end="url(#arrPA)"/><g fill="currentColor" stroke="none"><text x="30" y="75" font-style="italic">ω<tspan font-size="11" dy="4">p</tspan><tspan dy="-4"> = 2ω</tspan></text><text x="160" y="90" text-anchor="middle">χ<tspan font-size="11" dy="-7">(2)</tspan></text><text x="296" y="45" font-style="italic">ω<tspan font-size="11" dy="4">1</tspan></text><text x="296" y="135" font-style="italic">ω<tspan font-size="11" dy="4">2</tspan></text><text x="160" y="140" text-anchor="middle" font-size="12">pump → signal + idler</text></g><line x1="360" y1="150" x2="500" y2="150"/><line x1="360" y1="20" x2="500" y2="20" stroke-dasharray="4 4"/><line x1="360" y1="88" x2="500" y2="88" stroke-dasharray="4 4"/><line x1="385" y1="150" x2="385" y2="22" marker-end="url(#arrPA)"/><line x1="440" y1="20" x2="440" y2="86" marker-end="url(#arrPA)"/><line x1="440" y1="88" x2="440" y2="148" marker-end="url(#arrPA)"/><g fill="currentColor" stroke="none" font-style="italic"><text x="365" y="90">2ω</text><text x="448" y="58">ω<tspan font-size="11" dy="4">1</tspan></text><text x="448" y="124">ω<tspan font-size="11" dy="4">2</tspan></text></g></svg></div>

A classical pump at $2\omega$ splits in a $\chi^{(2)}$ crystal into two photons with $\omega_1+\omega_2=2\omega$.

### Degenerate case ($\omega_1=\omega_2=\omega$)

$$\mathcal{H}=\hbar \omega a^\dagger a + i \hbar \frac{\chi}{2}\big(a^{\dagger2} e^{-2i\omega t}-a^2 e^{2i \omega t}\big).$$

The time dependence is that of the classical pump field $\propto e^{-2i\omega t}$, which multiplies $a^{\dagger2}$ (one pump photon destroyed, two created). In the interaction picture with respect to $\hbar\omega a^\dagger a$, $a\to ae^{-i\omega t}$, which cancels it:

$$\mathcal{H}_I = i\hbar \frac{\chi}{2}\big(a^{\dagger2} -a^2\big).$$

Heisenberg equations, using $[a,a^{\dagger2}]=2a^\dagger$:

$$\dot{a}=\frac{1}{i\hbar}[a,\mathcal{H}_I]=\chi a^\dagger, \qquad \dot{a}^\dagger = \chi a
\quad\Rightarrow\quad
a(t)=a(0)\cosh(\chi t)+a^\dagger(0) \sinh(\chi t).$$

This is the squeezing transformation with $r=\chi t$. For the vacuum input, $\langle a^\dagger a\rangle=\sinh^2\chi t$ and $\langle a^{\dagger2}a^2\rangle = 3\sinh^4\chi t+\sinh^2\chi t$, so

$$g^{(2)}(0)= 1+\frac{\cosh(2 \chi t)}{\sinh^2(\chi t)} = 3+\frac{1}{\bar n} >1 .$$

The light is bunched because photons are produced in pairs. $g^{(2)}\to\infty$ for $\chi t\to0$: at low gain almost every detected photon has its twin. The unlimited growth of $\bar n=\sinh^2\chi t$ is an artefact of the undepleted classical pump.

### Nondegenerate case ($\omega_1+\omega_2=2\omega$): signal and idler

$$\mathcal{H}=\hbar \omega_1 a_1^\dagger a_1+\hbar \omega_2 a_2^\dagger a_2 + i \hbar \chi \big(a_1^\dagger a_2^\dagger e^{-2i\omega t}-a_1a_2e^{2i\omega t}\big), \qquad \mathcal H_I=i\hbar\chi\big(a_1^\dagger a_2^\dagger-a_1a_2\big),$$

$$\dot{a}_1=\chi a_2^\dagger, \quad \dot{a}_2^\dagger =\chi a_1
\quad\Rightarrow\quad
a_1(t)=a_1\cosh\chi t+a_2^\dagger\sinh\chi t, \qquad a_2(t)=a_2\cosh\chi t+a_1^\dagger\sinh\chi t .$$

Each mode alone is thermal with $\bar n=\sinh^2\chi t$ ($g^{(2)}_{11}=g^{(2)}_{22}=2$), and the photon numbers are perfectly correlated, $\hat n_1-\hat n_2=$ const.

### Cross-correlation and the Cauchy–Schwarz inequality

$$\langle a_1^\dagger a_2^\dagger a_2 a_1 \rangle = \int d^2 \alpha_1\, d^2 \alpha_2\; |\alpha_1|^2 |\alpha_2|^2\, P(\alpha_1, \alpha_2).$$

If $P\geq 0$, the Cauchy–Schwarz (Hölder) inequality with weight $P$ gives

$$\int P\,|\alpha_1|^2|\alpha_2|^2 \le \Big(\int P\,|\alpha_1|^4\Big)^{1/2}\Big(\int P\,|\alpha_2|^4\Big)^{1/2}
\quad\Leftrightarrow\quad
\langle a_1^{\dagger}a_2^\dagger a_2 a_1 \rangle \le \big(\langle a_1^{\dagger2} a_1^2 \rangle \langle a_2^{\dagger2} a_2^2\rangle\big)^{1/2},$$

i.e. $\big(g^{(2)}_{12}\big)^2\le g^{(2)}_{11}\,g^{(2)}_{22}$ with $g^{(2)}_{12}=\langle a_1^\dagger a_2^\dagger a_2a_1\rangle/(\langle a_1^\dagger a_1\rangle\langle a_2^\dagger a_2\rangle)$. Its violation is a nonclassicality witness. For the parametric amplifier, $\langle \hat n_1\hat n_2\rangle=2\bar n^2+\bar n$, so $g^{(2)}_{12}=2+1/\bar n>2=\sqrt{g^{(2)}_{11}g^{(2)}_{22}}$: the bound is violated for every gain.

> [!question]- My questions
> - Does the Wigner function coincide with the Husimi function for a coherent state?
>   No. Both are Gaussians centred at $\beta$, but with different widths: $W_\beta=\frac2\pi e^{-2|\alpha-\beta|^2}$ (variance $\frac14$ per quadrature in the $\alpha$-plane), while $Q_\beta=\frac1\pi e^{-|\alpha-\beta|^2}$ (variance $\frac12$). In general $W=\frac2\pi\int d^2\beta\,P(\beta)e^{-2|\alpha-\beta|^2}$ and $Q=\frac2\pi\int d^2\beta\,W(\beta)e^{-2|\alpha-\beta|^2}$. $W$ is $P$ smoothed by half of the vacuum noise, and $Q$ is $W$ smoothed by the other half. For a coherent state, $P=\delta^{(2)}(\alpha-\beta)$, so the three functions are Gaussians of variance $0$, $\frac14$ and $\frac12$.




# Lecture 10

## Moments from the generating function

For $G(x)=\sum_{n=0}^\infty p_nx^n$, each derivative at $x=1$ brings down one more factor:

$$G(1)=\sum_n p_n=1, \qquad G'(1)=\sum_n n\,p_n=\langle\hat n\rangle, \qquad G''(1)=\sum_n n(n-1)\,p_n=\langle\hat n(\hat n-1)\rangle .$$

Since $\langle\hat n^2\rangle=\langle\hat n(\hat n-1)\rangle+\langle\hat n\rangle$, and $\hat a^{\dagger2}\hat a^2=\hat n(\hat n-1)$,

$$\mathrm{Var}(n)=G''(1)+G'(1)-G'(1)^2, \qquad g^{(2)}(0)=\frac{\langle\hat a^{\dagger2}\hat a^2\rangle}{\langle\hat a^\dagger\hat a\rangle^2}=\frac{G''(1)}{G'(1)^2}.$$

For two modes, the normalised cross-correlation is $g^{(2)}_{12}=\dfrac{\langle\hat a_1^\dagger\hat a_1\hat a_2^\dagger\hat a_2\rangle}{\langle\hat a_1^\dagger\hat a_1\rangle\langle\hat a_2^\dagger\hat a_2\rangle}$.

**Examples.**

- **Fock state** $\ket m$, $p_n=\delta_{nm}$: $G=x^m$, $G'=m\,x^{m-1}$, $G''=m(m-1)\,x^{m-2}$, so
$$\mathrm{Var}(n)=0, \qquad g^{(2)}(0)=\frac{m(m-1)}{m^2}=1-\frac1m .$$
- **Coherent state**, $p_n=e^{-\lambda}\frac{\lambda^n}{n!}$ with $\lambda=|\alpha|^2$: $G=e^{-\lambda}\sum_n\frac{(\lambda x)^n}{n!}=e^{\lambda(x-1)}$, so $G'(1)=\lambda$, $G''(1)=\lambda^2$ and
$$\mathrm{Var}(n)=\lambda^2+\lambda-\lambda^2=\lambda, \qquad g^{(2)}(0)=1 .$$
- **Thermal state**, $p_n=(1-\beta)\beta^n$ with $\beta=e^{-\hbar\omega/k_BT}$: the geometric series gives $G=\frac{1-\beta}{1-\beta x}$, and
$$G'(x)=\frac{(1-\beta)\beta}{(1-\beta x)^2}, \qquad G''(x)=\frac{2(1-\beta)\beta^2}{(1-\beta x)^3}
\quad\Rightarrow\quad \bar n=G'(1)=\frac{\beta}{1-\beta}, \qquad G''(1)=2\bar n^2,$$
$$\mathrm{Var}(n)=\bar n^2+\bar n, \qquad g^{(2)}(0)=2 .$$

## Losses and the generating function

A state with photon distribution $p_n$ falls on a beam splitter with transmission $\eta$. The second input port is empty:

$$\hat a'= \sqrt{\eta}\,\hat a+ \sqrt{1-\eta}\,\hat v ,$$

where $\hat v$ is the annihilation operator of the second input mode, which is in the vacuum $\ket0$. The same model describes absorption and detector inefficiency. What is the distribution $p'_m$ of transmitted photons?

### Conditional probability $p(m|n)$

Take $n$ photons in, $\ket n\ket0=\frac{1}{\sqrt{n!}}(\hat a^\dagger)^n\ket{0,0}$. The beam splitter sends each creation operator into a superposition of the transmitted (t) and reflected (r) output modes, $\hat a^\dagger\to\sqrt\eta\,\hat a_t^\dagger+\sqrt{1-\eta}\,\hat a_r^\dagger$. Expanding with the binomial theorem and using $(\hat a^\dagger)^k\ket0=\sqrt{k!}\ket k$,

$$\ket n\ket0\;\to\;\frac{1}{\sqrt{n!}}\big(\sqrt\eta\,\hat a_t^\dagger+\sqrt{1-\eta}\,\hat a_r^\dagger\big)^n\ket{0,0}
=\sum_{m=0}^{n}\sqrt{\binom nm}\,\eta^{m/2}(1-\eta)^{(n-m)/2}\,\ket m_t\ket{n-m}_r .$$

The probability of $m$ transmitted photons is the square of the amplitude:

$$p(m|n)=\binom{n}{m}\eta^m (1-\eta)^{n-m}, \qquad m=0,1,\dots,n, \qquad p(m|n)=0 \ \text{ for } m>n .$$

> [!tip] Binomial interpretation
> Each photon is transmitted independently with probability $\eta$ and lost with probability $1-\eta$. One particular assignment (photons 1 and 3 through, the rest lost, ...) with $m$ transmitted photons has probability $\eta^m(1-\eta)^{n-m}$. There are $\binom nm$ ways to choose which $m$ of the $n$ photons get through. Check: summing over $m$ gives $\big(\eta+(1-\eta)\big)^n=1$. Every term of the expansion of $(\eta+1-\eta)^n$ is one assignment.

### Output distribution: the sum limits

By total probability, summing over the number of incident photons,

$$p'_m=\sum_{n=m}^{\infty}p_n\,p(m|n).$$

The sum starts at $n=m$ because at least $m$ photons must be incident to transmit $m$. Equivalently, one can sum from $n=0$, since $\binom nm=0$ for $n<m$.

<div style="text-align:center"><svg width="400" height="265" viewBox="0 0 400 265" xmlns="http://www.w3.org/2000/svg" fill="none" stroke="currentColor" stroke-width="1.4" font-family="Times New Roman, serif" font-size="15"><defs><marker id="arrL10" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="7" markerHeight="7" orient="auto"><path d="M0,0 L10,5 L0,10 z" fill="currentColor" stroke="none"/></marker></defs><line x1="45" y1="230" x2="269" y2="230" marker-end="url(#arrL10)"/><line x1="45" y1="230" x2="45" y2="35" marker-end="url(#arrL10)"/><line x1="52" y1="223" x2="240" y2="55" stroke-dasharray="4 4" stroke-opacity="0.6"/><circle cx="60" cy="215" r="4.5" fill="currentColor" stroke="none"/><circle cx="94" cy="215" r="4" stroke-opacity="0.45"/><circle cx="128" cy="215" r="4" stroke-opacity="0.45"/><circle cx="162" cy="215" r="4" stroke-opacity="0.45"/><circle cx="196" cy="215" r="4" stroke-opacity="0.45"/><circle cx="230" cy="215" r="4" stroke-opacity="0.45"/><circle cx="60" cy="185" r="4.5" fill="currentColor" stroke="none"/><circle cx="94" cy="185" r="4.5" fill="currentColor" stroke="none"/><circle cx="128" cy="185" r="4" stroke-opacity="0.45"/><circle cx="162" cy="185" r="4" stroke-opacity="0.45"/><circle cx="196" cy="185" r="4" stroke-opacity="0.45"/><circle cx="230" cy="185" r="4" stroke-opacity="0.45"/><circle cx="60" cy="155" r="4.5" fill="currentColor" stroke="none"/><circle cx="94" cy="155" r="4.5" fill="currentColor" stroke="none"/><circle cx="128" cy="155" r="4.5" fill="currentColor" stroke="none"/><circle cx="162" cy="155" r="4" stroke-opacity="0.45"/><circle cx="196" cy="155" r="4" stroke-opacity="0.45"/><circle cx="230" cy="155" r="4" stroke-opacity="0.45"/><circle cx="60" cy="125" r="4.5" fill="currentColor" stroke="none"/><circle cx="94" cy="125" r="4.5" fill="currentColor" stroke="none"/><circle cx="128" cy="125" r="4.5" fill="currentColor" stroke="none"/><circle cx="162" cy="125" r="4.5" fill="currentColor" stroke="none"/><circle cx="196" cy="125" r="4" stroke-opacity="0.45"/><circle cx="230" cy="125" r="4" stroke-opacity="0.45"/><circle cx="60" cy="95" r="4.5" fill="currentColor" stroke="none"/><circle cx="94" cy="95" r="4.5" fill="currentColor" stroke="none"/><circle cx="128" cy="95" r="4.5" fill="currentColor" stroke="none"/><circle cx="162" cy="95" r="4.5" fill="currentColor" stroke="none"/><circle cx="196" cy="95" r="4.5" fill="currentColor" stroke="none"/><circle cx="230" cy="95" r="4" stroke-opacity="0.45"/><circle cx="60" cy="65" r="4.5" fill="currentColor" stroke="none"/><circle cx="94" cy="65" r="4.5" fill="currentColor" stroke="none"/><circle cx="128" cy="65" r="4.5" fill="currentColor" stroke="none"/><circle cx="162" cy="65" r="4.5" fill="currentColor" stroke="none"/><circle cx="196" cy="65" r="4.5" fill="currentColor" stroke="none"/><circle cx="230" cy="65" r="4.5" fill="currentColor" stroke="none"/><rect x="51" y="116" width="120" height="18" rx="9" stroke-width="1.2"/><rect x="85" y="51" width="18" height="143" rx="9" stroke-width="1.2" stroke-dasharray="3 2"/><g fill="currentColor" stroke="none"><text x="272" y="235" font-style="italic">m</text><text x="30" y="41" font-style="italic">n</text><text x="60" y="247" text-anchor="middle" font-size="12">0</text><text x="36" y="219" text-anchor="middle" font-size="12">0</text><text x="94" y="247" text-anchor="middle" font-size="12">1</text><text x="36" y="189" text-anchor="middle" font-size="12">1</text><text x="128" y="247" text-anchor="middle" font-size="12">2</text><text x="36" y="159" text-anchor="middle" font-size="12">2</text><text x="162" y="247" text-anchor="middle" font-size="12">3</text><text x="36" y="129" text-anchor="middle" font-size="12">3</text><text x="196" y="247" text-anchor="middle" font-size="12">4</text><text x="36" y="99" text-anchor="middle" font-size="12">4</text><text x="230" y="247" text-anchor="middle" font-size="12">5</text><text x="36" y="69" text-anchor="middle" font-size="12">5</text><text x="238" y="51" font-size="12" font-style="italic">m = n</text><text x="276" y="129" font-size="12">— fixed n: m = 0 … n</text><text x="276" y="189" font-size="12">┆ fixed m: n = m … ∞</text><text x="276" y="99" font-size="12">● p(m|n) ≠ 0</text></g></svg></div>

The pairs $(m,n)$ that contribute fill the triangle $0\le m\le n$ (filled dots). A double sum over this triangle can be done column by column or row by row:

$$\sum_{m=0}^{\infty}\sum_{n=m}^{\infty}(\dots)\;=\;\sum_{n=0}^{\infty}\sum_{m=0}^{n}(\dots).$$

### Generating function

With $G(x)=\sum_n p_nx^n$ (§8.6),

$$G'(x)=\sum_{m=0}^{\infty}p'_m\,x^m=\sum_{m=0}^{\infty}\sum_{n=m}^{\infty}p_n\binom nm\eta^m(1-\eta)^{n-m}x^m .$$

Exchange the order of summation as above, and collect $\eta^mx^m=(\eta x)^m$:

$$G'(x)=\sum_{n=0}^{\infty}p_n\sum_{m=0}^{n}\binom nm(\eta x)^m(1-\eta)^{n-m}=\sum_{n=0}^{\infty}p_n\,(1-\eta+\eta x)^n .$$

The inner sum is the binomial theorem $(a+b)^n=\sum_{m=0}^n\binom nm a^mb^{n-m}$ with $a=\eta x$, $b=1-\eta$. The result is the old generating function at a new argument:

$$\boxed{G'(x)=G(1-\eta+\eta x)}$$

This is the result of §8.6, now obtained without the $P$ representation.

**Consequences.** Differentiating $k$ times, $\frac{d^k}{dx^k}G(1-\eta+\eta x)=\eta^kG^{(k)}(1-\eta+\eta x)$, and at $x=1$:

$$\langle\hat n(\hat n-1)\cdots(\hat n-k+1)\rangle'=\eta^k\,\langle\hat n(\hat n-1)\cdots(\hat n-k+1)\rangle .$$

- Mean: $\langle\hat n\rangle'=\eta\langle\hat n\rangle$, reduced by the factor $\eta$.
- $g^{(2)}(0)=\langle\hat n(\hat n-1)\rangle/\langle\hat n\rangle^2$ is unchanged by loss.
- Mandel $Q=\frac{\langle\hat n(\hat n-1)\rangle}{\langle\hat n\rangle}-\langle\hat n\rangle$ becomes $Q'=\eta Q$: loss drives every distribution towards Poissonian.
- Coherent state: $G=e^{-(1-x)\bar n}\to e^{-(1-x)\eta\bar n}$, still Poissonian. Fock state: $G=x^n\to(1-\eta+\eta x)^n$, binomial.

### Example: a Fock state through a lossy channel

For $\ket n$, $p_k=\delta_{kn}$ and $G(x)=x^n$, so

$$G'(x)=(1-\eta+\eta x)^n=\sum_{m=0}^n\binom nm\eta^m(1-\eta)^{n-m}x^m
\quad\Rightarrow\quad p'_m=\binom nm\eta^m(1-\eta)^{n-m}=p(m|n),$$

as it must be, since only $n$ photons are ever incident. The moments follow from the derivatives of $G'$ at $x=1$:

$$\langle\hat n\rangle'=n\eta, \qquad \langle\hat n(\hat n-1)\rangle'=n(n-1)\eta^2, \qquad \mathrm{Var}'=n(n-1)\eta^2+n\eta-n^2\eta^2=n\eta(1-\eta).$$

- $Q'=\mathrm{Var}'/\langle\hat n\rangle'-1=-\eta$. The state stays sub-Poissonian for every $\eta>0$, but less and less so.
- $g^{(2)}(0)=1-\frac1n$, unchanged by loss.
- For $\eta\to0$ with $n\eta$ fixed, $(1-\eta(1-x))^n\to e^{-n\eta(1-x)}$, the generating function of a Poisson distribution: rare survivors of many photons are Poissonian.

**Wigner function at the origin.**

> [!note] Not from the lecture: added derivation
> **$W(0)$ is the parity.** At $x=p=0$ the definition of $W$ gives, with $\xi=2y$,
> $$W(0,0)=\frac{1}{2\pi}\int d\xi\,\bra{\xi/2}\hat\rho\ket{-\xi/2}=\frac1\pi\int dy\,\bra{y}\hat\rho\ket{-y}=\frac1\pi\,\mathrm{Tr}\big(\hat\rho\,\hat\Pi\big),$$
> where $\hat\Pi\ket y=\ket{-y}$ is the parity operator. Hermite functions satisfy $\psi_n(-x)=(-1)^n\psi_n(x)$, so $\hat\Pi\ket n=(-1)^n\ket n$ and $\hat\Pi=(-1)^{\hat n}$. On the $\alpha$-plane ($dx\,dp=2\,d^2\alpha$) this becomes
> $$W(0)=\frac2\pi\,\langle(-1)^{\hat n}\rangle=\frac2\pi\sum_np_n(-1)^n=\frac2\pi\,G(-1).$$
> **After loss.** Evaluating the output generating function at $x=-1$ gives $G_{\rm out}(-1)=G(1-2\eta)$. For $\ket n$, $G=x^n$, so
> $$W_{\rm out}(0)=\frac2\pi\,(1-2\eta)^n .$$
> **Why $\eta\le\frac12$ removes all negativity.** Writing $\hat c=\sqrt\eta\,\hat a+\sqrt{1-\eta}\,\hat v$ in phase space, the output Wigner function is the scaled input convolved with the vacuum Gaussian $W_0(z)=\frac2\pi e^{-2|z|^2}$:
> $$W_{\rm out}(\alpha)=\frac{1}{1-\eta}\int d^2\beta\;W_{\rm in}(\beta)\,W_0\Big(\tfrac{\alpha-\sqrt\eta\,\beta}{\sqrt{1-\eta}}\Big).$$
> At $\eta=\frac12$ the exponent is $-2|\sqrt2\alpha-\beta|^2$, so $W_{\rm out}(\alpha)=2Q_{\rm in}(\sqrt2\,\alpha)\ge0$ (Lecture 9: $Q=\frac2\pi\int W\,e^{-2|\alpha-\beta|^2}$). Any $\eta<\frac12$ is a further loss applied to this, i.e. a convolution with a positive Gaussian, which keeps $W\ge0$.

For odd $n$ the negative dip at the origin therefore survives only for $\eta>\frac12$, and for $\eta\le\frac12$ no input state keeps a negative $W$ anywhere.

**Interactive plot.** Sliders for $n$ and $\eta$. Left: $W(\alpha)=\sum_mp'_m\,W_m(\alpha)$ of the attenuated state, with $W_m$ the Fock-state Wigner functions of Lecture 8. Right: $p'_m$ with an optional Poisson reference of the same mean.

```dataviewjs
// ===== CONFIG =====
const CFG = { n: 4, nMax: 20, eta: 0.8, L: 5 };
// ==================
// ---- loader (leave as is) ----
const LIB = "FUW/lib/";
const load = (src) => new Promise((ok, no) => { const s = document.createElement("script"); s.src = src; s.onload = ok; s.onerror = () => no(new Error("could not load " + src)); document.head.append(s); });
const libPath = async (n) => { const here = dv.current().file.folder, up = here.includes("/") ? here.slice(0, here.lastIndexOf("/")) + "/" : ""; for (const p of [LIB + n, "lib/" + n, here + "/lib/" + n, up + "lib/" + n, ...app.vault.getFiles().filter((x) => x.path.endsWith("lib/" + n)).map((x) => x.path)]) if (await app.vault.adapter.exists(p)) return p; throw new Error("lib/" + n + " not found in this vault (is the lib folder synced to this computer?)"); };
if (!window.JXG) await (window.__jxg ??= libPath("jsxgraphcore.js").then((p) => load(app.vault.adapter.getResourcePath(p))).catch(() => load("https://cdn.jsdelivr.net/npm/jsxgraph@1.10.1/distrib/jsxgraphcore.js")).catch((e) => { window.__jxg = null; throw e; }));
if (!window.RL) await (window.__rl ??= libPath("rlti.js").then((p) => load(app.vault.adapter.getResourcePath(p))).catch((e) => { window.__rl = null; throw e; }));
const K = await RL.init(dv), { f, el, C } = K;
// ---- shared plotting helpers ----
const GAP = 12, WS = Math.min(320, Math.floor((K.W - GAP) / 2)), WP = K.W - WS - GAP, dpr = window.devicePixelRatio || 1;
const box = "background:#fff;border:1px solid #e5e7eb;border-radius:10px";
const row = el("div", `display:flex;gap:${GAP}px;align-items:flex-start;margin-top:6px;flex-wrap:wrap`);
const cv = el("canvas", `width:${WS}px;height:${WS}px;${box}`); cv.width = Math.round(WS * dpr); cv.height = Math.round(WS * dpr);
const pdiv = el("div", `width:${WP}px;height:${WS}px;${box};touch-action:none`);
row.append(cv, pdiv); K.root.append(row);
const panel = el("div", "font-family:var(--font-monospace,monospace);font-size:0.8em;line-height:1.55;white-space:pre-wrap;color:var(--text-normal);margin-top:6px");
const stops = [[-1, [31, 95, 168]], [-0.5, [127, 166, 212]], [0, [248, 248, 248]], [0.5, [240, 164, 106]], [1, [194, 65, 12]]];
const cmap = (t) => { t = Math.max(-1, Math.min(1, t)); let i = 0; while (i < stops.length - 2 && t > stops[i + 1][0]) i++; const [t0, c0] = stops[i], [t1, c1] = stops[i + 1], u = (t - t0) / (t1 - t0); return c0.map((v, j) => Math.round(v + u * (c1[j] - v))); };
function heat(fun, L, vmax, label, overlay) {   // fun(x, y) on the α-plane, x = Re α, y = Im α
  const ctx = cv.getContext("2d"), Wd = cv.width, Hd = cv.height, img = ctx.createImageData(Wd, Hd), d = img.data;
  for (let py = 0; py < Hd; py++) { const y = L - (2 * L * py) / Hd;
    for (let px = 0; px < Wd; px++) { const x = -L + (2 * L * px) / Wd, [R, G, B] = cmap(fun(x, y) / vmax), o = 4 * (py * Wd + px); d[o] = R; d[o + 1] = G; d[o + 2] = B; d[o + 3] = 255; } }
  ctx.putImageData(img, 0, 0); ctx.save(); ctx.scale(dpr, dpr);
  const sx = (x) => ((x + L) / (2 * L)) * WS, sy = (y) => ((L - y) / (2 * L)) * WS;
  ctx.strokeStyle = "#9ca3af"; ctx.lineWidth = 1; ctx.beginPath(); ctx.moveTo(0, sy(0)); ctx.lineTo(WS, sy(0)); ctx.moveTo(sx(0), 0); ctx.lineTo(sx(0), WS); ctx.stroke();
  ctx.fillStyle = "#6b7280"; ctx.font = "10px sans-serif";
  for (let t = -Math.floor(L); t <= Math.floor(L); t++) if (t) { ctx.fillRect(sx(t) - 0.5, sy(0) - 3, 1, 6); ctx.fillRect(sx(0) - 3, sy(t) - 0.5, 6, 1); ctx.fillText(t, sx(t) - 3, sy(0) + 13); }
  ctx.fillStyle = C.ink; ctx.font = "italic 13px serif"; ctx.fillText("Re α", WS - 34, sy(0) - 6); ctx.fillText("Im α", sx(0) + 6, 13);
  if (overlay) overlay(ctx, sx, sy, WS / (2 * L));
  ctx.fillStyle = C.muted; ctx.font = "11px sans-serif"; ctx.fillText(label, 6, WS - 6); ctx.restore();
}
const axes = (xn, yn) => ({ x: { name: xn, withLabel: true, strokeColor: "#9ca3af", label: { position: "rt", offset: [-14, 14], fontSize: 14, strokeColor: C.ink }, ticks: { minorTicks: 0, strokeColor: "#9ca3af", label: { fontSize: 10, strokeColor: C.muted } } },
  y: { name: yn, withLabel: true, strokeColor: "#9ca3af", label: { position: "rt", offset: [8, -6], fontSize: 14, strokeColor: C.ink }, ticks: { minorTicks: 0, strokeColor: "#9ca3af", label: { fontSize: 10, strokeColor: C.muted } } } });
const board = (div, bb, xn, yn) => JXG.JSXGraph.initBoard(div, { boundingbox: bb, keepAspectRatio: false, axis: true, showCopyright: false, showNavigation: false, pan: { enabled: false }, zoom: { enabled: false }, defaultAxes: axes(xn, yn) });
const LF = [0]; for (let n = 1; n <= 400; n++) LF[n] = LF[n - 1] + Math.log(n);
const pois = (n, m) => (m <= 0 ? (n === 0 ? 1 : 0) : Math.exp(n * Math.log(m) - m - LF[n]));
// P(n) bars + Poisson reference with the same mean; returns an update function
function countsPlot(bP, cbP) {
  let P = [1], nShow = 10, mean = 0;
  const bars = bP.create("curve", [[0], [0]], { fixed: true, highlight: false, strokeColor: "#c2410c", strokeWidth: 1, fillColor: "#f0a46a", fillOpacity: 0.85 });
  bars.updateDataArray = function () { const xs = [], ys = []; for (let n = 0; n <= nShow; n++) { xs.push(n - 0.38, n - 0.38, n + 0.38, n + 0.38, NaN); ys.push(0, P[n] || 0, P[n] || 0, 0, NaN); } this.dataX = xs; this.dataY = ys; };
  const pl = bP.create("curve", [[0], [0]], { fixed: true, highlight: false, strokeColor: C.obs, strokeWidth: 2, dash: 2, visible: () => cbP.checked });
  pl.updateDataArray = function () { const xs = [], ys = []; for (let n = 0; n <= nShow; n++) { xs.push(n); ys.push(pois(n, mean)); } this.dataX = xs; this.dataY = ys; };
  for (let n = 0; n <= 80; n++) bP.create("point", [n, () => pois(n, mean)], { fixed: true, highlight: false, withLabel: false, size: 2.5, strokeColor: C.obs, fillColor: "#fff", visible: () => cbP.checked && n <= nShow });
  const leg = bP.create("text", [0, 0, () => "<span style='color:#c2410c'>■</span> state" + (cbP.checked ? " &nbsp; <span style='color:" + C.obs + "'>○</span> Poisson, same ⟨n⟩" : "")], { fixed: true, highlight: false, fontSize: 12, strokeColor: C.ink, anchorX: "right", anchorY: "top" });
  return (Pnew) => {
    P = Pnew; mean = 0; let m2 = 0, cum = 0, nEnd = 0; P.forEach((p, n) => { mean += n * p; m2 += n * n * p; });
    for (let n = 0; n < P.length; n++) { cum += P[n]; if (cum > 0.999) { nEnd = n; break; } }
    const varn = m2 - mean * mean; nShow = Math.min(80, Math.max(10, Math.ceil(Math.max(nEnd, mean + 4 * Math.sqrt(varn)))));
    let ymax = 0; for (let n = 0; n <= nShow; n++) ymax = Math.max(ymax, P[n] || 0, cbP.checked ? pois(n, mean) : 0); ymax *= 1.18;
    bP.setBoundingBox([-0.06 * nShow - 1, ymax, nShow + 1, -0.08 * ymax], false); leg.setPosition(JXG.COORDS_BY_USER, [nShow + 0.6, ymax * 0.97]); bP.update();
    return { mean, varn };
  };
}
const sN = K.slider("n", 1, CFG.nMax, 1, CFG.n, (v) => (+v).toFixed(0)), sE = K.slider("η", 0, 1, 0.01, CFG.eta);
const cbP = K.check("Poisson, same mean");
K.root.append(panel);
const bP = board(pdiv, [-1, 1, 12, -0.08], "m", "p'(m)"), upd = countsPlot(bP, cbP);
// binomial p'_m = C(n,m) η^m (1−η)^{n−m};  W_m(α) = (2/π)(−1)^m e^{−2|α|²} L_m(4|α|²)
const binom = (n, e) => { const P = []; for (let m = 0; m <= n; m++) P.push(e <= 0 ? +(m === 0) : e >= 1 ? +(m === n) : Math.exp(LF[n] - LF[m] - LF[n - m] + m * Math.log(e) + (n - m) * Math.log(1 - e))); return P; };
function wRadial(P, r) { const u = 4 * r * r; let a = 1, b = 1 - u, s = P[0] * a + (P.length > 1 ? -P[1] * b : 0);
  for (let k = 1; k < P.length - 1; k++) { const c = ((2 * k + 1 - u) * b - k * a) / (k + 1); a = b; b = c; s += (k % 2 ? 1 : -1) * P[k + 1] * c; }
  return (2 / Math.PI) * Math.exp(-2 * r * r) * s; }
function update() {
  const n = +sN.value, e = +sE.value, P = binom(n, e), st = upd(P);
  const R = 220, tab = []; for (let i = 0; i <= R; i++) tab.push(wRadial(P, (i / R) * CFG.L * Math.SQRT2));
  heat((x, y) => { const t = (Math.hypot(x, y) / (CFG.L * Math.SQRT2)) * R, i = Math.floor(t); return i >= R ? 0 : tab[i] + (t - i) * (tab[i + 1] - tab[i]); },
    CFG.L, 2 / Math.PI, "W(α) after loss, colour scale ±2/π");
  const Q = st.mean > 1e-9 ? (st.varn - st.mean) / st.mean : 0, W0 = (2 / Math.PI) * Math.pow(1 - 2 * e, n);
  panel.textContent =
`⟨n⟩' = ηn = ${f(st.mean)}    Var' = nη(1−η) = ${f(st.varn)}    Q' = −η = ${f(Q)}    g⁽²⁾ = 1 − 1/n = ${f(1 - 1 / n)}
W(0) = (2/π) G'(−1) = (2/π)(1 − 2η)ⁿ = ${f(W0)}   ${W0 < -1e-9 ? "negative" : n % 2 ? "≥ 0: odd n loses its negative centre for η ≤ ½" : "≥ 0 (even n)"}`;
}
for (const x of [sN, sE]) x.addEventListener("input", update);
cbP.onchange = update;
update();
```


### $g^{(2)}$ does not change with losses

Write $u=1-\eta+\eta x$ and differentiate $G'(x)=G(u)$ with the chain rule, $du/dx=\eta$:

$$\frac{dG'}{dx}=\eta\,G^{(1)}(u), \qquad \frac{d^2G'}{dx^2}=\eta^2\,G^{(2)}(u),$$

where $G^{(k)}$ is the $k$-th derivative of the input generating function. At $x=1$ we have $u=1$, so

$$g^{(2)}_{\rm out}(0) = \frac{\langle (\hat a^\dagger)^2 \hat a^2 \rangle'}{\langle \hat a^\dagger \hat a \rangle'^2}= \frac{\eta^2G^{(2)}(1)}{\big(\eta\,G^{(1)}(1)\big)^2}=\frac{G^{(2)}(1)}{G^{(1)}(1)^2}=g^{(2)}_{\rm in}(0).$$

The factors of $\eta$ cancel. Loss removes photons at random, which lowers the mean but leaves the normalised correlations unchanged.

## Two output modes

Now keep both outputs of the beam splitter: mode $c$ (transmitted, $\eta$) and mode $d$ (reflected, $1-\eta$), with vacuum in the second input.

<div style="text-align:center"><svg width="440" height="300" viewBox="0 0 440 300" xmlns="http://www.w3.org/2000/svg" fill="none" stroke="currentColor" stroke-width="1.6" font-family="Times New Roman, serif" font-size="17"><defs><marker id="arrBS10" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="7" markerHeight="7" orient="auto"><path d="M0,0 L10,5 L0,10 z" fill="currentColor" stroke="none"/></marker></defs><line x1="40" y1="170" x2="190" y2="170" stroke-width="2.4" marker-end="url(#arrBS10)"/><line x1="210" y1="285" x2="210" y2="190" stroke-dasharray="6 4" marker-end="url(#arrBS10)"/><rect x="195" y="155" width="30" height="30" transform="rotate(45 210 170)" fill="currentColor" fill-opacity="0.06" stroke-opacity="0.5"/><line x1="188" y1="192" x2="232" y2="148" stroke-width="2.6"/><line x1="230" y1="170" x2="360" y2="170" stroke-width="2.4" marker-end="url(#arrBS10)"/><line x1="210" y1="150" x2="210" y2="50" stroke-width="2.4" marker-end="url(#arrBS10)"/><path d="M362,150 L362,190 A20,20 0 0 0 362,150 Z" fill="currentColor" fill-opacity="0.15"/><path d="M190,48 L230,48 A20,20 0 0 0 190,48 Z" fill="currentColor" fill-opacity="0.15"/><g fill="currentColor" stroke="none"><text x="60" y="160" font-style="italic">â</text><text x="60" y="195" font-size="13">input, p<tspan dy="4" font-size="10">n</tspan></text><text x="220" y="275" font-style="italic">v̂</text><text x="220" y="292" font-size="13">vacuum |0⟩</text><text x="250" y="160" font-style="italic">ĉ</text><text x="250" y="200" font-size="13">transmitted, η</text><text x="222" y="110" font-style="italic">d̂</text><text x="222" y="128" font-size="13">reflected, 1−η</text><text x="392" y="175" font-size="14" font-style="italic">D<tspan dy="4" font-size="11">c</tspan></text><text x="196" y="20" font-size="14" font-style="italic">D<tspan dy="4" font-size="11">d</tspan></text><text x="240" y="230" font-size="13">BS</text></g></svg></div>

$$\hat c=\sqrt\eta\,\hat a+\sqrt{1-\eta}\,\hat v, \qquad \hat d=\sqrt{1-\eta}\,\hat a-\sqrt\eta\,\hat v .$$

The relative minus sign keeps the transformation unitary, so that $[\hat c,\hat d^\dagger]=0$.

The joint generating function is

$$G_{cd}(x,y)=\sum_{l,j}p_{lj}\,x^l y^j ,$$

where $p_{lj}$ is the probability of $l$ photons in $c$ and $j$ in $d$. With $n$ photons in, $j=n-l$ and $p_{l,n-l}=p_n\binom nl\eta^l(1-\eta)^{n-l}$, so the binomial theorem again closes the sum:

$$G_{cd}(x,y)=\sum_{n}p_n\sum_{l=0}^{n}\binom nl(\eta x)^l\big((1-\eta)y\big)^{n-l}=\sum_n p_n\big(\eta x+(1-\eta)y\big)^n=G\big(\eta x+(1-\eta)y\big).$$

Setting $y=1$ gives back the single-mode result $G(1-\eta+\eta x)$.

**Cross-correlation.** Mixed derivatives at $x=y=1$ give the joint moments, e.g. $\partial_x\partial_yG_{cd}\big|_{1,1}=\langle\hat n_c\hat n_d\rangle$:

$$\langle\hat n_c\rangle=\eta\,G^{(1)}(1), \qquad \langle\hat n_d\rangle=(1-\eta)\,G^{(1)}(1), \qquad \langle\hat n_c\hat n_d\rangle=\eta(1-\eta)\,G^{(2)}(1),$$

so

$$g^{(2)}_{cd}=\frac{\langle\hat n_c\hat n_d\rangle}{\langle\hat n_c\rangle\langle\hat n_d\rangle}=\frac{G^{(2)}(1)}{G^{(1)}(1)^2}=g^{(2)}_{\rm in}(0).$$

The coincidence rate between the two outputs measures the $g^{(2)}$ of the input for any $\eta$. This is the principle of the Hanbury Brown–Twiss setup. A single photon gives $G=x$, $G^{(2)}=0$ and $g^{(2)}_{cd}=0$: it is never detected in both outputs at once. A coherent state gives $g^{(2)}_{cd}=1$, and thermal light gives $2$.

## Sum or product of generating functions?

Both rules appear. Which one applies depends on how the two parts are combined.

**Mixture of states: weighted sum.** If the source emits $\hat\rho_1$ with probability $p_1$ and $\hat\rho_2$ with probability $p_2$, then $\hat\rho=p_1\hat\rho_1+p_2\hat\rho_2$. The photon distribution is a mixture, $p_n=p_1p_n^{(1)}+p_2p_n^{(2)}$, and since $G$ is linear in $p_n$,
$$G(x)=p_1G_1(x)+p_2G_2(x).$$
Example: a coherent state that is present only with probability $p$ (otherwise vacuum) has $G=p\,e^{-\lambda(1-x)}+(1-p)$. Then $G'(1)=p\lambda$ and $G''(1)=p\lambda^2$, so $g^{(2)}=1/p>1$: mixing in vacuum causes bunching.

**Independent modes counted together: product.** If a detector counts the total $n=n_1+n_2$ of two *independent* modes (two polarisations, two time bins, two independent sources on separate modes), then $x^{n}=x^{n_1}x^{n_2}$. Independence lets the expectation factorise:
$$G(x)=\langle x^{\hat n_1+\hat n_2}\rangle=\langle x^{\hat n_1}\rangle\langle x^{\hat n_2}\rangle=G_1(x)\,G_2(x).$$
More generally, the joint generating function of independent modes factorises, $G_{12}(x,y)=G_1(x)G_2(y)$. Setting $y=x$ gives the total count. Example: two independent thermal modes with mean $N$ each have $G=\big(1+N(1-x)\big)^{-2}$, so $g^{(2)}=6N^2/(2N)^2=\frac32$, between thermal ($2$) and coherent ($1$).

The product rule does **not** apply when two fields are superposed into the *same* mode, e.g. at a beam splitter. There the amplitudes add ($\hat c=\sqrt\eta\,\hat a+\sqrt{1-\eta}\,\hat v$) rather than the photon numbers. The output modes $c,d$ are correlated, so $G_{cd}(x,y)=G(\eta x+(1-\eta)y)$ does not factorise, except for a coherent input, where $G=e^{-\lambda(1-x)}$ splits into $e^{-\eta\lambda(1-x)}e^{-(1-\eta)\lambda(1-y)}$.


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


# Lecture 13: Atomic dynamics

<div style="text-align:center"><svg width="620" height="230" viewBox="0 0 620 230" xmlns="http://www.w3.org/2000/svg" fill="none" stroke="currentColor" stroke-width="1.5" font-family="Times New Roman, serif" font-size="15"><defs><marker id="arrL13" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="7" markerHeight="7" orient="auto"><path d="M0,0 L10,5 L0,10 z" fill="currentColor" stroke="none"/></marker></defs>
<line x1="40" y1="190" x2="110" y2="190" stroke-width="2.4"/><line x1="40" y1="50" x2="110" y2="50" stroke-width="2.4"/><line x1="40" y1="62" x2="110" y2="62" stroke-dasharray="4 3"/><line x1="70" y1="188" x2="70" y2="65" marker-end="url(#arrL13)"/><line x1="92" y1="188" x2="92" y2="53" stroke-dasharray="2 3" marker-end="url(#arrL13)"/>
<g fill="currentColor" stroke="none"><text x="116" y="194" font-style="italic">|g⟩</text><text x="116" y="54" font-style="italic">|e⟩</text><text x="38" y="130" text-anchor="end" font-style="italic">ω</text><text x="98" y="130" font-style="italic" font-size="13">ω<tspan font-size="10" dy="4">eg</tspan></text><text x="18" y="66" font-size="12" font-style="italic">Δ</text><text x="75" y="222" text-anchor="middle" font-size="14">two levels</text></g>
<line x1="210" y1="190" x2="270" y2="190" stroke-width="2.4"/><line x1="320" y1="160" x2="380" y2="160" stroke-width="2.4"/><line x1="320" y1="168" x2="380" y2="168" stroke-dasharray="4 3"/><line x1="255" y1="45" x2="335" y2="45" stroke-width="2.4"/><line x1="255" y1="30" x2="335" y2="30" stroke-dasharray="4 3"/><line x1="240" y1="188" x2="292" y2="33" stroke-width="2.2" marker-end="url(#arrL13)"/><line x1="350" y1="166" x2="298" y2="33" stroke-width="2.2" marker-end="url(#arrL13)"/>
<g fill="currentColor" stroke="none"><text x="276" y="194" font-style="italic">|g⟩</text><text x="386" y="164" font-style="italic">|s⟩</text><text x="341" y="49" font-style="italic">|e⟩</text><text x="232" y="34" font-size="13" font-style="italic">Δ</text><text x="388" y="178" font-size="13" font-style="italic">δ</text><text x="228" y="120" font-style="italic" text-anchor="end">ω<tspan font-size="10" dy="4">p</tspan><tspan dy="-4">, Ω</tspan><tspan font-size="10" dy="4">p</tspan></text><text x="226" y="140" font-size="12" text-anchor="end">probe</text><text x="338" y="110" font-style="italic">ω<tspan font-size="10" dy="4">c</tspan><tspan dy="-4">, Ω</tspan><tspan font-size="10" dy="4">c</tspan></text><text x="338" y="128" font-size="12">coupling</text><text x="295" y="222" text-anchor="middle" font-size="14">Λ scheme</text></g>
<line x1="480" y1="195" x2="560" y2="195" stroke-width="2.4"/><line x1="480" y1="120" x2="560" y2="120" stroke-width="2.4"/><line x1="480" y1="40" x2="560" y2="40" stroke-width="2.4"/><line x1="510" y1="193" x2="510" y2="123" stroke-width="2.2" marker-end="url(#arrL13)"/><line x1="530" y1="118" x2="530" y2="43" stroke-width="2.2" marker-end="url(#arrL13)"/>
<g fill="currentColor" stroke="none"><text x="566" y="199" font-style="italic">|g⟩</text><text x="566" y="124" font-style="italic">|e⟩</text><text x="566" y="44" font-style="italic">|s⟩</text><text x="504" y="162" font-style="italic" text-anchor="end">ω<tspan font-size="10" dy="4">p</tspan></text><text x="536" y="84" font-style="italic">ω<tspan font-size="10" dy="4">c</tspan></text><text x="520" y="222" text-anchor="middle" font-size="14">ladder (cascade)</text></g></svg></div>

### Two-level atom in a classical field

A classical field $E(t)=E_0\cos\omega t$ couples $\ket g$ and $\ket e$ through the dipole $d=\bra e\hat{\mathbf d}\cdot\boldsymbol\varepsilon\ket g$. Write $\cos\omega t=\frac12(e^{i\omega t}+e^{-i\omega t})$ and keep only the co-rotating terms (RWA). With $\hbar=1$,

$$\hat H = \omega_{eg}\ket e\bra e - \frac{\Omega}{2}\Big(e^{-i\omega t}\ket e\bra g + e^{i\omega t}\ket g\bra e\Big), \qquad \Omega = \frac{dE_0}{\hbar}\ \ \text{(Rabi frequency)} .$$

Remove the fast phase with the ansatz

$$\ket\psi = c_g\ket g + c_e\,e^{-i\omega t}\ket e .$$

Then $i\partial_t\ket\psi=\hat H\ket\psi$ gives $i\dot c_g\ket g+(i\dot c_e+\omega c_e)e^{-i\omega t}\ket e=\omega_{eg}c_ee^{-i\omega t}\ket e-\frac\Omega2\big(c_ge^{-i\omega t}\ket e+c_e\ket g\big)$. Comparing the coefficients of $\ket g$ and $\ket e$,

$$i\dot c_g=-\frac{\Omega}{2}c_e, \qquad i\dot c_e=-\frac{\Omega}{2}c_g-\Delta c_e, \qquad \Delta=\omega-\omega_{eg} .$$

The equations no longer depend on time. For $c_g(0)=1$ the solution gives **Rabi oscillations**,

$$P_e(t)=|c_e|^2=\frac{\Omega^2}{\Omega'^2}\sin^2\frac{\Omega' t}{2}, \qquad \Omega'=\sqrt{\Omega^2+\Delta^2},$$

with full inversion only on resonance.

> [!note] Why a laser needs at least 3 levels
> In steady state a driven two-level atom, with damping, gives $p_e \le \frac12$. Absorption and stimulated emission have the same rate, so pumping on the same transition can at most equalise the populations, never invert them. Population inversion needs a third (or fourth) level: pump to an auxiliary level, which decays quickly into the upper lasing level.

### Three-level atom: Λ and ladder schemes

In the **Λ scheme** two ground states $\ket g,\ket s$ share the excited state $\ket e$. A weak **probe** ($\omega_p$, $\Omega_p$) drives $g\leftrightarrow e$ and a strong **coupling** field ($\omega_c$, $\Omega_c$) drives $s\leftrightarrow e$. In the **ladder** scheme the second field instead drives $e\to s$ upwards. With energies measured from $\ket g$,

$$\hat H=\omega_{sg}\ket s\bra s+\omega_{eg}\ket e\bra e-\frac{\Omega_p}{2}\Big(e^{-i\omega_pt}\ket e\bra g+\text{h.c.}\Big)-\frac{\Omega_c}{2}\Big(e^{-i\omega_ct}\ket e\bra s+\text{h.c.}\Big).$$

Each amplitude carries the phase of the fields that reach that level from $\ket g$:

$$\ket\psi=c_g\ket g+c_e\,e^{-i\omega_pt}\ket e+c_s\,e^{-i(\omega_p-\omega_c)t}\ket s .$$

This makes the equations time-independent and defines two detunings:

$$\Delta=\omega_p-\omega_{eg}\ \ \text{(single-photon detuning)}, \qquad \delta=\omega_p-\omega_c-\omega_{sg}\ \ \text{(two-photon detuning)}.$$

(For the ladder, $\ket s$ is reached by absorbing both photons: use $e^{-i(\omega_p+\omega_c)t}$ and $\delta=\omega_p+\omega_c-\omega_{sg}$.) Inserting the ansatz as for two levels:

$$i \dot{c_g}=-\frac{\Omega_p}{2} c_e$$
$$i \dot{c_e} = -\Delta c_e - \frac{\Omega_p}{2} c_g -\frac{\Omega_c}{2}c_s$$
$$i\dot{c}_s=-\delta c_s - \frac{\Omega_c}{2} c_e$$
or written as a matrix:

$$ i \partial_t\begin{pmatrix} 
c_g \\ c_e \\ c_s
\end{pmatrix} = -\begin{pmatrix} 0 & \Omega_p/2 & 0 \\ \Omega_p/2 & \Delta & \Omega_c/2 \\ 0 & \Omega_c/2 & \delta \end{pmatrix} \begin{pmatrix} 
c_g \\ c_e \\ c_s
\end{pmatrix}
$$

## Dark state and coherent population trapping

At two-photon resonance ($\delta=0$), look for a superposition of the two ground states $\ket{D}=a \ket{g} + b \ket{s}$ that is not coupled to $\ket e$. From the matrix above,

$$\bra{e} \hat H \ket{D} = -\frac{1}{2}\big(\Omega_p a + \Omega_c b\big)=0
\quad\Rightarrow\quad
\ket{D}=\frac{\Omega_c\ket{g}-\Omega_p \ket{s}}{\sqrt{\Omega_p^2 + \Omega_c^2}} .$$

The orthogonal combination is the **bright state**,

$$\ket{B}=\frac{\Omega_p \ket{g} + \Omega_c \ket{s}}{\sqrt{\Omega_p^2 + \Omega_c^2}}, \qquad \bra e\hat H\ket B=-\frac12\sqrt{\Omega_p^2+\Omega_c^2} .$$

Only $\ket B$ couples to $\ket e$. The two excitation paths $g\to e$ and $s\to e$ interfere destructively for $\ket D$. Population that decays from $\ket e$ into $\ket D$ stays there, because $\ket D$ is a zero-energy eigenstate decoupled from the light. This is **coherent population trapping**: the atoms stop absorbing and fluorescing.

## Electromagnetically induced transparency (EIT)

What happens to a weak probe passing through such atoms? Model the decay by complex energies: $\gamma$ for $\ket e$ (spontaneous emission) and $\gamma_s$ for the $g$–$s$ coherence (dephasing, usually $\gamma_s\ll\gamma$). For a weak probe ($\Omega_p\ll\Omega_c$) the atoms stay in $\ket g$, so $c_g\approx1$:

$$i \dot{c}_e = -\Big(\Delta + i \frac{\gamma}{2}\Big) c_e- \frac{\Omega_p}{2}-\frac{\Omega_c}{2}c_s, \qquad
i \dot{c}_s = -\Big(\delta + i \frac{\gamma_s}{2}\Big)c_s - \frac{\Omega_c}{2}c_e .$$

**Steady state** ($\dot c_e=\dot c_s=0$). The second equation gives $c_s$; inserting it into the first,

$$c_s =-\frac{\Omega_c/2}{\delta + i\gamma_s/2}\,c_e, \qquad
c_e =- \frac{\Omega_p/2}{\Delta + i \gamma/2 - \dfrac{\Omega_c^2/4}{\delta+i\gamma_s/2}} .$$

**Susceptibility.** The probe $\mathbf E=\boldsymbol\varepsilon\,\frac{E_0}{2}(e^{-i\omega_pt}+\text{c.c.})$ induces a dipole $\langle\hat d\rangle=d\,(c_e e^{-i \omega_p t}+\text{c.c.})$ per atom. With $N$ atoms per unit volume, $P=N \langle \hat d \rangle=\epsilon_0\chi E$. Comparing the $e^{-i\omega_pt}$ parts, $N d\, c_e = \epsilon_0 \chi E_0/2$, and with $\Omega_p=dE_0/\hbar$:

$$\chi = - \frac{N d^2}{\epsilon_0 \hbar}\; \frac{1}{\Delta + i \gamma/2 - \dfrac{\Omega_c^2/4}{\delta+i\gamma_s/2}}, \qquad n=\sqrt{1+\chi}\approx 1+\frac{\chi}{2}.$$

$\mathrm{Im}\,\chi$ gives absorption (intensity absorption coefficient $\alpha=\frac{\omega}{c}\mathrm{Im}\,\chi$) and $\mathrm{Re}\,\chi$ gives the refractive index. Without the coupling ($\Omega_c=0$) this is the Lorentzian of a two-level atom. Its resonant absorption coefficient is $\alpha_0=\frac{2\omega}{c\gamma}\frac{Nd^2}{\epsilon_0\hbar}$.

For a resonant coupling field ($\Delta=\delta$) and $\gamma_s=0$:

$$\chi =-\frac{N d^2}{\epsilon_0 \hbar}\;\frac{1}{\Delta + i \gamma/2 - \dfrac{\Omega_c^2}{4 \Delta}} .$$

- **Imaginary part.** At $\Delta=0$ the term $\Omega_c^2/4\Delta$ diverges, so $\chi=0$. The medium is exactly transparent at two-photon resonance: the **transparency window**. Its width is $\approx\Omega_c^2/\gamma$ for $\Omega_c\lesssim\gamma$. For $\Omega_c\gg\gamma$ the line splits into two peaks at $\Delta=\pm\Omega_c/2$, the Autler–Townes doublet of the dressed states.
- **Real part.** Inside the window $\mathrm{Re}\,\chi$ varies steeply and linearly, $\chi\approx\frac{Nd^2}{\epsilon_0\hbar}\frac{4\Delta}{\Omega_c^2}$, with zero absorption. This gives slow light (below).

**Interactive plot.** $\mathrm{Im}\,\chi$ and $\mathrm{Re}\,\chi$ against probe detuning, in units where the bare resonant absorption is 1. Increase $\Omega_c$ to go from EIT to Autler–Townes, and increase $\gamma_s$ to see the window fill in. Detune the coupling field, $\Delta_c\gg\gamma$, to get the far-detuned (Raman) case: a narrow resonance near $\Delta=\Delta_c$, shifted by the light shift.

```dataviewjs
// ===== CONFIG =====
const CFG = { Oc: 1.0, OcMax: 6, gs: 0.0, gsMax: 0.3, Dc: 0, DcMax: 15 };   // all in units of γ
// ==================
// ---- loader (leave as is) ----
const LIB = "FUW/lib/";
const load = (src) => new Promise((ok, no) => { const s = document.createElement("script"); s.src = src; s.onload = ok; s.onerror = () => no(new Error("could not load " + src)); document.head.append(s); });
const libPath = async (n) => { const here = dv.current().file.folder, up = here.includes("/") ? here.slice(0, here.lastIndexOf("/")) + "/" : ""; for (const p of [LIB + n, "lib/" + n, here + "/lib/" + n, up + "lib/" + n, ...app.vault.getFiles().filter((x) => x.path.endsWith("lib/" + n)).map((x) => x.path)]) if (await app.vault.adapter.exists(p)) return p; throw new Error("lib/" + n + " not found in this vault (is the lib folder synced to this computer?)"); };
if (!window.JXG) await (window.__jxg ??= libPath("jsxgraphcore.js").then((p) => load(app.vault.adapter.getResourcePath(p))).catch(() => load("https://cdn.jsdelivr.net/npm/jsxgraph@1.10.1/distrib/jsxgraphcore.js")).catch((e) => { window.__jxg = null; throw e; }));
if (!window.RL) await (window.__rl ??= libPath("rlti.js").then((p) => load(app.vault.adapter.getResourcePath(p))).catch((e) => { window.__rl = null; throw e; }));
const K = await RL.init(dv), { f, el, C } = K;
// ---- controls ----
const sO = K.slider("Ω_c / γ", 0, CFG.OcMax, 0.01, CFG.Oc), sG = K.slider("γ_s / γ", 0, CFG.gsMax, 0.001, CFG.gs, (v) => (+v).toFixed(3));
const sC = K.slider("Δ_c / γ (coupling detuning)", -CFG.DcMax, CFG.DcMax, 0.1, CFG.Dc, (v) => (+v).toFixed(1));
const cb2 = K.check("two-level reference (Ω_c = 0)");
const box = "background:#fff;border:1px solid #e5e7eb;border-radius:10px", H = Math.round(K.W * 0.42);
const dI = el("div", `width:${K.W}px;height:${H}px;${box};touch-action:none;margin-top:6px`);
const dR = el("div", `width:${K.W}px;height:${H}px;${box};touch-action:none;margin-top:10px`);
const panel = el("div", "font-family:var(--font-monospace,monospace);font-size:0.8em;line-height:1.55;white-space:pre-wrap;color:var(--text-normal);margin-top:6px");
K.root.append(dI, dR, panel);
const ax = (n, pos, off) => ({ name: n, withLabel: true, strokeColor: "#9ca3af", label: { position: pos, offset: off, fontSize: 14, strokeColor: C.ink }, ticks: { minorTicks: 0, strokeColor: "#9ca3af", label: { fontSize: 10, strokeColor: C.muted } } });
const mk = (div, yn) => JXG.JSXGraph.initBoard(div, { boundingbox: [-6, 1.1, 6, -0.1], keepAspectRatio: false, axis: true, showCopyright: false, showNavigation: false, pan: { enabled: false }, zoom: { enabled: false }, defaultAxes: { x: ax("Δ / γ", "rt", [-14, 14]), y: ax(yn, "rt", [8, -6]) } });
const bI = mk(dI, "Im χ (absorption)"), bR = mk(dR, "Re χ (dispersion)");
// χ(Δ) in units of N d²/(ε₀ħ)·(2/γ):  χ = −(γ/2) / (Δ + iγ/2 − (Ω_c²/4)/(δ + iγ_s/2)),  δ = Δ − Δ_c,  γ = 1
const cdiv = (a, b) => { const d = b[0] * b[0] + b[1] * b[1]; return [(a[0] * b[0] + a[1] * b[1]) / d, (a[1] * b[0] - a[0] * b[1]) / d]; };
function chi(D, Oc) { const g = 1, gs = Math.max(+sG.value, 1e-7), dl = D - +sC.value;
  const t = cdiv([Oc * Oc / 4, 0], [dl, gs / 2]), den = [D - t[0], g / 2 - t[1]];
  const c = cdiv([-g / 2, 0], den); return c; }
const opt = (c, w, dash = 0, vis) => ({ fixed: true, highlight: false, strokeColor: c, strokeWidth: w, dash, numberPointsHigh: 3000, numberPointsLow: 1200, ...(vis ? { visible: vis } : {}) });
for (const [b, k] of [[bI, 1], [bR, 0]]) {
  b.create("functiongraph", [(D) => chi(D, 0)[k], -60, 60], opt(C.muted, 1.2, 2, () => cb2.checked));
  b.create("functiongraph", [(D) => chi(D, +sO.value)[k], -60, 60], opt(k ? C.obs : C.sel, 2.2));
  b.create("line", [[0, 0], [0, 1]], opt(C.faint, 0.8, 1));
}
function update() {
  const Oc = +sO.value, gs = +sG.value, Dc = +sC.value, R = Math.max(5, Math.abs(Dc) + 3, Oc + 2);
  let mI = 0.2, mR = 0.2; for (let i = 0; i <= 3000; i++) { const D = -R + (2 * R * i) / 3000, c = chi(D, Oc); mI = Math.max(mI, c[1]); mR = Math.max(mR, Math.abs(c[0])); }
  if (cb2.checked) { mI = Math.max(mI, 1); mR = Math.max(mR, 0.5); }
  bI.setBoundingBox([-R, mI * 1.15, R, -0.08 * mI], false); bR.setBoundingBox([-R, mR * 1.2, R, -mR * 1.2], false); bI.update(); bR.update();
  const c0 = chi(Dc, Oc), h = 1e-4, slope = (chi(Dc + h, Oc)[0] - chi(Dc - h, Oc)[0]) / (2 * h);
  panel.textContent =
`χ in units of N d²/(ε₀ħ)·(2/γ): the bare resonant absorption is Im χ = 1 (dashed).   Probe scanned, δ = Δ − Δ_c.
at two-photon resonance (Δ = Δ_c = ${f(Dc)} γ):  Im χ = ${f(c0[1])}   dRe χ/dΔ = ${f(slope)} /γ  ${slope > 0 ? "(normal dispersion → slow light)" : ""}
${Math.abs(Dc) < 1 ? (Oc <= 1 ? `EIT: window width ≈ Ω_c²/γ = ${f(Oc * Oc)} γ;  slope ≈ 2γ/Ω_c² = ${Oc > 0 ? f(2 / (Oc * Oc)) : "∞"} /γ (γ_s = 0)` : `Autler–Townes: absorption peaks near Δ ≈ ±Ω_c/2 = ±${f(Oc / 2)} γ`) : `far-detuned coupling: narrow Raman feature near Δ ≈ Δ_c + light shift Ω_c²/(4Δ_c) = ${f(Dc + Oc * Oc / (4 * Dc))} γ`}${gs > 0 ? `   — ground dephasing γ_s fills the window (needs Ω_c²/γ ≫ γ_s)` : ""}`;
}
for (const s of [sO, sG, sC]) s.addEventListener("input", update);
cb2.onchange = update;
update();
```

### Slow light

The wave number in the medium is $k=n(\omega)\,\omega/c$, so

$$v_g = \frac{d \omega }{dk}=\frac{c}{n_g}, \qquad n_g=n+ \omega \frac{d n}{d \omega}.$$

Inside the window $n\approx1$, but $dn/d\omega=dn/d\Delta=\frac12\,d\chi/d\Delta$ is huge:

$$n_g \approx \omega \frac{dn}{d \Delta} = \frac{\omega}{2}\, \frac{N d^2}{\epsilon_0 \hbar}\, \frac{4}{\Omega_c^2}
\quad\Rightarrow\quad
v_g =\frac{c}{n_g}= \frac{\Omega_c^2}{ \alpha_0 \gamma},$$

using $\frac{\omega Nd^2}{\epsilon_0\hbar}=\frac{\alpha_0c\gamma}{2}$. This requires the window to be wider than the ground-state decoherence, $\Omega_c^2/\gamma\gg\gamma_s$.

With the **optical depth** $\mathrm{OD}=\alpha_0 L$ (transmission $e^{-\mathrm{OD}}$ without the coupling field) and typical alkali-vapour numbers,

$$\frac{\gamma}{2 \pi} =6\ \text{MHz}, \quad \frac{\Omega_c}{2\pi} = 3\ \text{MHz}, \quad \mathrm{OD}=50,\quad L=1\ \text{cm}
\quad\Rightarrow\quad
v_g = \frac{\Omega_c^2L}{\mathrm{OD}\,\gamma}\approx 2\ \text{km/s},$$

a reduction of $c$ by a factor of $\sim10^5$. The pulse delay is $\tau=L/v_g=\mathrm{OD}\,\gamma/\Omega_c^2\approx5\ \mu$s. Switching $\Omega_c$ off while the pulse is inside the medium stores it in the $g$–$s$ coherence (EIT quantum memory).

### Far detuned: Raman transitions

For $|\Delta|\gg\gamma,\Omega_p,\Omega_c$ the excited state is hardly populated and follows the ground states adiabatically. Set $\dot c_e\approx0$ in $i\dot c_e=-\Delta c_e-\frac{\Omega_p}{2}c_g-\frac{\Omega_c}{2}c_s$:

$$c_e\approx-\frac{\Omega_pc_g+\Omega_cc_s}{2\Delta}.$$

Inserting this into the equations for $c_g,c_s$ eliminates $\ket e$ and leaves an **effective two-level atom** $\{\ket g,\ket s\}$, in the same convention $i\partial_t\mathbf c=-H\mathbf c$ as before:

$$i\partial_t\begin{pmatrix}c_g\\c_s\end{pmatrix}=-\hat H_{\rm eff}\begin{pmatrix}c_g\\c_s\end{pmatrix}, \qquad
\hat H_{\rm eff}= -\begin{pmatrix} \dfrac{\Omega_p^2}{4\Delta} & \dfrac{\Omega_R}{2} \\[2mm] \dfrac{\Omega_R}{2} & \dfrac{\Omega_c^2}{4\Delta}-\delta \end{pmatrix}, \qquad
\Omega_R=\frac{\Omega_p \Omega_c}{2 \Delta} .$$

The diagonal terms are the light shifts of $\ket g$ and $\ket s$. The off-diagonal **Raman Rabi frequency** $\Omega_R$ drives $g\leftrightarrow s$ through a virtual excited state. The Raman resonance sits at $\delta=(\Omega_c^2-\Omega_p^2)/4\Delta$, and spontaneous emission is suppressed by $\gamma/\Delta$.
