---
description: "HRU-cell intersections that map recharge and ET between HRUs and cells."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file lists the intersections between HRUs and groundwater cells. They distribute HRU recharge, groundwater ET, soil transfer and wetland exchange to cells. It is used when `conn_type` is 1, or as the fallback when `conn_type` is 2 and `lsucell.gw` is missing.

SWAT+ looks for `hrucell.gw` in the simulation working directory; it is not selected through `file.cio`. See the [`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L2128-L2183) reader.

# hrucell.gw

The first two lines are a title and column headings. Then give one line per HRU–cell intersection. Lines for the same HRU must be together, and HRUs must be in increasing order: the reader collects lines for HRU 1, then HRU 2, and so on, and moves to the next HRU when the HRU number changes ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L2159-L2183)). HRUs without lines are not connected to the aquifer.

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [hru_id](hru_id.md) | HRU number | integer | n/a | — | 1 to number of HRUs |
| [hru_area](hru_area.md) | Total HRU area | real | m² | — | — |
| [hru_cells](hru_cells.md) | Groundwater cell number | integer | n/a | — | 1 to ncell |
| [poly_area](poly_area.md) | Area of the HRU–cell intersection | real | m² | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
