---
description: "Cell status: 0 inactive, 1 active, 2 boundary"
---

# stat

**Code reference:** `gw_state(i)%stat` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_module.f90#L61), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L448)).

Cell status:

* **0, inactive:** not simulated; neighbors exchange no water with it ([`gwflow_lateral.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_lateral.f90#L59-L60)).
* **1, active:** heads are solved. Most sources and sinks (channel, tile, reservoir, floodplain, pumping) act only on active cells.
* **2, boundary:** the head is held at `init` ([`gwflow_lateral.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_lateral.f90#L155-L157)); whether neighbors exchange water with it depends on [bc_type](bc_type_array_i.md). Recharge that falls on a boundary cell is given to the nearest active cell ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L548-L568), [`gwflow_rech.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_rech.f90#L92)).

Only active cells count toward the GWFlow area used in basin totals ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L541-L546)).
