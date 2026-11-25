# Quadrature conventions: what changes, what doesn't

General convention, with one parameter $\lambda$:
$$
\hat x = \lambda(\hat a + \hat a^\dagger), \qquad \hat p = -i\lambda(\hat a - \hat a^\dagger), \qquad \lambda \in \left\{\tfrac{1}{\sqrt2},\ \tfrac12,\ 1\right\}.
$$

## 1. Derived quantities (check each line yourself)

**Commutator.** Using $[\hat a,\hat a^\dagger]=1$:
$$
[\hat x,\hat p] = -i\lambda^2\big[\hat a+\hat a^\dagger,\ \hat a-\hat a^\dagger\big] = -i\lambda^2(-1-1) = 2i\lambda^2 \equiv i\hbar_{\rm eff}.
$$
So $\lambda$ sets an effective $\hbar_{\rm eff} = 2\lambda^2$. Everything below follows from this.

**Inverse map.** $\hat a = \dfrac{\hat x + i\hat p}{2\lambda}$, so a phase-space point is labelled by $\gamma = \dfrac{x+ip}{2\lambda}$.

**Coherent-state centre.** From $\hat a|\alpha\rangle = \alpha|\alpha\rangle$: $\langle\hat x\rangle = 2\lambda\,\mathrm{Re}\,\alpha$ and $\langle\hat p\rangle = 2\lambda\,\mathrm{Im}\,\alpha$.

**Vacuum variance.** $\langle 0|(\hat a+\hat a^\dagger)^2|0\rangle = \langle 0|\hat a\hat a^\dagger|0\rangle = 1$, so $\mathrm{Var}(\hat x) = \lambda^2 = \hbar_{\rm eff}/2$.

**Wigner function** (with $\hbar \to \hbar_{\rm eff}$):
$$
W(x,p) = \frac{1}{\pi\hbar_{\rm eff}}\int dy\,\langle x+y|\hat\rho|x-y\rangle\,e^{-2ipy/\hbar_{\rm eff}} = \frac{1}{\pi\hbar_{\rm eff}}\,\mathrm{Tr}\big[\hat\rho\,\hat D\,\hat\Pi\,\hat D^\dagger\big].
$$

**Displacement and its BCH phase.**
$\hat D(x,p) = e^{i(p\hat x - x\hat p)/\hbar_{\rm eff}} = e^{ip\hat x/\hbar_{\rm eff}}\,e^{-ix\hat p/\hbar_{\rm eff}}\,e^{-ipx/(2\hbar_{\rm eff})}$.

**Coherent-state Wigner function.**
$$
W_{|\alpha\rangle}(x,p) = \frac{1}{\pi\hbar_{\rm eff}}\exp\!\left[-\frac{(x-x_0)^2+(p-p_0)^2}{\hbar_{\rm eff}}\right],
$$
with $\int W\,dx\,dp = 1$ and $|W| \le 1/(\pi\hbar_{\rm eff})$ (because $|\langle\hat\Pi\rangle| \le 1$).

## 2. Table

| Quantity | $\lambda = 1/\sqrt2$ | $\lambda = 1/2$ | $\lambda = 1$ |
|---|---|---|---|
| $[\hat x,\hat p]$ | $i$ | $i/2$ | $2i$ |
| $\alpha$ in terms of $(x,p)$ | $(x+ip)/\sqrt2$ | $x+ip$ | $(x+ip)/2$ |
| centre of $\lvert\alpha\rangle$ | $\sqrt2\,(a,b)$ | $(a,b)$ | $2(a,b)$ |
| distance from origin | $\sqrt2\,\lvert\alpha\rvert$ | $\lvert\alpha\rvert$ | $2\lvert\alpha\rvert$ |
| vacuum $\mathrm{Var}(\hat x)$ | $1/2$ | $1/4$ | $1$ |
| $W$ kernel | $e^{-2ipy}$ | $e^{-4ipy}$ | $e^{-ipy}$ |
| $W$ prefactor | $1/\pi$ | $2/\pi$ | $1/(2\pi)$ |
| coherent $W$ | $\frac1\pi e^{-(\Delta x^2+\Delta p^2)}$ | $\frac2\pi e^{-2(\Delta x^2+\Delta p^2)}$ | $\frac{1}{2\pi}e^{-(\Delta x^2+\Delta p^2)/2}$ |
| BCH phase in $\hat D$ | $e^{-ipx/2}$ | $e^{-ipx}$ | $e^{-ipx/4}$ |
| min. possible $W$ | $-1/\pi$ | $-2/\pi$ | $-1/(2\pi)$ |

($\alpha = a+ib$, and $\Delta x = x - x_0$, $\Delta p = p - p_0$.)

## 3. Consequences for $|\alpha\rangle \pm |\alpha^*\rangle$

| Quantity | $\lambda = 1/\sqrt2$ | $\lambda = 1/2$ | $\lambda = 1$ |
|---|---|---|---|
| blob centres | $\sqrt2(a,\pm b)$ | $(a,\pm b)$ | $2(a,\pm b)$ |
| separation (along $p$) | $2\sqrt2\,b$ | $2b$ | $4b$ |
| fringe factor $\cos(kx - 2ab)$, $k = 2b/\lambda$ | $k = 2\sqrt2\,b$ | $k = 4b$ | $k = 2b$ |
| fringe period in $x$ | $\pi/(\sqrt2\,b)$ | $\pi/(2b)$ | $\pi/b$ |

Rule of thumb: fringe wavevector = (separation)$/\hbar_{\rm eff}$. Check: $4\lambda b / (2\lambda^2) = 2b/\lambda$.

## 4. What does NOT depend on $\lambda$

- The Fock expansion $|\alpha\rangle = e^{-|\alpha|^2/2}\sum_n \frac{\alpha^n}{\sqrt{n!}}|n\rangle$ (it only uses $\hat a$).
- Overlaps: $\langle\alpha|\beta\rangle = e^{-|\alpha-\beta|^2/2}\,e^{i\,\mathrm{Im}(\alpha^*\beta)}$, and so $\langle\alpha|\alpha^*\rangle = e^{-2b^2}e^{-2iab}$.
- Normalization: $\mathcal N_\pm = \big[2(1\pm e^{-2b^2}\cos 2ab)\big]^{-1/2}$.
- $W$ in the $\alpha$-plane, $\gamma = u+iv$: $W(\gamma) = \frac{2}{\pi}\mathrm{Tr}[\hat\rho\,\hat D(\gamma)\hat\Pi\hat D^\dagger(\gamma)]$, with $d^2\gamma = du\,dv$.
  Proof: $dx\,dp = 4\lambda^2\,du\,dv$, so $W(\gamma) = 4\lambda^2 W(x,p) = 2\lambda^2\cdot\frac{2}{\pi\hbar_{\rm eff}}\cdots = \frac{2}{\pi}\cdots$.
- Exponents written in $\gamma$: $\frac{\Delta x^2+\Delta p^2}{\hbar_{\rm eff}} = \frac{4\lambda^2|\gamma-\alpha|^2}{2\lambda^2} = 2|\gamma-\alpha|^2$.
- Physics: the sign of $W$, where it is negative, and the ratio of fringe period to blob width.

**Advice:** compute in $\gamma$, where nothing depends on $\lambda$. Convert to $(x,p)$ only at the end, with $x + ip = 2\lambda\gamma$ and $W(x,p) = W(\gamma)/(4\lambda^2)$.
