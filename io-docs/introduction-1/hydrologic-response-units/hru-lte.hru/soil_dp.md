---
description: Soil profile depth
---

# soil\_dp

**Code reference:** `hlt_db(i)%soildep` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_lte_module.f90#L16)).

Soil profile depth in mm. It is multiplied by the texture properties in [soils\_lte.sol](../../soils/soils_lte.sol/) to get the profile available water capacity and porosity in mm ([`hru_lte_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_lte_read.f90#L258-L259)).
