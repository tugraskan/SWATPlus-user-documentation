---
description: "This file identifies cataloging-unit elements and their basin, routing-unit, and regional area fractions."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file identifies cataloging-unit elements and their basin, routing-unit, and regional area fractions.

SWAT+ looks for `element.ccu` in the simulation working directory; it is not selected through `file.cio`. See the [ch_read_elements.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/ch_read_elements.f90#L145) reader.

# element.ccu

The first two lines contain a title and column headings. Enter one row per element using the fields below.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [k](k.md) | Record number | integer | n/a | — | — |
| [name](name.md) | Record name | string | n/a | — | — |
| [obtyp](obtyp.md) | Object type | string | n/a | — | — |
| [obtypno](obtypno.md) | Object identifier | integer | n/a | — | — |
| [bsn_frac](bsn_frac.md) | Basin expansion fraction | real | — | — | — |
| [ru_frac](ru_frac.md) | Routing-unit expansion fraction | real | — | — | — |
| [reg_frac](reg_frac.md) | Regional expansion fraction | real | — | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
