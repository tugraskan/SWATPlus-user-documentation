---
description: "This file contains salt-ion composition values for fertilizers."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file contains salt-ion composition values for fertilizers.

SWAT+ looks for `salt_fertilizer.frt` in the simulation working directory; it is not selected through `file.cio`. See the [salt_fert_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/salt_fert_read.f90#L24) reader.

# salt_fertilizer.frt

The first two lines contain a title and column headings. Each following row contains the fields below, in this order.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [name](name.md) | Record name | string | n/a | — | — |
| [so4](so4.md) | Sulfate ion fraction | real | kg/kg fertilizer | — | — |
| [ca](ca.md) | Calcium ion fraction | real | kg/kg fertilizer | — | — |
| [mg](mg.md) | Magnesium ion fraction | real | kg/kg fertilizer | — | — |
| [na](na.md) | Sodium ion fraction | real | kg/kg fertilizer | — | — |
| [k](k.md) | Record number | real | kg/kg fertilizer | — | — |
| [cl](cl.md) | Chloride ion fraction | real | kg/kg fertilizer | — | — |
| [co3](co3.md) | Carbonate ion fraction | real | kg/kg fertilizer | — | — |
| [hco3](hco3.md) | Bicarbonate ion fraction | real | kg/kg fertilizer | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
