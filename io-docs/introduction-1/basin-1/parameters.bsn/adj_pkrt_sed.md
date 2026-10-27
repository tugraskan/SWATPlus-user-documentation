---
description: Peak rate factor for the NRCS dimensionless-hydrograph peak-runoff equation
---

# adj\_pkrt\_sed

**Code reference:** `bsn_prm%prf`

**Declared type:** `basin_parms` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/basin_read_prm.f90#L24), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/basin_module.f90#L84)).


When the NRCS dimensionless-hydrograph method is selected, SWAT+ uses adj_pkrt_sed to calculate HRU peak runoff rate from runoff depth, HRU area, and time of concentration. It is not a main-channel sediment-routing factor in SWAT+ main (6f515368).
