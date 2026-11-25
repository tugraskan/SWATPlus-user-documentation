---
description: "This file supplies named pesticide export-coefficient values."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file supplies named pesticide export-coefficient values, selected via `file.cio` (`in_exco%pest`, default `"exco_pest.exc"`) and read by [`exco_read_pest.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/exco_read_pest.f90#L28-L94) only when `cs_db%num_pests > 0` in [`constituents.cs`](../../constituents/constituents.cs.md) ([`exco_db_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/exco_db_read.f90#L57)). Each row contains the record name followed by one constant pesticide loading value per simulated pesticide in `constituents.cs` order.

# exco\_pest.exc

The first two lines contain a title and column headings. Each following row contains the fields below, in this order ([`exco_read_pest.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/exco_read_pest.f90#L62)).

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [exco\_pest\_name(ii)](exco_pest_name_ii.md) | Identifier linking this record to a named EXCO pesticide entry | string | n/a | — | — |
| [pest(ipest)](pest_ipest.md) | Pesticide export-coefficient loading for each simulated pesticide | real | mg | 0 | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
