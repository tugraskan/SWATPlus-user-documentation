---
description: "This file supplies the initial mineral fractions used by groundwater solute transport."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file supplies the initial mineral fractions used by groundwater solute transport.

SWAT+ looks for `minerals.gw` in the simulation working directory; it is not selected through `file.cio`. See the [gwflow_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/gwflow_read.f90#L1681) reader.

# minerals.gw

Give the number of minerals and then the input method for each mineral. A `single` entry supplies one value throughout the domain. An `array` entry supplies a structured grid or per-cell mineral values, according to the groundwater grid.

## Mineral count

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [gw_nminl](gw_nminl.md) | The total number of salt minerals to be read and tracked for groundwater solute transport | integer | n/a | — | — |

## Input method

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [read_type](read_type.md) | The method used to supply values for each salt mineral | string | n/a | — | — |

## Uniform value

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [single_value](single_value.md) | The uniform mass fraction of a salt mineral applied to all groundwater cells when read_type is set to single | real | — | — | — |

## Structured-grid values

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [grid_val(i,j)](grid_val_i_j.md) | The per-cell mass fraction of a salt mineral for a structured grid when read_type is set to array | real | — | — | — |

## Per-cell values

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [fract(m)](fract_m.md) | The mass fraction of salt mineral m within a groundwater cell | real | — | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
