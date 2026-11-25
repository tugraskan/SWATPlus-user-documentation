---
description: "Cells whose groundwater transit paths are written to output."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This optional file lists cells whose groundwater travel path is written to `gwflow_transit_cell`. It is read only for structured grids. When it exists, SWAT+ also writes travel times to channels (`gwflow_transit_chan`) and, with tiles, to tiles (`gwflow_transit_tile`).

SWAT+ looks for `transit.gw` in the simulation working directory; it is not selected through `file.cio`. See the [`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L2247-L2273) reader.

# transit.gw

The file has a title line, a heading line, the number of cells, then one cell number per line ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L2263-L2272)).

## Cell count

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [gw_transit_num](gw_transit_num.md) | Number of cells listed | integer | n/a | — | — |

## Cells

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [cell_transit](cell_transit.md) | Cell number, one per line | integer | n/a | — | 1 to ncell |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
