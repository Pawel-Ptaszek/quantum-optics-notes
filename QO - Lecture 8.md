← [[QO - Lecture 7|Lecture 7]] · [[QO - chapter I|Full chapter]]

# Lecture 8

## Calculating $W(x,p)$ from the definition

We evaluate the Wigner function directly from its definition,

$$W(x,p)=\frac{1}{2\pi}\int d\xi\, e^{-ip\xi}\,\bra{x+\xi/2}\hat\rho\ket{x-\xi/2}, \qquad \hat\rho=\ket\psi\bra\psi:\quad \bra{x+\xi/2}\hat\rho\ket{x-\xi/2}=\psi(x+\xi/2)\,\psi^*(x-\xi/2).$$

### Coherent state

For real $\alpha$ the coherent state is the vacuum Gaussian displaced by $\sqrt2\alpha$ in $x$ (recall $\langle\hat x\rangle=\sqrt2\,\mathrm{Re}\,\alpha$):

$$\psi_\alpha(x)=\Big(\frac{1}{\pi}\Big)^{1/4} e^{-\frac{1}{2}(x-\sqrt{2} \alpha)^2}.$$

The product $\psi_\alpha(x+\xi/2)\psi_\alpha(x-\xi/2)=\pi^{-1/2}e^{-(x-\sqrt2\alpha)^2-\xi^2/4}$, and $\int d\xi\,e^{-ip\xi}e^{-\xi^2/4}=2\sqrt\pi\,e^{-p^2}$, so

$$W_{\alpha}(x,p)=\frac{1}{\pi}\, e^{-(x-\sqrt{2}\alpha)^2 -p^2}.$$

### Fock state

**Husimi function.** Using $\langle\alpha|n\rangle=e^{-|\alpha|^2/2}\alpha^{*n}/\sqrt{n!}$,

$$Q_n(\alpha)= \frac{1}{\pi} |\langle \alpha | n \rangle |^2 = \frac{1}{\pi} e^{-|\alpha|^2} \frac{|\alpha|^{2n}}{n!}.$$

It is rotationally symmetric (a Fock state has no phase), peaks on the ring $|\alpha|=\sqrt n$, and for $n\ge1$ vanishes at the origin, $Q_n(0)=|\langle0|n\rangle|^2/\pi=0$: a "hole" in the centre. $Q$ is non-negative for every state, so this hole is the only trace of nonclassicality it shows.

**Wigner function.** The wavefunctions are

$$\psi_n(x)=\frac{1}{\sqrt{2^n n! \sqrt{\pi}}}\,e^{-x^2/2}H_n(x),$$

so, with $\xi=2y$,

$$W_n(x,p)=\frac{1}{\pi}\,\frac{1}{2^n n! \sqrt{\pi}} \int dy\; e^{-2ipy}\, e^{-x^2-y^2}\,H_n(x+y)\,H_n(x-y).$$

Instead of integrating the product of two Hermite polynomials directly, we use the generating function

$$e^{2ut-t^2} = \sum_{m} H_m(u)\frac{t^m}{m!}
\quad\Rightarrow\quad
e^{2(x+y)t-t^2}\, e^{2(x-y)s-s^2}=\sum_{m,n}H_m(x+y)\,H_n(x-y)\, \frac{t^m s^n}{m!\, n!}.$$

Multiplying by $e^{-2ipy-y^2}$ and integrating over $y$ is a Gaussian integral, $\int dy\,e^{-y^2+by}=\sqrt\pi\,e^{b^2/4}$ with $b=2(t-s-ip)$:

$$\int dy\; e^{-2ipy-y^2}\,e^{2(x+y)t-t^2+2(x-y)s-s^2} = \sqrt{\pi}\, e^{-p^2}\,e^{2(x-ip)t+2(x+ip)s-2ts}
\\ = \sqrt{\pi}\, e^{-p^2} \sum_{j,k,l} \frac{2^{j+k+l}(-1)^l (x-ip)^j (x+ip)^k\, t^{j+l}s^{k+l}}{j!\,k!\,l!}.$$

The diagonal term $W_n$ is $n!^2$ times the coefficient of $t^ns^n$, i.e. $j=k=n-l$, and $(x-ip)(x+ip)=x^2+p^2$:

$$W_n(x,p)=\frac{n!}{2^n\pi}\,e^{-(x^2+p^2)} \sum_{l=0}^{n} \frac{2^{2n-l}(-1)^l(x^2 +p^2)^{n-l}}{l!\, ((n-l)!)^2}
= \frac{(-1)^n}{\pi}\, e^{-(x^2+p^2)}\,L_n\big(2(x^2+p^2)\big),$$

where in the last step $k=n-l$ and $L_n(u)=\sum_k\binom nk\frac{(-u)^k}{k!}$ is the Laguerre polynomial. On the $\alpha$-plane ($x^2+p^2=2|\alpha|^2$, normalised in $d^2\alpha$) this reads $W_n(\alpha)=\frac{2}{\pi}(-1)^n e^{-2|\alpha|^2}L_n(4|\alpha|^2)$. $W_n(0)=(-1)^n\frac{2}{\pi}$ is the most negative value any Wigner function can take, and $W_n$ has $n$ circular nodes. The generating function in $t,s$ thus gives the Wigner functions of all Fock states at once (and, through the off-diagonal $t^ms^n$ terms, of $\ket m\bra n$).

**Interactive plot.** Left: $Q_n$ or $W_n$ on the $\alpha$-plane (dashed ring $|\alpha|=\sqrt n$). Right: radial cuts of both. Compare the single smooth ring of $Q$ with the $n$ sign changes of $W$.

