---
description: "Cells with phreatophytes and their areas."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file lists the cells that contain phreatophytes. It is read when [phreato.gw](../phreato.gw/README.md) exists.

SWAT+ looks for `phreato_cell.gw` in the simulation working directory; it is not selected through `file.cio`. See the [`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1434-L1455) reader.

# phreato_cell.gw

The first two lines are a title and column headings. Then give one line per cell ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1447-L1454)).

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [gw_phyt_ids](gw_phyt_ids.md) | Cell number | integer | n/a | — | 1 to ncell |
| [gw_phyt_area](gw_phyt_area.md) | Phreatophyte area in the cell | real | m² | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
