---
description: "Diversion canal that supplies the pond"
---

# canal

**Code reference:** `gw_pond_info(i)%canal` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_module.f90#L405), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1951)).

Number of the diversion canal the pond's daily diversion is taken from; 0 for none. It is used only when `chan` is 0, and only when the canal has water in storage; the diversion is limited to that storage ([`gwflow_pond.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_pond.f90#L151-L163)).
