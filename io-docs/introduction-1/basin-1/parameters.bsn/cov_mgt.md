---
description: Scaling parameter for cover and management factor for overland flow erosion
---

# cov\_mgt

**Code reference:** `bsn_prm%c_factor` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L128), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_prm.f90#L24)).

Dimensionless scaling multiplier ($c_{\text{mgt}}$, table default `0.03`, range `0.001–0.45`; struct and runtime fallback default `0.` when `< 1.e-6` in [`basin_prm_default.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_prm_default.f90#L49)) applied to the cover and management factor $C$ in the overland-flow erosion equation in [`ero_ovrsed.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ero_ovrsed.f90#L197-L198) (see [rill](rill.md)). Active only when [gampt](../codes.bsn/gampt.md) `> 0`.
