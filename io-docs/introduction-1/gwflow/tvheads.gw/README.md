---
description: "Provides time-varying groundwater head values at boundary cells, read once at initialization when the file exists and used to populate the per-cell head series for each stress period year."
---

# tvheads.gw

{% hint style="info" %}
The inspected Editor has an exporter for this filename; generation depends on the relevant feature settings. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Provides time-varying groundwater head values at boundary cells, read once at initialization when the file exists and used to populate the per-cell head series for each stress period year.

SWAT+ uses the literal filename `tvheads.gw` in the simulation working directory rather than selecting this filename through `file.cio`. It is read by [gwflow_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/gwflow_read.f90#L1463). File-presence requirements and feature conditions are determined by this reader; a missing file is not assumed to be harmless.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a header record, then a header record.

### Record at line 1479

Source condition/loop: `if(i_exist) then > do i=1,gw_ntvh`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [cell_id](cell_id.md) | Groundwater cell identifier for this prescribed-head series | integer | n/a | — | — |
| [gw_tvh_vals(i,j)](gw_tvh_vals_i_j.md) | Prescribed head value for cell i and time index j | real | — | — | — |
