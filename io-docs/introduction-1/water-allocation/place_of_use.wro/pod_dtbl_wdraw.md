---
description: "Flow-control decision table name for maximum withdrawal"
---

# dtbl_wdraw (POD)

**Code reference:** `pou(ipou)%pod(ipod)%dtbl_wdraw` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_module.f90#L24), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_read.f90#L97)).

25-character name of a flow-control decision table in [flo_con.dtl](../../decision-tables/flo_con.dtl/README.md) (`dtbl_flo`), or `"null"` when fixed [ann_max](pod_ann_max.md) is used. Crosswalked into `dtbl_wdraw_num` in [`water_allocation_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_read.f90#L170-L178), and checked at the end of each simulation year in [`time_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/time_control.f90#L378-L380) to reset `wdraw_cur = 0.` when `"null"`. However, `dtbl_wdraw_num` is never evaluated in simulation.
