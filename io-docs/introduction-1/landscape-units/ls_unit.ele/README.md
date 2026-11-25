---
description: This file lists the HRUs and HRU-LTEs that are elements of a Landscape Unit.
---

# ls\_unit.ele

This file lists each HRU or HRU-LTE landscape element along with its basin and Landscape Unit area fractions, read by [`lsu_read_elements.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/lsu_read_elements.f90#L98-L135). SWAT+ uses these element records for LSU- and basin-level output weighting ([`lsu_output.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/lsu_output.f90#L34-L53), [`basin_output.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_output.f90#L30-L53)) and dynamic HRU area updates ([`hru_fr_change.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_fr_change.f90#L79-L97)).

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [id](id-ls_unit.ele.md) | ID of the element | integer | n/a | — | — |
| [name](name-ls_unit.ele.md) | Name of the element | string | n/a | — | — |
| [obj\_typ](obj_typ.md) | Object type of the element | string | n/a | — | — |
| [obj\_typ\_no](obj_typ_no.md) | Object ID of the element | integer | n/a | — | — |
| [bsn\_frac](bsn_frac.md) | Fraction of basin area assigned to this object | real | fraction | — | — |
| [ru\_frac](ru_frac.md) | Fraction of Landscape Unit area assigned to this object | real | fraction | — | — |
