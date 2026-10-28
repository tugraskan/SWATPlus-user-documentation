---
description: "This file relates water-table depth to groundwater uptake by phreatophytes."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file relates water-table depth to groundwater uptake by phreatophytes.

SWAT+ looks for `phreato.gw` in the simulation working directory; it is not selected through `file.cio`. See the [gwflow_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/gwflow_read.f90#L1416) reader.

# phreato.gw

The first two lines contain a title and column headings. Each following row contains the fields below, in this order.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [gw_phyt_dep](gw_phyt_dep.md) | Depth below ground surface (m) at which the phreatophyte ET-rate relationship is defined | real | — | — | — |
| [gw_phyt_rate](gw_phyt_rate.md) | Transpiration rate (m/day) at the corresponding depth below ground surface | real | — | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
