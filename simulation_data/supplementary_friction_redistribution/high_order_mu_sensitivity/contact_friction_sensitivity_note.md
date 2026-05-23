# Simulation-only sliding contact/friction sensitivity

This study keeps the command-layer representatives fixed and enables the rod/guide sliding friction interface as a perturbation. It is not a re-optimization pass and it is not an experimental friction identification result.

- NShape: 31
- Normal preload: 0.200000 N
- Normal gain: 1.000000
- Max drive-space friction force: 12.000000 N

## Key table

| label | mu | max error (mm) | force sat. | max friction (N) | max normal (N) | endpoint jerk | constraints |
|---|---:|---:|---:|---:|---:|---:|---:|
| lowest_endpoint_jerk | 0.0800 | 0.621899 | 0.037393 | 4.138501 | 87.981145 | 452518.592 | 0 |
| lowest_endpoint_jerk | 0.1200 | 0.614647 | 0.039530 | 6.249544 | 88.132858 | 452518.592 | 0 |
| balanced_pareto | 0.0800 | 0.626580 | 0.031250 | 4.173446 | 87.982401 | 464757.780 | 0 |
| balanced_pareto | 0.1200 | 0.619148 | 0.031250 | 6.293623 | 88.148469 | 464757.780 | 0 |

## Interpretation

The purpose is to quantify whether the previously selected command representatives remain usable after adding a first-order rod sliding friction perturbation. A robust command should avoid a disproportionate increase in max error, force saturation, or endpoint jerk as `mu` increases.
