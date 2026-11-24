← [[QO - Lecture 7|Lecture 7 (full)]] · [[QO - chapter I|Full chapter]]

# Lecture 7 (comp)

## Counting photons

We can do photon statistics, but that is not all. For classical states the number of clicks $k$ satisfies

$$\frac{\Delta^2k}{\bar k}\geq 1 .$$

Photon counting is insensitive to the phase of the field. How about the phase?

## Homodyne detection

<div style="text-align:center"><svg width="620" height="300" viewBox="0 0 620 300" xmlns="http://www.w3.org/2000/svg" fill="none" stroke="currentColor" stroke-width="1.6" font-family="Times New Roman, serif" font-size="18"><defs><marker id="c75arrBHD7" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="7" markerHeight="7" orient="auto"><path d="M0,0 L10,5 L0,10 z" fill="currentColor" stroke="none"/></marker></defs><g transform="translate(40,0)"><line x1="60" y1="160" x2="222" y2="160" marker-end="url(#c75arrBHD7)"/><line x1="240" y1="290" x2="240" y2="178" marker-end="url(#c75arrBHD7)"/><rect x="222" y="142" width="36" height="36"/><line x1="222" y1="178" x2="258" y2="142" stroke-width="2.4"/><line x1="258" y1="160" x2="385" y2="160" marker-end="url(#c75arrBHD7)"/><line x1="240" y1="142" x2="240" y2="62" marker-end="url(#c75arrBHD7)"/><path d="M386,146 h12 a14,14 0 0 1 0,28 h-12 z"/><path d="M226,60 v-12 a14,14 0 0 1 28,0 v12 z"/><line x1="268" y1="34" x2="452" y2="34"/><line x1="412" y1="160" x2="470" y2="160"/><line x1="452" y1="34" x2="470" y2="34"/><line x1="470" y1="34" x2="470" y2="70" marker-end="url(#c75arrBHD7)"/><circle cx="470" cy="88" r="16"/><line x1="470" y1="160" x2="470" y2="106" marker-end="url(#c75arrBHD7)"/><line x1="486" y1="88" x2="530" y2="88" marker-end="url(#c75arrBHD7)"/><g fill="currentColor" stroke="none"><g font-style="italic"><text x="54" y="152" text-anchor="end">signal â</text><text x="252" y="282">LO |β⟩, β = |β|e<tspan dy="-7" font-size="12">iθ</tspan></text><text x="320" y="152">ĉ</text><text x="250" y="110">d̂</text><text x="500" y="116" font-size="15">n₋ ≈ √2|β| x̂<tspan dy="5" font-size="11">θ</tspan></text></g><text x="470" y="95" text-anchor="middle" font-size="22">−</text><text x="400" y="196" text-anchor="middle" font-size="14">D<tspan dy="3" font-size="10">c</tspan></text><text x="214" y="30" text-anchor="end" font-size="14">D<tspan dy="3" font-size="10">d</tspan></text><text x="284" y="136" font-size="13">BS 50:50</text></g></g></svg></div>

We measure the difference of the two photocurrents, $\hat n_-=\hat c^\dagger \hat c-\hat d^\dagger \hat d$, with $\hat c=(\hat b+\hat a)/\sqrt2$ and $\hat d=(\hat b-\hat a)/\sqrt2$. One arm carries the signal $\hat a$, the other a coherent state $\ket\beta$, $\beta=|\beta|e^{i\theta}$ (the local oscillator).

$$\hat n_-=\frac{1}{2}\Big[(\hat a^\dagger + \hat b^\dagger)(\hat a+\hat b)-(\hat b^\dagger-\hat a^\dagger)(\hat b-\hat a)\Big]=\hat a^\dagger \hat b+ \hat b^\dagger\hat a$$

For the state $\ket{\psi}=\ket{\phi}_a\ket{\beta}_b$ we replace $\hat b$ by $\beta$; this is valid for a strong local oscillator, $|\beta|^2\gg\langle\hat a^\dagger\hat a\rangle$:

$$\hat n_- \approx \beta\,\hat a^\dagger + \beta^*\hat a= |\beta|\big(\hat a^\dagger e^{i\theta}+\hat a\, e^{-i \theta}\big), \qquad \frac{\hat n_{-}}{\sqrt{2}|\beta|}=\frac{\hat a\, e^{-i \theta}+\hat a^\dagger e^{i \theta}}{\sqrt{2}}=\hat x_\theta .$$

With $\hat q=(\hat a+\hat a^\dagger)/\sqrt{2}$ and $\hat p=(\hat a-\hat a^\dagger)/i\sqrt2$ this is the rotated quadrature

$$\hat x_\theta=\hat q \cos\theta + \hat p\sin \theta .$$

The measured distribution of $x_\theta$ is a projection of the Wigner function onto a line (see the figure under *Quantum state tomography*). To get full state tomography we must repeat the measurement for many $\theta$.

For coherent states, and for all classical states, every quadrature satisfies

$$\Delta^2x_\theta \geq \frac{1}{2} .$$

<div style="text-align:center"><svg width="440" height="410" viewBox="0 0 440 410" xmlns="http://www.w3.org/2000/svg" fill="none" stroke="currentColor" stroke-width="1.6" font-family="Times New Roman, serif" font-size="16"><defs><marker id="c75arrU7" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="7" markerHeight="7" orient="auto"><path d="M0,0 L10,5 L0,10 z" fill="currentColor" stroke="none"/></marker></defs><path d="M70,360 L70,31.0 L99.8,31.0 L99.8,31.0 L101.2,45.8 L102.6,59.3 L104.0,71.7 L105.4,83.1 L106.8,93.6 L108.2,103.4 L109.6,112.4 L111.0,120.9 L112.4,128.8 L113.8,136.2 L115.2,143.1 L116.6,149.6 L118.0,155.8 L119.4,161.6 L120.8,167.0 L122.2,172.2 L123.6,177.1 L125.0,181.8 L126.4,186.2 L127.8,190.4 L129.2,194.4 L130.6,198.2 L132.0,201.9 L133.4,205.4 L134.8,208.7 L136.2,211.9 L137.6,215.0 L139.0,217.9 L140.4,220.8 L141.8,223.5 L143.2,226.1 L144.6,228.6 L146.0,231.0 L147.4,233.4 L148.8,235.6 L150.2,237.8 L151.6,239.9 L153.0,241.9 L154.4,243.9 L155.8,245.8 L157.2,247.6 L158.6,249.4 L160.0,251.1 L161.4,252.8 L162.8,254.4 L164.2,256.0 L165.6,257.5 L167.0,259.0 L168.4,260.4 L169.8,261.8 L171.2,263.1 L172.6,264.5 L174.0,265.8 L175.4,267.0 L176.8,268.2 L178.2,269.4 L179.6,270.6 L181.0,271.7 L182.4,272.8 L183.8,273.9 L185.2,274.9 L186.6,275.9 L188.0,276.9 L189.4,277.9 L190.8,278.9 L192.2,279.8 L193.6,280.7 L195.0,281.6 L196.4,282.5 L197.8,283.3 L199.2,284.1 L200.6,285.0 L202.0,285.8 L203.4,286.5 L204.8,287.3 L206.2,288.0 L207.6,288.8 L209.0,289.5 L210.4,290.2 L211.8,290.9 L213.2,291.6 L214.6,292.2 L216.0,292.9 L217.4,293.5 L218.8,294.1 L220.2,294.7 L221.6,295.4 L223.0,295.9 L224.4,296.5 L225.8,297.1 L227.2,297.7 L228.6,298.2 L230.0,298.7 L231.4,299.3 L232.8,299.8 L234.2,300.3 L235.6,300.8 L237.0,301.3 L238.4,301.8 L239.8,302.3 L241.2,302.8 L242.6,303.2 L244.0,303.7 L245.4,304.1 L246.8,304.6 L248.2,305.0 L249.6,305.4 L251.0,305.9 L252.4,306.3 L253.8,306.7 L255.2,307.1 L256.6,307.5 L258.0,307.9 L259.4,308.3 L260.8,308.6 L262.2,309.0 L263.6,309.4 L265.0,309.7 L266.4,310.1 L267.8,310.5 L269.2,310.8 L270.6,311.1 L272.0,311.5 L273.4,311.8 L274.8,312.1 L276.2,312.5 L277.6,312.8 L279.0,313.1 L280.4,313.4 L281.8,313.7 L283.2,314.0 L284.6,314.3 L286.0,314.6 L287.4,314.9 L288.8,315.2 L290.2,315.5 L291.6,315.8 L293.0,316.1 L294.4,316.3 L295.8,316.6 L297.2,316.9 L298.6,317.1 L300.0,317.4 L301.4,317.6 L302.8,317.9 L304.2,318.2 L305.6,318.4 L307.0,318.6 L308.4,318.9 L309.8,319.1 L311.2,319.4 L312.6,319.6 L314.0,319.8 L315.4,320.1 L316.8,320.3 L318.2,320.5 L319.6,320.7 L321.0,321.0 L322.4,321.2 L323.8,321.4 L325.2,321.6 L326.6,321.8 L328.0,322.0 L329.4,322.2 L330.8,322.4 L332.2,322.6 L333.6,322.8 L335.0,323.0 L336.4,323.2 L337.8,323.4 L339.2,323.6 L340.6,323.8 L342.0,324.0 L343.4,324.2 L344.8,324.3 L346.2,324.5 L347.6,324.7 L349.0,324.9 L350.4,325.0 L351.8,325.2 L353.2,325.4 L354.6,325.6 L356.0,325.7 L357.4,325.9 L358.8,326.1 L360.2,326.2 L361.6,326.4 L363.0,326.6 L364.4,326.7 L365.8,326.9 L367.2,327.0 L368.6,327.2 L370.0,327.3 L371.4,327.5 L372.8,327.6 L374.2,327.8 L375.6,327.9 L377.0,328.1 L378.4,328.2 L379.8,328.4 L381.2,328.5 L382.6,328.6 L384.0,328.8 L385.4,328.9 L386.8,329.1 L388.2,329.2 L389.6,329.3 L391.0,329.5 L392.0,360 Z" fill="currentColor" fill-opacity="0.26" stroke="none"/><rect x="169.0" y="31.0" width="223.0" height="230.0" fill="currentColor" fill-opacity="0.06" stroke="none"/><line x1="169.0" y1="261.0" x2="169.0" y2="31.0" stroke-dasharray="4 4"/><line x1="169.0" y1="261.0" x2="392.0" y2="261.0" stroke-dasharray="4 4"/><polyline points="103.6,68.3 105.0,80.0 106.4,90.8 107.8,100.7 109.2,110.0 110.6,118.6 112.0,126.7 113.4,134.2 114.8,141.2 116.2,147.9 117.6,154.1 119.0,160.0 120.4,165.6 121.8,170.8 123.2,175.8 124.6,180.5 126.0,185.0 127.4,189.3 128.8,193.3 130.2,197.2 131.6,200.9 133.0,204.4 134.4,207.8 135.8,211.1 137.2,214.2 138.6,217.1 140.0,220.0 141.4,222.7 142.8,225.4 144.2,227.9 145.6,230.4 147.0,232.7 148.4,235.0 149.8,237.2 151.2,239.3 152.6,241.4 154.0,243.3 155.4,245.2 156.8,247.1 158.2,248.9 159.6,250.6 161.0,252.3 162.4,253.9 163.8,255.5 165.2,257.1 166.6,258.6 168.0,260.0 169.4,261.4 170.8,262.8 172.2,264.1 173.6,265.4 175.0,266.7 176.4,267.9 177.8,269.1 179.2,270.3 180.6,271.4 182.0,272.5 183.4,273.6 184.8,274.6 186.2,275.7 187.6,276.7 189.0,277.6 190.4,278.6 191.8,279.5 193.2,280.5 194.6,281.3 196.0,282.2 197.4,283.1 198.8,283.9 200.2,284.7 201.6,285.5 203.0,286.3 204.4,287.1 205.8,287.8 207.2,288.6 208.6,289.3 210.0,290.0 211.4,290.7 212.8,291.4 214.2,292.0 215.6,292.7 217.0,293.3 218.4,294.0 219.8,294.6 221.2,295.2 222.6,295.8 224.0,296.4 225.4,296.9 226.8,297.5 228.2,298.1 229.6,298.6 231.0,299.1 232.4,299.7 233.8,300.2 235.2,300.7 236.6,301.2 238.0,301.7 239.4,302.1 240.8,302.6 242.2,303.1 243.6,303.5 245.0,304.0 246.4,304.4 247.8,304.9 249.2,305.3 250.6,305.7 252.0,306.2 253.4,306.6 254.8,307.0 256.2,307.4 257.6,307.8 259.0,308.1 260.4,308.5 261.8,308.9 263.2,309.3 264.6,309.6 266.0,310.0 267.4,310.4 268.8,310.7 270.2,311.0 271.6,311.4 273.0,311.7 274.4,312.1 275.8,312.4 277.2,312.7 278.6,313.0 280.0,313.3 281.4,313.6 282.8,313.9 284.2,314.2 285.6,314.5 287.0,314.8 288.4,315.1 289.8,315.4 291.2,315.7 292.6,316.0 294.0,316.2 295.4,316.5 296.8,316.8 298.2,317.1 299.6,317.3 301.0,317.6 302.4,317.8 303.8,318.1 305.2,318.3 306.6,318.6 308.0,318.8 309.4,319.1 310.8,319.3 312.2,319.5 313.6,319.8 315.0,320.0 316.4,320.2 317.8,320.5 319.2,320.7 320.6,320.9 322.0,321.1 323.4,321.3 324.8,321.5 326.2,321.7 327.6,322.0 329.0,322.2 330.4,322.4 331.8,322.6 333.2,322.8 334.6,323.0 336.0,323.2 337.4,323.4 338.8,323.5 340.2,323.7 341.6,323.9 343.0,324.1 344.4,324.3 345.8,324.5 347.2,324.6 348.6,324.8 350.0,325.0 351.4,325.2 352.8,325.3 354.2,325.5 355.6,325.7 357.0,325.9 358.4,326.0 359.8,326.2 361.2,326.3 362.6,326.5 364.0,326.7 365.4,326.8 366.8,327.0 368.2,327.1 369.6,327.3 371.0,327.4 372.4,327.6 373.8,327.7 375.2,327.9 376.6,328.0 378.0,328.2 379.4,328.3 380.8,328.5 382.2,328.6" stroke-width="2.2"/><circle cx="169.0" cy="261.0" r="4.5" fill="currentColor"/><line x1="70" y1="360" x2="408.8" y2="360" marker-end="url(#c75arrU7)"/><line x1="70" y1="360" x2="70" y2="17.0" marker-end="url(#c75arrU7)"/><g fill="currentColor" stroke="none" font-size="14"><text x="408.8" y="380" text-anchor="end" font-style="italic" font-size="16">Δq</text><text x="60" y="21.19999999999999" text-anchor="end" font-style="italic" font-size="16">Δp</text><text x="168.99494936611666" y="378" text-anchor="middle">1/√2</text><text x="64" y="266.00505063388334" text-anchor="end">1/√2</text><text x="116.2" y="301.2">forbidden</text><text x="116.2" y="317.2" font-size="12">Δq Δp &lt; ½</text><text x="259.0" y="136.0" text-anchor="middle">classical states</text><text x="259.0" y="152.0" text-anchor="middle" font-size="12">(mixtures of coherent states)</text><text x="176.99494936611666" y="279.00505063388334" font-size="12">coherent states</text><text x="128.8" y="94.0" text-anchor="middle" font-size="12">squeezed</text><text x="128.8" y="108.0" text-anchor="middle" font-size="12">in q</text><text x="329.0" y="276.0" text-anchor="middle" font-size="12">squeezed in p</text><text x="385.0" y="346.0" font-size="12" font-style="italic" text-anchor="end">Δq Δp = ½</text></g></svg></div>

