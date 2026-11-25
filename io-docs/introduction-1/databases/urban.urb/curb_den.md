---
description: Curb length density
---

# curb\_den

**Code reference:** `urbdb(iu)%curbden` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/urban_data_module.f90#L9)).

**Current use:** converts washed-off solids from kg per curb km to kg/ha ([`hru_urban.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_urban.f90#L147)). It is used by the build-up/wash-off method only.

Curb length may be measured directly by scaling the total length of streets off of maps and multiplying by two. To calculate the density, the curb length is divided by the area represented by the map.
