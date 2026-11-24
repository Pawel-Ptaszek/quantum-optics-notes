← [[QO - Lecture 6|Lecture 6]] · [[QO - chapter I|Full chapter]] · [[QO - Lecture 7.5|Compressed version]]

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

---
[[QO - Lecture 6|← Previous: Lecture 6]] · [[QO - Lecture 8|Next: Lecture 8 →]]
