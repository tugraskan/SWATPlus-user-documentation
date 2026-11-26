---
description: "Water temperature"
---

# temp

**Code reference:** `osrc_om(iom_osrc)%temp` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L49), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/om_osrc_read.f90#L43)).

Water temperature (`deg C`; Fortran struct default: `0.`). On SWAT+ dev the withdrawal copies the record `osrc_om(j)`, including this temperature, which is not converted ([`wallo_withdraw.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_withdraw.f90#L53-L57)). `j` is the outside-source object number from [point_of_diver.wro](../point_of_diver.wro/README.md). (SWAT+ main reset the record first, so this value was not used.)
