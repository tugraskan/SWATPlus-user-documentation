---
description: "This file identifies the objects included in aquifer cataloging units and their area fractions."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source (main `6f515368`; the read layout is unchanged on dev `aa4179fe`). A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

{% hint style="warning" %}
In SWAT+ main (`6f515368`), [`aqu_read_elements.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_read_elements.f90#L146-L192) (called from [`proc_cal.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/proc_cal.f90#L28)) reads `aqu_catunit.ele` and saves the row count in `db_mx%aqu_elem` (`#L169`), which actively gates `basin_aquifer_output` in [`command.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L635). However, the element attributes themselves are either unused or copied only into unread `acu_cal` arrays.
{% endhint %}

This file identifies the objects included in aquifer cataloging units and their area fractions.

# aqu\_catunit.ele

The first two lines contain a title and column headings. Enter one row per element using the fields below.

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [k](k.md) | Record number | integer | n/a | — | — |
| [name](name.md) | Record name | string | n/a | — | — |
| [obtyp](obtyp.md) | Object type | string | n/a | — | — |
| [obtypno](obtypno.md) | Object identifier | integer | n/a | — | — |
| [bsn\_frac](bsn_frac.md) | Basin expansion fraction | real | fraction | — | — |
| [ru\_frac](ru_frac.md) | Routing-unit expansion fraction | real | fraction | — | — |
| [reg\_frac](reg_frac.md) | Regional expansion fraction | real | fraction | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
