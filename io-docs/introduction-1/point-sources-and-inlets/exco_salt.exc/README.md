---
description: "Defines named salt export-coefficient records with one value per salt ion."
---

# exco_salt.exc

{% hint style="info" %}
The inspected Editor has a dispatched exporter for this input format; generation depends on project settings. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Defines named salt export-coefficient records with one value per salt ion.

The reader obtains the filename through `in_exco%salt`.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a title record, then a header record, then a title record.

### Record at line 63

Source condition/loop: `if (i_exist .or. in_exco%salt /= "null") then > do > do ii = 1, db_mx%exco_salt`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [exco_salt_name(ii)](exco_salt_name_ii.md) | Name identifying this salt export-coefficient record | string | n/a | — | — |
| [salt(isalt)](salt_isalt.md) | Export-coefficient value for salt ion isalt | real | — | — | — |
