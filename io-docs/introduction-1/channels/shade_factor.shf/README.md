---
description: "This file contains daily channel shading factors."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file contains daily channel shading factors.

# shade_factor.shf

The first two lines contain a title and column headings. Each following row contains the fields below, in this order.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [jday](jday.md) | Day of year | integer | day of year | — | — |
| [cha](cha.md) | Channel (reach) identifier for the shading entry | integer | n/a | — | — |
| [value](value.md) | Fraction of incoming shortwave radiation blocked by shading | real | fraction | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
