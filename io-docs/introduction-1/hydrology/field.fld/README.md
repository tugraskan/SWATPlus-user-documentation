---
description: This file specifies the properties of representative fields.
---

# field.fld

| Field           | Description         |  Type  | Unit | Default | Range |
| --------------- | ------------------- | :----: | :--: | :-----: | :---: |
| [name](name.md) | Name of the field   | string |  n/a |   n/a   |  n/a  |
| [len](len.md)\* | Length of the field |  real  |   m  |  500.0  |       |
| [wd](wd.md)\* | Width of the field  |  real  |   m  |  100.0  |       |
| ang             | Currently not used  |  real  |      |         |       |

\* Input-file labels marked with an asterisk have different Fortran names: `len` → `field_db(ith)%length`; `wd` → `field_db(ith)%wid`. [Reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/field_read.f90#L49).
