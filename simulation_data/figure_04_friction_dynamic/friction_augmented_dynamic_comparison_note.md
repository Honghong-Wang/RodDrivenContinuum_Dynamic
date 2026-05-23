# Friction-augmented dynamic replay comparison

This simulation compares the previous dynamic replay baseline with a rod-guide/spacer sliding-friction augmented dynamic replay under the same command construction. It is simulation-only and does not identify a measured friction coefficient.

- mu: 0.0800
- normal preload: 0.2000 N
- normal gain: 1.0000
- max drive-space friction: 12.0000 N
- figure: `D:\RodDrindcontinuum\src\3sec\outputs\three_section_friction_augmented_dynamic_comparison\friction_augmented_dynamic_comparison_figure.png`

## Case metrics

| case | mu | max error (mm) | mean error (mm) | max force (N) | sat. fraction | max friction (N) | net work (J) |
|---|---:|---:|---:|---:|---:|---:|---:|
| dynamic_no_friction | 0.0000 | 0.629465 | 0.126008 | 169.905 | 0.000000 | 0.000000 | 0.000000 |
| dynamic_with_friction | 0.0800 | 0.614759 | 0.130990 | 167.831 | 0.000000 | 1.366297 | 0.003466 |

## Pair delta

- max tip delta: 0.159600 mm
- mean tip delta: 0.047566 mm
- max force delta: 0.649302 N
- mean force delta: -0.844469 N
