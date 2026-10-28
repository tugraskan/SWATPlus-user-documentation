---
description: "Defines connections between land-use cells (LSUs) and groundwater model grid cells, read when the LSU-to-cell linking option is enabled, followed by per-cell association records that map each LSU to its contributing grid cells and fractional areas."
---

# lsucell.gw

{% hint style="info" %}
Editor generation of this exact format has not been verified in the inspected checkout. The table below describes the Fortran source, not an Editor export contract. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Defines connections between land-use cells (LSUs) and groundwater model grid cells, read when the LSU-to-cell linking option is enabled, followed by per-cell association records that map each LSU to its contributing grid cells and fractional areas.

SWAT+ uses the literal filename `lsucell.gw` in the simulation working directory rather than selecting this filename through `file.cio`. It is read by [gwflow_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/gwflow_read.f90#L2055). File-presence requirements and feature conditions are determined by this reader; a missing file is not assumed to be harmless.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a header record.

### Additional read at line 2089

Source condition/loop: `if(lsu_cells_link == 1) then`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [nlsu](nlsu.md) | Number of land-use source (LSU) entries in this linkage block | integer | n/a | — | — |

### Additional read at line 2090

Source condition/loop: `if(lsu_cells_link == 1) then`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [nlsu_connected](nlsu_connected.md) | Count of LSU-to-grid-cell connections to be read in the following association records | integer | n/a | — | — |

### Additional read at line 2092

Source condition/loop: `if(lsu_cells_link == 1) then > do i=1,nlsu_connected`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [lsu_id](lsu_id.md) | Identifier of the LSU being linked to one or more groundwater grid cells | integer | n/a | — | — |

### Data record

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [lsu](lsu.md) | Identifier of the LSU that owns the grid-cell association on this record | integer | n/a | — | — |
| [lsu_area](lsu_area.md) | Total area of the LSU used as the denominator when computing the fractional grid-cell coverage | real | — | — | — |
| [lsu_cells](lsu_cells.md) | Groundwater grid cell index associated with the LSU on this record | integer | n/a | — | — |
| [poly_area](poly_area.md) | Planimetered polygon area of the LSU-grid-cell intersection, divided by lsu_area to yield the fractional coverage | real | — | — | — |