```dataviewjs
// ===== CONFIG =====
const CFG = { n: 1, nMax: 15, L: 4.5 };
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
const pois = (n, m) => (m <= 0 ? (n === 0 ? 1 : 0) : Math.exp(n * Math.log(m) - m - LF[n]));
// P(n) bars + Poisson reference with the same mean; returns an update function
function countsPlot(bP, cbP) {
  let P = [1], nShow = 10, mean = 0;
  const bars = bP.create("curve", [[0], [0]], { fixed: true, highlight: false, strokeColor: "#c2410c", strokeWidth: 1, fillColor: "#f0a46a", fillOpacity: 0.85 });
  bars.updateDataArray = function () { const xs = [], ys = []; for (let n = 0; n <= nShow; n++) { xs.push(n - 0.38, n - 0.38, n + 0.38, n + 0.38, NaN); ys.push(0, P[n], P[n], 0, NaN); } this.dataX = xs; this.dataY = ys; };
  const pl = bP.create("curve", [[0], [0]], { fixed: true, highlight: false, strokeColor: C.obs, strokeWidth: 2, dash: 2, visible: () => cbP.checked });
  pl.updateDataArray = function () { const xs = [], ys = []; for (let n = 0; n <= nShow; n++) { xs.push(n); ys.push(pois(n, mean)); } this.dataX = xs; this.dataY = ys; };
  for (let n = 0; n <= 80; n++) bP.create("point", [n, () => pois(n, mean)], { fixed: true, highlight: false, withLabel: false, size: 2.5, strokeColor: C.obs, fillColor: "#fff", visible: () => cbP.checked && n <= nShow });
  const leg = bP.create("text", [0, 0, () => "<span style='color:#c2410c'>■</span> state" + (cbP.checked ? " &nbsp; <span style='color:" + C.obs + "'>○</span> Poisson, same ⟨n⟩" : "")], { fixed: true, highlight: false, fontSize: 12, strokeColor: C.ink, anchorX: "right", anchorY: "top" });
  return (Pnew) => {
    P = Pnew; mean = 0; let m2 = 0, cum = 0, nEnd = 0; P.forEach((p, n) => { mean += n * p; m2 += n * n * p; });
    for (let n = 0; n < P.length; n++) { cum += P[n]; if (cum > 0.999) { nEnd = n; break; } }
    const varn = m2 - mean * mean; nShow = Math.min(80, Math.max(10, Math.ceil(Math.max(nEnd, mean + 4 * Math.sqrt(varn)))));
    let ymax = 0; for (let n = 0; n <= nShow; n++) ymax = Math.max(ymax, P[n], cbP.checked ? pois(n, mean) : 0); ymax *= 1.18;
    bP.setBoundingBox([-0.06 * nShow - 1, ymax, nShow + 1, -0.08 * ymax], false); leg.setPosition(JXG.COORDS_BY_USER, [nShow + 0.6, ymax * 0.97]); bP.update();
    return { mean, varn };
  };
}
const sN = K.slider("n", 0, CFG.nMax, 1, CFG.n, (v) => (+v).toFixed(0));
const sel = K.select([["Q", "Husimi Q"], ["W", "Wigner W"]]);
K.root.append(panel);
// Q(α) = e^{−|α|²}|α|^{2n}/(π n!),   W(α) = (2/π)(−1)ⁿ e^{−2|α|²} Lₙ(4|α|²)   (both normalised in d²α)
const lag = (n, u) => { let a = 1, b = 1 - u; if (n === 0) return 1; for (let k = 1; k < n; k++) { const c = ((2 * k + 1 - u) * b - k * a) / (k + 1); a = b; b = c; } return b; };
const Qr = (n, r) => Math.exp(-r * r + (n ? 2 * n * Math.log(r) : 0) - LF[n]) / Math.PI;
const Wr = (n, r) => (2 / Math.PI) * (n % 2 ? -1 : 1) * Math.exp(-2 * r * r) * lag(n, 4 * r * r);
const bR = board(pdiv, [-0.5, 0.7, CFG.L, -0.75], "|α|", "");
bR.create("line", [[0, 0], [1, 0]], { fixed: true, highlight: false, strokeColor: C.muted, strokeWidth: 0.5 });
const cQ = bR.create("functiongraph", [(r) => Qr(+sN.value, Math.max(r, 1e-9)), 0, CFG.L], { fixed: true, highlight: false, strokeColor: "#c2410c", strokeWidth: 2.4 });
const cW = bR.create("functiongraph", [(r) => Wr(+sN.value, r), 0, CFG.L], { fixed: true, highlight: false, strokeColor: "#1f5fa8", strokeWidth: 2.4 });
const vr = bR.create("line", [[() => Math.sqrt(+sN.value), 0], [() => Math.sqrt(+sN.value), 1]], { fixed: true, highlight: false, strokeColor: C.muted, dash: 2, strokeWidth: 1 });
bR.create("text", [CFG.L - 0.1, 0.66, "<span style='color:#c2410c'>━</span> Q(|α|) &nbsp; <span style='color:#1f5fa8'>━</span> W(|α|) &nbsp; ┆ |α| = √n"], { fixed: true, highlight: false, fontSize: 12, strokeColor: C.ink, anchorX: "right", anchorY: "top" });
function update() {
  const n = +sN.value, isQ = sel.value === "Q";
  cQ.setAttribute({ strokeWidth: isQ ? 2.8 : 1.4 }); cW.setAttribute({ strokeWidth: isQ ? 1.4 : 2.8 }); bR.update();
  const qmax = Qr(n, Math.sqrt(Math.max(n, 1e-9)));
  if (isQ) heat((x, y) => Qr(n, Math.max(Math.hypot(x, y), 1e-9)), CFG.L, qmax, `Q(α) for |${n}⟩, colour scale 0 … ${f(qmax)}`,
      (ctx, sx, sy, s) => { ctx.strokeStyle = C.muted; ctx.setLineDash([3, 3]); ctx.beginPath(); ctx.arc(sx(0), sy(0), Math.sqrt(n) * s, 0, 2 * Math.PI); ctx.stroke(); ctx.setLineDash([]); });
  else heat((x, y) => Wr(n, Math.hypot(x, y)), CFG.L, 2 / Math.PI, `W(α) for |${n}⟩, colour scale ±2/π`);
  panel.textContent =
`Q(0) = ${n ? "0  (⟨0|n⟩ = 0: the hole)" : "1/π"}    max Q = ${f(qmax)} on the ring |α| = √n = ${f(Math.sqrt(n))}
W(0) = (−1)ⁿ 2/π = ${f(Wr(n, 0))}    W has ${n} radial nodes; it is negative somewhere for every n ≥ 1, Q never is`;
}
sN.addEventListener("input", update); sel.onchange = update;
update();
```

**Creation and annihilation operators as derivatives in phase space.** In general, multiplying $\hat\rho$ by $\hat a$ or $\hat a^\dagger$ acts on the Wigner function as a first-order differential operator:

$$\hat a\hat\rho \leftrightarrow \Big(\alpha+\frac12\frac{\partial}{\partial\alpha^*}\Big)W, \qquad
\hat\rho\hat a \leftrightarrow \Big(\alpha-\frac12\frac{\partial}{\partial\alpha^*}\Big)W, \\
\hat a^\dagger\hat\rho \leftrightarrow \Big(\alpha^*-\frac12\frac{\partial}{\partial\alpha}\Big)W, \qquad
\hat\rho\hat a^\dagger \leftrightarrow \Big(\alpha^*+\frac12\frac{\partial}{\partial\alpha}\Big)W.$$

A check: for the vacuum, $W_0=\frac2\pi e^{-2|\alpha|^2}$ and $\partial_{\alpha^*}W_0=-2\alpha W_0$, so $\hat a\ket0\bra0\leftrightarrow(\alpha-\alpha)W_0=0$, as it must be. For example, applying $\hat a^\dagger(\cdot)\hat a$ once gives $(\alpha^*-\frac12\partial_\alpha)(\alpha-\frac12\partial_{\alpha^*})W_0=(4|\alpha|^2-1)W_0=W_1$, and $n$ applications give $n!\,W_n$; master equations become Fokker–Planck-type equations for $W$ in the same way.

### Squeezing

