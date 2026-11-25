---
description: "This file contains constituent composition values for fertilizers."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file contains constituent composition values for fertilizers.

SWAT+ looks for `fertilizer.frt_cs` in the simulation working directory; it is not selected through `file.cio`. See the [cs_fert_read.f90](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cs_fert_read.f90#L25) reader.

# fertilizer.frt_cs

The first two lines contain a title and column headings. Each following row contains the fields below, in this order.

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [fertnm](fertnm.md) | Fertilizer name label | string | n/a | — | — |
| [seo4](seo4.md) | SeO4 constituent mass fraction | real | kg/kg fertilizer | — | — |
| [seo3](seo3.md) | SeO3 constituent mass fraction | real | kg/kg fertilizer | — | — |
| [boron](boron.md) | Boron constituent mass fraction | real | kg/kg fertilizer | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.

The reader expects one row for every [fertilizer.frt](../fertilizer.frt/) record, in the same order ([`cs_fert_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cs_fert_read.f90#L30-L38)).

{% hint style="warning" %}
These values are applied by `manu` operations, the `manure` decision-table action, and `fert` operations on ponded fields. The call for a dry-field `fert` operation is commented out ([`mgt_sched.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/mgt_sched.f90#L390-L409)). For manure, the row number comes from [manure\_db.frt](../manure_db.frt/), not from `fertilizer.frt`. This comes from source reading, not a model run.
{% endhint %}
