← [[QO - Lecture 12|Lecture 12]] · [[QO - chapter I|Full chapter]]

# Lecture 13: Atomic dynamics

<div style="text-align:center"><svg width="620" height="230" viewBox="0 0 620 230" xmlns="http://www.w3.org/2000/svg" fill="none" stroke="currentColor" stroke-width="1.5" font-family="Times New Roman, serif" font-size="15"><defs><marker id="arrL13" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="7" markerHeight="7" orient="auto"><path d="M0,0 L10,5 L0,10 z" fill="currentColor" stroke="none"/></marker></defs>
<line x1="40" y1="190" x2="110" y2="190" stroke-width="2.4"/><line x1="40" y1="50" x2="110" y2="50" stroke-width="2.4"/><line x1="40" y1="62" x2="110" y2="62" stroke-dasharray="4 3"/><line x1="70" y1="188" x2="70" y2="65" marker-end="url(#arrL13)"/><line x1="92" y1="188" x2="92" y2="53" stroke-dasharray="2 3" marker-end="url(#arrL13)"/>
<g fill="currentColor" stroke="none"><text x="116" y="194" font-style="italic">|g⟩</text><text x="116" y="54" font-style="italic">|e⟩</text><text x="38" y="130" text-anchor="end" font-style="italic">ω</text><text x="98" y="130" font-style="italic" font-size="13">ω<tspan font-size="10" dy="4">eg</tspan></text><text x="18" y="66" font-size="12" font-style="italic">Δ</text><text x="75" y="222" text-anchor="middle" font-size="14">two levels</text></g>
<line x1="210" y1="190" x2="270" y2="190" stroke-width="2.4"/><line x1="320" y1="160" x2="380" y2="160" stroke-width="2.4"/><line x1="320" y1="168" x2="380" y2="168" stroke-dasharray="4 3"/><line x1="255" y1="45" x2="335" y2="45" stroke-width="2.4"/><line x1="255" y1="30" x2="335" y2="30" stroke-dasharray="4 3"/><line x1="240" y1="188" x2="292" y2="33" stroke-width="2.2" marker-end="url(#arrL13)"/><line x1="350" y1="166" x2="298" y2="33" stroke-width="2.2" marker-end="url(#arrL13)"/>
<g fill="currentColor" stroke="none"><text x="276" y="194" font-style="italic">|g⟩</text><text x="386" y="164" font-style="italic">|s⟩</text><text x="341" y="49" font-style="italic">|e⟩</text><text x="232" y="34" font-size="13" font-style="italic">Δ</text><text x="388" y="178" font-size="13" font-style="italic">δ</text><text x="228" y="120" font-style="italic" text-anchor="end">ω<tspan font-size="10" dy="4">p</tspan><tspan dy="-4">, Ω</tspan><tspan font-size="10" dy="4">p</tspan></text><text x="226" y="140" font-size="12" text-anchor="end">probe</text><text x="338" y="110" font-style="italic">ω<tspan font-size="10" dy="4">c</tspan><tspan dy="-4">, Ω</tspan><tspan font-size="10" dy="4">c</tspan></text><text x="338" y="128" font-size="12">coupling</text><text x="295" y="222" text-anchor="middle" font-size="14">Λ scheme</text></g>
<line x1="480" y1="195" x2="560" y2="195" stroke-width="2.4"/><line x1="480" y1="120" x2="560" y2="120" stroke-width="2.4"/><line x1="480" y1="40" x2="560" y2="40" stroke-width="2.4"/><line x1="510" y1="193" x2="510" y2="123" stroke-width="2.2" marker-end="url(#arrL13)"/><line x1="530" y1="118" x2="530" y2="43" stroke-width="2.2" marker-end="url(#arrL13)"/>
<g fill="currentColor" stroke="none"><text x="566" y="199" font-style="italic">|g⟩</text><text x="566" y="124" font-style="italic">|e⟩</text><text x="566" y="44" font-style="italic">|s⟩</text><text x="504" y="162" font-style="italic" text-anchor="end">ω<tspan font-size="10" dy="4">p</tspan></text><text x="536" y="84" font-style="italic">ω<tspan font-size="10" dy="4">c</tspan></text><text x="520" y="222" text-anchor="middle" font-size="14">ladder (cascade)</text></g></svg></div>