Let's take other states saturating uncertainty principle
<div style="text-align:center"><svg width="440" height="410" viewBox="0 0 440 410" xmlns="http://www.w3.org/2000/svg" fill="none" stroke="currentColor" stroke-width="1.6" font-family="Times New Roman, serif" font-size="16"><defs><marker id="arrU7" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="7" markerHeight="7" orient="auto"><path d="M0,0 L10,5 L0,10 z" fill="currentColor" stroke="none"/></marker></defs><path d="M70,360 L70,31.0 L99.8,31.0 L99.8,31.0 L101.2,45.8 L102.6,59.3 L104.0,71.7 L105.4,83.1 L106.8,93.6 L108.2,103.4 L109.6,112.4 L111.0,120.9 L112.4,128.8 L113.8,136.2 L115.2,143.1 L116.6,149.6 L118.0,155.8 L119.4,161.6 L120.8,167.0 L122.2,172.2 L123.6,177.1 L125.0,181.8 L126.4,186.2 L127.8,190.4 L129.2,194.4 L130.6,198.2 L132.0,201.9 L133.4,205.4 L134.8,208.7 L136.2,211.9 L137.6,215.0 L139.0,217.9 L140.4,220.8 L141.8,223.5 L143.2,226.1 L144.6,228.6 L146.0,231.0 L147.4,233.4 L148.8,235.6 L150.2,237.8 L151.6,239.9 L153.0,241.9 L154.4,243.9 L155.8,245.8 L157.2,247.6 L158.6,249.4 L160.0,251.1 L161.4,252.8 L162.8,254.4 L164.2,256.0 L165.6,257.5 L167.0,259.0 L168.4,260.4 L169.8,261.8 L171.2,263.1 L172.6,264.5 L174.0,265.8 L175.4,267.0 L176.8,268.2 L178.2,269.4 L179.6,270.6 L181.0,271.7 L182.4,272.8 L183.8,273.9 L185.2,274.9 L186.6,275.9 L188.0,276.9 L189.4,277.9 L190.8,278.9 L192.2,279.8 L193.6,280.7 L195.0,281.6 L196.4,282.5 L197.8,283.3 L199.2,284.1 L200.6,285.0 L202.0,285.8 L203.4,286.5 L204.8,287.3 L206.2,288.0 L207.6,288.8 L209.0,289.5 L210.4,290.2 L211.8,290.9 L213.2,291.6 L214.6,292.2 L216.0,292.9 L217.4,293.5 L218.8,294.1 L220.2,294.7 L221.6,295.4 L223.0,295.9 L224.4,296.5 L225.8,297.1 L227.2,297.7 L228.6,298.2 L230.0,298.7 L231.4,299.3 L232.8,299.8 L234.2,300.3 L235.6,300.8 L237.0,301.3 L238.4,301.8 L239.8,302.3 L241.2,302.8 L242.6,303.2 L244.0,303.7 L245.4,304.1 L246.8,304.6 L248.2,305.0 L249.6,305.4 L251.0,305.9 L252.4,306.3 L253.8,306.7 L255.2,307.1 L256.6,307.5 L258.0,307.9 L259.4,308.3 L260.8,308.6 L262.2,309.0 L263.6,309.4 L265.0,309.7 L266.4,310.1 L267.8,310.5 L269.2,310.8 L270.6,311.1 L272.0,311.5 L273.4,311.8 L274.8,312.1 L276.2,312.5 L277.6,312.8 L279.0,313.1 L280.4,313.4 L281.8,313.7 L283.2,314.0 L284.6,314.3 L286.0,314.6 L287.4,314.9 L288.8,315.2 L290.2,315.5 L291.6,315.8 L293.0,316.1 L294.4,316.3 L295.8,316.6 L297.2,316.9 L298.6,317.1 L300.0,317.4 L301.4,317.6 L302.8,317.9 L304.2,318.2 L305.6,318.4 L307.0,318.6 L308.4,318.9 L309.8,319.1 L311.2,319.4 L312.6,319.6 L314.0,319.8 L315.4,320.1 L316.8,320.3 L318.2,320.5 L319.6,320.7 L321.0,321.0 L322.4,321.2 L323.8,321.4 L325.2,321.6 L326.6,321.8 L328.0,322.0 L329.4,322.2 L330.8,322.4 L332.2,322.6 L333.6,322.8 L335.0,323.0 L336.4,323.2 L337.8,323.4 L339.2,323.6 L340.6,323.8 L342.0,324.0 L343.4,324.2 L344.8,324.3 L346.2,324.5 L347.6,324.7 L349.0,324.9 L350.4,325.0 L351.8,325.2 L353.2,325.4 L354.6,325.6 L356.0,325.7 L357.4,325.9 L358.8,326.1 L360.2,326.2 L361.6,326.4 L363.0,326.6 L364.4,326.7 L365.8,326.9 L367.2,327.0 L368.6,327.2 L370.0,327.3 L371.4,327.5 L372.8,327.6 L374.2,327.8 L375.6,327.9 L377.0,328.1 L378.4,328.2 L379.8,328.4 L381.2,328.5 L382.6,328.6 L384.0,328.8 L385.4,328.9 L386.8,329.1 L388.2,329.2 L389.6,329.3 L391.0,329.5 L392.0,360 Z" fill="currentColor" fill-opacity="0.26" stroke="none"/><rect x="169.0" y="31.0" width="223.0" height="230.0" fill="currentColor" fill-opacity="0.06" stroke="none"/><line x1="169.0" y1="261.0" x2="169.0" y2="31.0" stroke-dasharray="4 4"/><line x1="169.0" y1="261.0" x2="392.0" y2="261.0" stroke-dasharray="4 4"/><polyline points="103.6,68.3 105.0,80.0 106.4,90.8 107.8,100.7 109.2,110.0 110.6,118.6 112.0,126.7 113.4,134.2 114.8,141.2 116.2,147.9 117.6,154.1 119.0,160.0 120.4,165.6 121.8,170.8 123.2,175.8 124.6,180.5 126.0,185.0 127.4,189.3 128.8,193.3 130.2,197.2 131.6,200.9 133.0,204.4 134.4,207.8 135.8,211.1 137.2,214.2 138.6,217.1 140.0,220.0 141.4,222.7 142.8,225.4 144.2,227.9 145.6,230.4 147.0,232.7 148.4,235.0 149.8,237.2 151.2,239.3 152.6,241.4 154.0,243.3 155.4,245.2 156.8,247.1 158.2,248.9 159.6,250.6 161.0,252.3 162.4,253.9 163.8,255.5 165.2,257.1 166.6,258.6 168.0,260.0 169.4,261.4 170.8,262.8 172.2,264.1 173.6,265.4 175.0,266.7 176.4,267.9 177.8,269.1 179.2,270.3 180.6,271.4 182.0,272.5 183.4,273.6 184.8,274.6 186.2,275.7 187.6,276.7 189.0,277.6 190.4,278.6 191.8,279.5 193.2,280.5 194.6,281.3 196.0,282.2 197.4,283.1 198.8,283.9 200.2,284.7 201.6,285.5 203.0,286.3 204.4,287.1 205.8,287.8 207.2,288.6 208.6,289.3 210.0,290.0 211.4,290.7 212.8,291.4 214.2,292.0 215.6,292.7 217.0,293.3 218.4,294.0 219.8,294.6 221.2,295.2 222.6,295.8 224.0,296.4 225.4,296.9 226.8,297.5 228.2,298.1 229.6,298.6 231.0,299.1 232.4,299.7 233.8,300.2 235.2,300.7 236.6,301.2 238.0,301.7 239.4,302.1 240.8,302.6 242.2,303.1 243.6,303.5 245.0,304.0 246.4,304.4 247.8,304.9 249.2,305.3 250.6,305.7 252.0,306.2 253.4,306.6 254.8,307.0 256.2,307.4 257.6,307.8 259.0,308.1 260.4,308.5 261.8,308.9 263.2,309.3 264.6,309.6 266.0,310.0 267.4,310.4 268.8,310.7 270.2,311.0 271.6,311.4 273.0,311.7 274.4,312.1 275.8,312.4 277.2,312.7 278.6,313.0 280.0,313.3 281.4,313.6 282.8,313.9 284.2,314.2 285.6,314.5 287.0,314.8 288.4,315.1 289.8,315.4 291.2,315.7 292.6,316.0 294.0,316.2 295.4,316.5 296.8,316.8 298.2,317.1 299.6,317.3 301.0,317.6 302.4,317.8 303.8,318.1 305.2,318.3 306.6,318.6 308.0,318.8 309.4,319.1 310.8,319.3 312.2,319.5 313.6,319.8 315.0,320.0 316.4,320.2 317.8,320.5 319.2,320.7 320.6,320.9 322.0,321.1 323.4,321.3 324.8,321.5 326.2,321.7 327.6,322.0 329.0,322.2 330.4,322.4 331.8,322.6 333.2,322.8 334.6,323.0 336.0,323.2 337.4,323.4 338.8,323.5 340.2,323.7 341.6,323.9 343.0,324.1 344.4,324.3 345.8,324.5 347.2,324.6 348.6,324.8 350.0,325.0 351.4,325.2 352.8,325.3 354.2,325.5 355.6,325.7 357.0,325.9 358.4,326.0 359.8,326.2 361.2,326.3 362.6,326.5 364.0,326.7 365.4,326.8 366.8,327.0 368.2,327.1 369.6,327.3 371.0,327.4 372.4,327.6 373.8,327.7 375.2,327.9 376.6,328.0 378.0,328.2 379.4,328.3 380.8,328.5 382.2,328.6" stroke-width="2.2"/><circle cx="169.0" cy="261.0" r="4.5" fill="currentColor"/><line x1="70" y1="360" x2="408.8" y2="360" marker-end="url(#arrU7)"/><line x1="70" y1="360" x2="70" y2="17.0" marker-end="url(#arrU7)"/><g fill="currentColor" stroke="none" font-size="14"><text x="408.8" y="380" text-anchor="end" font-style="italic" font-size="16">Δq</text><text x="60" y="21.19999999999999" text-anchor="end" font-style="italic" font-size="16">Δp</text><text x="168.99494936611666" y="378" text-anchor="middle">1/√2</text><text x="64" y="266.00505063388334" text-anchor="end">1/√2</text><text x="116.2" y="301.2">forbidden</text><text x="116.2" y="317.2" font-size="12">Δq Δp &lt; ½</text><text x="259.0" y="136.0" text-anchor="middle">classical states</text><text x="259.0" y="152.0" text-anchor="middle" font-size="12">(mixtures of coherent states)</text><text x="176.99494936611666" y="279.00505063388334" font-size="12">coherent states</text><text x="128.8" y="94.0" text-anchor="middle" font-size="12">squeezed</text><text x="128.8" y="108.0" text-anchor="middle" font-size="12">in q</text><text x="329.0" y="276.0" text-anchor="middle" font-size="12">squeezed in p</text><text x="385.0" y="346.0" font-size="12" font-style="italic" text-anchor="end">Δq Δp = ½</text></g></svg></div>
$$x_\theta = \frac{1}{2} (a e^{-i\theta} + a^\dagger e^{i \theta})$$
measure of squeezing:
$$s(\theta) = 4 \Delta^2 x_\theta -1$$
Class of states: squeezed coherent states:
$$S(\xi)=e^{\frac{1}{2}(\xi^*a^2 -\xi {a^\dagger}^2)}$$
$$S^\dagger a S=a+\frac{1}{2}[a,()] + \frac{1}{3!}[a,...]$$
The nested commutators only involve $[a,\tfrac12\xi (a^\dagger)^2]=\xi a^\dagger$ and $[a^\dagger,\tfrac12\xi^* a^2]=-\xi^* a$, so the series resums to cosh and sinh: $S^\dagger a S = a \cosh r-a^\dagger e^{i\theta}\sinh r$, where $\xi=re^{i \theta}$
$$S^\dagger a^\dagger S = a^{\dagger}\cosh(r)-a \sinh(r) e^{-i \theta}$$
$$\bra{\psi_\xi}a\ket{\psi_\xi}=\bra{0}S^\dagger a S \ket{0}=0$$
Now we can calculate the variance of quadratures
$$\Delta^2 X_1 =\bra{0}S^\dagger (\frac{1}{2}(a+a^\dagger))^2 S \ket{0} - \bra{0} S^\dagger \frac{1}{2}(a+a^\dagger)S \ket{0}^2$$
if we insert $S S^\dagger$
$$=\frac{1}{4} (\cosh^2(r)+\sinh^2(r)-2 \sinh(r)\cosh(r) \cos(\theta))$$
for $\theta=0$
$$\Delta^2 X_1=\frac{1}{4}(\cosh r-\sinh r)^2  = \frac{1}{4}e^{-2r}$$
as $r \rightarrow \infty $, the quadrature $\Delta^2 X_1 \rightarrow 0$
The second quadrature is:
$$\Delta^2 X_2 = \frac{1}{4}e^{2r}$$
$$\Delta X_1 \Delta X_2 =\frac{1}{4}$$

