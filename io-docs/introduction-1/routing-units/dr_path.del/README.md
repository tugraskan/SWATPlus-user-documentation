---
description: "This file supplies named pathogen delivery values."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file supplies named pathogen delivery ratios, read by [`dr_path_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/dr_path_read.f90#L63) only when `cs_db%num_paths > 0` in [`constituents.cs`](../../constituents/constituents.cs.md) ([`dr_db_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/dr_db_read.f90#L58)). Each row contains the record name followed by one dimensionless delivery-ratio column per simulated pathogen in `constituents.cs` order.

# dr\_path.del

The first two lines contain a title and column headings. Each following row contains the fields below, in this order.

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [dr\_path\_name(ii)](dr_path_name_ii.md) | Name identifying this pathogen delivery record | string | n/a | — | — |
| [path(ipath)](path_ipath.md) | Delivery ratio for each simulated pathogen | real | fraction | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
