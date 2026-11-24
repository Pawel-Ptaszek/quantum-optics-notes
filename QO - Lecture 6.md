← [[QO - Lecture 5|Lecture 5]] · [[QO - chapter I|Full chapter]]

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

$$G^{(2)}(\tau) = \big\langle\mathcal E^*(t)\mathcal E(t+\tau)\big\rangle\big\langle\mathcal E^*(t+\tau)\mathcal E(t)\big\rangle + \big\langle\mathcal E^*(t)\mathcal E(t)\big\rangle\big\langle\mathcal E^*(t+\tau)\mathcal E(t+\tau)\big\rangle \\= |G^{(1)}(\tau)|^2+\big[G^{(1)}(0)\big]^2. \tag{10.26}$$

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

$$G_{\rm clicks}(x) = \sum_k P_k\,x^k = \sum_n p_n\sum_{k=0}^n\binom nk(\eta x)^k(1-\eta)^{n-k} \\= \sum_n p_n\,(1-\eta+\eta x)^n = G(1-\eta+\eta x). \tag{10.31}$$

Each derivative with respect to $x$ produces a factor $\eta$, so the factorial moments are scaled as $\langle k(k-1)\cdots(k-r+1)\rangle = \eta^r\langle n(n-1)\cdots(n-r+1)\rangle$. In particular $\bar k = \eta\bar n$ and $\langle k(k-1)\rangle = \eta^2\langle n(n-1)\rangle$. Two consequences follow. First, the measured second-order correlation function is independent of the efficiency,

$$g^{(2)}_{\rm clicks}(0) = \frac{\langle k(k-1)\rangle}{\bar k^2} = \frac{\eta^2\langle n(n-1)\rangle}{\eta^2\bar n^2} = g^{(2)}(0), \tag{10.32}$$

which is why $g^{(2)}$ is the preferred measure of nonclassicality in experiments with lossy detectors. Second, since $\Delta^2k-\bar k = \langle k(k-1)\rangle-\bar k^2 = \eta^2\big(\Delta^2n-\bar n\big)$, the Mandel parameter $Q = (\Delta^2n-\bar n)/\bar n$ is reduced by the efficiency,

$$Q_{\rm clicks} = \frac{\Delta^2k-\bar k}{\bar k} = \frac{\eta^2(\Delta^2n-\bar n)}{\eta\bar n} = \eta\,Q. \tag{10.33}$$

Losses drive every distribution towards the Poisson distribution. They preserve the sign of $Q$, so a super-Poissonian distribution stays super-Poissonian, but the departure from the Poisson value shrinks in proportion to $\eta$. In particular an inefficient detector cannot make the observed distribution narrower than the Poisson distribution; the sub-Poissonian character of a nonclassical state, $Q<0$, is diluted and disappears completely as $\eta\to0$.

**Mixtures of coherent states.** For the classical state $\hat\rho = \int d^2\alpha\,P(\alpha)\ket\alpha\bra\alpha$ with $P\ge0$, applying (10.30) to each member of the mixture gives

$$P_k = \int d^2\alpha\;P(\alpha)\,\frac{\big(\eta|\alpha|^2\big)^k}{k!}\,e^{-\eta|\alpha|^2}, \tag{10.34}$$

which is Mandel's formula of §8.4 with $W=\eta|\alpha|^2$. By the result of §8.4, $\Delta^2k = \bar k+\mathrm{Var}(W) = \bar k+\eta^2\,\mathrm{Var}(|\alpha|^2)\ge\bar k$. A classical field, observed with any detector efficiency, never yields sub-Poissonian counting statistics.

---
[[QO - Lecture 5|← Previous: Lecture 5]] · [[QO - Lecture 7|Next: Lecture 7 →]]