### Squeezed coherent states

A **squeezed coherent state** is obtained by squeezing the vacuum and then displacing it,

$$\ket{\alpha,\xi} = \hat D(\alpha)\,\hat S(\xi)\ket0, \qquad \xi = re^{i\theta}.$$

We abbreviate $\mu = \cosh r$ and $\nu = e^{i\theta}\sinh r$, so that $\hat S^\dagger\hat a\hat S = \mu\hat a-\nu\hat a^\dagger$, and use $\hat D^\dagger\hat a\hat D = \hat a+\alpha$.

**Mean photon number.** Inserting $\hat D\hat D^\dagger = \hat 1$ between $\hat a^\dagger$ and $\hat a$,

$$\langle\hat a^\dagger\hat a\rangle_{\alpha,\xi} = \bra0\hat S^\dagger\hat D^\dagger\hat a^\dagger\hat D\hat D^\dagger\hat a\hat D\hat S\ket0 = \bra0\hat S^\dagger(\hat a^\dagger+\alpha^*)(\hat a+\alpha)\hat S\ket0 = |\alpha|^2+\sinh^2r .$$

The cross terms vanish because $\bra0\hat S^\dagger\hat a\hat S\ket0 = 0$, and the last term is $\|\hat S^\dagger\hat a\hat S\ket0\|^2 = \|-\nu\hat a^\dagger\ket0\|^2 = \sinh^2r$. The coherent part contributes $|\alpha|^2$ and the squeezing adds $\sinh^2r$ photons.

**Eigenvalue equation.** Start from $\hat a\ket0 = 0$ and insert $\hat S^\dagger\hat D^\dagger\hat D\hat S = \hat 1$:

$$0 = \hat D\hat S\,\hat a\,\hat S^\dagger\hat D^\dagger\;\hat D\hat S\ket0 .$$

