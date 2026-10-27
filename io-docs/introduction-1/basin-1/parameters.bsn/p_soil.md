---
description: Phosphorus soil partitioning coefficient
---

# p\_soil

**Code reference:** `bsn_prm%phoskd`

**Declared type:** `basin_parms` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/basin_read_prm.f90#L24), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/basin_module.f90#L96)).

The phosphorus soil partitioning coefficient _p\_soil_ is the ratio of the soluble phosphorus concentration in the top 10 mm of soil to the concentration of soluble phosphorus in surface runoff.

The primary mechanism of phosphorus movement in the soil is by diffusion. Diffusion is the migration of ions over small distances (1-2 mm) in the soil solution in response to a concentration gradient. Due to the low mobility of solution phosphorus, surface runoff will only partially interact with the solution P stored in the top 10 mm of soil.
