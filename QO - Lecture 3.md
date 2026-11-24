← [[QO - Lecture 2|Lecture 2]] · [[QO - chapter I|Full chapter]]

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


### 6.4 Purity

It turns out, quite obviously that thermal states are not pure. To show that we will calculate purity from $\rho^2$
$$ \rho^2 = \frac{e^{-2 \beta \mathcal{H}}}{Z^2}$$
$${\rm Tr}(\rho^2)=\sum_n \bra{n} \rho^2 \ket{n} = \frac{\sum e^{-2 \beta E_n}}{(\sum_n e^{- \beta E_n})^2}$$
Therefore ${\rm Tr}(\rho^2)=\sum_n p_n^2$. From Cauchy schwarz we know:

$$1=(\sum_n p_n)^2>\sum_n p_n^2$$
Therefore: ${\rm Tr}(\rho^2)<1$, impure


### 6.5 Interactive: Gaussian states, from thermal to pure

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



---
[[QO - Lecture 2|← Previous: Lecture 2]] · [[QO - Lecture 4|Next: Lecture 4 →]]
