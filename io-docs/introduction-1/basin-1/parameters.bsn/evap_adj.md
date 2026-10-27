---
description: Reach evaporation adjustment factor
---

# evap\_adj

**Code reference:** `bsn_prm%evrch`

**Declared type:** `basin_parms` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/basin_read_prm.f90#L24), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/basin_module.f90#L109)).

The evaporation coefficient is a calibration parameter for the user that was created to allow reach evaporation to be dampened in arid regions. The original equation tends to overestimate evaporation in these areas.
