---
description: Exponential coefficient for overland flow
---

# surq\_exp

**Code reference:** `bsn_prm%eros_expo` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L127), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_prm.f90#L24)).

Dimensionless exponent $\beta$ applied to bed shear stress $\tau$ (`N/m^2`) in the overland-flow erosion equation in [`ero_ovrsed.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ero_ovrsed.f90#L197-L198) (table default `1.2`, range `1–3`; struct and runtime fallback default `0.` when `< 1.e-6` in [`basin_prm_default.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_prm_default.f90#L48); see [rill](rill.md)). Active only when [gampt](../codes.bsn/gampt.md) `> 0`.
