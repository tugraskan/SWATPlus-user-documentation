---
description: "This file identifies the objects included in point-source cataloging units and their area fractions."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source (main `6f515368`; the read layout is unchanged on dev `aa4179fe`). A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

{% hint style="warning" %}
In SWAT+ main (`6f515368`), [`rec_read_elements.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/rec_read_elements.f90#L133-L180) (called from [`proc_cal.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/proc_cal.f90#L31)) reads `rec_catunit.ele` into `pcu_elem`. Only `obtypno` and `ru_frac` are copied into `pcu_cal` (`#L175-L176`), which is never read in simulation calculations; all other attributes have `reads=none`.
{% endhint %}

This file identifies the objects included in point-source cataloging units and their area fractions.

# rec\_catunit.ele

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
