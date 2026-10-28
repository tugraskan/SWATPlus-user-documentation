---
description: "Defines recharge ponds for the groundwater model, each supplying water to a specified channel, canal, or outside source, with surface area, bed hydraulic conductivity, weather station, evaporation coefficient, and start timing used to compute pond water balance and recharge to connected grid cells."
---

# ponds.gw

{% hint style="info" %}
The inspected Editor has an exporter for this filename; generation depends on the relevant feature settings. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Defines recharge ponds for the groundwater model, each supplying water to a specified channel, canal, or outside source, with surface area, bed hydraulic conductivity, weather station, evaporation coefficient, and start timing used to compute pond water balance and recharge to connected grid cells.

SWAT+ uses the literal filename `ponds.gw` in the simulation working directory rather than selecting this filename through `file.cio`. It is read by [gwflow_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/gwflow_read.f90#L1933). File-presence requirements and feature conditions are determined by this reader; a missing file is not assumed to be harmless.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a header record, then a header record.

### Record at line 1948

Source condition/loop: `if(i_exist) then > do i=1,gw_npond`.

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
