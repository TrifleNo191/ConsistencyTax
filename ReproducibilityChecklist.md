# Reproducibility Checklist — Consistency Tax

This checklist summarizes what is needed to reproduce and test the CT framework.

## 1. Conceptual Assumptions

- Landauer’s principle and standard stochastic thermodynamics hold.
- The system’s task, architecture class, and environment are specified.
- CT counts **avoidable** misalignment costs relative to a coherent reference under those constraints.
- All CT estimates explicitly state:
  - which variables are used (W, M, S, G or P, Q, R),
  - how \(P^\*\) is constructed or approximated,
  - what costs are included/excluded.

## 2. Code and Environment

- Language: Python (3.10+).
- Recommended:
  - `numpy`, `scipy`, `pandas`, `matplotlib`.
- Randomness:
  - Set seeds explicitly for all simulations.
- Hardware:
  - For LLM experiments, log GPU/TPU model, driver, and power-measurement method.

## 3. Toy POMDP Simulation

**Inputs**

- Two-state environment; observation accuracy 0.9 (modifiable).
- Bias parameter grid for agent beliefs.

**Procedure**

1. Implement environment and optimal Bayesian posterior.
2. Implement biased posterior parameterized by bias \(b\).
3. Compute CT(b) = average \(\KL(P^\*(W|O)\,\|\,P_b(W|O))\).
4. Plot CT vs bias.

**Expected Output**

- U-shaped CT curve with minimum near \(b=0\).
- Values matching order-of-magnitude in provided table.

## 4. LLM CTI Benchmark

**Setup**

- Fixed model; fixed decoding settings.
- 1000+ factual/mathematical/logic prompts with ground-truth answers.

**Procedure**

1. Collect:
   - truthful answers,
   - constrained-false narratives satisfying prompt constraints.
2. Record, for each run:
   - tokens generated,
   - latency,
   - hardware energy (via counters),
   - log-likelihood if available.
3. Define CT\_Q = mean(cost\_false − cost\_truth).

**Acceptance Criteria**

- Report confidence intervals.
- Publish full prompt set and scripts.
- Treat “no significant difference” as a meaningful result.

## 5. Human Deception Task

- Register protocol; predefine hypotheses.
- Use matched task difficulty across truth/deception conditions.
- Collect RT, accuracy, physiological indices.
- Share anonymized data and analysis code.

## 6. Microbial Conflicting-Cue Experiment

- Specify strains, media, gradients, and measurement equipment.
- Record growth rate, motility metrics, ATP/oxygen usage.
- Publicly release raw and processed datasets.

## 7. Organizational CT Index

- Predefine indicators (policy–practice gaps, restatements, incidents).
- Document sources and transformations.
- Publish codebooks and scripts.

## 8. Reporting Standards

- Provide:
  - full parameter listings,
  - seeding strategy,
  - hardware summary,
  - exact formulae for CT estimates.
- Tag any unverifiable assumptions as such.
- Commit to publishing negative results.

This checklist is intentionally conservative: if a result depends on an unstated choice, it does not count as evidence for CT.