The inverse transformations are $\hat S\hat a\hat S^\dagger = \mu\hat a+\nu\hat a^\dagger$ (replace $\xi\to-\xi$) and $\hat D\hat a\hat D^\dagger = \hat a-\alpha$. Hence $\hat D\hat S\hat a\hat S^\dagger\hat D^\dagger = \mu(\hat a-\alpha)+\nu(\hat a^\dagger-\alpha^*)$, and

$$\big(\mu\,\hat a+\nu\,\hat a^\dagger\big)\ket{\alpha,\xi} = \gamma\,\ket{\alpha,\xi}, \qquad \gamma = \alpha\cosh r+\alpha^*e^{i\theta}\sinh r .$$

For $\alpha = 0$ this reduces to $(\mu\hat a+\nu\hat a^\dagger)\ket\xi = 0$, the equation used for the squeezed vacuum below. In terms of the quadratures $\hat X_{1,2}$ ($\hat a = \hat X_1+i\hat X_2$) and for $\theta = 0$, the operator is $\mu\hat a+\nu\hat a^\dagger = (\mu+\nu)\hat X_1+i(\mu-\nu)\hat X_2$, so the equation can also be written as

$$\big(\hat X_1+i\lambda\hat X_2\big)\ket{\alpha,\xi} = \chi\,\ket{\alpha,\xi}, \qquad \lambda = \frac{\mu-\nu}{\mu+\nu} = e^{-2r}, \qquad \chi = \frac{\gamma}{\mu+\nu}.$$

For real $\alpha$, $\gamma = \alpha(\mu+\nu)$ and $\chi = \alpha$. Eigenstates of $\hat X_1+i\lambda\hat X_2$ are minimum-uncertainty states with $\Delta X_1/\Delta X_2 = \lambda$; the squeezed coherent states are exactly these.

## Photon number distribution of squeezed states

Expand the squeezed vacuum in the Fock basis, $\ket{\xi}=\sum_{n} c_n \ket{n}$. Setting $\alpha=0$ in the eigenvalue equation above,
$$(\mu\hat a + \nu\hat a^\dagger)\ket{\xi}=0 .$$
Projecting onto $\bra n$ gives $\mu\sqrt{n+1}\,c_{n+1}+\nu\sqrt n\,c_{n-1}=0$, i.e.
$$c_{n+1}=-\frac{\nu}{\mu}\sqrt{\frac{n}{n+1}}\,c_{n-1}.$$
Since $c_1 = 0$ (the $n=0$ equation), all odd amplitudes vanish. Iterating from $c_0$,
$$c_{2m}=(-1)^m (e^{i \theta} \tanh r)^m \sqrt{\frac{(2m-1)!!}{(2m)!!}}\,c_0 .$$
Normalization:
$$|c_0|^2 \Big(1+\sum_{m\ge1} \frac{(2m-1)!!}{(2m)!!}\tanh^{2m}r\Big)=|c_0|^2\,(1-\tanh^2 r)^{-1/2}=|c_0|^2\cosh r=1,$$
using $(1-z)^{-1/2}=\sum_m \frac{(2m-1)!!}{(2m)!!}z^m$. Hence $c_0=1/\sqrt{\cosh r}$ and, with $\frac{(2m-1)!!}{(2m)!!}=\frac{(2m)!}{4^m (m!)^2}$,
$$P(2m)=|c_{2m}|^2=\frac{(2m)!}{4^m (m!)^2} \frac{(\tanh r)^{2m}}{\cosh r}, \qquad P(2m+1)=0 .$$

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



### Photon number distribution of squeezed coherent states

Projecting the eigenvalue equation onto $\bra n$, with $\ket{\alpha,\xi} = \sum_nc_n\ket n$, gives the three-term recurrence

$$\mu\sqrt{n+1}\;c_{n+1}+\nu\sqrt n\;c_{n-1} = \gamma\,c_n .$$

We try $c_n = c_0\,t^n f_n/\sqrt{n!}$. Substituting and multiplying by $\sqrt{n!}/(c_0t^{n-1})$ gives $\mu t^2f_{n+1}+\nu nf_{n-1} = \gamma tf_n$. This is the Hermite recurrence $H_{n+1}(z) = 2zH_n(z)-2nH_{n-1}(z)$ provided $\nu = 2\mu t^2$ and $\gamma t = 2\mu t^2z$, i.e.

$$t^2 = \frac\nu{2\mu} = \frac12e^{i\theta}\tanh r, \qquad z = \frac{\gamma}{2\mu t} = \frac{\gamma}{\sqrt{e^{i\theta}\sinh2r}} .$$

Fixing $c_0 = \langle0|\alpha,\xi\rangle$ by normalization, the amplitudes are

$$c_n = \frac{1}{\sqrt{\cosh r}}\,\exp\Big[-\frac12|\alpha|^2-\frac12\alpha^{*2}e^{i\theta}\tanh r\Big]\Big(\frac12e^{i\theta}\tanh r\Big)^{n/2}\frac{H_n(z)}{\sqrt{n!}}, \qquad P(n) = |c_n|^2 .$$

For $r\to0$ this reduces to the Poisson distribution of $\ket\alpha$. For $\alpha = 0$, $z = 0$ and $H_n(0) = 0$ for odd $n$, which reproduces the even-only distribution of the squeezed vacuum derived above.

> [!example] Homework (from the board)
> Solve $(\mu\hat a+\nu\hat a^\dagger)\ket\xi = 0$ in the position representation $\langle x|\cdot\rangle$ and find the wavefunction of the squeezed vacuum.

**Interactive plot.** The bars are $P(n)$ computed from the recurrence above; the Wigner function is the Gaussian with mean $\alpha$ and covariance $\frac14R(\theta/2)\,\mathrm{diag}(e^{-2r},e^{2r})\,R(\theta/2)^T$ (the quadrature $\hat X_{\theta/2}$ is squeezed); the Husimi $Q$ (switch above the plot) is the same Gaussian with the vacuum noise added, covariance $+\frac14\mathbb 1$, so it is never narrower than the vacuum in any direction. Squeezing along the displacement ($\theta = 2\arg\alpha$) gives sub-Poissonian statistics; squeezing across it gives super-Poissonian statistics with oscillations in $P(n)$.

