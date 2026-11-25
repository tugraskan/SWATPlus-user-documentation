---
description: "Water-table depth versus phreatophyte transpiration rate."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This optional file relates water-table depth to the transpiration rate of phreatophytes. Its presence turns phreatophyte uptake on; there is no setting in `codes.gw`. The cells come from [phreato_cell.gw](../phreato_cell.gw/README.md), which must then also exist.

SWAT+ looks for `phreato.gw` in the simulation working directory; it is not selected through `file.cio`. See the [`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1411-L1433) reader.

# phreato.gw

The first two lines are a title and column headings. Then give one depth–rate pair per line, with depths increasing ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1430-L1432)).

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [gw_phyt_dep](gw_phyt_dep.md) | Water-table depth below ground | real | m | — | — |
| [gw_phyt_rate](gw_phyt_rate.md) | Transpiration rate at that depth | real | m/day | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
