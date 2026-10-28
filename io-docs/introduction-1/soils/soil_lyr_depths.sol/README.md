---
description: "This file supplies cumulative depths used to construct custom soil layers."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file supplies cumulative depths used to construct custom soil layers.

SWAT+ looks for `soil_lyr_depths.sol` in the simulation working directory; it is not selected through `file.cio`. See the [soils_init.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/soils_init.f90#L166) reader.

# soil_lyr_depths.sol

The file contains a title, headings, a units label, and cumulative soil-layer depths. Supply depths in increasing order. The model inserts a 10 mm surface layer while constructing the final layers.

## Input values

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [units](units.md) | Units text token read before the depth values | string | n/a | — | — |

## Input values

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [csld](csld.md) | Cumulative custom soil-layer depth used to construct layer boundaries | integer | n/a | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
