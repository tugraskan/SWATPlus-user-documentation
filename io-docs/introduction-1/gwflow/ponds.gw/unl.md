---
description: "1 = supplied from outside the model"
---

# unl

**Code reference:** `gw_pond_info(i)%unl` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_module.f90#L406), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1952)).

1 means the daily diversion comes from outside the model and is added in full ([`gwflow_pond.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_pond.f90#L189-L190)). It is used only when `chan` and `canal` are both 0. Solutes enter at the concentrations in [unl_conc](unl_conc_j.md).
