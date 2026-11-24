← [[QO - Lecture 8|Lecture 8]] · [[QO - chapter I|Full chapter]]

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

---
[[QO - Lecture 8|← Previous: Lecture 8]] · [[QO - Lecture 10|Next: Lecture 10 →]]
