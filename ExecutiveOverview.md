# Consistency Tax: Why the Physics of Coherence Might Matter

**Short version:**  
When a physical system keeps its story straight about the world, itself, and what it is trying to do, it can in principle run cheaper than one that constantly juggles contradictions. The **Consistency Tax (CT)** framework turns that idea into a quantitative, testable statement.

## What CT Is

Consider four elements:

- **W** – the world (what is actually happening),
- **M** – a system’s internal model,
- **S** – its signals or actions,
- **G** – its objectives or constraints.

Any real system induces a joint distribution \(P(W,M,S,G)\).
Now imagine the best version of that system that:

1. faces the same environment and hardware limits,
2. keeps \(W,M,S,G\) mutually consistent,
3. minimizes task loss plus energy/compute cost.

Call its joint distribution \(P^\*(W,M,S,G)\).

**Consistency Tax** is defined as

\[
\mathrm{CT} = k_B T \ln 2 \cdot D_{KL}\!\big(P \,\|\, P^\*\big),
\]

a Landauer-scaled Kullback–Leibler divergence.
It measures the *avoidable* energetic overhead of being incoherent relative to a realistic coherent baseline.

## Why It Matters

CT gives a common language for:

- **AI systems:** extra energy/latency when a model is forced to maintain false or inconsistent outputs.
- **Brains and behaviour:** additional effort required for sustained deception or self-contradiction.
- **Cells and microbes:** wasted work when signals misrepresent actual conditions.
- **Organizations:** costs of “reality vs dashboard vs press release” mismatches.

The framework is deliberately modest:
it adds no new physics.
It repackages known thermodynamic bounds to ask:
> If we accounted honestly for all the erasures, corrections, and bookkeeping caused by misalignment, would we see a systematic cost?

## What’s New

- A single CT formula over \(W,M,S,G\), with a principled coherent reference.
- A mechanistic three-term bound that separates:
  1. bad models,
  2. dishonest signalling,
  3. extra erasures.
- A cross-domain experimental program: language models, human tasks, microbes, organizations, and agent-based evolution.

## Testable Predictions

1. Constraining AI models to maintain false narratives increases energy/latency versus truthful baselines.
2. Sustained deception in humans has higher metabolic and response-time cost than matched truthful tasks.
3. Systems fed systematically conflicting signals (biological or institutional) waste more energy achieving the same outcomes.

If good experiments do **not** find these effects, or if misaligned systems can be made cheaper under full accounting, the CT framework should be revised or dropped.

## Takeaway

CT is a structured hypothesis about the cost of incoherence, not a slogan.
Its value depends entirely on whether the outlined tests show that keeping your story straight is, in fact, physically cheaper.
