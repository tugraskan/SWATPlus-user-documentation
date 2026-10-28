---
description: "This file groups point sources into cataloging units."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file groups point sources into cataloging units.

# rec_catunit.def

The file contains a title, a region count, headings, and one row per region. Each region row ends with the number of element-list entries and those entries.

## Number of regions

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [mreg](mreg.md) | Number of regions | integer | n/a | — | — |

## Input values

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [k](k.md) | Record number | integer | n/a | — | — |
| [name](name.md) | Record name | string | n/a | — | — |
| [area_ha](area_ha.md) | Region area | real | — | — | — |
| [nspu](nspu.md) | Number of element-list entries | integer | n/a | — | — |
| [elem_cnt](elem_cnt.md) | Element-list entry | integer | n/a | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
