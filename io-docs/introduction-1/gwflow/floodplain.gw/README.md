---
description: "This file connects floodplain areas and channels to groundwater cells."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file connects floodplain areas and channels to groundwater cells.

SWAT+ looks for `floodplain.gw` in the simulation working directory; it is not selected through `file.cio`. See the [gwflow_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/gwflow_read.f90#L1180) reader.

# floodplain.gw

The tables below describe the file’s input entries. Repeat array values for the configured constituents or members; these are not additional fixed columns.

## Input values

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [gw_fp_ncells](gw_fp_ncells.md) | Number of floodplain connections | integer | n/a | — | — |

## Input values

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [gw_fp_cellid](gw_fp_cellid.md) | Grid cell identifier (gw_fp_cellid) for each floodplain groundwater interaction cell | integer | n/a | — | — |
| [gw_fp_chanid](gw_fp_chanid.md) | Channel identifier (gw_fp_chanid) associated with each floodplain groundwater cell | integer | n/a | — | — |
| [gw_fp_K](gw_fp_k.md) | Hydraulic conductivity (gw_fp_K) value for each floodplain groundwater cell | real | — | — | — |
| [gw_fp_area](gw_fp_area.md) | Area (gw_fp_area) of each floodplain groundwater cell | real | — | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
