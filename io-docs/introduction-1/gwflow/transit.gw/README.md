---
description: "Defines the number of and cell membership for groundwater transit cells on a structured grid, read by the gwflow reader when the grid type is structured and the file exists."
---

# transit.gw

{% hint style="info" %}
Editor generation of this exact format has not been verified in the inspected checkout. The table below describes the Fortran source, not an Editor export contract. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Defines the number of and cell membership for groundwater transit cells on a structured grid, read by the gwflow reader when the grid type is structured and the file exists.

SWAT+ uses the literal filename `transit.gw` in the simulation working directory rather than selecting this filename through `file.cio`. It is read by [gwflow_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/gwflow_read.f90#L2262). File-presence requirements and feature conditions are determined by this reader; a missing file is not assumed to be harmless.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a header record, then a header record.

### Record at line 2265

Source condition/loop: `if(grid_type == "structured") then > if(i_exist) then`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [gw_transit_num](gw_transit_num.md) | Count of groundwater transit cells to be read from the file | integer | n/a | — | — |

### Record at line 2268

Source condition/loop: `if(grid_type == "structured") then > if(i_exist) then > do i=1,gw_transit_num`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [cell_transit](cell_transit.md) | Cell identifier indexing into the structured grid's cell list for one transit cell entry | integer | n/a | — | — |