## Phase space: a plethora of representations

1. The $P$-function: a coherent state is $\delta^2(\alpha - \alpha_0)$, which is not very convenient to draw.
2. The Wigner function:

$$W(x,p)=\frac{1}{2 \pi \hbar}\int^{\infty}_{-\infty} d \xi\; e^{-i p \xi/ \hbar} \Big\langle x+\frac\xi2\Big| \hat \rho \Big|x- \frac\xi2\Big\rangle$$

This is the density operator in position space around the centre of mass $x$, Fourier transformed with respect to the relative distance $\xi$. For a pure state $\hat\rho = |\psi \rangle \langle \psi |$:

$$W(x,p)= \frac{1}{2 \pi \hbar} \int d \xi\; e^{-ip \xi/\hbar}\, \psi\Big(x+\frac\xi2\Big)\,\psi^*\Big(x-\frac\xi2\Big)$$

**Marginal distributions.**

$$\int dp\; W(x,p)=\frac{1}{2\pi\hbar}\int d\xi\,\underbrace{\int dp\,e^{-ip\xi/\hbar}}_{2\pi\hbar\,\delta(\xi)}\Big\langle x+\frac\xi2\Big|\hat\rho\Big|x-\frac\xi2\Big\rangle= \langle x|\hat\rho |x\rangle$$

