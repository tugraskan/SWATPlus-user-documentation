---
description: Alpha coefficient for gamma function unit hydrograph
---

# uhyd\_alpha

**Code reference:** `bsn_prm%uhalpha` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L124), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_prm.f90#L24)).

Dimensionless shape parameter $\alpha$ (table default `5`, range `0.5–10`; struct and runtime fallback default `1.0` when `< 1.e-6` in [`basin_prm_default.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_prm_default.f90#L45)) used when the gamma function unit hydrograph ([uhyd](../codes.bsn/uhyd.md) = `1`) is selected for sub-daily runoff routing in [`unit_hyd.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/unit_hyd.f90#L105-L107):

$$q(t) = \left(\frac{t}{t_p}\right)^{\alpha} \exp\!\left(\left(1 - \frac{t}{t_p}\right)\alpha\right)$$

where $t$ is elapsed time (`hours`) and $t_p$ is time to peak (`hours`).