### Two-level atom in a classical field

A classical field $E(t)=E_0\cos\omega t$ couples $\ket g$ and $\ket e$ through the dipole $d=\bra e\hat{\mathbf d}\cdot\boldsymbol\varepsilon\ket g$. Write $\cos\omega t=\frac12(e^{i\omega t}+e^{-i\omega t})$ and keep only the co-rotating terms (RWA). With $\hbar=1$,

$$\hat H = \omega_{eg}\ket e\bra e - \frac{\Omega}{2}\Big(e^{-i\omega t}\ket e\bra g + e^{i\omega t}\ket g\bra e\Big), \qquad \Omega = \frac{dE_0}{\hbar}\ \ \text{(Rabi frequency)} .$$

Remove the fast phase with the ansatz

$$\ket\psi = c_g\ket g + c_e\,e^{-i\omega t}\ket e .$$

Then $i\partial_t\ket\psi=\hat H\ket\psi$ gives $i\dot c_g\ket g+(i\dot c_e+\omega c_e)e^{-i\omega t}\ket e=\omega_{eg}c_ee^{-i\omega t}\ket e-\frac\Omega2\big(c_ge^{-i\omega t}\ket e+c_e\ket g\big)$. Comparing the coefficients of $\ket g$ and $\ket e$,

$$i\dot c_g=-\frac{\Omega}{2}c_e, \qquad i\dot c_e=-\frac{\Omega}{2}c_g-\Delta c_e, \qquad \Delta=\omega-\omega_{eg} .$$

The equations no longer depend on time. For $c_g(0)=1$ the solution gives **Rabi oscillations**,

$$P_e(t)=|c_e|^2=\frac{\Omega^2}{\Omega'^2}\sin^2\frac{\Omega' t}{2}, \qquad \Omega'=\sqrt{\Omega^2+\Delta^2},$$

with full inversion only on resonance.

> [!note] Why a laser needs at least 3 levels
> In steady state a driven two-level atom, with damping, gives $p_e \le \frac12$. Absorption and stimulated emission have the same rate, so pumping on the same transition can at most equalise the populations, never invert them. Population inversion needs a third (or fourth) level: pump to an auxiliary level, which decays quickly into the upper lasing level.

### Three-level atom: Λ and ladder schemes

In the **Λ scheme** two ground states $\ket g,\ket s$ share the excited state $\ket e$. A weak **probe** ($\omega_p$, $\Omega_p$) drives $g\leftrightarrow e$ and a strong **coupling** field ($\omega_c$, $\Omega_c$) drives $s\leftrightarrow e$. In the **ladder** scheme the second field instead drives $e\to s$ upwards. With energies measured from $\ket g$,

$$\hat H=\omega_{sg}\ket s\bra s+\omega_{eg}\ket e\bra e-\frac{\Omega_p}{2}\Big(e^{-i\omega_pt}\ket e\bra g+\text{h.c.}\Big)-\frac{\Omega_c}{2}\Big(e^{-i\omega_ct}\ket e\bra s+\text{h.c.}\Big).$$

Each amplitude carries the phase of the fields that reach that level from $\ket g$:

$$\ket\psi=c_g\ket g+c_e\,e^{-i\omega_pt}\ket e+c_s\,e^{-i(\omega_p-\omega_c)t}\ket s .$$

This makes the equations time-independent and defines two detunings:

$$\Delta=\omega_p-\omega_{eg}\ \ \text{(single-photon detuning)}, \qquad \delta=\omega_p-\omega_c-\omega_{sg}\ \ \text{(two-photon detuning)}.$$

(For the ladder, $\ket s$ is reached by absorbing both photons: use $e^{-i(\omega_p+\omega_c)t}$ and $\delta=\omega_p+\omega_c-\omega_{sg}$.) Inserting the ansatz as for two levels:

$$i \dot{c_g}=-\frac{\Omega_p}{2} c_e$$
$$i \dot{c_e} = -\Delta c_e - \frac{\Omega_p}{2} c_g -\frac{\Omega_c}{2}c_s$$
$$i\dot{c}_s=-\delta c_s - \frac{\Omega_c}{2} c_e$$
or written as a matrix:

$$ i \partial_t\begin{pmatrix} 
c_g \\ c_e \\ c_s
\end{pmatrix} = -\begin{pmatrix} 0 & \Omega_p/2 & 0 \\ \Omega_p/2 & \Delta & \Omega_c/2 \\ 0 & \Omega_c/2 & \delta \end{pmatrix} \begin{pmatrix} 
c_g \\ c_e \\ c_s
\end{pmatrix}
$$

## Dark state and coherent population trapping

At two-photon resonance ($\delta=0$), look for a superposition of the two ground states $\ket{D}=a \ket{g} + b \ket{s}$ that is not coupled to $\ket e$. From the matrix above,

$$\bra{e} \hat H \ket{D} = -\frac{1}{2}\big(\Omega_p a + \Omega_c b\big)=0
\quad\Rightarrow\quad
\ket{D}=\frac{\Omega_c\ket{g}-\Omega_p \ket{s}}{\sqrt{\Omega_p^2 + \Omega_c^2}} .$$

The orthogonal combination is the **bright state**,

$$\ket{B}=\frac{\Omega_p \ket{g} + \Omega_c \ket{s}}{\sqrt{\Omega_p^2 + \Omega_c^2}}, \qquad \bra e\hat H\ket B=-\frac12\sqrt{\Omega_p^2+\Omega_c^2} .$$

Only $\ket B$ couples to $\ket e$. The two excitation paths $g\to e$ and $s\to e$ interfere destructively for $\ket D$. Population that decays from $\ket e$ into $\ket D$ stays there, because $\ket D$ is a zero-energy eigenstate decoupled from the light. This is **coherent population trapping**: the atoms stop absorbing and fluorescing.

## Electromagnetically induced transparency (EIT)

What happens to a weak probe passing through such atoms? Model the decay by complex energies: $\gamma$ for $\ket e$ (spontaneous emission) and $\gamma_s$ for the $g$–$s$ coherence (dephasing, usually $\gamma_s\ll\gamma$). For a weak probe ($\Omega_p\ll\Omega_c$) the atoms stay in $\ket g$, so $c_g\approx1$:

$$i \dot{c}_e = -\Big(\Delta + i \frac{\gamma}{2}\Big) c_e- \frac{\Omega_p}{2}-\frac{\Omega_c}{2}c_s, \qquad
i \dot{c}_s = -\Big(\delta + i \frac{\gamma_s}{2}\Big)c_s - \frac{\Omega_c}{2}c_e .$$

**Steady state** ($\dot c_e=\dot c_s=0$). The second equation gives $c_s$; inserting it into the first,

$$c_s =-\frac{\Omega_c/2}{\delta + i\gamma_s/2}\,c_e, \qquad
c_e =- \frac{\Omega_p/2}{\Delta + i \gamma/2 - \dfrac{\Omega_c^2/4}{\delta+i\gamma_s/2}} .$$

**Susceptibility.** The probe $\mathbf E=\boldsymbol\varepsilon\,\frac{E_0}{2}(e^{-i\omega_pt}+\text{c.c.})$ induces a dipole $\langle\hat d\rangle=d\,(c_e e^{-i \omega_p t}+\text{c.c.})$ per atom. With $N$ atoms per unit volume, $P=N \langle \hat d \rangle=\epsilon_0\chi E$. Comparing the $e^{-i\omega_pt}$ parts, $N d\, c_e = \epsilon_0 \chi E_0/2$, and with $\Omega_p=dE_0/\hbar$:

$$\chi = - \frac{N d^2}{\epsilon_0 \hbar}\; \frac{1}{\Delta + i \gamma/2 - \dfrac{\Omega_c^2/4}{\delta+i\gamma_s/2}}, \qquad n=\sqrt{1+\chi}\approx 1+\frac{\chi}{2}.$$

$\mathrm{Im}\,\chi$ gives absorption (intensity absorption coefficient $\alpha=\frac{\omega}{c}\mathrm{Im}\,\chi$) and $\mathrm{Re}\,\chi$ gives the refractive index. Without the coupling ($\Omega_c=0$) this is the Lorentzian of a two-level atom. Its resonant absorption coefficient is $\alpha_0=\frac{2\omega}{c\gamma}\frac{Nd^2}{\epsilon_0\hbar}$.