```dataviewjs
// ===== CONFIG =====
const CFG = { amp: 2, ampMax: 3.5, arg: 0, r: 0.5, rMax: 1.2, th: 0, L: 4.5, N: 260 };
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
const pois = (n, m) => (m <= 0 ? (n === 0 ? 1 : 0) : Math.exp(n * Math.log(m) - m - LF[n]));
// P(n) bars + Poisson reference with the same mean; returns an update function
function countsPlot(bP, cbP) {
  let P = [1], nShow = 10, mean = 0;
  const bars = bP.create("curve", [[0], [0]], { fixed: true, highlight: false, strokeColor: "#c2410c", strokeWidth: 1, fillColor: "#f0a46a", fillOpacity: 0.85 });
  bars.updateDataArray = function () { const xs = [], ys = []; for (let n = 0; n <= nShow; n++) { xs.push(n - 0.38, n - 0.38, n + 0.38, n + 0.38, NaN); ys.push(0, P[n], P[n], 0, NaN); } this.dataX = xs; this.dataY = ys; };
  const pl = bP.create("curve", [[0], [0]], { fixed: true, highlight: false, strokeColor: C.obs, strokeWidth: 2, dash: 2, visible: () => cbP.checked });
  pl.updateDataArray = function () { const xs = [], ys = []; for (let n = 0; n <= nShow; n++) { xs.push(n); ys.push(pois(n, mean)); } this.dataX = xs; this.dataY = ys; };
  for (let n = 0; n <= 80; n++) bP.create("point", [n, () => pois(n, mean)], { fixed: true, highlight: false, withLabel: false, size: 2.5, strokeColor: C.obs, fillColor: "#fff", visible: () => cbP.checked && n <= nShow });
  const leg = bP.create("text", [0, 0, () => "<span style='color:#c2410c'>■</span> state" + (cbP.checked ? " &nbsp; <span style='color:" + C.obs + "'>○</span> Poisson, same ⟨n⟩" : "")], { fixed: true, highlight: false, fontSize: 12, strokeColor: C.ink, anchorX: "right", anchorY: "top" });
  return (Pnew) => {
    P = Pnew; mean = 0; let m2 = 0, cum = 0, nEnd = 0; P.forEach((p, n) => { mean += n * p; m2 += n * n * p; });
    for (let n = 0; n < P.length; n++) { cum += P[n]; if (cum > 0.999) { nEnd = n; break; } }
    const varn = m2 - mean * mean; nShow = Math.min(80, Math.max(10, Math.ceil(Math.max(nEnd, mean + 4 * Math.sqrt(varn)))));
    let ymax = 0; for (let n = 0; n <= nShow; n++) ymax = Math.max(ymax, P[n], cbP.checked ? pois(n, mean) : 0); ymax *= 1.18;
    bP.setBoundingBox([-0.06 * nShow - 1, ymax, nShow + 1, -0.08 * ymax], false); leg.setPosition(JXG.COORDS_BY_USER, [nShow + 0.6, ymax * 0.97]); bP.update();
    return { mean, varn };
  };
}
const sA = K.slider("|α|", 0, CFG.ampMax, 0.01, CFG.amp), sG = K.slider("arg α", 0, 360, 1, CFG.arg, (v) => v + "°");
const sR = K.slider("r", 0, CFG.rMax, 0.01, CFG.r), sT = K.slider("θ", 0, 360, 1, CFG.th, (v) => v + "°");
const sel = K.select([["W", "Wigner W"], ["Q", "Husimi Q"]]), cbV = K.check("vacuum circle"), cbP = K.check("Poisson, same mean");
K.root.append(panel);
const bP = board(pdiv, [-1, 1, 20, -0.08], "n", "P(n)"), upd = countsPlot(bP, cbP);
// c_n from (μ a + ν a†)|α,ξ⟩ = γ|α,ξ⟩:  μ√(n+1) c_{n+1} = γ c_n − ν √n c_{n−1}
function amplitudes(al, r, th) {
  const mu = Math.cosh(r), nu = [Math.cos(th) * Math.sinh(r), Math.sin(th) * Math.sinh(r)];
  const mul = (p, q) => [p[0] * q[0] - p[1] * q[1], p[0] * q[1] + p[1] * q[0]], ac = [al[0], -al[1]];
  const g = [al[0] * mu + mul(ac, nu)[0], al[1] * mu + mul(ac, nu)[1]];
  const t = Math.tanh(r), a2c = mul(ac, ac), e = mul(a2c, [Math.cos(th) * t, Math.sin(th) * t]);   // α*² e^{iθ} tanh r
  const amp0 = Math.exp(-(al[0] ** 2 + al[1] ** 2) / 2 - e[0] / 2) / Math.sqrt(mu), ph0 = -e[1] / 2;
  const c = [[amp0 * Math.cos(ph0), amp0 * Math.sin(ph0)]];
  c[1] = [mul(g, c[0])[0] / mu, mul(g, c[0])[1] / mu];
  for (let n = 1; n < CFG.N - 1; n++) { const a1 = mul(g, c[n]), b1 = mul(nu, c[n - 1]), s = Math.sqrt(n);
    c[n + 1] = [(a1[0] - s * b1[0]) / (mu * Math.sqrt(n + 1)), (a1[1] - s * b1[1]) / (mu * Math.sqrt(n + 1))]; }
  return { P: c.map((z) => z[0] ** 2 + z[1] ** 2), g };
}
function update() {
  const A = +sA.value, ag = (+sG.value * Math.PI) / 180, r = +sR.value, th = (+sT.value * Math.PI) / 180, al = [A * Math.cos(ag), A * Math.sin(ag)];
  const { P, g } = amplitudes(al, r, th), st = upd(P);
  // Wigner function: Gaussian, mean α, covariance ¼ R(θ/2) diag(e^{-2r}, e^{2r}) R(θ/2)^T  (X_{θ/2} is squeezed)
  const c = Math.cos(th / 2), s = Math.sin(th / 2), e1 = Math.exp(-2 * r) / 4, e2 = Math.exp(2 * r) / 4;
  // Husimi Q: the same Gaussian smoothed by the vacuum, covariance + ¼·1
  const isQ = sel.value === "Q", q = isQ ? 0.25 : 0;
  const vxx = c * c * e1 + s * s * e2 + q, vxy = c * s * (e1 - e2), vyy = s * s * e1 + c * c * e2 + q, det = vxx * vyy - vxy * vxy, nrm = 1 / (2 * Math.PI * Math.sqrt(det));
  heat((x, y) => { const dx = x - al[0], dy = y - al[1]; return nrm * Math.exp(-0.5 * (vyy * dx * dx - 2 * vxy * dx * dy + vxx * dy * dy) / det); }, CFG.L, isQ ? 1 / Math.PI : 2 / Math.PI, isQ ? "Q(α), colour scale 0 … 1/π" : "W(α), colour scale ±2/π",
    (ctx, sx, sy, k) => { if (!cbV.checked) return; ctx.setLineDash([4, 3]); ctx.strokeStyle = C.obs; ctx.beginPath(); ctx.arc(sx(al[0]), sy(al[1]), 0.5 * k, 0, 7); ctx.stroke(); ctx.setLineDash([]); });
  const nbar = A * A + Math.sinh(r) ** 2, F = st.varn / st.mean;
  panel.textContent =
`γ = α cosh r + α* e^{iθ} sinh r = ${f(g[0])} ${g[1] < 0 ? "−" : "+"} ${f(Math.abs(g[1]))}i
⟨n⟩ = ${f(st.mean)}  (|α|² + sinh²r = ${f(nbar)})   Δ²n = ${f(st.varn)}   Fano Δ²n/⟨n⟩ = ${f(F)}   ${F < 1 - 1e-6 ? "sub-Poissonian" : F > 1 + 1e-6 ? "super-Poissonian" : "Poissonian"}
Var(X_{θ/2}) = ${f(e1)},  Var(X_{θ/2+π/2}) = ${f(e2)}   (vacuum 0.250)`;
}
for (const x of [sA, sG, sR, sT]) x.addEventListener("input", update);
for (const x of [sel, cbV, cbP]) x.onchange = update;
update();
```

### Cat states

A **cat state** is a superposition of two coherent states of equal amplitude $\alpha$ (real) and opposite phases $\pm\varphi$,

$$\ket{\rm CAT} = \frac{N}{\sqrt2}\Big(\ket{\alpha e^{i\varphi}}+\ket{\alpha e^{-i\varphi}}\Big).$$

