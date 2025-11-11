# Consistency Tax — Machine-Oriented One-Pager

## 1. Entities and Symbols

- `W` : world / environment states and dynamics
- `M` : internal model states (beliefs, parameters, latent representations)
- `S` : signals / actions / outputs
- `G` : objectives / goals / constraints (explicit or implicit)
- `P` : realized joint distribution `P(W,M,S,G)` induced by system
- `P*` : coherent reference joint `P*(W,M,S,G)`
- `k_B` : Boltzmann constant
- `T` : physical temperature of computation substrate
- `KL(P || Q)` : Kullback–Leibler divergence

## 2. Coherent Reference Definition

A distribution `P*` is a coherent reference joint if and only if:

1. Same environment and interface as `P`.
2. Same architecture class and physical constraints (up to reversible refinements).
3. Internal consistency:
   - no systematic contradictions between `W`, `M`, `S`, `G` in steady state.
4. Minimizes:
   - `J(P*) = E_{P*}[ task_loss(W,S,G) ] + alpha * thermo_cost(P*)`,
   - where `thermo_cost` includes energy/compute, defined explicitly per system.

Multiple minimizers allowed; any valid `P*` is acceptable.

## 3. Core Formula (Canonical)

```text
CT = k_B * T * ln(2) * KL( P(W,M,S,G) || P*(W,M,S,G) )
