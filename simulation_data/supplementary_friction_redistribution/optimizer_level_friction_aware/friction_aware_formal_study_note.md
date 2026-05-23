# Simulation-only friction-aware constrained optimizer study

This study upgrades localized friction redistribution from a post-processing scan to an optimizer-level constrained command problem. It is simulation-only; friction and local contact parameters are used for sensitivity and robustness, not experimental identification.

## Settings

- Optimizer budget: 16 evaluations
- Optimizer NShape: 21
- High-order replay: NShape=31, CommandStride=1
- Friction coefficient: 0.1200

- Recipient uptake target weight/fraction: 2.0000 / 0.3500

- Recipient contact gain/bias: 1.6000 / 0.2000 N

## Representatives

| role | eval | max error (mm) | D3+D9 | D3 | D9 | recipient | barrier |
|---|---:|---:|---:|---:|---:|---:|---:|
| lowest_tracking_error | 1 | 0.613472 | 0.829446 | 0.602896 | 0.226549 | 0.095764 | 0.149564 |
| lowest_d3d9_share | 15 | 0.820316 | 0.811216 | 0.523560 | 0.287657 | 0.099701 | 0.000090 |
| balanced_friction_pareto | 14 | 0.639815 | 0.818474 | 0.531733 | 0.286741 | 0.098352 | 0.002716 |

## High-order comparison

| role | mode | max error (mm) | D3+D9 | D3 | D9 | recipient | force sat | qddot | endpoint jerk | leakage | failures |
|---|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| lowest_tracking_error | fixed_source | 0.602652 | 0.824897 | 0.497029 | 0.327868 | 0.115656 | 0.016043 | 35459.130 | 1133098.960 | 0.000e+00 | 0 |
| lowest_tracking_error | post_processing_redistribution | 0.602653 | 0.880306 | 0.698388 | 0.181918 | 0.079941 | 0.182888 | 35459.130 | 1133098.960 | 3.788e-18 | 0 |
| lowest_tracking_error | optimizer_level_redistribution | 0.602652 | 0.853927 | 0.629005 | 0.224922 | 0.096354 | 0.101604 | 35459.130 | 1133098.960 | 1.995e-18 | 0 |
| lowest_d3d9_share | fixed_source | 0.731359 | 0.819357 | 0.489531 | 0.329826 | 0.116801 | 0.012739 | 26920.751 | 923312.319 | 0.000e+00 | 0 |
| lowest_d3d9_share | post_processing_redistribution | 0.734865 | 0.876730 | 0.693466 | 0.183264 | 0.081977 | 0.198514 | 26920.751 | 923312.319 | 3.771e-18 | 0 |
| lowest_d3d9_share | optimizer_level_redistribution | 0.730942 | 0.835114 | 0.556572 | 0.278542 | 0.105853 | 0.057325 | 26920.751 | 923312.319 | 9.095e-19 | 0 |
| balanced_friction_pareto | fixed_source | 0.626956 | 0.822194 | 0.493705 | 0.328489 | 0.115711 | 0.014365 | 26920.632 | 497194.045 | 0.000e+00 | 0 |
| balanced_friction_pareto | post_processing_redistribution | 0.626956 | 0.876661 | 0.690400 | 0.186261 | 0.082084 | 0.188950 | 26920.625 | 497194.045 | 3.633e-18 | 0 |
| balanced_friction_pareto | optimizer_level_redistribution | 0.626956 | 0.833547 | 0.552303 | 0.281244 | 0.107340 | 0.043094 | 26920.625 | 497194.045 | 9.095e-19 | 0 |

## Interpretation boundary

The comparison uses the same command timing for each representative and contrasts fixed source, fixed-parameter post-processing redistribution, and optimizer-level redistribution. The goal is to test whether the optimizer-level friction barriers reduce the section-1 D3/D9 bottleneck without sacrificing tracking, actuator feasibility, acceleration, endpoint jerk, or nullspace consistency.