**Normalization.** The overlap of the two components is $\langle\alpha e^{-i\varphi}|\alpha e^{i\varphi}\rangle = \exp\big(-\alpha^2+\alpha^2e^{2i\varphi}\big) = e^{-2\alpha^2\sin^2\varphi}\,e^{i\alpha^2\sin2\varphi}$. Requiring $\langle{\rm CAT}|{\rm CAT}\rangle = N^2\big(1+\mathrm{Re}\,\langle\alpha e^{-i\varphi}|\alpha e^{i\varphi}\rangle\big) = 1$ gives

$$N^2(\varphi) = \frac{1}{1+\cos\big(\alpha^2\sin2\varphi\big)\,e^{-p_\varphi^2}}, \qquad p_\varphi = \sqrt2\,\alpha\sin\varphi .$$

The two components sit at the same position $x = \sqrt2\alpha\cos\varphi$ and at momenta $\pm p_\varphi$; for $p_\varphi\gg1$ they no longer overlap and $N^2\to1$.

**Photon number distribution.** With $\langle m|\beta\rangle = e^{-|\beta|^2/2}\beta^m/\sqrt{m!}$,

$$P_m = |\langle m|{\rm CAT}\rangle|^2 = \frac{N^2}{2}\Big|\langle m|\alpha e^{i\varphi}\rangle+\langle m|\alpha e^{-i\varphi}\rangle\Big|^2 = \Big|A_m^{1/2}e^{im\varphi}+A_m^{1/2}e^{-im\varphi}\Big|^2 = 4A_m\cos^2(m\varphi), \qquad A_m = \frac12N^2\frac{\alpha^{2m}}{m!}e^{-\alpha^2}.$$

The Poisson distribution of a coherent state is modulated by $\cos^2(m\varphi)$. For $\varphi = \pi/2$ (the even cat $\ket{i\alpha}+\ket{-i\alpha}$) only even $m$ survive; for $\varphi\to0$ the two components merge into $\ket\alpha$ and the statistics become Poissonian again. The **Fano factor** $\Delta^2n/\bar n$ as a function of $\varphi$ (bottom panel of the plot below) therefore starts at one, oscillates between sub- and super-Poissonian values, and returns to one at $\varphi = \pi$.

**Wigner function.** Writing the coherent-state wavefunctions as $\psi_\beta(x) = \pi^{-1/4}e^{\frac12(\beta^2-|\beta|^2)}e^{-\frac12(x-\sqrt2\beta)^2}$,

$$\psi_{\rm CAT}(x) = \frac{1}{\pi^{1/4}}\frac{N}{\sqrt2}\,e^{-\alpha^2\sin^2\varphi}\,e^{\frac i2\alpha^2\sin2\varphi}\Big(e^{-\frac12(x-\sqrt2\alpha e^{i\varphi})^2}+e^{-i\alpha^2\sin2\varphi}\,e^{-\frac12(x-\sqrt2\alpha e^{-i\varphi})^2}\Big).$$

Inserting this into the definition of $W$, the Wigner function is the sum of the two coherent-state Gaussians and an interference term,

$$W_{\rm CAT} = \frac{N^2}{2}\Big(W_{\ket{\alpha e^{i\varphi}}}+W_{\ket{\alpha e^{-i\varphi}}}+W_I\Big), \\ W_I = \frac2\pi\cos\Big(2\sqrt2\,\alpha\sin\varphi\,\big(x-\tfrac{1}{\sqrt2}\alpha\cos\varphi\big)\Big)\,e^{-(x-\sqrt2\alpha\cos\varphi)^2-p^2},$$

with $W_{\ket\beta} = \frac1\pi e^{-(x-\sqrt2\,\mathrm{Re}\beta)^2-(p-\sqrt2\,\mathrm{Im}\beta)^2}$. The interference term sits midway between the two components; its fringes run perpendicular to the line joining them, with period $\pi/(\sqrt2\alpha\sin\varphi)$ in $x$. Because $W_I$ takes negative values, the cat state is nonclassical.

**$Q$ function.** From $\langle\beta|\gamma\rangle = e^{-\frac12|\beta-\gamma|^2}e^{i\,\mathrm{Im}(\beta^*\gamma)}$,

$$Q(\beta) = \frac1\pi\,\bigg|\langle\beta|\,\frac{N}{\sqrt2}\Big(\ket{\alpha e^{i\varphi}}+\ket{\alpha e^{-i\varphi}}\Big)\bigg|^2 .$$

$Q$ shows two smooth humps; the interference survives only as a weak modulation in the overlap region, since the Gaussian smoothing washes out the fringes.

