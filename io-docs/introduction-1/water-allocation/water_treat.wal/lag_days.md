---
description: "Lag time applied to treated outflow"
---

# lag_days

**Code reference:** `wtp(iwtp)%lag_days` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_module.f90#L157), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_treatment_read.f90#L46)).

Treatment lag time before outflow (`days`; uninitialized in the derived-type definition). In `6f515368`, [`wallo_treatment.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_treatment.f90#L66,L87-L88) explicitly applies no lagging and resets `wtp_om_stor(iwtp) = hz` each day.

*(Note: In SWAT+ main (6f515368), this column is parsed into memory but is not used in simulation calculations).*
