---
description: "This file supplies named salt-ion export-coefficient values."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file supplies named salt-ion export-coefficient values, selected via `file.cio` (`in_exco%salt`, default `"exco_salt.exc"`) and read by [`exco_read_salt.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/exco_read_salt.f90#L29-L94) only when `cs_db%num_salts > 0` in [`constituents.cs`](../../constituents/constituents.cs.md) ([`exco_db_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/exco_db_read.f90#L60)). Each row contains the record name followed by one constant salt-ion loading value per simulated salt ion in `constituents.cs` order.

# exco\_salt.exc

The first two lines contain a title and column headings. Each following row contains the fields below, in this order ([`exco_read_salt.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/exco_read_salt.f90#L63)).

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [exco\_salt\_name(ii)](exco_salt_name_ii.md) | Name identifying this salt export-coefficient record | string | n/a | — | — |
| [salt(isalt)](salt_isalt.md) | Salt-ion export-coefficient loading for each simulated salt ion | real | kg | 0 | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
