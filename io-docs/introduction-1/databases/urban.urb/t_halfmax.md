---
description: >-
  Time for amount of solids on impervious areas to build up to 1/2 of maximum
  level
---

# t\_halfmax

**Code reference:** `urbdb(iu)%thalf` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/urban_data_module.f90#L12)).

**Current use:** half-saturation time of the build-up curve described under [dirt\_max](dirt_max.md) ([`hru_urban.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_urban.f90#L128-L144)).

Number of days for amount of solids on impervious areas to build up from 0 kg/curb km to half the maximum amount of solids allowed (i.e. 0.5\*[dirt\_max](dirt_max.md)).
