---
description: "This file supplies named pathogen export-coefficient values."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file supplies named pathogen export-coefficient values, selected via `file.cio` (`in_exco%path`, default `"exco_path.exc"`) and read by [`exco_read_path.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/exco_read_path.f90#L29-L95) only when `cs_db%num_paths > 0` in [`constituents.cs`](../../constituents/constituents.cs.md) ([`exco_db_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/exco_db_read.f90#L58)). Each row contains the record name followed by one constant pathogen loading value per simulated pathogen in `constituents.cs` order.

# exco\_path.exc

The first two lines contain a title and column headings. Each following row contains the fields below, in this order ([`exco_read_path.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/exco_read_path.f90#L63)).

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [exco\_path\_name(ii)](exco_path_name_ii.md) | Name identifying this pathogen export-coefficient record | string | n/a | — | — |
| [path(ipath)](path_ipath.md) | Pathogen export-coefficient loading for each simulated pathogen | real | — | 0 | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
