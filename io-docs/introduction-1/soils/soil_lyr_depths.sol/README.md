---
description: "This file supplies cumulative depths used to construct custom soil layers."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file supplies cumulative depths used to construct custom soil layers.

SWAT+ looks for `soil_lyr_depths.sol` in the simulation working directory; it is not selected through `file.cio`. See the [`soils_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soils_init.f90#L166-L277) reader.

# soil_lyr_depths.sol

The file contains a title, headings, a units label, and cumulative soil-layer depths. Supply depths in increasing order. The model inserts a 10 mm surface layer while constructing the final layers.

## Units line

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [units](units.md) | Units text token read before the depth values | string | n/a | — | — |

## Layer depth values

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [csld](csld.md) | Cumulative custom soil-layer depth used to construct layer boundaries | integer | mm | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
