← [[QO - Lecture 9|Lecture 9]] · [[QO - chapter I|Full chapter]]

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

---
[[QO - Lecture 9|← Previous: Lecture 9]] · [[QO - Lecture 11|Next: Lecture 11 →]]
