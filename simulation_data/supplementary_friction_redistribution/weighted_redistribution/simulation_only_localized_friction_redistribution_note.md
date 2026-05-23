# Simulation-only localized friction bottleneck and command-level redistribution

This chapter reports simulation-only results. The friction coefficients and local contact weights are used for sensitivity and robustness analysis, not as experimentally identified physical parameters.

## Method

The scan fixes the same command baseline and evaluates weighted nullspace command redistribution for the section-1 / drive-3/9 friction bottleneck. The optimized variables are `RedistributionGain`, `OverTransferWeight`, `RecipientFinalForceWeight`, `MaxBias`, and `NoIncreaseWeight`.

Section-1 contact is represented with disk-level normal allocation, guide-hole offset bias for drives 3/9, spacer contact bias hooks, and controlled recipient drives D6/2/5/8. A global contact solver is intentionally deferred.

## Scan settings

- Candidate label: balanced_pareto
- mu: 0.1200
- Scan NShape / CommandStride: 21 / 12
- High-order NShape / CommandStride: 31 / 1

## Pareto scan summary

| label | gain | overW | recW | max bias (um) | noIncW | max error (mm) | D3+D9 | D3 | D9 | recipients | force sat | qddot | endpoint jerk | leakage |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| fixed_source | 0.000 | 0.000 | 0.000 | 0.000 | 0.000 | 0.648336 | 0.649277 | 0.361806 | 0.287471 | 0.082304 | 0.015576 | 20102.965 | 281818.104 | 0.000e+00 |
| conservative | 0.300 | 2.000 | 0.150 | 20.000 | 2.000 | 0.648340 | 0.645784 | 0.389277 | 0.256508 | 0.081979 | 0.052960 | 20103.015 | 281818.104 | 7.638e-19 |
| low_error_guard | 0.450 | 4.000 | 0.120 | 30.000 | 5.000 | 0.648340 | 0.628001 | 0.410112 | 0.217890 | 0.087709 | 0.093458 | 20103.015 | 281818.104 | 1.913e-18 |
| balanced | 0.600 | 3.000 | 0.120 | 40.000 | 3.000 | 0.678741 | 0.626936 | 0.420575 | 0.206361 | 0.089485 | 0.109034 | 20103.015 | 281818.104 | 2.747e-18 |
| d9_guard | 0.800 | 5.000 | 0.080 | 60.000 | 5.000 | 0.798298 | 0.632760 | 0.459108 | 0.173652 | 0.094564 | 0.174455 | 20103.015 | 281818.104 | 5.947e-18 |
| wide_transfer | 0.900 | 3.000 | 0.050 | 80.000 | 2.000 | 0.788523 | 0.631956 | 0.455559 | 0.176397 | 0.093999 | 0.165109 | 20102.998 | 281818.104 | 3.802e-18 |
| aggressive | 1.100 | 4.000 | 0.080 | 80.000 | 4.000 | 0.904882 | 0.633195 | 0.469128 | 0.164067 | 0.102032 | 0.211838 | 20103.015 | 281818.104 | 5.761e-18 |

## Selected representatives

| role | label | max error (mm) | D3+D9 | D3 | D9 | recipients |
|---|---|---:|---:|---:|---:|---:|
| lowest_d3d9_share | balanced | 0.678741 | 0.626936 | 0.420575 | 0.206361 | 0.089485 |
| lowest_tracking_error | conservative | 0.648340 | 0.645784 | 0.389277 | 0.256508 | 0.081979 |
| balanced_pareto | low_error_guard | 0.648340 | 0.628001 | 0.410112 | 0.217890 | 0.087709 |

## High-order verification

| stage | label | max error (mm) | D3+D9 | D3 | D9 | force sat | qddot | endpoint jerk | constraints |
|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| high_order | fixed_source | 0.634316 | 0.860072 | 0.518106 | 0.341966 | 0.032328 | 21489.394 | 464757.780 | 0 |
| high_order | balanced | 0.634317 | 0.901943 | 0.699130 | 0.202813 | 0.195043 | 21489.377 | 464757.780 | 0 |
| high_order | conservative | 0.634316 | 0.886831 | 0.622749 | 0.264082 | 0.114224 | 21489.366 | 464757.780 | 0 |
| high_order | low_error_guard | 0.634316 | 0.900339 | 0.685887 | 0.214452 | 0.178879 | 21489.366 | 464757.780 | 0 |

## Limitation

All results are numerical simulations. No experimental friction identification is claimed. The current local contact model is intended to prioritize the section-1 friction bottleneck before introducing friction/contact/load complexity.
