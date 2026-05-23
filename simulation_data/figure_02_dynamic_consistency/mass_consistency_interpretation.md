# Simulation-only M(q) consistency interpretation

This study is a numerical simulation check only. It does not use or imply experimental validation.

- SPD path check: all_spd = 1, min_eig = 1.330090e-09.
- Energy-drift improvement from adding C(q,qdot)qdot: NaN x.
- Max missing kinetic-power term without C(q,qdot)qdot: 4.695398e-06 W.
- Max Christoffel power-identity residual after adding C(q,qdot)qdot: 8.470329e-22 W.

Decision rule: if `UseConstantMass=false`, the variable-mass dynamics should enable `DynamicUseGeometricInertia=true`. The previous variable-M/no-C mode should be treated only as a diagnostic perturbation, not as a mechanically consistent forward model.
