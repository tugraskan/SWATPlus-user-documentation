---
description: "Defines irrigation demand definitions tied to HRUs for water allocation, read when the file exists and used to populate the HRU irrigation database."
---

# water_hru_irr.wal

{% hint style="info" %}
Editor generation of this exact format has not been verified in the inspected checkout. The table below describes the Fortran source, not an Editor export contract. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Defines irrigation demand definitions tied to HRUs for water allocation, read when the file exists and used to populate the HRU irrigation database.

SWAT+ uses the literal filename `water_hru_irr.wal` in the simulation working directory rather than selecting this filename through `file.cio`. It is read by [water_hru_irr_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/water_hru_irr_read.f90#L29). File-presence requirements and feature conditions are determined by this reader; a missing file is not assumed to be harmless.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a title record.

### Record at line 32

Source condition/loop: `if (i_exist) then > do`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [imax](imax.md) | maximum number of irrigation entries in the file, used to size arrays and control the read loop | integer | n/a | — | — |

### Record at line 40

Source condition/loop: `if (i_exist) then > do > do irr = 1, imax`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [name](name.md) | identifier of the irrigation user or operation | string | n/a | — | — |
| [hrus](hrus.md) | number of irrigation operations sourced from the irrigation operations file | integer | n/a | — | — |

### Record at line 45

Source condition/loop: `if (i_exist) then > do > do irr = 1, imax > do j = 1, num_hru`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [hru_num(j)](hru_num_j.md) | HRU number associated with the j-th irrigation operation | integer | n/a | — | — |
| [dtbl_lum(j)](dtbl_lum_j.md) | name of the decision table used to set daily irrigation demand for the j-th HRU | string | n/a | — | — |
