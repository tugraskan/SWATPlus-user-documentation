---
description: First column listing elements in the Routing Unit
---

# elements

**Code reference:** `elem_cnt(isp)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L23), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_read_elements.f90#L126-L133)).

If [elem\_tot](elem_tot.md) = 1, there is only one element in the Routing Unit, whose ID ([id](../untitled-2/id-rout_unit.ele.md) in [**rout\_unit.ele**](../untitled-2/)) is specified in this column. If [elem\_tot](elem_tot.md) > 1, this column is followed by additional columns on the same line (without extra column headers) until `elem_tot` integer tokens have been read.

Consecutive element IDs can be written as a range by placing the starting ID followed by the negated ending ID in the next column, which [`define_unit_elements.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/define_unit_elements.f90#L53-L92) expands into `ru_def(iru)%num(:)` (for example, `elem_tot = 2` with `1 -5` expands to element IDs `1, 2, 3, 4, 5`).
