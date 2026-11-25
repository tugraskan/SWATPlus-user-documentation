---
description: "This file supplies named pesticide delivery values."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file supplies named pesticide delivery ratios, read by [`dr_read_pest.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/dr_read_pest.f90#L63) only when `cs_db%num_pests > 0` in [`constituents.cs`](../../constituents/constituents.cs.md) ([`dr_db_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/dr_db_read.f90#L57)). Each row contains the record name followed by one dimensionless delivery-ratio column per simulated pesticide in `constituents.cs` order.

# dr\_pest.del

The first two lines contain a title and column headings. Each following row contains the fields below, in this order.

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [dr\_pest\_name(ii)](dr_pest_name_ii.md) | Identifier linking this record to a named pesticide delivery definition | string | n/a | — | — |
| [pest(ipest)](pest_ipest.md) | Pesticide delivery ratio associated with each simulated pesticide | real | fraction | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
