---
description: "This file defines recharge ponds and their water sources, dimensions, and operating dates."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file defines recharge ponds and their water sources, dimensions, and operating dates.

SWAT+ looks for `ponds.gw` in the simulation working directory; it is not selected through `file.cio`. See the [gwflow_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/gwflow_read.f90#L1933) reader.

# ponds.gw

The first two lines contain a title and column headings. Each following row contains the fields below, in this order.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [id](id.md) | Unique identifier for the recharge pond | integer | n/a | — | — |
| [area](area.md) | Surface area of the recharge pond in square meters | real | — | — | — |
| [chan](chan.md) | Channel identifier that provides water to the recharge pond | integer | n/a | — | — |
| [canal](canal.md) | Canal identifier that provides water to the recharge pond | integer | n/a | — | — |
| [unl](unl.md) | Flag indicating an outside source supplies water to the pond (1 = outside source) | integer | n/a | — | — |
| [bed_k](bed_k.md) | Hydraulic conductivity of the pond bed sediments in meters per day | real | — | — | — |
| [wsta](wsta.md) | Weather station identifier used for precipitation and potential evapotranspiration inputs | integer | n/a | — | — |
| [evap_co](evap_co.md) | Evaporation coefficient applied to potential evapotranspiration to compute pond evaporation | real | — | — | — |
| [yr_start](yr_start.md) | Year at which the recharge pond begins operation | integer | n/a | — | — |
| [mo_start](mo_start.md) | Month at which the recharge pond begins operation | integer | n/a | — | — |
| [dy_start](dy_start.md) | Day of month at which the recharge pond begins operation | integer | n/a | — | — |
| [unl_conc(j)](unl_conc_j.md) | Array of solute concentrations for an outside water source supplying the pond | real | — | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
