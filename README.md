# Pivotal Trial Predictions — AI Scientist

Pre-registered, timestamped predictions for 20 upcoming Phase 3 pivotal clinical trial readouts (Apr–Aug 2026).

## Method
Each trial is evaluated independently by the **AI Scientist** (Claude Opus 4.6 + /bayesian-eval-trial skill) using a Bayesian hierarchical framework. Three replicate campaigns (V1, V2, V3) are run for stability assessment.

## Prediction Format
Each `predictions/<trial>.json` file contains:
- **Raw Bayesian posterior** — uncorrected sequential posterior
- **Correlation-corrected (pre-review)** — model's own estimate after dampening correlated observations
- **Final** — after external reviewer reconciliation
- **Trading signal** — Ensemble V1+V2+V3 CorrC at 50% threshold → LONG or SHORT

## Integrity
- Every prediction is a **GPG-signed git commit** (key: `CD3A1DEF2DEB1BCC`)
- Each commit hash is **Bitcoin-timestamped** via [OpenTimestamps](https://opentimestamps.org/)
- OTS proofs (`.ots` files) are committed back to the repo
- Predictions are made **before** trial readout announcements
- Anyone can verify with `ots verify ots_proofs/TRIAL.ots` that these predictions were timestamped on April 16, 2026 — before any of the trial readouts.

## Trials
| # | Trial | NCT | Drug | Company | Ticker | Expected Readout |
|---|-------|-----|------|---------|--------|-----------------|
| 1 | REGAL | NCT04229979 | Galinpepimut-S | Sellas Life Sciences | SLS | Imminent |
| 2 | TRAILRUNNER-ALZ 1 | NCT05463731 | Remternetug | Eli Lilly | LLY | Apr-May 2026 |
| 3 | AFFINITY DUCHENNE | NCT05693142 | RGX-202 | REGENXBIO | RGNX | Apr-May 2026 |
| 4 | REMODEL 1 | NCT05147220 | Remibrutinib | Novartis | NVS | May-Jun 2026 |
| 5 | REMODEL 2 | NCT05156281 | Remibrutinib | Novartis | NVS | May-Jun 2026 |
| 6 | POLARIS-AD | NCT05531526 | Mirodenafil | AriBio | ARIO | May 2026 |
| 7 | CARDIO-TTRansform | NCT06194825 | Eplontersen | AstraZeneca/Ionis | AZN | May 2026 |
| 8 | Lumateperone MDD | NCT06462612 | Lumateperone | Intra-Cellular | ITCI | May 2026 |
| 9 | MUIR | NCT06347133 | Plozasiran | Arrowhead | ARWR | May 2026 |
| 10 | BHV-7000 Epilepsy | NCT06309966 | BHV-7000 | Biohaven | BHVN | May 2026 |
| 11 | Voyage | NCT06741228 | MM120 (DT120) | Definium | DFTX | May 2026 |
| 12 | Lp(a)HORIZON | NCT04023552 | Pelacarsen | Novartis/Ionis | NVS/IONS | H1 2026 |
| 13 | REVEAL-2 | NCT06625398 | Elegrobart | Viridian | VRDN | Q2 2026 |
| 14 | Harmony Melanoma | NCT05352672 | Fianlimab+Cemiplimab | Regeneron | REGN | H1 2026 |
| 15 | PALISADE-4 | NCT06615557 | Fasedienol | Vistagen | VTGN | H1 2026 |
| 16 | DIAMOND-1 | NCT05066997 | OCS-01 | Oculis | OCS | Jun 2026 |
| 17 | DIAMOND-2 | NCT06172257 | OCS-01 | Oculis | OCS | Jun 2026 |
| 18 | ABTECT Maintenance | NCT05535946 | Obefazimod | Abivax | ABVX | Jun 2026 |
| 19 | XPORT-EC-042 | NCT05611931 | Selinexor | Karyopharm | KPTI | Mid-2026 |
| 20 | PIVOT-006 | NCT06111235 | Cretostimogene | CG Oncology | CGON | Jun 2026 |

## Public Key
```
$(cat signing_key.pub)
```
