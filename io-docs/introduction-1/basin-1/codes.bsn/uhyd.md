---
description: Unit Hydrograph method
---

# uhyd

**Code reference:** `bsn_cc%uhyd` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L53), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_cc.f90#L24)).

Selects the sub-daily unit hydrograph ordinate shape in [`unit_hyd.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/unit_hyd.f90#L94-L107) (struct default `1`).

| Code | Option |
| ---- | ------ |
| 0 | Triangular Unit Hydrograph |
| 1 | Gamma Function Unit Hydrograph |

For a basetime $t_b$ adjusted by [adj\_uhyd](../parameters.bsn/adj_uhyd.md), code `0` uses linear rising ($t / t_p$) and falling ($(t_b - t)/(t_b - t_p)$) limbs, whereas code `1` uses the gamma shape with [uhyd\_alpha](../parameters.bsn/uhyd_alpha.md) ($\alpha$):

$$t_p = 0.375\,t_b, \qquad q(t) = \left(\frac{t}{t_p}\right)^{\alpha} \exp\!\left(\left(1 - \frac{t}{t_p}\right)\alpha\right)$$

where:
- $t_p$ is time to peak (`hours`),
- $t_b$ is the unit hydrograph basetime (`hours`),
- $q(t)$ is the dimensionless unit hydrograph ordinate at time $t$,
- $t$ is time since runoff began (`hours`), and
- $\alpha$ is `uhyd_alpha` (dimensionless).

The Unit Hydrograph method is only relevant when simulating at a sub-daily timestep and [gampt](gampt.md) = 0.
