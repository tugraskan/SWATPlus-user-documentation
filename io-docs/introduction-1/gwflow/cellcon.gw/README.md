---
description: "Defines the neighbor connectivity of each groundwater flow cell. Each row lists a cell identifier followed by the count and identifiers of the cells hydraulically connected to it, so that mass, energy, and lateral exchange calculations can iterate over adjacent cells in the same index order as the cell list."
---

# cellcon.gw

{% hint style="info" %}
The inspected Editor has an exporter for this filename; generation depends on the relevant feature settings. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Defines the neighbor connectivity of each groundwater flow cell. Each row lists a cell identifier followed by the count and identifiers of the cells hydraulically connected to it, so that mass, energy, and lateral exchange calculations can iterate over adjacent cells in the same index order as the cell list.

SWAT+ uses the literal filename `cellcon.gw` in the simulation working directory rather than selecting this filename through `file.cio`. It is read by [gwflow_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/gwflow_read.f90#L505). File-presence requirements and feature conditions are determined by this reader; a missing file is not assumed to be harmless.

Skip metadata and column-header records. Each of ncell rows contains cell_id, ncon, then ncon neighbor identifiers. Rows must follow the cell index order; the reader stops when the leading identifier differs from the expected row index.

### Cell and neighbors

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [cell_id](cell_id.md) | Cell identifier; must equal the current row index so the reader can verify row ordering and stop when a row is out of sequence | integer | n/a | — | — |
| [ncon](ncon.md) | Number of neighbor cell identifiers that follow in this record | integer | n/a | — | — |
| [neighbor_cell_id](neighbor_cell_id.md) | Identifier of a cell hydraulically connected to the row's cell, repeated once for each neighbor declared by ncon (repeated) | integer | n/a | — | — |
