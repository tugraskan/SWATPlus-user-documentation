---
description: "Defines groups of groundwater cells for GWFlow by listing a group label, a count of cell identifiers, and that many cell IDs per row. Groups are indexed by row order and are mapped through cell_id_list in a structured grid."
---

# sw_group.gw

{% hint style="info" %}
The inspected Editor has an exporter for this filename; generation depends on the relevant feature settings. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Defines groups of groundwater cells for GWFlow by listing a group label, a count of cell identifiers, and that many cell IDs per row. Groups are indexed by row order and are mapped through cell_id_list in a structured grid.

SWAT+ uses the literal filename `sw_group.gw` in the simulation working directory rather than selecting this filename through `file.cio`. It is read by [gwflow_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/gwflow_read.f90#L2307). File-presence requirements and feature conditions are determined by this reader; a missing file is not assumed to be harmless.

Skip metadata and column-header records. Each nonblank row is a group_id, a count, and that many cell IDs. Groups are indexed by row order. In a structured grid, supplied cell IDs are mapped through cell_id_list.

### Channel cell group

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [group_id](group_id.md) | Leading group label for the channel_cell_group record; serves as a human-readable identifier for the group | string | n/a | — | — |
| [ncell](ncell.md) | Number of cell identifiers following this value in the record | integer | n/a | — | — |
| [cell_id](cell_id.md) | Cell identifier repeated ncell times; identifies a member cell of the group (repeated) | integer | n/a | — | — |
