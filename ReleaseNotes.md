# Consistency Tax — Release Notes

This repository packages the current best formulation of the **Consistency Tax (CT)** and **Epistemic Thermodynamics** program for community review.

## What’s Original

1. **Canonical CT definition**  
   - CT is defined as \( \mathrm{CT} = k_B T \ln 2 \cdot D_{KL}(P(W,M,S,G) \,\|\, P^\*(W,M,S,G)) \),  
     where \(P^\*\) is a coherent, cost-minimizing reference joint under the same constraints.
2. **Three-term operational inequality**  
   - A template bound decomposing CT into:
     - model–world mismatch,
     - model–signal distortion,
     - misalignment-attributable erasure rates.
3. **Cross-domain template**
   - A unified treatment of AI models, biological systems, human cognition, and organizations using the same CT object.
4. **Falsification and rejection protocol**
   - Explicit conditions under which CT should be considered trivial, unsupported, or wrong.
5. **CT-informed tooling**
   - CTI metrics, CT\_Q overhead measures, and the Formulate++ pipeline for low-CT scientific problem formulation.

## What’s Conjectural

- General tightness of the model–signal term (CT\_2) for arbitrary architectures.
- Quantitative thresholds (e.g. CT becoming selection-relevant at \(\sim 1\%\) of the energy budget).
- Aggregation laws for CT across hierarchical systems (neurons → brains → institutions).
- Strength and generality of “truth/coherence is typically cheaper” in complex strategic settings.

These are stated as **hypotheses** and tagged with confidence/evidence grades in the main paper.

## What’s Empirically Supported (Indirectly)

- Landauer’s bound and stochastic thermodynamics (foundational A-grade evidence).
- Qualitative costs of deception in humans and organizations (B–C grade).
- Toy simulations (POMDP, simple CT calculations) demonstrating plausible CT behaviour.

No strong domain-wide CT claim rests solely on these; they are consistency checks.

## How to Reproduce or Extend

1. Rebuild all toy results from `Supplement.tex` pseudocode (POMDP, ABMs, etc.).
2. Implement the LLM CTI benchmark with real power and latency measurements.
3. Design deception tasks and biological experiments following the specified protocols.
4. Construct organizational CT indices from real datasets.
5. Publish results regardless of outcome; negative findings are decisive evidence.

## Known Gaps

- Lack of real-world joule-level CT measurements.
- Incomplete proofs for CT\_2 and multi-scale composition.
- Limited treatment of adversarial or reflexive environments.

These are deliberately left visible so future work can target them directly.
