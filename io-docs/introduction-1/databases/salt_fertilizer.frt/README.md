---
description: This file contains salt-ion composition values for fertilizers.
---

# salt_fertilizer.frt

{% hint style="info" %}
The inspected SWAT+ Editor version can generate this file when salt-fertilizer export is enabled. Editor checkout checked: `1efec55`.

The table below is based on the SWAT+ Fortran source code. Its contents should not be assumed to match the labels, defaults, or options available in SWAT+ Editor. A dash means that no recommended default or range has been established here; it is not a Fortran initialization value.
{% endhint %}

Salt-ion composition of fertilizer. Application routines multiply each ion mass fraction by the amount of fertilizer applied.

SWAT+ looks directly for the literal filename `salt_fertilizer.frt` in the simulation working directory; this filename is not selected through `file.cio`. It is read by [salt_fert_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/salt_fert_read.f90#L24). If the file is absent, no salt-fertilizer composition records are loaded from it.

The first line is a title and the second line is a header. Each subsequent record contains the fields below, in this order. There is no separate record-count line. The reader requests exactly one record per fertilizer database entry (db_mx%fertparm). Keep these records in the same order as the fertilizer database; the name field is not used to reorder them.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [name](name.md) | Fertilizer name | string | n/a | — | — |
| [so4](so4.md) | Sulfate ion fraction | real | kg/kg fertilizer | — | — |
| [ca](ca.md) | Calcium ion fraction | real | kg/kg fertilizer | — | — |
| [mg](mg.md) | Magnesium ion fraction | real | kg/kg fertilizer | — | — |
| [na](na.md) | Sodium ion fraction | real | kg/kg fertilizer | — | — |
| [k](k.md) | Potassium ion fraction | real | kg/kg fertilizer | — | — |
| [cl](cl.md) | Chloride ion fraction | real | kg/kg fertilizer | — | — |
| [co3](co3.md) | Carbonate ion fraction | real | kg/kg fertilizer | — | — |
| [hco3](hco3.md) | Bicarbonate ion fraction | real | kg/kg fertilizer | — | — |

Recommended defaults and ranges are not specified by this page. The dash does not imply a default of zero.

The values are mass per mass of fertilizer: multiplying kg fertilizer/ha by kg constituent/kg fertilizer gives kg constituent/ha. They are not absolute application loads in kg/ha, despite the older source comments. No required sum of the constituent values is established here.
