---
description: "Defines named pathogen export-coefficient records with one value per pathogen."
---

# exco_path.exc

{% hint style="info" %}
The inspected Editor has a dispatched exporter for this input format; generation depends on project settings. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Defines named pathogen export-coefficient records with one value per pathogen.

The reader obtains the filename through `in_exco%path`.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a title record, then a header record, then a title record.

### Record at line 63

Source condition/loop: `if (i_exist .or. in_exco%path /= "null") then > do > do ii = 1, db_mx%exco_path`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [exco_path_name(ii)](exco_path_name_ii.md) | Name identifying this pathogen export-coefficient record | string | n/a | — | — |
| [path(ipath)](path_ipath.md) | Export-coefficient value for pathogen ipath | real | — | — | — |
