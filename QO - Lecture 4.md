← [[QO - Lecture 3|Lecture 3]] · [[QO - chapter I|Full chapter]]

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

- $\Delta t$ - total measurement time
- $\delta t$ - single interval, short enough that at most one click happens in it

Probability of a click in one interval ($C$ includes the quantum efficiency and $1/\hbar\omega$):

$$p=C\, \mathcal{I}\, \delta t \ll 1$$

Mean number of counts in the whole window:

$$W= C\, \mathcal{I}\, \Delta t = Np \qquad\Rightarrow\qquad p=\frac{W}{N} \ll 1$$

**Probability of $n$ counts.** The intervals are independent, so $n$ is binomially distributed. For $N\to\infty$ at fixed $W$:

$$p_n = \binom{N}{n}\left(\frac{W}{N}\right)^n \left(1-\frac{W}{N}\right)^{N-n}$$

- $\binom{N}{n} = \frac{N(N-1)\cdots(N-n+1)}{n!} \to \frac{N^n}{n!}$, which cancels the $N^{-n}$;
- $\left(1-\frac{W}{N}\right)^{N-n} \to e^{-W}$.

$$p_n \;\to\; \frac{W^n}{n!}\,e^{-W}$$

A **Poisson** distribution: $\langle n\rangle = W$ and $\mathrm{Var}(n) = \langle n\rangle$.  The same statistics as a coherent state.

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

 the Bose–Einstein distribution of §6, now obtained from classical intensity fluctuations.

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
- Thermal state with mean photon number $N$ is a Gaussian mixture of coherent states, i.e. a coherent state "smeared out" around $\alpha=0$:

$$\hat\rho_{\rm th} = \sum_n \frac{N^n}{(1+N)^{n+1}} \ket{n} \bra{n}, \qquad P(\alpha)= \frac{1}{\pi N}\,e^{-|\alpha|^2/N}$$

*Check*: photon-number distribution, using $|\langle n|\alpha\rangle|^2 = e^{-|\alpha|^2}|\alpha|^{2n}/n!$, polar coordinates and $\int_0^\infty dr\, r^{2n+1}e^{-ar^2} = \frac{n!}{2a^{n+1}}$ (as in §2.2) with $a = 1+\frac1N$:

$$\bra{n} \hat\rho_{\rm th} \ket{n} = \int d^2 \alpha\; P(\alpha)\, |\langle n|\alpha\rangle|^2 = \frac{2\pi}{\pi N\, n!}\int_0^\infty dr\; r^{2n+1}\, e^{-r^2(1+1/N)} = \frac{1}{N}\frac{1}{(1+1/N)^{n+1}} = \frac{N^n}{(1+N)^{n+1}} $$

This is exactly Mandel's formula (§8.4) with $W = |\alpha|^2$: a state with a genuine, nonnegative $P$ behaves like classical light with a fluctuating amplitude.

**Nonclassicality.** The photon-number variance is $\mathrm{Var}(n) = \langle (\hat a^\dagger \hat a)^2 \rangle - \langle \hat a^\dagger \hat a \rangle^2$. Normal ordering, $(\hat a^\dagger\hat a)^2 = \hat a^\dagger(\hat a^\dagger\hat a+1)\hat a = \hat a^{\dagger2}\hat a^2 + \hat a^\dagger\hat a$, gives $\langle \hat n^2\rangle - \langle\hat n\rangle = \langle \hat a^{\dagger2}\hat a^2\rangle = \int d^2\alpha\, P(\alpha)|\alpha|^4$, so

$$\mathrm{Var}(n) - \langle \hat n\rangle = \int d^2\alpha\; P(\alpha)\,\big(|\alpha|^2 - \langle\hat n\rangle\big)^2$$

If $P\ge 0$ this is $\ge 0$. Hence **sub-Poissonian** light requires a $P$-function that is negative or more singular than δ.

**Example: Fock state** $\ket{n}$: $\mathrm{Var}(n) = 0 < \langle\hat n\rangle = n$ for $n\ge1$ — sub-Poissonian, hence nonclassical: no nonnegative $P(\alpha)$ can describe it.

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

### 8.8 Other witnesses of nonclassicality: quadrature squeezing

Quadrature $\hat X_\theta = \frac12\left(\hat a\, e^{-i\theta} + \hat a^\dagger e^{i\theta}\right)$, vacuum (and coherent-state) variance $\frac14$. By the argument of §8.5,