For a resonant coupling field ($\Delta=\delta$) and $\gamma_s=0$:

$$\chi =-\frac{N d^2}{\epsilon_0 \hbar}\;\frac{1}{\Delta + i \gamma/2 - \dfrac{\Omega_c^2}{4 \Delta}} .$$

- **Imaginary part.** At $\Delta=0$ the term $\Omega_c^2/4\Delta$ diverges, so $\chi=0$. The medium is exactly transparent at two-photon resonance: the **transparency window**. Its width is $\approx\Omega_c^2/\gamma$ for $\Omega_c\lesssim\gamma$. For $\Omega_c\gg\gamma$ the line splits into two peaks at $\Delta=\pm\Omega_c/2$, the Autler–Townes doublet of the dressed states.
- **Real part.** Inside the window $\mathrm{Re}\,\chi$ varies steeply and linearly, $\chi\approx\frac{Nd^2}{\epsilon_0\hbar}\frac{4\Delta}{\Omega_c^2}$, with zero absorption. This gives slow light (below).

**Interactive plot.** $\mathrm{Im}\,\chi$ and $\mathrm{Re}\,\chi$ against probe detuning, in units where the bare resonant absorption is 1. Increase $\Omega_c$ to go from EIT to Autler–Townes, and increase $\gamma_s$ to see the window fill in. Detune the coupling field, $\Delta_c\gg\gamma$, to get the far-detuned (Raman) case: a narrow resonance near $\Delta=\Delta_c$, shifted by the light shift.

