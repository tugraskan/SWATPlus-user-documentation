---
description: "Defines salt-recall (water-quality) time-series recalls. Each entry names a recall dataset and the source file from which time-series values are read, with a recall type selecting the temporal resolution (day, month, or year)."
---

# salt_recall.rec

{% hint style="info" %}
The inspected Editor has a dispatched exporter for this input format; generation depends on project settings. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Defines salt-recall (water-quality) time-series recalls. Each entry names a recall dataset and the source file from which time-series values are read, with a recall type selecting the temporal resolution (day, month, or year).

SWAT+ uses the literal filename `salt_recall.rec` in the simulation working directory rather than selecting this filename through `file.cio`. It is read by [recall_read_salt.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/recall_read_salt.f90#L43). File-presence requirements and feature conditions are determined by this reader; a missing file is not assumed to be harmless.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a title record, then a header record.

### Record at line 106

Source condition/loop: `if (i_exist .or. "salt_recall.rec" /= "null") then > do > do ii = 1, imax`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [i](i.md) | Leading integer identifier consumed by this source read | integer | n/a | — | — |

### Record at line 109

Source condition/loop: `if (i_exist .or. "salt_recall.rec" /= "null") then > do > do ii = 1, imax`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [k](k.md) | Leading integer identifier consumed by this source read | integer | n/a | — | — |
| [name](name.md) | Name identifying the salt-recall dataset | string | n/a | — | — |
| [typ](typ.md) | Recall type selecting the temporal resolution: 1=day, 2=month, 3=year | integer | n/a | — | — |
| [filename](filename.md) | Filename of the source file from which the salt-recall time-series values are read | string | n/a | — | — |
