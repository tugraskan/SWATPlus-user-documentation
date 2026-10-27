---
description: Phosphorus uptake distribution parameter
---

# p\_uptake

**Code reference:** `bsn_prm%p_updis`

**Declared type:** `basin_parms` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/basin_read_prm.f90#L24), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/basin_module.f90#L89)).

This parameter controls plant uptake of phosphorus from the different soil horizons in the same way that [_n\_uptake_](n_uptake.md) controls nitrogen uptake.&#x20;

Phosphorus removed from the soil by plants is taken from the solution phosphorus pool. The importance of the phosphorus uptake distribution parameter lies in its control over the maximum amount of solution P removed from the upper layers. Because the top 10 mm of the soil profile interacts with surface runoff, the phosphorus uptake distribution parameter will influence the amount of labile phosphorus available for transport in surface runoff. The model allows lower layers in the root zone to fully compensate for lack of solution P in the upper layers, so there should not be significant changes in phosphorus stress with variation in the value used for _p\_uptake_.