```dataviewjs
// ===== CONFIG =====
const CFG = { Oc: 1.0, OcMax: 6, gs: 0.0, gsMax: 0.3, Dc: 0, DcMax: 15 };   // all in units of γ
// ==================
// ---- loader (leave as is) ----
const LIB = "FUW/lib/";
const load = (src) => new Promise((ok, no) => { const s = document.createElement("script"); s.src = src; s.onload = ok; s.onerror = () => no(new Error("could not load " + src)); document.head.append(s); });
const libPath = async (n) => { const here = dv.current().file.folder, up = here.includes("/") ? here.slice(0, here.lastIndexOf("/")) + "/" : ""; for (const p of [LIB + n, "lib/" + n, here + "/lib/" + n, up + "lib/" + n, ...app.vault.getFiles().filter((x) => x.path.endsWith("lib/" + n)).map((x) => x.path)]) if (await app.vault.adapter.exists(p)) return p; throw new Error("lib/" + n + " not found in this vault (is the lib folder synced to this computer?)"); };
if (!window.JXG) await (window.__jxg ??= libPath("jsxgraphcore.js").then((p) => load(app.vault.adapter.getResourcePath(p))).catch(() => load("https://cdn.jsdelivr.net/npm/jsxgraph@1.10.1/distrib/jsxgraphcore.js")).catch((e) => { window.__jxg = null; throw e; }));
if (!window.RL) await (window.__rl ??= libPath("rlti.js").then((p) => load(app.vault.adapter.getResourcePath(p))).catch((e) => { window.__rl = null; throw e; }));
const K = await RL.init(dv), { f, el, C } = K;
// ---- controls ----
const sO = K.slider("Ω_c / γ", 0, CFG.OcMax, 0.01, CFG.Oc), sG = K.slider("γ_s / γ", 0, CFG.gsMax, 0.001, CFG.gs, (v) => (+v).toFixed(3));
const sC = K.slider("Δ_c / γ (coupling detuning)", -CFG.DcMax, CFG.DcMax, 0.1, CFG.Dc, (v) => (+v).toFixed(1));
const cb2 = K.check("two-level reference (Ω_c = 0)");
const box = "background:#fff;border:1px solid #e5e7eb;border-radius:10px", H = Math.round(K.W * 0.42);
const dI = el("div", `width:${K.W}px;height:${H}px;${box};touch-action:none;margin-top:6px`);
const dR = el("div", `width:${K.W}px;height:${H}px;${box};touch-action:none;margin-top:10px`);
const panel = el("div", "font-family:var(--font-monospace,monospace);font-size:0.8em;line-height:1.55;white-space:pre-wrap;color:var(--text-normal);margin-top:6px");
K.root.append(dI, dR, panel);
const ax = (n, pos, off) => ({ name: n, withLabel: true, strokeColor: "#9ca3af", label: { position: pos, offset: off, fontSize: 14, strokeColor: C.ink }, ticks: { minorTicks: 0, strokeColor: "#9ca3af", label: { fontSize: 10, strokeColor: C.muted } } });
const mk = (div, yn) => JXG.JSXGraph.initBoard(div, { boundingbox: [-6, 1.1, 6, -0.1], keepAspectRatio: false, axis: true, showCopyright: false, showNavigation: false, pan: { enabled: false }, zoom: { enabled: false }, defaultAxes: { x: ax("Δ / γ", "rt", [-14, 14]), y: ax(yn, "rt", [8, -6]) } });
const bI = mk(dI, "Im χ (absorption)"), bR = mk(dR, "Re χ (dispersion)");
// χ(Δ) in units of N d²/(ε₀ħ)·(2/γ):  χ = −(γ/2) / (Δ + iγ/2 − (Ω_c²/4)/(δ + iγ_s/2)),  δ = Δ − Δ_c,  γ = 1
const cdiv = (a, b) => { const d = b[0] * b[0] + b[1] * b[1]; return [(a[0] * b[0] + a[1] * b[1]) / d, (a[1] * b[0] - a[0] * b[1]) / d]; };
function chi(D, Oc) { const g = 1, gs = Math.max(+sG.value, 1e-7), dl = D - +sC.value;
  const t = cdiv([Oc * Oc / 4, 0], [dl, gs / 2]), den = [D - t[0], g / 2 - t[1]];
  const c = cdiv([-g / 2, 0], den); return c; }
const opt = (c, w, dash = 0, vis) => ({ fixed: true, highlight: false, strokeColor: c, strokeWidth: w, dash, numberPointsHigh: 3000, numberPointsLow: 1200, ...(vis ? { visible: vis } : {}) });
for (const [b, k] of [[bI, 1], [bR, 0]]) {
  b.create("functiongraph", [(D) => chi(D, 0)[k], -60, 60], opt(C.muted, 1.2, 2, () => cb2.checked));
  b.create("functiongraph", [(D) => chi(D, +sO.value)[k], -60, 60], opt(k ? C.obs : C.sel, 2.2));
  b.create("line", [[0, 0], [0, 1]], opt(C.faint, 0.8, 1));
}
function update() {
  const Oc = +sO.value, gs = +sG.value, Dc = +sC.value, R = Math.max(5, Math.abs(Dc) + 3, Oc + 2);
  let mI = 0.2, mR = 0.2; for (let i = 0; i <= 3000; i++) { const D = -R + (2 * R * i) / 3000, c = chi(D, Oc); mI = Math.max(mI, c[1]); mR = Math.max(mR, Math.abs(c[0])); }
  if (cb2.checked) { mI = Math.max(mI, 1); mR = Math.max(mR, 0.5); }
  bI.setBoundingBox([-R, mI * 1.15, R, -0.08 * mI], false); bR.setBoundingBox([-R, mR * 1.2, R, -mR * 1.2], false); bI.update(); bR.update();
  const c0 = chi(Dc, Oc), h = 1e-4, slope = (chi(Dc + h, Oc)[0] - chi(Dc - h, Oc)[0]) / (2 * h);
  panel.textContent =
`χ in units of N d²/(ε₀ħ)·(2/γ): the bare resonant absorption is Im χ = 1 (dashed).   Probe scanned, δ = Δ − Δ_c.
at two-photon resonance (Δ = Δ_c = ${f(Dc)} γ):  Im χ = ${f(c0[1])}   dRe χ/dΔ = ${f(slope)} /γ  ${slope > 0 ? "(normal dispersion → slow light)" : ""}
${Math.abs(Dc) < 1 ? (Oc <= 1 ? `EIT: window width ≈ Ω_c²/γ = ${f(Oc * Oc)} γ;  slope ≈ 2γ/Ω_c² = ${Oc > 0 ? f(2 / (Oc * Oc)) : "∞"} /γ (γ_s = 0)` : `Autler–Townes: absorption peaks near Δ ≈ ±Ω_c/2 = ±${f(Oc / 2)} γ`) : `far-detuned coupling: narrow Raman feature near Δ ≈ Δ_c + light shift Ω_c²/(4Δ_c) = ${f(Dc + Oc * Oc / (4 * Dc))} γ`}${gs > 0 ? `   — ground dephasing γ_s fills the window (needs Ω_c²/γ ≫ γ_s)` : ""}`;
}
for (const s of [sO, sG, sC]) s.addEventListener("input", update);
cb2.onchange = update;
update();
```