$$\langle p|\hat\rho|p\rangle=\int dx'\,dx''\,\underbrace{\langle p|x'\rangle\langle x''|p\rangle}_{e^{-ip(x'-x'')/\hbar}/2\pi\hbar}\langle x'|\hat\rho|x''\rangle\;\overset{x'=x+\xi/2,\;x''=x-\xi/2}{=}\\ \;\frac{1}{2\pi\hbar}\int dx\,d\xi\,e^{-ip\xi/\hbar}\Big\langle x+\frac\xi2\Big|\hat\rho\Big|x-\frac\xi2\Big\rangle=\int dx\; W(x,p)$$

The change of variables has unit Jacobian. Together, $\int dx \int dp\; W(x,p)={\rm Tr}\,\hat\rho=1$.

**Overlaps.**

$${\rm Tr}(\hat\rho_1 \hat\rho_2)=2 \pi \hbar \int dx \int dp\; W_1(x,p)\,W_2(x,p)$$

Since ${\rm Tr}\,\hat\rho^2 \leq 1$:

$$\int dx \int dp\; W^2 \leq \frac{1}{2 \pi \hbar}$$

Take $\hat\rho_1 = | \phi \rangle \langle\phi|$ and $\hat\rho_2 = | \phi_\perp \rangle \langle \phi_\perp|$:

$$0=\int dx \int dp\; W_\phi\, W_{\phi_\perp}$$

So $W(x,p)$ may be negative.

## Time evolution

$$\frac{\partial \hat\rho}{\partial t}=- \frac{i}{\hbar}[\hat H, \hat\rho], \qquad \hat H = \frac{\hat p^2}{2m}+U(\hat x)$$

Inserting this into $W$ gives two contributions, $\partial_t W = T + U$: $T$ from the kinetic commutator $[\hat p^2,\hat\rho]/2m$ and $U$ from the potential $[U(\hat x),\hat\rho]$. The result is

$$\Big(\partial_t+\frac{p}{m} \partial_x - \frac{dU}{dx} \partial_p\Big)W= \sum_{n=1}^{\infty}\frac{(-1)^n}{(2n+1)!}\Big(\frac\hbar2\Big)^{2n}U^{(2n+1)}(x)\,\partial_p^{2n+1}W$$

The left-hand side is the classical Liouville equation; the quantum terms on the right vanish for quadratic Hamiltonians.

## Calculating observables

$\langle \hat A \rangle = {\rm Tr}(\hat\rho \hat A)$. We define the Weyl symbol

$$A(x,p)=\int d \xi\; e^{-i p \xi /\hbar} \Big\langle x+\frac\xi2\Big|\hat A \Big|x-\frac\xi2\Big\rangle$$

Then

$$\langle \hat A \rangle = \int dx \int dp\; A(x,p)\,W(x,p)$$

This is the Wigner–Weyl representation.

## Quantum state tomography

Quadrature eigenstates:

$$\hat x_\theta \ket{x_\theta}=x_\theta \ket{x_\theta}, \qquad \langle q|\cos \theta\, \hat q + \sin \theta\, \hat p |x_\theta\rangle=x_\theta \langle q|x_\theta\rangle$$

**Wigner function of a quadrature state.**

$$W_{\ket{x_\theta}}(x,p)=\frac{1}{2 \pi \hbar} \int dy\; e^{-ipy /\hbar} \Big\langle x+\frac y2\Big|x_\theta\Big\rangle \Big\langle x_\theta\Big|x-\frac y2\Big\rangle$$

This is a Gaussian integral, and the result is a delta function along a line with slope set by $\theta$:

$$W_{\ket{x_\theta}}(x,p)=\frac{1}{2 \pi \hbar}\, \delta\big(x_\theta - x\cos \theta - p\sin \theta \big)$$

Define the measured distribution:

$$W(x_\theta) = {\rm Tr}\big(\hat\rho\,\ket{x_\theta}\bra{x_\theta}\big)=2 \pi \hbar \int dx\int dp\; W_{\ket{x_\theta}}\,W_\rho$$

$W$ is projected onto a line, i.e. integrated along the lines $x\cos\theta+p\sin\theta=x_\theta$.

<div style="text-align:center"><svg width="470" height="400" viewBox="0 0 470 400" xmlns="http://www.w3.org/2000/svg" fill="none" stroke="currentColor" stroke-width="1.6" font-family="Times New Roman, serif" font-size="16"><defs><marker id="c75arrT7" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="7" markerHeight="7" orient="auto"><path d="M0,0 L10,5 L0,10 z" fill="currentColor" stroke="none"/></marker></defs><g transform="translate(30,40)"><ellipse cx="200" cy="200" rx="70" ry="38" transform="rotate(-60 200 200)" fill="currentColor" fill-opacity="0.18"/><ellipse cx="200" cy="200" rx="40" ry="20" transform="rotate(-60 200 200)" fill="currentColor" fill-opacity="0.22" stroke="none"/><line x1="48.8" y1="114.1" x2="183.8" y2="347.9" stroke-width="0.8" opacity="0.45" stroke-dasharray="3 4"/><line x1="67.8" y1="103.1" x2="202.8" y2="336.9" stroke-width="0.8" opacity="0.45" stroke-dasharray="3 4"/><line x1="86.9" y1="92.1" x2="221.9" y2="325.9" stroke-width="0.8" opacity="0.45" stroke-dasharray="3 4"/><line x1="105.9" y1="81.1" x2="240.9" y2="314.9" stroke-width="0.8" opacity="0.45" stroke-dasharray="3 4"/><line x1="125.0" y1="70.1" x2="260.0" y2="303.9" stroke-width="0.8" opacity="0.45" stroke-dasharray="3 4"/><line x1="144.1" y1="59.1" x2="279.1" y2="292.9" stroke-width="0.8" opacity="0.45" stroke-dasharray="3 4"/><line x1="163.1" y1="48.1" x2="298.1" y2="281.9" stroke-width="0.8" opacity="0.45" stroke-dasharray="3 4"/><line x1="182.2" y1="37.1" x2="317.2" y2="270.9" stroke-width="0.8" opacity="0.45" stroke-dasharray="3 4"/><line x1="201.2" y1="26.1" x2="336.2" y2="259.9" stroke-width="0.8" opacity="0.45" stroke-dasharray="3 4"/><line x1="70.1" y1="275.0" x2="329.9" y2="125.0" marker-end="url(#c75arrT7)" stroke-width="1.8"/><line x1="50" y1="200" x2="360" y2="200" stroke-width="1" opacity="0.6" marker-end="url(#c75arrT7)"/><line x1="200" y1="350" x2="200" y2="40" stroke-width="1" opacity="0.6" marker-end="url(#c75arrT7)"/><line x1="25.4" y1="127.6" x2="224.6" y2="12.6" stroke-width="1"/><polyline points="29.7,125.0 33.1,122.9 36.5,120.8 39.9,118.7 43.2,116.5 46.6,114.2 49.8,111.9 53.0,109.4 56.1,106.8 59.1,103.9 62.0,100.9 64.7,97.6 67.2,94.0 69.6,90.1 71.8,85.9 73.7,81.3 75.5,76.4 77.2,71.2 78.6,65.8 80.0,60.2 81.4,54.6 82.8,49.0 84.3,43.6 86.0,38.5 87.9,33.9 90.2,29.8 92.8,26.3 95.8,23.6 99.3,21.6 103.2,20.3 107.5,19.8 112.2,19.9 117.2,20.5 122.4,21.6 127.8,23.0 133.4,24.6 138.9,26.2 144.5,27.8 149.9,29.2 155.2,30.4 160.3,31.3 165.3,31.9 170.0,32.1 174.6,32.0 179.0,31.6 183.2,30.9 187.3,29.9 191.2,28.8 195.0,27.4 198.8,25.9 202.4,24.2 206.1,22.5 209.6,20.7 213.2,18.8 216.7,16.9 220.2,15.0" stroke-width="2"/><path d="M260,200 A60,60 0 0 0 252.0,170.0" stroke-width="1"/><g fill="currentColor" stroke="none" font-style="italic"><text x="333.9" y="119.0">x<tspan font-size="11" dy="4">θ</tspan></text><text x="365" y="205">q</text><text x="206" y="40">p</text><text x="266" y="188" font-size="14">θ</text><text x="95" y="330" font-size="14">W(q,p)</text><text x="124.6" y="-10.5" font-size="14">pr(x<tspan font-size="10" dy="3">θ</tspan><tspan dy="-3">)</tspan></text></g></g></svg></div>

We need to invert this to get $\hat\rho$. Take the Fourier transform $\int d x_\theta\, e^{i t x_\theta} W(x_\theta)$ and invert the Radon transformation:

$$W_\rho(x,p)= \frac{1}{(2\pi)^2} \int_{-\infty}^{\infty} dt\, |t| \int_{-\pi/2}^{\pi/2} d \theta \int d x_\theta\; W(x_\theta)\,e^{it (x_\theta-x \cos \theta - p \sin \theta)}$$

## Beyond the Wigner function: $Q$ and $P$

In general, for a quasi-probability distribution $F_\rho$ and the matching phase-space function $A(x,p)$:

$$\langle \hat A \rangle = \int dx \int dp\; A(x,p)\,F_\rho(x,p)$$

The Husimi function, with $\alpha=\alpha_R+i\alpha_I$:

$$Q(\alpha_R, \alpha_I)=\frac{1}{\pi}\langle\alpha|\hat\rho|\alpha\rangle$$

> [!question]- Questions
> - If the state is multimode, can a subsystem go below the uncertainty bound?
> - What is the Wigner-function (Weyl) representation of the Susskind–Glogower phase operator?
> - Can a squeezed state improve phase estimation in homodyne detection, and what does its Weyl-Wigner representation look like?
> - What does homodyne detection measure when the local oscillator is a coherent state of finite amplitude, i.e. is it still a projective measurement?
> - Which derivative terms appear in the Wigner equation of motion for the simplest non-quadratic Hamiltonian?
> - How can one detect nonclassicality in a general Gaussian state?
