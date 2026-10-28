---
description: "This file selects HRUs for groundwater pumping observation output."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file selects HRUs for groundwater pumping observation output.

SWAT+ looks for `hru_pump.gw` in the simulation working directory; it is not selected through `file.cio`. See the [gwflow_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/gwflow_read.f90#L933) reader.

# hru_pump.gw

After the title and column headings, enter the number of HRUs to list, then one HRU identifier per following row.

## HRU count

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [num_hru_pump_obs](num_hru_pump_obs.md) | Number of HRU groundwater pumping observations to be read and processed | integer | n/a | — | — |

## HRU identifiers

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [hru_pump_ids(i)](hru_pump_ids_i.md) | HRU identifier associated with the i-th groundwater pumping observation | integer | n/a | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
