---
description: "This file identifies the objects included in aquifer cataloging units and their area fractions."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file identifies the objects included in aquifer cataloging units and their area fractions.

# aqu_catunit.ele

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
