---
description: "This file identifies cataloging-unit elements and their basin, routing-unit, and regional area fractions."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source (`6f515368`). A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

{% hint style="warning" %}
SWAT+ looks for the hardcoded filename `element.ccu` in the working directory ([`ch_read_elements.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_read_elements.f90#L145)), ignoring the `ch_catunit.ele` (`in_regs%ele_cha`) slot in `file.cio`. In SWAT+ main (`6f515368`), its attributes are either unused or copied only into unread `ccu_cal` arrays ([`ch_read_elements.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_read_elements.f90#L182-L183), [`ch_read_orders_cal.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_read_orders_cal.f90#L130-L131)).
{% endhint %}

This file identifies cataloging-unit elements and their basin, routing-unit, and regional area fractions.

# element.ccu

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
