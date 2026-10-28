---
description: "Defines groundwater pumping extraction rates and the start and end dates of pumping periods for specified aquifer cells."
---

# pumpex.gw

{% hint style="info" %}
The inspected Editor has an exporter for this filename; generation depends on the relevant feature settings. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Defines groundwater pumping extraction rates and the start and end dates of pumping periods for specified aquifer cells.

SWAT+ uses the literal filename `pumpex.gw` in the simulation working directory rather than selecting this filename through `file.cio`. It is read by [gwflow_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/gwflow_read.f90#L958). File-presence requirements and feature conditions are determined by this reader; a missing file is not assumed to be harmless.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a header record, then a header record.

### Data record

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [header](header.md) | Leading text label read on each pumping data row; this is not a separate file-header record | string | n/a | — | — |
| [pumpex_cell](pumpex_cell.md) | Aquifer cell number associated with the pumping rate and dates on this record | integer | n/a | — | — |
| [gw_pumpex_rates_tmp](gw_pumpex_rates_tmp.md) | Groundwater pumping rate assigned to the cell for the given period | real | — | — | — |
| [pe_yr_s](pe_yr_s.md) | Starting year of the pumping period for the cell | integer | n/a | — | — |
| [pe_dy_s](pe_dy_s.md) | Starting day of the pumping period for the cell | integer | n/a | — | — |
| [pe_yr_e](pe_yr_e.md) | Ending year of the pumping period for the cell | integer | n/a | — | — |
| [pe_dy_e](pe_dy_e.md) | Ending day of the pumping period for the cell | integer | n/a | — | — |
