---
description: "This file supplies named sets of initial general-constituent values for aquifers."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file supplies named sets of initial general-constituent values for aquifers.

SWAT+ looks for `cs_aqu.ini` in the simulation working directory; it is not selected through `file.cio`. See the [`cs_aqu_read.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/cs_aqu_read.f90#L23-L58) reader.

# cs\_aqu.ini

The first **3 lines** contain a title and two header lines ([`cs_aqu_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cs_aqu_read.f90#L24-L28)). Each following row contains `name` followed by `2 * cs_db%num_cs` values in `aqu` (first `cs_db%num_cs` dissolved concentrations, then `cs_db%num_cs` sorbed concentrations).

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [name](name.md) | Record name | string | n/a | — | — |
| [aqu](aqu.md) | Dissolved (`1..num_cs`) and sorbed (`num_cs+1..2*num_cs`) constituent values in the aquifer | real | mg/L; mg/kg | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