$$\Delta^2 X_\theta = \tfrac14 + \int d^2\alpha\; P(\alpha)\,\big(\mathrm{Re}(\alpha e^{-i\theta}) - \langle \hat X_\theta\rangle\big)^2 \;\geq\; \tfrac14 \quad \text{if } P\ge 0$$

so **squeezing**, $\Delta^2 X_\theta < \frac14$ for some $\theta$, is a nonclassicality witness (it catches squeezed states, which $g^{(2)}$ may miss).

**Balanced homodyne detection** measures $\hat X_\theta$: the signal $\hat a$ is mixed on a 50:50 BS with a strong coherent **local oscillator** (LO) $\ket\beta$, $\beta = |\beta|e^{i\theta}$, and the two photocurrents are subtracted.

<div style="text-align:center"><svg width="620" height="300" viewBox="0 0 620 300" xmlns="http://www.w3.org/2000/svg" fill="none" stroke="currentColor" stroke-width="1.6" font-family="Times New Roman, serif" font-size="18"><defs><marker id="arrBHD" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="7" markerHeight="7" orient="auto"><path d="M0,0 L10,5 L0,10 z" fill="currentColor" stroke="none"/></marker></defs><g transform="translate(40,0)"><line x1="60" y1="160" x2="222" y2="160" marker-end="url(#arrBHD)"/><line x1="240" y1="290" x2="240" y2="178" marker-end="url(#arrBHD)"/><rect x="222" y="142" width="36" height="36"/><line x1="222" y1="178" x2="258" y2="142" stroke-width="2.4"/><line x1="258" y1="160" x2="385" y2="160" marker-end="url(#arrBHD)"/><line x1="240" y1="142" x2="240" y2="62" marker-end="url(#arrBHD)"/><path d="M386,146 h12 a14,14 0 0 1 0,28 h-12 z"/><path d="M226,60 v-12 a14,14 0 0 1 28,0 v12 z"/><line x1="268" y1="34" x2="452" y2="34"/><line x1="412" y1="160" x2="470" y2="160"/><line x1="452" y1="34" x2="470" y2="34"/><line x1="470" y1="34" x2="470" y2="70" marker-end="url(#arrBHD)"/><circle cx="470" cy="88" r="16"/><line x1="470" y1="160" x2="470" y2="106" marker-end="url(#arrBHD)"/><line x1="486" y1="88" x2="530" y2="88" marker-end="url(#arrBHD)"/><g fill="currentColor" stroke="none"><g font-style="italic"><text x="54" y="152" text-anchor="end">signal â</text><text x="252" y="282">LO |β⟩, β = |β|e<tspan dy="-7" font-size="12">iθ</tspan></text><text x="320" y="152">ĉ</text><text x="250" y="110">d̂</text><text x="500" y="116" font-size="15">i₋ ∝ |β| X̂<tspan dy="5" font-size="11">θ</tspan></text></g><text x="470" y="95" text-anchor="middle" font-size="22">−</text><text x="400" y="196" text-anchor="middle" font-size="14">D<tspan dy="3" font-size="10">c</tspan></text><text x="214" y="30" text-anchor="end" font-size="14">D<tspan dy="3" font-size="10">d</tspan></text><text x="284" y="136" font-size="13">BS 50:50</text></g></g></svg></div>

With $\hat c = \frac{1}{\sqrt2}(\hat a+\hat b)$, $\hat d = \frac{1}{\sqrt2}(\hat a-\hat b)$:

$$\hat n_c - \hat n_d = \hat a^\dagger \hat b + \hat b^\dagger \hat a \;\approx\; \beta\,\hat a^\dagger + \beta^*\hat a = 2|\beta|\,\hat X_\theta$$

(replacing the strong LO mode $\hat b$ by the number $\beta$). The LO intensity amplifies the signal quadrature above the detector noise; the LO phase $\theta$ selects which quadrature is measured.

Summary of witnesses: 
- $g^{(2)}(0)<1$ (sub-Poissonian),
- $\Delta^2 X_\theta<\frac14$ (squeezing), 
- negative Wigner function (§8.9). 
Each is **sufficient** for nonclassicality, none is necessary.

### 8.9 Wigner function

> The Wigner function $W(\alpha)$ is a phase-space "quasi-probability" distribution: it behaves like a joint probability for the two quadratures, except that it can be negative and negativity is a signature of nonclassical light. Contrary to the $P$ function, its marginal distributions represent the actual probabilities

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
[[QO - Lecture 3|← Previous: Lecture 3]] · [[QO - Lecture 5|Next: Lecture 5 →]]
