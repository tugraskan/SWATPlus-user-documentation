---
description: Adjustment factor for the weather-generator half-hour rainfall fraction
---

# adj\_pkrt

**Code reference:** `bsn_prm%adj_pkr`

**Declared type:** `basin_parms` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/basin_read_prm.f90#L24), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/basin_module.f90#L83)).

When the weather generator estimates the monthly maximum half-hour rainfall fraction, SWAT+ multiplies that estimate by adj_pkrt and then limits the result to 0.1-0.95. This field does not directly control sediment routing in SWAT+ main (6f515368).
