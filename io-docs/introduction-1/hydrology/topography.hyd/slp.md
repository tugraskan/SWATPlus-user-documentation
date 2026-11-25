---
description: Average slope steepness
---

# slp

**Code reference:** `topo_db(ith)%slope` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/topography_data_module.f90#L7)).

Average slope steepness, measured as vertical rise per unit horizontal distance (m/m). For example, enter 0.02 for a 2% slope. The built-in record uses 0.02.

Slope increases the lateral-flow term in [`swr_percmicro.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/swr_percmicro.f90#L60-L73) and reduces the HRU overland travel time through:

$$t_o = \frac{0.0556 \, (L n)^{0.6}}{(S + 0.0001)^{0.3}}$$

where $t_o$ is the HRU overland travel time (h), $L$ is [slope length](slp_len.md) (m), $n$ is overland Manning's roughness (dimensionless), and $S$ is `slp` (m/m). Routing units use 0.001 in the corresponding denominator. [`time_conc_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/time_conc_init.f90#L42-L60)
