---
description: "The dr_pest.del file defines pesticide delivery data for each specified pesticide, read into the model when a pesticide delivery file is present or referenced."
---

# dr_pest.del

{% hint style="info" %}
Editor generation of this exact format has not been verified in the inspected checkout. The table below describes the Fortran source, not an Editor export contract. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

The dr_pest.del file defines pesticide delivery data for each specified pesticide, read into the model when a pesticide delivery file is present or referenced.

The reader obtains the filename through `in_delr%pest`.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a title record, then a header record, then a title record.

### Record at line 63

Source condition/loop: `if (i_exist .or. in_delr%pest /= "null") then > do > do ii = 1, db_mx%dr_pest`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [dr_pest_name(ii)](dr_pest_name_ii.md) | Identifier linking this record to a named pesticide delivery definition | string | n/a | — | — |
| [pest(ipest)](pest_ipest.md) | Pesticide delivery value associated with the named pesticide | real | — | — | — |
