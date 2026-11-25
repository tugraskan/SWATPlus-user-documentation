---
description: Revap coefficient
---

# revap

**Code reference:** `hlt_db(i)%revapc` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_lte_module.f90#L23)).

Dimensionless fraction of actual evapotranspiration that is also removed from shallow aquifer storage, limited to the water available there ([`hru_lte_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_lte_control.f90#L334)):

$$revap = ET_a \times c$$

where $revap$ is shallow aquifer revap (`mm`), $ET_a$ is actual evapotranspiration (`mm`), and $c$ is the `revap` coefficient (dimensionless).
