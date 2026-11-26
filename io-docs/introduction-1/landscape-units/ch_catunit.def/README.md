---
description: "This file groups channels into cataloging units for reporting."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source (main `6f515368`; the read layout is unchanged on dev `aa4179fe`). A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

{% hint style="warning" %}
In SWAT+ main (`6f515368`), [`ch_read_elements.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_read_elements.f90#L33-L78) (called from [`proc_cal.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/proc_cal.f90#L29)) reads `ch_catunit.def` into `ccu_out` (`reads=none`), stores `mreg` into `db_mx%cha_reg` (`#L77`, overwritten if `ch_reg.def` is present), and on the `nspu <= 0` fallback (`#L68-L70`) sets `num_tot = sp_ob%res` while looping `sp_ob%chan`.
{% endhint %}

This file groups channels into cataloging units for reporting.

# ch\_catunit.def

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
