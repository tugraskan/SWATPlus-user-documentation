---
description: "This file identifies groundwater cells containing phreatophytes and their groundwater uptake areas."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file identifies groundwater cells containing phreatophytes and their groundwater uptake areas.

SWAT+ looks for `phreato_cell.gw` in the simulation working directory; it is not selected through `file.cio`. See the [gwflow_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/gwflow_read.f90#L1435) reader.

# phreato_cell.gw

The first two lines contain a title and column headings. Each following row contains the fields below, in this order.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [gw_phyt_ids](gw_phyt_ids.md) | Identifier of a grid cell that contains phreatophytes, drawn from the model's cell numbering | integer | n/a | — | — |
| [gw_phyt_area](gw_phyt_area.md) | Ground-water uptake area, in square meters, for each phreatophyte cell listed in gw_phyt_ids | real | — | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
