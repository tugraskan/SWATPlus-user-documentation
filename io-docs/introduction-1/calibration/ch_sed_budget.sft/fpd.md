---
description: Target flood-plain accretion rate in ch_sed_budget.sft.
---

# fpd

**Code reference:** `chcal(i)%ord(iord)%meas%fpd` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calibration_data_module.f90#L294), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_read_orders_cal.f90#L122)).

Target annual flood-plain sediment accretion rate (`mm/yr`, struct default `0.`).

*(Note: In SWAT+ main (6f515368) and dev (aa4179fe), this column is parsed into memory but is not used in simulation calculations).*
