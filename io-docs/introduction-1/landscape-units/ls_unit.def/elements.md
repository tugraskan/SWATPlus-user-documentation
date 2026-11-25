---
description: Element IDs and inclusive range endpoints belonging to the Landscape Unit
---

# elements

**Code reference:** `elem_cnt(isp)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L23), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/lsu_read_elements.f90#L70)).

Space-delimited list of `elem_tot` integers specifying the element IDs (matching [`id`](../ls_unit.ele/id-ls_unit.ele.md) in [`ls_unit.ele`](../ls_unit.ele/README.md)) assigned to this Landscape Unit (`integer`, dimensionless). Positive entries represent single element IDs; a positive integer followed by a negative integer (`start -end`) expands inclusively from `start` through `|end|` in [`define_unit_elements.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/define_unit_elements.f90#L17-L92).

The expanded indices are stored in `lsu_out(i)%num` with count `lsu_out(i)%num_tot` ([`lsu_read_elements.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/lsu_read_elements.f90#L76-L77)) and iterated during LSU output, initialization, and GWFlow aggregation ([`lsu_output.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/lsu_output.f90#L34-L35), [`lsu_carbon_output.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/lsu_carbon_output.f90#L46-L47), [`basin_sw_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_sw_init.f90#L67-L68), [`gwflow_gwet.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_gwet.f90#L39-L40), [`gwflow_rech.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_rech.f90#L77-L78)).
