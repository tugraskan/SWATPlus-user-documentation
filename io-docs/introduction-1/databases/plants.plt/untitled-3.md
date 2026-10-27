---
description: Residue factor for percent cover equation
---

# rsd\_pctcov

**Code reference:** `pldb(ic)%rsd_pctcov`

**Declared type:** `plant_db` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/plant_parm_read.f90#L57), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/plant_data_module.f90#L102)).

SWAT+ main (6f515368) reads this dimensionless residue percent-cover factor and replaces values less than or equal to zero with 0.4, but no simulation routine reads the resulting value. This input has no simulation effect in this release.
