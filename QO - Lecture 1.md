← [[QO - chapter I|Full chapter]] · [[QO - Lecture 2|Lecture 2 →]]

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

---
[[QO - Lecture 2|Next: Lecture 2 →]]
