---
description: "This file connects reservoirs to groundwater cells."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file connects reservoirs to groundwater cells.

SWAT+ looks for `rescell.gw` in the simulation working directory; it is not selected through `file.cio`. See the [gwflow_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/gwflow_read.f90#L1113) reader.

# rescell.gw

After the title and column headings, give reservoir-bed thickness, conductivity, and connection count on separate lines. Follow these with one row per reservoir–groundwater-cell connection.

## Reservoir-bed thickness

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [res_cell](res_cell.md) | Index of the groundwater cell connected to the reservoir | integer | n/a | — | — |
| [res_id](res_id.md) | Identifier of the reservoir receiving the groundwater connection | integer | n/a | — | — |
| [res_stage](res_stage.md) | Stage height associated with the reservoir connection | real | — | — | — |

## Reservoir-bed conductivity

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [res_thick](res_thick.md) | Thickness of the reservoir connection used in conductance calculations | real | — | — | — |

## Connection count

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [res_K](res_k.md) | Hydraulic conductivity of the reservoir connection material | real | — | — | — |

## Connections

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [num_res_cells](num_res_cells.md) | Number of groundwater-connected reservoir cells to read | integer | n/a | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
