---
description: Coefficient to estimate maximum LAI during tree growth
---

# bm\_tree\_acc

**Code reference:** `pldb(ic)%laixco_tree`

**Declared type:** `plant_db` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/plant_parm_read.f90#L57), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/plant_data_module.f90#L81)).

This dimensionless coefficient pertains to perennials. SWAT+ multiplies it by the base-10 logarithm of current years to maturity divided by total years to maturity to estimate the LAI exponent during tree growth. It is not a fraction of biomass converted to residue.
