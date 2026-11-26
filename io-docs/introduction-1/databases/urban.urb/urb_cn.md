---
description: Moisture-condition-II curve-number input for impervious urban areas (currently not used)
---

# urb\_cn

**Code reference:** `urbdb(iu)%urbcn2` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/urban_data_module.f90#L16)).

Moisture-condition-II curve-number input for impervious urban areas.

*(Note: In SWAT+ main (6f515368) and dev (aa4179fe), this column is parsed into memory but is not used in simulation calculations.)* Daily curve-number runoff uses a fixed impervious curve number of 98 ([`sq_daycn.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sq_daycn.f90#L45)).
