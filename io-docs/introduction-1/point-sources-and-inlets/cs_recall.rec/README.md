---
description: "Defines general-constituent recall entries by name, temporal type, and the input data filename supplying their values."
---

# cs_recall.rec

{% hint style="info" %}
Editor generation of this exact format has not been verified in the inspected checkout. The table below describes the Fortran source, not an Editor export contract. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Defines general-constituent recall entries by name, temporal type, and the input data filename supplying their values.

SWAT+ uses the literal filename `cs_recall.rec` in the simulation working directory rather than selecting this filename through `file.cio`. It is read by [recall_read_cs.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/recall_read_cs.f90#L43). File-presence requirements and feature conditions are determined by this reader; a missing file is not assumed to be harmless.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a title record, then a header record.

### Record at line 105

Source condition/loop: `if (i_exist .or. in_rec%recall_rec /= "null") then > do > do ii = 1, imax`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [i](i.md) | Leading integer identifier consumed by this source read | integer | n/a | — | — |

### Record at line 108

Source condition/loop: `if (i_exist .or. in_rec%recall_rec /= "null") then > do > do ii = 1, imax`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [k](k.md) | Leading integer identifier consumed by this source read | integer | n/a | — | — |
| [name](name.md) | Short identifier name assigned to the recall entry | string | n/a | — | — |
| [typ](typ.md) | Recall temporal type code: 1 for daily, 2 for monthly, or 3 for yearly data | integer | n/a | — | — |
| [filename](filename.md) | Name of the input file supplying constituent recall values | string | n/a | — | — |
