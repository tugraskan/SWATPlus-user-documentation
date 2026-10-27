---
description: Residue factor for surface cover (C factor) equation
---

# rsd\_covfac

**Code reference:** `pldb(ic)%rsd_covfac` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/plant_data_module.f90#L103)).

Dimensionless residue factor for the surface-cover C-factor equation. Values less than or equal to zero are replaced by 0.04, and the value is accumulated into the plant community's residue-cover factor during initialization.
