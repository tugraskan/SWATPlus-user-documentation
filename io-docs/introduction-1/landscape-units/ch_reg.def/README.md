---
description: "This file defines channel regions and the elements included in each region."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source (main `6f515368`; the read layout is unchanged on dev `aa4179fe`). A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

{% hint style="warning" %}
In SWAT+ main (`6f515368`), [`ch_read_elements.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_read_elements.f90#L82-L122) (called from [`proc_cal.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/proc_cal.f90#L29)) stores `mreg` into `db_mx%cha_reg` (`#L121`, used in [`calsoft_sed.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_sed.f90#L42) and [`ch_read_orders_cal.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_read_orders_cal.f90#L126)). The region element lists in `ccu_reg` only populate `ccu_cal` (`#L179-L183`, [`ch_read_orders_cal.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_read_orders_cal.f90#L127-L131)), which is never read in simulation calculations.
{% endhint %}

This file defines channel regions and the elements included in each region.

# ch\_reg.def

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
