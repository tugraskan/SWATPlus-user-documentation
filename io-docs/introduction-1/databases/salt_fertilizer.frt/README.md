---
description: "This file contains salt-ion composition values for fertilizers."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file contains salt-ion composition values for fertilizers.

SWAT+ looks for `salt_fertilizer.frt` in the simulation working directory; it is not selected through `file.cio`. See the [salt_fert_read.f90](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_fert_read.f90#L24) reader.

# salt_fertilizer.frt

The first two lines contain a title and column headings. Each following row contains the fields below, in this order.

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [name](name.md) | Record name | string | n/a | — | — |
| [so4](so4.md) | Sulfate ion fraction | real | kg/kg fertilizer | — | — |
| [ca](ca.md) | Calcium ion fraction | real | kg/kg fertilizer | — | — |
| [mg](mg.md) | Magnesium ion fraction | real | kg/kg fertilizer | — | — |
| [na](na.md) | Sodium ion fraction | real | kg/kg fertilizer | — | — |
| [k](k.md) | Potassium ion fraction | real | kg/kg fertilizer | — | — |
| [cl](cl.md) | Chloride ion fraction | real | kg/kg fertilizer | — | — |
| [co3](co3.md) | Carbonate ion fraction | real | kg/kg fertilizer | — | — |
| [hco3](hco3.md) | Bicarbonate ion fraction | real | kg/kg fertilizer | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.

The reader expects one row for every [fertilizer.frt](../fertilizer.frt/) record, in the same order ([`salt_fert_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_fert_read.f90#L29-L37)).

{% hint style="warning" %}
In SWAT+ main (`6f515368`) these values are applied by `manu` operations, the `manure` decision-table action, and `fert` operations on ponded fields. The call for a dry-field `fert` operation is commented out ([`mgt_sched.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_sched.f90#L390-L409)). For manure, the row number comes from [manure\_db.frt](../manure_db.frt/), not from `fertilizer.frt`. This comes from source reading, not a model run.
{% endhint %}
