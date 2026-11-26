---
description: "This file groups aquifers into cataloging units for reporting and regional calculations."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source (main `6f515368`; the read layout is unchanged on dev `aa4179fe`). A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

{% hint style="warning" %}
In SWAT+ main (`6f515368`), [`aqu_read_elements.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_read_elements.f90#L33-L126) (called from [`proc_cal.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/proc_cal.f90#L28)) opens `aqu_catunit.def` twice: first into `acu_out` (`#L36`), and again at line 89 into `acu_reg` after inquiring `in_regs%def_aqu_reg` (`aqu_reg.def`) at lines 86–87. Neither `acu_out` nor `acu_cal` (populated from `acu_reg` at `#L184-L188`) is read in simulation calculations.
{% endhint %}

This file groups aquifers into cataloging units for reporting and regional calculations.

# aqu\_catunit.def

The file contains a title, a region count, headings, and one row per region. Each region row ends with the number of element-list entries and those entries.

## Number of regions

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [mreg](mreg.md) | Number of regions | integer | n/a | — | — |

## Input values

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [k](k.md) | Record number | integer | n/a | — | — |
| [name](name.md) | Record name | string | n/a | — | — |
| [area\_ha](area_ha.md) | Region area | real | ha | — | — |
| [nspu](nspu.md) | Number of element-list entries | integer | n/a | — | — |
| [elem\_cnt](elem_cnt.md) | Element-list entry | integer | n/a | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
