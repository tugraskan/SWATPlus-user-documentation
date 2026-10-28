---
description: "This file links HRUs to groundwater cells and gives the area of each intersection."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file links HRUs to groundwater cells and gives the area of each intersection.

SWAT+ looks for `hrucell.gw` in the simulation working directory; it is not selected through `file.cio`. See the [gwflow_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/gwflow_read.f90#L2128) reader.

# hrucell.gw

The first two lines contain a title and column headings. Each following row contains the fields below, in this order.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [hru_id](hru_id.md) | Identifier of the HRU to which this groundwater cell belongs | integer | n/a | — | — |
| [hru_area](hru_area.md) | Total area of the HRU | real | — | — | — |
| [hru_cells](hru_cells.md) | Groundwater cell identifier for this HRU-cell association | integer | n/a | — | — |
| [poly_area](poly_area.md) | Area of the HRU-cell intersection used to calculate HRU and cell area fractions | real | — | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
