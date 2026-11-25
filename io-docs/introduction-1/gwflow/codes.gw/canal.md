---
description: "Canal seepage from gwflow_canal.con (1 = on)"
---

# canal

**Code reference:** `gw_canal_flag` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_module.f90#L324), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L250)).

1 turns the process on; 0 (or a missing setting) leaves it off. When on and [gwflow_canal.con](../../databases/gwflow_canal.con/README.md) exists, canals seep to or receive water from the cells they cross. Canal widths, depths, bed thickness and conductivity come from the canal records of the water-allocation input ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1237-L1274)). If the file is missing, SWAT+ writes a message and no canal exchange is simulated.
