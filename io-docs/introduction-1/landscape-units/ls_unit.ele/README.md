---
This file lists the HRUs and HRU-LTEs that are elements of a Landscape Unit.
---

# ls\_unit.ele

| Field                         | Description                                             | Type    |
| ----------------------------- | ------------------------------------------------------- | ------- |
| [id](id-ls_unit.ele.md)\* | ID of the element                                       | integer |
| [name](name-ls_unit.ele.md)   | Name of the element                                     | string  |
| [obj\_typ](obj_typ.md)\* | Object type of the element                              | string  |
| [obj\_typ\_no](obj_typ_no.md)\* | Object ID of the element                                | integer |
| [bsn\_frac](bsn_frac.md) | Fraction of basin area assigned to this object | real |
| [ru\_frac](ru_frac.md) | Fraction of Landscape Unit area assigned to this object | real |

\* Input-file labels marked with an asterisk have different Fortran names: `id` → `k`; `obj_typ` → `lsu_elem(i)%obtyp`; `obj_typ_no` → `lsu_elem(i)%obtypno`. [Reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/lsu_read_elements.f90#L127).
