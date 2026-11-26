---
description: "POD conveyance type"
---

# conv_typ (POD)

**Code reference:** `pou(ipou)%pod(ipod)%conv_typ` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_module.f90#L19), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_read.f90#L95-L98)).

10-character conveyance type (`pipe` or `pump`; default: `""`). It is only checked in [`wallo_transfer.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_transfer.f90#L24) (where the `pump` branch is empty), and the call to `wallo_transfer` in [`wallo_return.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_return.f90#L21) is commented out in SWAT+ main (`6f515368`), so conveyance losses are not applied during simulation.
