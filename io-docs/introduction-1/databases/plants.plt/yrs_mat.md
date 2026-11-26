---
description: Years to maturity
---

# yrs\_mat

**Code reference:** `pldb(ic)%mat_yrs` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_data_module.f90#L77)).

**Current use:** values below 1 are set to 1 ([`plant_parm_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_parm_read.f90#L402)). Perennials (and, on SWAT+ dev, herbaceous perennials) gain one year of maturity at each year end up to this value ([`time_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/time_control.f90#L349-L352)).

This variable pertains to trees only. It is not used for other types of plants.
