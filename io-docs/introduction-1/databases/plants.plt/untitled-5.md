---
description: >-
  Fraction of field capacity to initiate growth of tropical plants during
  monsoon season
---

# frac\_sw\_gro

**Code reference:** `pldb(ic)%frsw_gro` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/plant_data_module.f90#L99)).

SWAT+ main (6f515368) reads this column but does not use it. The source comment describes the intended value as a 30-day sum of precipitation minus potential evapotranspiration for initiating tropical-plant growth during monsoon season; however, the declaration labels it as a fraction, so the intended input unit is unresolved in this release.
