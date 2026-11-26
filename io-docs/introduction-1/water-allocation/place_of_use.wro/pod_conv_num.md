---
description: "POD conveyance object number"
---

# conv_num (POD)

**Code reference:** `pou(ipou)%pod(ipod)%conv_num` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_module.f90#L20), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_read.f90#L95-L98)).

Integer index of the conveyance object (pipe or pump; default: `0`). It is only read in [`wallo_transfer.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_transfer.f90#L23), which is commented out at [`wallo_return.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_return.f90#L21) and never called in SWAT+ main (`6f515368`).
