---
description: "This file defines the grid cells that contain phreatophytes (deep-rooted vegetation) and the ground-water uptake area associated with each, used by the phreatophyte ground-water flow routines."
---

# phreato_cell.gw

{% hint style="info" %}
The inspected Editor has an exporter for this filename; generation depends on the relevant feature settings. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

This file defines the grid cells that contain phreatophytes (deep-rooted vegetation) and the ground-water uptake area associated with each, used by the phreatophyte ground-water flow routines.

SWAT+ uses the literal filename `phreato_cell.gw` in the simulation working directory rather than selecting this filename through `file.cio`. It is read by [gwflow_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/gwflow_read.f90#L1435). File-presence requirements and feature conditions are determined by this reader; a missing file is not assumed to be harmless.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a header record, then a header record.

### Data record

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [gw_phyt_ids](gw_phyt_ids.md) | Identifier of a grid cell that contains phreatophytes, drawn from the model's cell numbering | integer | n/a | — | — |
| [gw_phyt_area](gw_phyt_area.md) | Ground-water uptake area, in square meters, for each phreatophyte cell listed in gw_phyt_ids | real | — | — | — |
