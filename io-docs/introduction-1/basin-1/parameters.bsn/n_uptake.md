---
description: Nitrogen uptake distribution parameter
---

# n\_uptake

**Code reference:** `bsn_prm%n_updis`

**Declared type:** `basin_parms` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/basin_read_prm.f90#L24), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/basin_module.f90#L88)).

Root density is greatest near the surface, and plant nitrogen uptake in the upper portion of the soil will be greater than in the lower portion. The depth distribution of nitrogen uptake is controlled by _n\_uptake_, the nitrogen uptake distribution parameter.

The importance of the nitrogen uptake distribution parameter lies in its control over the maximum amount of nitrate removed from the upper layers. Because the top 10 mm of the soil profile interacts with surface runoff, the nitrogen uptake distribution parameter will influence the amount of nitrate available for transport in surface runoff. The model allows lower layers in the root zone to fully compensate for lack of nitrate in the upper layers, so there should not be significant changes in nitrogen stress with variation in the value used for _n\_uptake_.
