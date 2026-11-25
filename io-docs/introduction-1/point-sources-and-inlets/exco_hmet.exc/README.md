---
description: "This file supplies named heavy-metal export-coefficient values."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file supplies named heavy-metal export-coefficient values, selected via `file.cio` (`in_exco%hmet`, default `"exco_hmet.exc"`) and read by [`exco_read_hmet.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/exco_read_hmet.f90#L29-L95) only when `cs_db%num_metals > 0` in [`constituents.cs`](../../constituents/constituents.cs.md) ([`exco_db_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/exco_db_read.f90#L59)). Each row contains the record name followed by one constant heavy-metal loading value per simulated metal in `constituents.cs` order.

# exco\_hmet.exc

The first two lines contain a title and column headings. Each following row contains the fields below, in this order ([`exco_read_hmet.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/exco_read_hmet.f90#L63)).

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [exco\_hmet\_name(ii)](exco_hmet_name_ii.md) | Name identifying a heavy-metals export-coefficient record | string | n/a | — | — |
| [hmet(ihmet)](hmet_ihmet.md) | Heavy-metal export-coefficient loading for each simulated metal | real | — | 0 | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
