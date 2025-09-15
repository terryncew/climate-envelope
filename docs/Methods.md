# Envelope Predictability (v0.1) — Methods

**Claim.** Climate envelopes (means/anomalies) are predictable even when weather paths are chaotic. We make that predictability operational with boundary-aware observables and a unified reliability score.

## Observables
- **κ (bend):** deviation from ensemble envelope (norm distance of member to ensemble mean/band).
- **χ (twist):** order sensitivity of assimilation/updates (spread across identical-data, permuted-order runs).
- **h (residue):** budget drift after a closed cycle (e.g., rolling energy/moisture imbalance).
- **D_topo (defect density):** rate of topology/continuity violations (spurious sources/sinks, non-closing loops).
- **Φ\*** (coherence): multi-model/ensemble agreement (e.g., normalized inverse spread or MI).
- **τ** (memory): slow-reservoir timescale (e.g., OHC/soil moisture index).

## Unified score
\[
\mathrm{ULT}_{\text{topo}}
=\frac{\bar{\Phi}^*\cdot\tau}
{(1+\bar{\kappa})^{\alpha}(1+\bar{\chi})^{\gamma}(1+\bar{\varepsilon})^{\beta}}
\cdot(1-\bar{R})\cdot(1-D_{\text{topo}})
\]
High Φ\*, long τ, low κ/χ/ε/D_topo ⇒ reliable envelope.

## Falsifiable hypotheses
H1 Envelope Law — Low κ + high Φ\*,τ ⇒ seasonal mean verifies.  
H2 Twist Predictor — χ spikes precede forecast busts even when κ is modest.  
H3 Residue Foreshock — rising h precedes regime shifts.  
H4 Defect Alarm — D_topo jumps warn of instability independent of κ.

## Receipts (machine-verifiable)
Each experiment emits `docs/receipt.latest.json`:
- `claim`, `because[]`, `but[]`, `so`
- `telem` (κ, χ, h, D_topo, Φ*, τ, ULT_topo), `thresholds`, `window`
- `verify` (schema version, signature)

**Boundary-first rule:** if budgets/topology fail, correct those before any statistical correction.

**Attribution (design principles):** boundaries→meaning; scaffolding over raw IQ; surprise needs new structure; receipts close the AI reality gap. (Source: Sir Terrynce’s Almanac.)
