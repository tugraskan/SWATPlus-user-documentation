---
description: "POU array index served by the POD"
---

# num (POU)

**Code reference:** `pod(ipod)%pou(ipou)%num` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_module.f90#L92), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_read.f90#L222-L224)).

1-based index of the receiving POU in the global `pou` array from [place_of_use.wro](../place_of_use.wro/README.md) (default: `0`). Used to look up the receiving POU in [`wallo_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_control.f90#L20-L26), which passes it to [`wallo_withdraw.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_withdraw.f90#L29-L37).
