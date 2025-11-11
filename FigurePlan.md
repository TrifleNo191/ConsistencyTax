# Figure and Experiment Plan

Each figure is designed to be self-contained, symbol-consistent, and directly tied to a testable or explanatory claim of the Consistency Tax (CT) framework.

---

## Figure 1 — Consistency Tax Schematic

**Purpose**  
Visualize the core objects and the definition of CT.

**Content**  
- Nodes: \(W\) (world), \(M\) (model), \(S\) (signals/actions), \(G\) (goals).
- Arrows showing causal/informational relationships.
- Overlay: actual joint \(P(W,M,S,G)\) vs coherent reference \(P^\*(W,M,S,G)\).
- CT indicated as \(\kT \, \KL(P\Vert P^\*)\).

**Generation Method**  
- Drawn with TikZ (no external data).
- Caption must restate: “CT is defined as \(k_B T \ln 2 \cdot \KL(P\Vert P^\*)\) over \((W,M,S,G)\) under shared constraints.”

**TikZ Stub**
```tex
\begin{tikzpicture}[>=stealth, node distance=2.6cm]
\node (W) [draw, circle] {$W$};
\node (M) [draw, circle, right of=W] {$M$};
\node (S) [draw, circle, right of=M] {$S$};
\node (G) [draw, circle, below of=M] {$G$};
\draw[->] (W) -- (M);
\draw[->] (M) -- (S);
\draw[->] (G) -- (M);
\draw[->] (G) -- (S);
\node[below=1.4cm of G, align=center] (label)
  {$\mathrm{CT} = k_B T \ln 2 \cdot \KL(P(W,M,S,G)\Vert P^\*(W,M,S,G))$};
\end{tikzpicture}
Figure 2 — Three-Term Decomposition Diagram
Purpose
Explain how CT can be operationally decomposed into:

model–world mismatch (CT
1
1
​
 ),

model–signal mismatch (CT
2
2
​
 ),

erasure overhead (CT
3
3
​
 ).

Content

Blocks for Environment 
𝑃
P, Model 
𝑄
Q, Signals 
𝑅
R.

Arcs labeled 
\KL
(
𝑃
∥
𝑄
)
\KL(P∥Q), 
\KL
(
𝑄
∥
𝑅
)
\KL(Q∥R), and 
𝑟
erase
r 
erase
​
 .

Text: “Template inequality: 
\ct
(
𝑡
)
≥
\kT
[
𝜆
1
\KL
(
𝑃
∥
𝑄
)
+
𝜆
2
\KL
(
𝑄
∥
𝑅
)
+
𝑟
erase
]
\ct(t)≥\kT[λ 
1
​
 \KL(P∥Q)+λ 
2
​
 \KL(Q∥R)+r 
erase
​
 ].”

Generation Method

TikZ block diagram.

No empirical data.

Figure 3 — Toy POMDP: Bias vs Consistency Tax
Purpose
Show that belief bias in a simple environment produces a U-shaped CT curve:
CT minimal at unbiased belief; grows with 
∣
bias
∣
∣bias∣.

Data Source

Generated from toy POMDP simulation defined in Supplement.tex.

CSV: ct_pomdp_results.csv with columns bias, ct.

Generation Method

Use pgfplots to plot bias (x-axis) vs ct (y-axis).

Include axis labels, grid, and units (nats or bits).

Stub

tex
Copy code
\begin{tikzpicture}
\begin{axis}[
  xlabel={Bias parameter},
  ylabel={CT (nats)},
  grid=both
]
\addplot table [x=bias, y=ct, col sep=comma]{ct_pomdp_results.csv};
\end{axis}
\end{tikzpicture}
Caption must state simulation details and that this is a toy illustration.

Figure 4 — LLM Token/Energy Overhead: Truth vs Constrained False
Purpose
Empirically test CT
2
2
​
  in language models.

Content

Bars (or points) for:

Simple factual Q/A,

Math tasks,

Logic tasks.

For each: relative overhead (%) in tokens and/or energy between truthful and constrained-false outputs.

Data Source

Results from LLM CTI benchmark:

Same model and decoding settings,

Logged latency/energy/tokens.

Generation Method

pgfplots bar chart using a CSV produced by experiments.

Caption must specify model, hardware, and that data are architecture-specific.

Figure 5 — Rarity Bound: Minimum Overhead vs Probability
Purpose
Visualize theoretical lower bound:
overhead
min
⁡
=
log
⁡
2
(
1
/
𝑝
)
overhead 
min
​
 =log 
2
​
 (1/p) bits for enforcing rare signals.

Content

Log-scale x-axis: probability 
𝑝
p of the constrained outcome.

y-axis: 
log
⁡
2
(
1
/
𝑝
)
log 
2
​
 (1/p).

Generation Method

Analytic curve via pgfplots.

Stub

tex
Copy code
\begin{tikzpicture}
\begin{axis}[
  xmode=log,
  xmin=1e-8, xmax=1e-1,
  xlabel={$p$ (probability of constrained signal)},
  ylabel={Minimum overhead (bits)},
  grid=both
]
\addplot[domain=1e-8:1e-1,samples=200]{ln(1/x)/ln(2)};
\end{axis}
\end{tikzpicture}
Figure 6 — Coherence vs Deception Regime Diagram
Purpose
Summarize when coherence vs deception is favoured.

Content

Axes:

x-axis: feedback strength / surveillance,

y-axis: benefit of deception relative to CT cost.

Regions:

“Coherence favoured” (high feedback, moderate benefit),

“Deception viable” (low feedback, high benefit),

“Underdetermined / architecture-dependent”.

Generation Method

Schematic via TikZ; no data.

Caption connects regions to predicted evolutionary/game-theoretic outcomes.

Figure 7 — Cross-Domain Instantiations Table
Purpose
Show how the same CT formalism applies across domains.

Content
Columns:

Domain,

𝑊
W,

𝑀
M,

𝑆
S,

𝐺
G,

CT components measured (CT
1
1
​
 , CT
2
2
​
 , CT
3
3
​
 ),

Example experiment.

Generation Method

LaTeX table with booktabs.

Entries based on designs in MainPaper/Supplement.

Figure 8 — CTI / CT_Q Measurement Pipeline
Purpose
Explain how to estimate CT-like quantities from empirical logs.

Content

Flow:
prompts/environment → system → logs (tokens, energy, etc.) → cost estimator → CT_Q / CTI.

Notes on controlling for length and difficulty.

Generation Method

TikZ block diagram.

Used in Experiments section.

General Requirements
All figures:

Must define 
𝑊
,
𝑀
,
𝑆
,
𝐺
,
𝑃
,
𝑃
\*
,
𝑄
,
𝑅
,
𝜆
1
,
𝜆
2
,
𝑟
erase
W,M,S,G,P,P 
\*
 ,Q,R,λ 
1
​
 ,λ 
2
​
 ,r 
erase
​
  in caption or be referenced to the Glossary.

Use units on all axes (bits, nats, joules, seconds, percentage).

Avoid decorative elements that obscure quantitative meaning.

Reference data files or scripts where applicable.

Any figure based on hypothetical or toy data must say so explicitly in the caption.

makefile
Copy code
::contentReference[oaicite:0]{index=0}






