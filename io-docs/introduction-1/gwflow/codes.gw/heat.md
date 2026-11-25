---
description: "Heat transport (1 = on)"
---

# heat

**Code reference:** `gw_heat_flag` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_module.f90#L472), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L252)).

1 turns the process on; 0 (or a missing setting) leaves it off. When on, groundwater temperature is simulated. Each cell takes its thermal conductivity from the `thermal_K` column of its `K_zone` in [zones.gw](../zones.gw/thermal_k.md), and its initial temperature from the `init_temp` column of [cells.gw](../cells.gw/cell_init_temp_i.md) ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1490-L1495)).
