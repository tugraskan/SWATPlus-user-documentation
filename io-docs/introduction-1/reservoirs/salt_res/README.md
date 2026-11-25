---
description: "This file supplies named sets of initial salt-ion concentrations for reservoirs and wetlands."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file supplies named sets of initial salt-ion concentrations for reservoirs and wetlands.

SWAT+ looks for `salt_res` in the simulation working directory; it is not selected through `file.cio`. It reads this file via [`res_read_saltdb.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_read_saltdb.f90#L26-L73) only when `salt_res` exists and `nut_res` in `file.cio` is not `null`. Before data rows, SWAT+ skips **11 header lines** (2 title lines, 8 descriptive lines, and 1 column-header line). Each data row lists `name` followed by one initial concentration (`c_init`) per salt ion configured in [**constituents.cs**](../../constituents/constituents.cs.md).

# salt\_res

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [name](name.md) | Name of the reservoir and wetland salt record | string | n/a | — | — |
| [c\_init](c_init.md) | Initial concentration of each configured salt ion in reservoir or wetland water | real | g/m3 | 0.0 | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
