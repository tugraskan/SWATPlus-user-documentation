---
description: "This file identifies the model objects included in landscape regions."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source (main `6f515368`; the read layout is unchanged on dev `aa4179fe`). A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

{% hint style="warning" %}
In SWAT+ main (`6f515368`), [`reg_read_elements.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reg_read_elements.f90#L1-L205) is never called, so `ls_reg.ele` is not opened during standard runs.
{% endhint %}

This file identifies the model objects included in landscape regions.

# ls\_reg.ele

The first two lines contain a title and column headings. Enter one row per element using the fields below.

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [k](k.md) | Record number | integer | n/a | — | — |
| [name](name.md) | Record name | string | n/a | — | — |
| [ha](ha.md) | Area of the region element in hectares | real | ha | — | — |
| [obtyp](obtyp.md) | Object type | string | n/a | — | — |
| [obtypno](obtypno.md) | Object identifier | integer | n/a | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
