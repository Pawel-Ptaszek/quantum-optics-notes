← [[QO - Lecture 4|Lecture 4]] · [[QO - chapter I|Full chapter]]

# Lecture 5

## 9. Glauber's theory of photodetection and correlation functions

### 9.1 A detector measures click probabilities

A photodetector doesn't measure "the field". The experimentally accessible quantities are click probabilities (per unit time):

| Quantity | Meaning |
| --- | --- |
| $P_1(\mathbf r,t)\,\delta t$ | probability of a click at $\mathbf r$ in $[t, t+\delta t]$ |
| $P_2(\mathbf r,t;\mathbf r',t')\,\delta t\,\delta t'$ | joint probability of clicks at $(\mathbf r,t)$ and at $(\mathbf r',t')$ |
| $P_n(\mathbf r_1,t_1;\dots;\mathbf r_n,t_n)$ | $n$-fold coincidences |

We will express them through the state of the field.

### 9.2 Detector & field interaction

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

but we don't measure $\Phi$ → at the end we trace over it.

**1st-order perturbation theory:**

$$\langle \epsilon,\Phi | \psi_I \rangle \approx \frac{1}{i \hbar} \int dt'\, \bra{\epsilon, \Phi} \hat H_I(t') \ket{g ,\psi_0} = -\frac{1}{i \hbar} \int dt'\, e^{i (\epsilon - \epsilon_g) t'/\hbar}\, d_{\epsilon g}\, \bra{\Phi} \hat{E}(t') \ket{\psi_0}$$

> [!note] Comment
> Same as the classical result §9.3, but the field amplitude $E(t')$ is replaced by the matrix element $\bra\Phi\hat E(t')\ket{\psi_0}$ between field states.

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

**Total click probability**= sum over the unobserved $\Phi$ (and the continuum of $\epsilon$), using $\sum_\Phi \ket\Phi\bra\Phi = \hat 1$:

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

first-order coherence; $|g^{(1)}|$ is the **fringe visibility** in an interferometer.

$$g^{(2)}(\tau) = \frac{\langle \hat E^{(-)}(t)\,\hat E^{(-)}(t+\tau)\,\hat E^{(+)}(t+\tau)\,\hat E^{(+)}(t)\rangle}{\langle \hat E^{(-)}(t)\hat E^{(+)}(t)\rangle^2}$$

intensity correlations (HBT). For a single mode at $\tau=0$ it reduces to $\langle(\hat a^\dagger)^2\hat a^2\rangle/\langle\hat a^\dagger\hat a\rangle^2$ of §8.7. Bunching: $g^{(2)}(0) > g^{(2)}(\tau)$; antibunching: $g^{(2)}(0) < g^{(2)}(\tau)$.

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
[[QO - Lecture 4|← Previous: Lecture 4]] · [[QO - Lecture 6|Next: Lecture 6 →]]