```dataviewjs
// ===== CONFIG =====
const CFG = { amp: 2, ampMax: 3.5, phi: 90, L: 4.5, N: 200 };
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
const pois = (n, m) => (m <= 0 ? (n === 0 ? 1 : 0) : Math.exp(n * Math.log(m) - m - LF[n]));
// P(n) bars + Poisson reference with the same mean; returns an update function
function countsPlot(bP, cbP) {
  let P = [1], nShow = 10, mean = 0;
  const bars = bP.create("curve", [[0], [0]], { fixed: true, highlight: false, strokeColor: "#c2410c", strokeWidth: 1, fillColor: "#f0a46a", fillOpacity: 0.85 });
  bars.updateDataArray = function () { const xs = [], ys = []; for (let n = 0; n <= nShow; n++) { xs.push(n - 0.38, n - 0.38, n + 0.38, n + 0.38, NaN); ys.push(0, P[n], P[n], 0, NaN); } this.dataX = xs; this.dataY = ys; };
  const pl = bP.create("curve", [[0], [0]], { fixed: true, highlight: false, strokeColor: C.obs, strokeWidth: 2, dash: 2, visible: () => cbP.checked });
  pl.updateDataArray = function () { const xs = [], ys = []; for (let n = 0; n <= nShow; n++) { xs.push(n); ys.push(pois(n, mean)); } this.dataX = xs; this.dataY = ys; };
  for (let n = 0; n <= 80; n++) bP.create("point", [n, () => pois(n, mean)], { fixed: true, highlight: false, withLabel: false, size: 2.5, strokeColor: C.obs, fillColor: "#fff", visible: () => cbP.checked && n <= nShow });
  const leg = bP.create("text", [0, 0, () => "<span style='color:#c2410c'>■</span> state" + (cbP.checked ? " &nbsp; <span style='color:" + C.obs + "'>○</span> Poisson, same ⟨n⟩" : "")], { fixed: true, highlight: false, fontSize: 12, strokeColor: C.ink, anchorX: "right", anchorY: "top" });
  return (Pnew) => {
    P = Pnew; mean = 0; let m2 = 0, cum = 0, nEnd = 0; P.forEach((p, n) => { mean += n * p; m2 += n * n * p; });
    for (let n = 0; n < P.length; n++) { cum += P[n]; if (cum > 0.999) { nEnd = n; break; } }
    const varn = m2 - mean * mean; nShow = Math.min(80, Math.max(10, Math.ceil(Math.max(nEnd, mean + 4 * Math.sqrt(varn)))));
    let ymax = 0; for (let n = 0; n <= nShow; n++) ymax = Math.max(ymax, P[n], cbP.checked ? pois(n, mean) : 0); ymax *= 1.18;
    bP.setBoundingBox([-0.06 * nShow - 1, ymax, nShow + 1, -0.08 * ymax], false); leg.setPosition(JXG.COORDS_BY_USER, [nShow + 0.6, ymax * 0.97]); bP.update();
    return { mean, varn };
  };
}
const sA = K.slider("α", 0.05, CFG.ampMax, 0.01, CFG.amp), sF = K.slider("φ", 0, 180, 1, CFG.phi, (v) => v + "°");
const sel = K.select([["W", "Wigner W"], ["Q", "Husimi Q"]]), cbP = K.check("Poisson, same mean");
const fdiv = el("div", `width:${K.W}px;height:${Math.round(WS * 0.75)}px;${box};touch-action:none;margin-top:${GAP}px`);
K.root.append(fdiv, panel);
const bP = board(pdiv, [-1, 1, 20, -0.08], "m", "P(m)"), upd = countsPlot(bP, cbP);
// photon statistics:  P_m = 2 N² e^{−α²} α^{2m}/m! cos²(mφ)
const N2 = (a, ph) => 1 / (1 + Math.cos(a * a * Math.sin(2 * ph)) * Math.exp(-2 * a * a * Math.sin(ph) ** 2));
const Pm = (a, ph) => { const n2 = N2(a, ph), out = []; for (let m = 0; m < CFG.N; m++) out.push(2 * n2 * Math.exp(-a * a + 2 * m * Math.log(a) - LF[m]) * Math.cos(m * ph) ** 2); return out; };
const fano = (a, ph) => { const P = Pm(a, ph); let m1 = 0, m2 = 0; P.forEach((p, m) => { m1 += m * p; m2 += m * m * p; }); return (m2 - m1 * m1) / m1; };
// Fano factor vs φ
const bF = board(fdiv, [-8, 3, 188, -0.2], "φ°", "Δ²n / n̄");
bF.create("line", [[0, 1], [1, 1]], { fixed: true, highlight: false, strokeColor: C.muted, dash: 2 });
const fcur = bF.create("functiongraph", [(d) => fano(+sA.value, (d * Math.PI) / 180), 0.5, 179.5], { fixed: true, highlight: false, strokeColor: C.obs, strokeWidth: 2.2 });
const fdot = bF.create("point", [() => +sF.value, () => fano(+sA.value, (Math.max(0.5, Math.min(179.5, +sF.value)) * Math.PI) / 180)], { fixed: true, highlight: false, withLabel: false, size: 4, strokeColor: C.sel, fillColor: C.sel });
// complex helpers
const cm = (p, q) => [p[0] * q[0] - p[1] * q[1], p[0] * q[1] + p[1] * q[0]], cexp = (z) => { const e = Math.exp(z[0]); return [e * Math.cos(z[1]), e * Math.sin(z[1])]; };
function update() {
  const a = +sA.value, ph = (+sF.value * Math.PI) / 180, n2 = N2(a, ph), b1 = [a * Math.cos(ph), a * Math.sin(ph)], b2 = [a * Math.cos(ph), -a * Math.sin(ph)];
  const st = upd(Pm(a, ph));
  // ⟨β2|β1⟩ = e^{−2α² sin²φ} e^{iα² sin 2φ}
  const ov = cexp([-2 * a * a * Math.sin(ph) ** 2, a * a * Math.sin(2 * ph)]);
  if (sel.value === "W") heat((x, y) => {
      const d1 = (x - b1[0]) ** 2 + (y - b1[1]) ** 2, d2 = (x - b2[0]) ** 2 + (y - b2[1]) ** 2;
      const zz = cm([x - b1[0], y - b1[1]], [x - b2[0], -y + b2[1]]) /* (α − β1)(α* − β2*) */, cr = cm(ov, cexp([-2 * zz[0], -2 * zz[1]]));
      return (n2 / 2) * (2 / Math.PI) * (Math.exp(-2 * d1) + Math.exp(-2 * d2) + 2 * cr[0]);
    }, CFG.L, 2 / Math.PI, "W(α), colour scale ±2/π");
  else heat((x, y) => {   // Q(α) = (N²/2π) |⟨α|β1⟩ + ⟨α|β2⟩|²,   ⟨α|β⟩ = e^{−|α−β|²/2} e^{i Im(α*β)}
      const t = (b) => cexp([-((x - b[0]) ** 2 + (y - b[1]) ** 2) / 2, x * b[1] - y * b[0]]), s1 = t(b1), s2 = t(b2);
      return (n2 / (2 * Math.PI)) * ((s1[0] + s2[0]) ** 2 + (s1[1] + s2[1]) ** 2);
    }, CFG.L, 1 / Math.PI, "Q(α), colour scale 0 … 1/π");
  let fmax = 0; for (let d = 1; d < 180; d += 1) fmax = Math.max(fmax, fano(a, (d * Math.PI) / 180));
  bF.setBoundingBox([-8, Math.max(2, fmax * 1.12), 188, -0.12 * Math.max(2, fmax * 1.12)], false); bF.update();
  const F = st.varn / st.mean;
  panel.textContent =
`N² = 1/(1 + cos(α² sin 2φ) e^{−2α² sin²φ}) = ${f(n2)}     p_φ = ±√2 α sin φ = ±${f(Math.SQRT2 * a * Math.sin(ph))}
⟨n⟩ = ${f(st.mean)}   Δ²n = ${f(st.varn)}   Fano Δ²n/⟨n⟩ = ${f(F)}   ${F < 1 - 1e-6 ? "sub-Poissonian" : F > 1 + 1e-6 ? "super-Poissonian" : "Poissonian"}`;
}
for (const x of [sA, sF]) x.addEventListener("input", update);
sel.onchange = update; cbP.onchange = update;
update();
```

> [!question]- Questions
> - Why are the oscillations in the photon number of squeezed coherent states no longer of period two photons?
>   For $\alpha = 0$ the state is a parity eigenstate and only even $n$ occur. The displacement breaks this symmetry, and $P(n)\propto|H_n(z)|^2$ with complex $z$ oscillates with a period set by $\alpha$ and $r$ rather than by parity. In phase space the oscillations come from the interference of the two regions where the squeezed ellipse crosses the ring of the Fock state $\ket n$, so their period depends on the geometry of the ellipse.
> - Check what happens when a squeezed state is the input in homodyne detection, and how this is used in LIGO.

**Further reading**

- [Properties of squeezed number states and squeezed thermal states](https://journals.aps.org/pra/pdf/10.1103/PhysRevA.40.2494)
- W. P. Schleich, *Quantum Optics in Phase Space* (Wiley-VCH, 2001)
- [Oscillations in photon distribution of squeezed states and interference in phase space](https://sci-hub.pl/storage/2024/1035/07d7a00c2dd7648a0b842a38071397b3/schleich1987.pdf)
- [Area of overlap and interference in phase space versus Wigner pseudoprobabilities](https://sci-hub.pl/10.1103/PhysRevA.38.1177)
- [Sub-Planck Structure in Phase Space and Its Relevance for Quantum Decoherence](https://sci-hub.pl/10.1038/35089017)

---
[[QO - Lecture 7|← Previous: Lecture 7]] · [[QO - Lecture 9|Next: Lecture 9 →]]
