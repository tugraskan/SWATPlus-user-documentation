---
description: "Defines named outside-basin receiving objects and their associated filenames for water allocation."
---

# outside_rcv.wal

{% hint style="info" %}
Editor generation of this exact format has not been verified in the inspected checkout. The table below describes the Fortran source, not an Editor export contract. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Defines named outside-basin receiving objects and their associated filenames for water allocation.

SWAT+ uses the literal filename `outside_rcv.wal` in the simulation working directory rather than selecting this filename through `file.cio`. It is read by [water_orcv_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/water_orcv_read.f90#L34). File-presence requirements and feature conditions are determined by this reader; a missing file is not assumed to be harmless.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a title record.

### Additional read at line 37

Source condition/loop: `if (.not. i_exist .or. 'outside_rcv.wal' == "null") then / else > do`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [imax](imax.md) | integer determining the maximum array size and total number of records in the file | integer | n/a | — | — |

### Data record

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [i](i.md) | Leading integer identifier consumed by this source read | integer | n/a | — | — |
| [name](name.md) | character string identifying the name of the outside basin receiving object | string | n/a | — | — |
| [filename](filename.md) | character string specifying the filename associated with the outside basin receiving object | string | n/a | — | — |
