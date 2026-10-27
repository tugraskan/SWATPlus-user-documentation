---
description: First column listing elements in the Routing Unit
---

# elements

**Code reference:** `elem_cnt(isp)`

**Declared type:** `integer` (variable in `ru_read_elements`) ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/ru_read_elements.f90#L126), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/hydrograph_module.f90#L23)).

If [elem\_tot](elem_tot.md) = 1, there can be only one element in the Routing Unit, whose ID ([id](../untitled-2/id-rout_unit.ele.md) in [**rout\_unit.ele**](../untitled-2/)) is specified in this column. If [elem\_tot](elem_tot.md) > 1, this column is followed by additional columns listing the elements included in the Routing Unit, but those columns will not have a header. If there are several elements with consecutive numbers in a Routing Unit, they can be listed by specifying the first one in one column and the last one with a hyphen in front of it in the next column.
