---
description: "The floodplain.gw file defines groundwater-floodplain interaction cells, read when the gw_fp_flag is enabled, specifying which grid cells are linked to floodplain channels and their associated hydraulic properties."
---

# floodplain.gw

{% hint style="info" %}
Editor generation of this exact format has not been verified in the inspected checkout. The table below describes the Fortran source, not an Editor export contract. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

The floodplain.gw file defines groundwater-floodplain interaction cells, read when the gw_fp_flag is enabled, specifying which grid cells are linked to floodplain channels and their associated hydraulic properties.

SWAT+ uses the literal filename `floodplain.gw` in the simulation working directory rather than selecting this filename through `file.cio`. It is read by [gwflow_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/gwflow_read.f90#L1180). File-presence requirements and feature conditions are determined by this reader; a missing file is not assumed to be harmless.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a header record.

### Additional read at line 1182

Source condition/loop: `if(gw_fp_flag == 1) then > if(i_exist) then`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [gw_fp_ncells](gw_fp_ncells.md) | Number of floodplain groundwater interaction cells (gw_fp_ncells) to be allocated and read from the data record | integer | n/a | — | — |

### Data record

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [gw_fp_cellid](gw_fp_cellid.md) | Grid cell identifier (gw_fp_cellid) for each floodplain groundwater interaction cell, used to index into the groundwater state array | integer | n/a | — | — |
| [gw_fp_chanid](gw_fp_chanid.md) | Channel identifier (gw_fp_chanid) associated with each floodplain groundwater cell, linking the cell to a specific channel object | integer | n/a | — | — |
| [gw_fp_K](gw_fp_k.md) | Hydraulic conductivity (gw_fp_K) value for each floodplain groundwater cell, used in floodplain flow calculations and subject to calibration parameter changes | real | — | — | — |
| [gw_fp_area](gw_fp_area.md) | Area (gw_fp_area) of each floodplain groundwater cell, which may be overridden by the grid cell's state area if the provided value is larger | real | — | — | — |
