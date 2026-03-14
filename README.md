<div align="center">

```
▸  M A T H E M A T I C A L   D E S C E N T  ◂
```

# Impossible Geometry
### *Three structures that shouldn't exist — but do*

> *"Somewhere between a proof and a hallucination,  
> mathematics hides the most violent beauty  
> the universe has ever produced."*

<br>

[![Kaggle](https://img.shields.io/badge/View%20on-Kaggle-20BEFF?style=for-the-badge&logo=kaggle&logoColor=white)](https://www.kaggle.com/code/nachikettalekar/mathematical-descent-chaos-primes-4d-space)
[![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://python.org)
[![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)](https://numpy.org)
[![Matplotlib](https://img.shields.io/badge/Matplotlib-11557c?style=for-the-badge&logo=python&logoColor=white)](https://matplotlib.org)

<br>

</div>

---

## ◈ What Is This?

A **visual deep-dive into four mathematical structures** that emerge from deceptively simple equations. No machine learning. No datasets. No shortcuts.

Just pure mathematics doing impossible things — rendered with PDE simulations, density renders, Fourier analysis, and a live rotating 4D animation. Each section explains exactly what is happening mathematically, not just what it looks like.

Every structure in this repo was generated from equations small enough to fit on a single line. The complexity you see was not added. It was **unavoidable**.

---

## ⬡ Repository Structure

The notebook is split into five files to keep each one lightweight and GitHub-renderable:

```
impossible-geometry/
│
├── README.md
│
├── 00_impossible_geometry_index.ipynb     ← Start here — animated header + series overview
├── 01_gray_scott_reaction_diffusion.ipynb ← § 01  Turing instability & biological patterning
├── 02_clifford_attractor.ipynb            ← § 02  Strange attractors & flame fractal rendering
├── 03_ulam_prime_spiral.ipynb             ← § 03  Prime diagonals & the open Bateman-Horn conjecture
└── 04_tesseract_4d.ipynb                  ← § 04  4D hypercube with dual-perspective animation
```

> **Why split?** The tesseract section generates a jshtml animation that inflates a single file beyond GitHub's 25 MB render limit. Each file here is **16–25 KB** before execution.

---

## ◈ The Four Sections

### `§ 01` — Gray-Scott Reaction-Diffusion  `🟢`

**Two chemicals. Two equations. Every pattern in nature.**

```
∂U/∂t = Dᵤ∇²U − UV² + f(1 − U)
∂V/∂t = Dᵥ∇²V + UV² − (f + k)V
```

In 1952, Alan Turing proved that if an activator spreads *slower* than its inhibitor, a uniform state becomes unstable and spontaneously breaks into structured patterns. This is **Turing instability** — the mathematical mechanism behind:

- Leopard spots and cheetah stripes
- Zebrafish pigmentation
- Fingerprint whorls
- Coral branching geometry
- Hair follicle spacing

The notebook simulates 8,000 time steps and captures the pattern evolving from random seeds. A second plot runs the same equations four times with different `(f, k)` pairs, producing spots, coral, worm tunnels, and mitosis-like blobs — from **identical physics**.

---

### `§ 02` — Clifford Strange Attractor  `🟣`

**Four numbers. Six million steps. Zero randomness.**

```
xₙ₊₁ = sin(a · yₙ) + c · cos(a · xₙ)
yₙ₊₁ = sin(b · xₙ) + d · cos(b · yₙ)
```

Take a point. Apply the rule. Record where it lands. Repeat six million times without adding a single random number. The result looks hand-drawn and organic. It is neither.

The point is trapped in a bounded region — the **attractor set** — from which it can never escape. Within it, the orbit never settles, never repeats exactly, and never stops. The attractor has **fractal geometry** with a Hausdorff dimension of ~1.6 — not a whole number, between a curve (1D) and a filled region (2D).

Rendered using **flame fractal density rendering**: a log-scale 2D histogram that maps visit frequency to brightness, revealing the ghostly skeleton the orbit obsessively re-traces.

| Parameter Set | Label | Character |
|---|---|---|
| `a=-1.7 b=1.3 c=-0.1 d=-1.21` | Folded ribbon | Bilateral near-symmetry, dense bright ridges |
| `a=-1.4 b=-1.3 c=-1.5 d=-1.3` | Branching tree | Orbit fans from central trunk into filaments |
| `a=1.5 b=-1.8 c=1.6 d=0.9` | Collapsed spiral | Dense core, sparse looping arms |

---

### `§ 03` — Ulam Prime Spiral  `🟡`

**Primes hiding in diagonals. Discovered by accident in 1963. Still not fully explained.**

In 1963, Stanisław Ulam was bored in a meeting. He doodled integers in a clockwise spiral and circled the primes. He ran it on a Los Alamos computer. The primes were lining up along diagonals.

**Why it happens:** Every diagonal in the spiral corresponds exactly to a quadratic polynomial `an² + bn + c`. If that polynomial generates prime-dense output, its diagonal lights up. Euler's famous example:

```
n² − n + 41   is prime for every n from 0 to 40
n = 41 :  41 × 41 = 1681   ✗   (the streak finally breaks)
```

The **2D Fourier Transform** of the prime grid reveals sharp off-axis spikes at the diagonal angles. Random primes would give a featureless uniform disk. The spikes mathematically prove the structure is a genuine arithmetical periodicity — not an optical illusion.

The **Bateman-Horn conjecture** quantifies prime density of polynomials but has never been proved. The **Riemann Hypothesis**, after 166 years, still waits.

---

### `§ 04` — 4D Tesseract — Animated  `🔵`

**A hypercube rotating simultaneously in two 4D planes.**

Building up dimension by dimension:

| Dim | Name | Vertices | Edges | Faces | 3-Cells |
|-----|------|----------|-------|-------|---------|
| 1D | Line segment | 2 | 1 | — | — |
| 2D | Square | 4 | 4 | 1 | — |
| 3D | Cube | 8 | 12 | 6 | 1 |
| **4D** | **Tesseract** | **16** | **32** | **24** | **8 full cubes** |

In 4D space there are **six independent rotation planes**: XY, XZ, XW, YZ, YW, ZW. The animation applies two simultaneously at incommensurable speeds:

```
R₁ : XW-plane at angular rate t
R₂ : YZ-plane at angular rate 1.3t
R  = R₂ · R₁   applied to all 16 vertices per frame
```

Projection is done in two stages: (1) **4D perspective divide** on the W axis collapses 4D → 3D, producing the inner/outer cube depth effect. (2) **Orthographic drop of Z** collapses 3D → 2D for display.

The inner cube "popping through" the outer is not a rendering glitch. In 4D, those cubic cells connect in a way that has no 3D analogue. As different cells rotate to the front of the W axis, their projected sizes exchange — in 4D space it is completely smooth and non-self-intersecting.

> The confusion you feel watching it is geometrically accurate. Your brain evolved to parse 3D scenes. That oscillating sense of impossible topology is exactly what a 4D rotation looks like from inside a 3D brain.

---

## ⬡ Three Profound Truths

```
01  Simple rules produce infinite complexity.
    Chaos is not the absence of order —
    it is order we cannot compress.

02  The universe has at least 4 dimensions.
    Every object you have ever seen
    is a shadow of something higher.

03  Primes are not random.
    They obey a law no human has proved.
    The Riemann Hypothesis still waits.
```

---

## ◈ Running Locally

**Requirements**

```bash
pip install numpy matplotlib ipython
```

All notebooks are self-contained. No external datasets.

**Estimated runtimes per section**

| Notebook | What runs | Time |
|----------|-----------|------|
| `01_gray_scott` | 8,000-step PDE simulation × 5 configs | ~60 s |
| `02_clifford` | 6M-iteration attractor × 3 param sets | ~3–5 min |
| `03_ulam` | Sieve of 361,201 integers + FFT | ~15 s |
| `04_tesseract` | 90-frame animation render | ~10 s |

**Run in the cloud — no setup needed**

[![Kaggle](https://img.shields.io/badge/Open%20on-Kaggle-20BEFF?style=flat-square&logo=kaggle&logoColor=white)](https://www.kaggle.com/code/nachikettalekar/mathematical-descent-chaos-primes-4d-space)

---

## ⬡ Design Notes

All visual cells use `display(HTML(...))` in code cells with `"source_hidden": true` metadata — so the HTML, animations, and CSS actually execute and render in Kaggle/JupyterLab, while remaining invisible to the reader. Only the four computation cells are visible.

- **Fonts:** [Orbitron](https://fonts.google.com/specimen/Orbitron) · [Share Tech Mono](https://fonts.google.com/specimen/Share+Tech+Mono) · [Bebas Neue](https://fonts.google.com/specimen/Bebas+Neue)
- **Colourmap:** custom per-section, built with `LinearSegmentedColormap`
- **Animation:** `matplotlib.animation.FuncAnimation` → `to_jshtml()` for in-notebook playback

---

## ◈ Tags

`mathematics` · `visualization` · `animation` · `fractal` · `chaos-theory` · `number-theory` · `simulation` · `numpy` · `matplotlib` · `reaction-diffusion` · `4d-geometry` · `prime-numbers` · `generative-art` · `educational` · `turing-instability` · `strange-attractor`

---

<div align="center">

<br>

```
▸  end of descent  ◂
```

*Made with NumPy, Matplotlib, and an unreasonable amount of mathematical curiosity.*

</div>
