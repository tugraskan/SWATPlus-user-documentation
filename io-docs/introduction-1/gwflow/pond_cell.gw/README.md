---
description: "Defines groundwater pond cells and their association with grid cells for the groundwater flow solver. Each record links a pond identifier to a specific model grid cell and carries an additional parameter used by the pond-to-cell linkage."
---

# pond_cell.gw

{% hint style="info" %}
The inspected Editor has an exporter for this filename; generation depends on the relevant feature settings. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Defines groundwater pond cells and their association with grid cells for the groundwater flow solver. Each record links a pond identifier to a specific model grid cell and carries an additional parameter used by the pond-to-cell linkage.

SWAT+ uses the literal filename `pond_cell.gw` in the simulation working directory rather than selecting this filename through `file.cio`. It is read by [gwflow_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/gwflow_read.f90#L1980). File-presence requirements and feature conditions are determined by this reader; a missing file is not assumed to be harmless.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a header record, then a header record.

### Data record

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [dum_id](dum_id.md) | integer identifier of the pond whose groundwater cell count or cell list is being referenced by this record | integer | n/a | — | — |
| [cell_num](cell_num.md) | model grid cell number associated with the pond on this record; used to map the pond to a spatial location in the grid | integer | n/a | — | — |
| [dum4](dum4.md) | real-valued parameter associated with the pond-cell linkage; exact meaning not documented in the available source references | real | — | — | — |
