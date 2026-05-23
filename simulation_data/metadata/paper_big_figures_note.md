# Paper big-figure package

This folder contains manuscript figures and supplementary diagnostics for the simulation-only narrative.

## Figure set

- `Fig_M1_dynamic_quasistatic_comparison`: Main figure: dynamic replay under the quasi-static length-command baseline
- `Fig_D1a_basic_dynamic_tip_trajectory`: Supplement: same-baseline tip trajectory validation
- `Fig_D1b_basic_dynamic_diagnostics`: Supplement: same-baseline error, force, and velocity diagnostics
- `Fig_D2_dynamic_mass_energy_consistency`: Supplement: mass SPD and geometric-inertia power consistency
- `Fig_M4_dynamic_consistency_error_mechanism`: Main figure: mass SPD, geometric-inertia power consistency, and energy closure
- `Fig_D3_same_baseline_dynamic_stage_comparison`: Supplement: quasi-static, replay, endpoint shaping, and optimizer comparison
- `Fig_D4_dynamic_pareto_and_optimizer`: Supplement: duration-error Pareto map and constrained optimizer search
- `Fig_M5_optimizer_performance_deepening`: Main figure: staged dynamic feasibility and optimizer evidence
- `Fig_F1_contact_friction_contribution_sensitivity`: Supplement: section-drive friction contribution and mu sensitivity
- `Fig_F2_friction_aware_redistribution`: Supplement: friction-aware redistribution comparison
- `Fig_M6_task_case_error_performance`: Main figure: spatial double-ellipse crossing trajectory and actuation diagnostics

The figures are generated from existing formal simulation outputs. No new dynamic replay or expensive optimization is executed by the figure script.
