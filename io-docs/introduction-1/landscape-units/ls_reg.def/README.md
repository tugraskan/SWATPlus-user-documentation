---
description: "This file defines landscape regions, their land-use groups, and the elements they contain."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source (main `6f515368`; the read layout is unchanged on dev `aa4179fe`). A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

{% hint style="warning" %}
In SWAT+ main (`6f515368`), [`reg_read_elements.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reg_read_elements.f90#L1-L205) is never called. Soft-calibration regions are instead read from `water_balance.sft` by [`lcu_read_softcal.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/lcu_read_softcal.f90#L63-L108), so `ls_reg.def` is not opened during standard runs.
{% endhint %}

This file defines landscape regions, their land-use groups, and the elements they contain.

# ls\_reg.def

After the title, give the region and land-use-group counts, followed by the headings. Enter the land-use-group definitions and then the region definitions with their element lists.

## File counts

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [mreg](mreg.md) | Number of regions | integer | n/a | — | — |
| [mlug](mlug.md) | Number of land-use groups | integer | n/a | — | — |

## Land-use groups

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [i](i.md) | Record number | integer | n/a | — | — |
| [num](num.md) | Numeric identifier (num) of a land use group | integer | n/a | — | — |
| [name](name.md) | Record name | string | n/a | — | — |

## Regions

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [k](k.md) | Record number | integer | n/a | — | — |
| [name](name_2.md) | Record name | string | n/a | — | — |
| [area\_ha](area_ha.md) | Region area | real | ha | — | — |
| [nspu](nspu.md) | Number of element-list entries | integer | n/a | — | — |
| [elem\_cnt](elem_cnt.md) | Element-list entry | integer | n/a | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
