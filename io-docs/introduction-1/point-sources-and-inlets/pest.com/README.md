---
description: "pest.com defines pesticide application recall records read by recall_read.f90, associating a named pesticide recall schedule with a timing type and an external data filename for periodic reapplication during simulation."
---

# pest.com

{% hint style="info" %}
Editor generation of this exact format has not been verified in the inspected checkout. The table below describes the Fortran source, not an Editor export contract. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

pest.com defines pesticide application recall records read by recall_read.f90, associating a named pesticide recall schedule with a timing type and an external data filename for periodic reapplication during simulation.

SWAT+ uses the literal filename `pest.com` in the simulation working directory rather than selecting this filename through `file.cio`. It is read by [recall_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/recall_read.f90#L205). File-presence requirements and feature conditions are determined by this reader; a missing file is not assumed to be harmless.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a title record, then a header record.

### Additional read at line 225

Source condition/loop: `if (i_exist ) then > do > do ipc = 1, db_mx%pestcom`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [ipestcom_db](ipestcom_db.md) | ipestcom_db is an integer pointer indexing into the pestcom_db database array during the conditional read loop over pestcom entries | integer | n/a | — | — |

### Additional read at line 229

Source condition/loop: `if (i_exist ) then > do > do ipc = 1, db_mx%pestcom > do ii = 1, imax`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [i](i.md) | Leading integer identifier consumed by this source read | integer | n/a | — | — |

### Data record

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [k](k.md) | Leading integer identifier consumed by this source read | integer | n/a | — | — |
| [name](name.md) | name is a 16-character identifier for the pesticide recall record | string | n/a | — | — |
| [typ](typ.md) | typ is an integer recall type specifying the periodicity of the pesticide application: 1=day, 2=month, 3=year | integer | n/a | — | — |
| [filename](filename.md) | filename is a 13-character name of an external file containing pesticide application data referenced by this recall record | string | n/a | — | — |
