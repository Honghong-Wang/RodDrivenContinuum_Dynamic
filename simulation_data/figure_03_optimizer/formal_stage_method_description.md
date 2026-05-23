# Method description and stage definition

This study uses a staged, simulation-only workflow. The same quasi-static geometric reference is used as the source trajectory, and each subsequent stage changes only the command-generation layer or the dynamic replay model.

## Fixed representatives

The local optimizer is summarized by three fixed representatives: lowest tracking error, lowest endpoint jerk, and balanced Pareto. These are not retuned after selection; each is re-evaluated with the high-order setting used in the formal comparison.

## Stage definitions

1. Quasi-static geometric baseline: reduced-coordinate reference path and target-fitting error, with no actuator force state and no dynamic replay.
2. Raw dynamic replay: original command replayed with the force-state actuator, force magnitude limit, and force-rate limit.
3. Activity retime warm start: dynamic-activity-based timing adjustment used as the optimizer warm start.
4. Endpoint shaping: command-level C2 endpoint easing to reduce the initial and terminal transient.
5. Local optimizer: fixed-duration optimization of time-scale knots plus endpoint easing duration with force-rate, qddot, and jerk barriers.

## Simulation-only limitation

The results are numerical simulations only. They demonstrate dynamic consistency, actuator-constrained command feasibility, and Pareto trade-offs under the present reduced-order model. They do not establish experimental accuracy, friction/contact validity, or external-load robustness.

## Next-stage boundary

Friction, contact, and external loads should be introduced only after the constrained command layer is kept fixed. This separation prevents actuator-feasibility conclusions from being mixed with later environmental modeling assumptions.

## Comparison table summary

| stage | duration (s) | max error (mm) | force sat. | force-rate util. | max qddot | endpoint jerk | constraints |
|---|---:|---:|---:|---:|---:|---:|---:|
| quasi-static geometric baseline | 15.000 | 0.000000 | NaN | NaN | 680.863 | 307.523 | 0 |
| raw dynamic replay | 15.000 | 1.630580 | 0.131537 | 1.000001 | 1465.356 | 307.523 | 0 |
| activity retime warm start | 20.000 | 0.611575 | 0.016358 | 1.000000 | 1631.209 | 441.276 | 0 |
| endpoint shaping | 20.000 | 0.625495 | 0.016043 | 1.000002 | 28377.585 | 1351597.423 | 0 |
| local optimizer: lowest error | 20.000 | 0.608594 | 0.013904 | 1.000003 | 35524.187 | 1133098.960 | 0 |
| local optimizer: lowest endpoint jerk | 20.000 | 0.636438 | 0.036325 | 1.000003 | 26979.035 | 452518.592 | 0 |
| local optimizer: balanced Pareto | 20.000 | 0.641604 | 0.029095 | 1.000002 | 21543.352 | 464757.780 | 0 |
