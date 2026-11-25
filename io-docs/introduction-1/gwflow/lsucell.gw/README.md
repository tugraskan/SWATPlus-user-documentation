---
description: "LSU-cell intersections that map recharge and ET between landscape units and cells."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file lists the intersections between landscape units (LSUs) and groundwater cells. It is used when `conn_type` is 2, or as the fallback when `conn_type` is 1 and `hrucell.gw` is missing. With LSU links, groundwater-to-soil transfer and wetland exchange are turned off, and every HRU uses the mean recharge delay of all cells.

SWAT+ looks for `lsucell.gw` in the simulation working directory; it is not selected through `file.cio`. See the [`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L2055-L2122) reader.

# lsucell.gw

The file has, in order: a title line; the number of LSUs; the number of connected LSUs; the numbers of the connected LSUs, one per line; two heading lines; then one line per LSU–cell intersection. Intersection lines for the same LSU must be together, and LSUs must be in increasing order ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L2056-L2122)).

## LSU count

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [nlsu](nlsu.md) | Number of LSUs in the model | integer | n/a | — | — |

## Connected-LSU count

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [nlsu_connected](nlsu_connected.md) | Number of LSUs listed as connected | integer | n/a | — | — |

## Connected LSUs

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [lsu_id](lsu_id.md) | Number of a connected LSU, one per line | integer | n/a | — | 1 to nlsu |

## Intersections

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [lsu](lsu.md) | LSU number | integer | n/a | — | 1 to nlsu |
| [lsu_area](lsu_area.md) | Total LSU area | real | m² | — | — |
| [lsu_cells](lsu_cells.md) | Groundwater cell number | integer | n/a | — | 1 to ncell |
| [poly_area](poly_area.md) | Area of the LSU–cell intersection | real | m² | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
