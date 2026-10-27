# elements

**Code reference:** `elem_cnt(isp)`

**Declared type:** `integer` (variable in `lsu_read_elements`) ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/lsu_read_elements.f90#L70), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/hydrograph_module.f90#L23)).

If elem\_tot = 1, there can be only one element in the Landscape Unit, whose number (id in rout\_unit.ele) is specified in this column. If elem\_tot >1, this column is followed by additional columns listing the elements included in the Landscape Unit, but those columns will not have a header. If there are several elements with consecutive numbers in a Landscape Unit, they can be listed by specifying the first one in one column and the last one with a hyphen in front of it in the next column.
