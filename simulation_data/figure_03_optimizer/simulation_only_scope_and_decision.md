# Simulation-only constrained command optimizer

This study is numerical simulation research only. It intentionally avoids experimental claims and uses existing simulated warm-start results.

The command layer jointly tunes dynamic-activity retiming and endpoint command shaping, with warm starts from `20s velocity_dominant_m4` and `c2_q8500_j4e6`.

- valid cases: 4 / 4
- best composite case: T20p0s_velocity_m4_protected_c2_q8500_j4e6
- best max error: 0.6158 mm
- lowest force saturation: 0.0102
- lowest force-rate utilization: 1.0000

Friction/contact/external-load studies should be deferred until this constrained command layer is stable, otherwise the main simulation contribution becomes diluted.