### Slow light

The wave number in the medium is $k=n(\omega)\,\omega/c$, so

$$v_g = \frac{d \omega }{dk}=\frac{c}{n_g}, \qquad n_g=n+ \omega \frac{d n}{d \omega}.$$

Inside the window $n\approx1$, but $dn/d\omega=dn/d\Delta=\frac12\,d\chi/d\Delta$ is huge:

$$n_g \approx \omega \frac{dn}{d \Delta} = \frac{\omega}{2}\, \frac{N d^2}{\epsilon_0 \hbar}\, \frac{4}{\Omega_c^2}
\quad\Rightarrow\quad
v_g =\frac{c}{n_g}= \frac{\Omega_c^2}{ \alpha_0 \gamma},$$

using $\frac{\omega Nd^2}{\epsilon_0\hbar}=\frac{\alpha_0c\gamma}{2}$. This requires the window to be wider than the ground-state decoherence, $\Omega_c^2/\gamma\gg\gamma_s$.

With the **optical depth** $\mathrm{OD}=\alpha_0 L$ (transmission $e^{-\mathrm{OD}}$ without the coupling field) and typical alkali-vapour numbers,

$$\frac{\gamma}{2 \pi} =6\ \text{MHz}, \quad \frac{\Omega_c}{2\pi} = 3\ \text{MHz}, \quad \mathrm{OD}=50,\quad L=1\ \text{cm}
\quad\Rightarrow\quad
v_g = \frac{\Omega_c^2L}{\mathrm{OD}\,\gamma}\approx 2\ \text{km/s},$$

a reduction of $c$ by a factor of $\sim10^5$. The pulse delay is $\tau=L/v_g=\mathrm{OD}\,\gamma/\Omega_c^2\approx5\ \mu$s. Switching $\Omega_c$ off while the pulse is inside the medium stores it in the $g$–$s$ coherence (EIT quantum memory).

### Far detuned: Raman transitions

For $|\Delta|\gg\gamma,\Omega_p,\Omega_c$ the excited state is hardly populated and follows the ground states adiabatically. Set $\dot c_e\approx0$ in $i\dot c_e=-\Delta c_e-\frac{\Omega_p}{2}c_g-\frac{\Omega_c}{2}c_s$:

$$c_e\approx-\frac{\Omega_pc_g+\Omega_cc_s}{2\Delta}.$$

Inserting this into the equations for $c_g,c_s$ eliminates $\ket e$ and leaves an **effective two-level atom** $\{\ket g,\ket s\}$, in the same convention $i\partial_t\mathbf c=-H\mathbf c$ as before:

$$i\partial_t\begin{pmatrix}c_g\\c_s\end{pmatrix}=-\hat H_{\rm eff}\begin{pmatrix}c_g\\c_s\end{pmatrix}, \qquad
\hat H_{\rm eff}= -\begin{pmatrix} \dfrac{\Omega_p^2}{4\Delta} & \dfrac{\Omega_R}{2} \\[2mm] \dfrac{\Omega_R}{2} & \dfrac{\Omega_c^2}{4\Delta}-\delta \end{pmatrix}, \qquad
\Omega_R=\frac{\Omega_p \Omega_c}{2 \Delta} .$$

The diagonal terms are the light shifts of $\ket g$ and $\ket s$. The off-diagonal **Raman Rabi frequency** $\Omega_R$ drives $g\leftrightarrow s$ through a virtual excited state. The Raman resonance sits at $\delta=(\Omega_c^2-\Omega_p^2)/4\Delta$, and spontaneous emission is suppressed by $\gamma/\Delta$.

---
[[QO - Lecture 12|← Previous: Lecture 12]] · 
