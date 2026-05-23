# Simulation data package

This directory contains the numerical data selected for the initial Engineering with Computers submission package.

Organization:
- `metadata/`: figure generation manifest, notes, and small reproducibility helper scripts.
- `figure_01_dynamic_replay/`: same-baseline dynamic replay data, quasi-static reference, scalar metrics, and time-history diagnostics.
- `figure_02_dynamic_consistency/`: reduced mass matrix SPD/symmetry and energy/power closure checks.
- `figure_03_optimizer/`: stage comparison, constrained command optimizer, duration-error Pareto, representative high-order replay data, and the supplementary optimizer acceleration/endpoint-jerk diagnostic figure.
- `figure_04_friction_dynamic/`: friction-on/off dynamic replay comparison data and mu=0.08 replay result.
- `figure_05_endpoint_contact/`: endpoint approach-slide-retract contact task summary and MAT result.
- `figure_06_integrated_task/`: integrated dynamics-friction-contact task summary and MAT result.
- `figure_07_task_level/`: spatial double-ellipse target, drive-length commands, and estimated drive-force time series.
- `supplementary_friction_redistribution/`: data supporting the localized friction bottleneck, redistribution, and optimizer-level friction-aware studies.

Key indices:
- `figure_data_map.csv` maps each data file to its paper figure or supplementary analysis role.
- `data_file_manifest.csv` lists every file in this data package.

Simulation-only note: these files are numerical simulation artifacts. They are not experimental measurements and should not be interpreted as identified physical parameters.
