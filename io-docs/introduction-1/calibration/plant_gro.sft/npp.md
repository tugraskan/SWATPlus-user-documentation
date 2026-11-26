---
description: Net primary productivity target in plant_gro.sft.
---

# npp

**Code reference:** `plcal(i)%lum(ilum)%meas%npp` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calibration_data_module.f90#L245), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_read_regions_cal.f90#L86)).

Average annual net primary productivity (dry-weight biomass) target (`t/ha`, struct default `0.`).

*(Note: In SWAT+ main (6f515368) and dev (aa4179fe), this column is parsed into memory but is not used in simulation calculations).*
