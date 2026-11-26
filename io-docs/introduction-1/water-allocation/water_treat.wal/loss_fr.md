---
description: "Fraction of water lost during treatment"
---

# loss_fr

**Code reference:** `wtp(iwtp)%loss_fr` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_module.f90#L158), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_treatment_read.f90#L46)).

Fraction of water lost during treatment (`fraction`; uninitialized in the derived-type definition). In `6f515368`, [`wallo_treatment.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_treatment.f90#L68) instead uses `wtp_om_treat%flo` (from [om_treat.wal](../om_treat.wal/README.md)) to scale treated outflow.

*(Note: In SWAT+ main (6f515368) and dev (aa4179fe), this column is parsed into memory but is not used in simulation calculations).*
