---
description: "Water-loss fraction for the pipe"
---

# loss_fr

**Code reference:** `pipe(ipipe)%loss_fr` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_module.f90#L183), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_pipe_read.f90#L46,L53)).

Fraction of conveyed water lost in the pipe (`fraction`; uninitialized in the derived-type definition). In [`wallo_transfer.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_transfer.f90#L27), it scales conveyed POD hydrographs via:

$$H_{\text{pod}} \leftarrow \left(1 - f_{\text{loss}}\right) \cdot H_{\text{pod}}$$

where $H_{\text{pod}}$ is the conveyed POD hydrograph and $f_{\text{loss}}$ is `loss_fr` (fraction). However, the call to `wallo_transfer` in [`wallo_return.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_return.f90#L21) is commented out, so `wallo_transfer` is never called in SWAT+ main (`6f515368`).
