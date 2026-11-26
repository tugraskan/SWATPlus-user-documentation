---
description: "Fraction of water lost during use"
---

# loss_fr

**Code reference:** `wuse(iwuse)%loss_fr` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_module.f90#L158), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_use_read.f90#L49)).

Fraction of water lost during use (`fraction`; uninitialized in the derived-type definition). In `6f515368`, [`wallo_use.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_use.f90#L56) instead multiplies stored inflow by `wuse_om_efflu%flo` (from [om_use.wal](../om_use.wal/README.md)) to compute effluent volume.

*(Note: In SWAT+ main (6f515368) and dev (aa4179fe), this column is parsed into memory but is not used in simulation calculations).*
