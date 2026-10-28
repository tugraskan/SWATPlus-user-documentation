---
description: "This file defines landscape regions, their land-use groups, and the elements they contain."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file defines landscape regions, their land-use groups, and the elements they contain.

# ls_reg.def

After the title, give the region and land-use-group counts, followed by the headings. Enter the land-use-group definitions and then the region definitions with their element lists.

## File counts

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [mreg](mreg.md) | Number of regions | integer | n/a | — | — |
| [mlug](mlug.md) | Number of land-use groups | integer | n/a | — | — |

## Land-use groups

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [i](i.md) | Record number | integer | n/a | — | — |
| [num](num.md) | Numeric identifier (num) of a land use group | integer | n/a | — | — |
| [name](name.md) | Record name | string | n/a | — | — |

## Regions

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [k](k.md) | Record number | integer | n/a | — | — |
| [name](name_2.md) | Record name | string | n/a | — | — |
| [area_ha](area_ha.md) | Region area | real | — | — | — |
| [nspu](nspu.md) | Number of element-list entries | integer | n/a | — | — |
| [elem_cnt](elem_cnt.md) | Element-list entry | integer | n/a | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
