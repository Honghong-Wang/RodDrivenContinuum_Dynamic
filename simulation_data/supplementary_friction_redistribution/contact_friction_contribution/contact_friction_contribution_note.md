# Drive and section friction contribution analysis

This analysis reads the NShape=31 rod/guide sliding friction verification cases and decomposes the friction load by drive and by section. Section attribution is approximate: each drive friction magnitude is allocated according to the estimated section-level normal-load contribution.

## Drive 3 and drive 9 check

| case | drive | impulse (N s) | share | max friction (N) | max normal (N) |
|---|---:|---:|---:|---:|---:|
| lowest_endpoint_jerk_mu0_08 | 3 | 7.417128 | 0.400526 | 4.138501 | 74.469643 |
| lowest_endpoint_jerk_mu0_08 | 9 | 4.902862 | 0.264755 | 2.565698 | 61.841356 |
| lowest_endpoint_jerk_mu0_12 | 3 | 11.032367 | 0.403504 | 6.249544 | 74.656547 |
| lowest_endpoint_jerk_mu0_12 | 9 | 7.297657 | 0.266908 | 3.889345 | 62.032831 |
| balanced_pareto_mu0_08 | 3 | 7.780994 | 0.406137 | 4.173446 | 77.371232 |
| balanced_pareto_mu0_08 | 9 | 5.131521 | 0.267845 | 2.587445 | 67.457245 |
| balanced_pareto_mu0_12 | 3 | 11.547341 | 0.405978 | 6.293623 | 77.804670 |
| balanced_pareto_mu0_12 | 9 | 7.626513 | 0.268131 | 3.924479 | 67.736247 |

## Top drive contributors

| case | drive | sections | share | impulse (N s) | max friction (N) |
|---|---:|---|---:|---:|---:|
| balanced_pareto_mu0_08 | 3 | 1 | 0.406137 | 7.780994 | 4.173446 |
| balanced_pareto_mu0_12 | 3 | 1 | 0.405978 | 11.547341 | 6.293623 |
| lowest_endpoint_jerk_mu0_12 | 3 | 1 | 0.403504 | 11.032367 | 6.249544 |
| lowest_endpoint_jerk_mu0_08 | 3 | 1 | 0.400526 | 7.417128 | 4.138501 |
| balanced_pareto_mu0_12 | 9 | 1 | 0.268131 | 7.626513 | 3.924479 |
| balanced_pareto_mu0_08 | 9 | 1 | 0.267845 | 5.131521 | 2.587445 |
| lowest_endpoint_jerk_mu0_12 | 9 | 1 | 0.266908 | 7.297657 | 3.889345 |
| lowest_endpoint_jerk_mu0_08 | 9 | 1 | 0.264755 | 4.902862 | 2.565698 |
| lowest_endpoint_jerk_mu0_08 | 4 | 1 2 3 | 0.108076 | 2.001397 | 1.020392 |
| lowest_endpoint_jerk_mu0_12 | 4 | 1 2 3 | 0.106673 | 2.916579 | 1.517309 |
| balanced_pareto_mu0_12 | 4 | 1 2 3 | 0.103534 | 2.944847 | 1.537600 |
| balanced_pareto_mu0_08 | 4 | 1 2 3 | 0.101707 | 1.948554 | 1.002870 |

## Section-level contribution

| case | section | active drives | share | impulse (N s) |
|---|---:|---|---:|---:|
| lowest_endpoint_jerk_mu0_08 | 1 | 1 2 3 4 5 6 7 8 9 | 0.777422 | 14.396677 |
| lowest_endpoint_jerk_mu0_08 | 2 | 1 2 4 5 7 8 | 0.135875 | 2.516192 |
| lowest_endpoint_jerk_mu0_08 | 3 | 1 4 7 | 0.086703 | 1.605612 |
| lowest_endpoint_jerk_mu0_12 | 1 | 1 2 3 4 5 6 7 8 9 | 0.780009 | 21.326560 |
| lowest_endpoint_jerk_mu0_12 | 2 | 1 2 4 5 7 8 | 0.133862 | 3.659992 |
| lowest_endpoint_jerk_mu0_12 | 3 | 1 4 7 | 0.086129 | 2.354880 |
| balanced_pareto_mu0_08 | 1 | 1 2 3 4 5 6 7 8 9 | 0.785929 | 15.057275 |
| balanced_pareto_mu0_08 | 2 | 1 2 4 5 7 8 | 0.131639 | 2.522008 |
| balanced_pareto_mu0_08 | 3 | 1 4 7 | 0.082432 | 1.579282 |
| balanced_pareto_mu0_12 | 1 | 1 2 3 4 5 6 7 8 9 | 0.783093 | 22.273730 |
| balanced_pareto_mu0_12 | 2 | 1 2 4 5 7 8 | 0.132189 | 3.759875 |
| balanced_pareto_mu0_12 | 3 | 1 4 7 | 0.084718 | 2.409654 |

## Interpretation

- `lowest_endpoint_jerk_mu0_08`: top drive is D3 with share 0.401; D3+D9 combined share 0.665. Top section is S1 with share 0.777. Top pair is S1-D3 with share 0.401.
- `lowest_endpoint_jerk_mu0_12`: top drive is D3 with share 0.404; D3+D9 combined share 0.670. Top section is S1 with share 0.780. Top pair is S1-D3 with share 0.404.
- `balanced_pareto_mu0_08`: top drive is D3 with share 0.406; D3+D9 combined share 0.674. Top section is S1 with share 0.786. Top pair is S1-D3 with share 0.406.
- `balanced_pareto_mu0_12`: top drive is D3 with share 0.406; D3+D9 combined share 0.674. Top section is S1 with share 0.783. Top pair is S1-D3 with share 0.406.

A section or drive should be treated as dominant only if it consistently owns the largest impulse share across both representatives and both friction levels. Drive 3/9 dominance is assessed by their combined share and by whether either appears among the top section-drive pairs.
