---
description: "Defines connection rows for each canal object read from the gwflow_canal.con file when gw_canal_flag is enabled and the file exists, supplying per-canal identifiers, object totals, and a flattened buffer of connection entries that the reader unpacks into cell number, length, and stage values."
---

# gwflow_canal.con

{% hint style="info" %}
Editor generation of this exact format has not been verified in the inspected checkout. The table below describes the Fortran source, not an Editor export contract. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Defines connection rows for each canal object read from the gwflow_canal.con file when gw_canal_flag is enabled and the file exists, supplying per-canal identifiers, object totals, and a flattened buffer of connection entries that the reader unpacks into cell number, length, and stage values.

SWAT+ uses the literal filename `gwflow_canal.con` in the simulation working directory rather than selecting this filename through `file.cio`. It is read by [gwflow_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/gwflow_read.f90#L1277). File-presence requirements and feature conditions are determined by this reader; a missing file is not assumed to be harmless.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a header record.

### Record at line 1333

Source condition/loop: `if(gw_canal_flag == 1) then > if(i_exist) then > do`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [canal_id](canal_id.md) | integer index identifying the canal object whose header row is being read | integer | n/a | — | — |
| [obj_tot](obj_tot.md) | integer count of connection objects associated with the canal, used to size allocation and accumulate totals | integer | n/a | — | — |

### Record at line 1338

Source condition/loop: `if(gw_canal_flag == 1) then > if(i_exist) then > do`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [canal_id](canal_id.md) | integer index identifying the canal object whose connection detail row is being read | integer | n/a | — | — |
| [obj_tot](obj_tot.md) | integer count of connection objects associated with the canal, used to allocate the connection row buffer | integer | n/a | — | — |
| [con_row_buf(j)](con_row_buf_j.md) | real value from the flattened connection buffer, interpreted as cell number (j-1)*3+1), length ((j-1)*3+2), or stage ((j-1)*3+3) depending on position within each three-value group | real | — | — | — |
