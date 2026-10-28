---
description: "Defines named heavy-metal export-coefficient records with one value per heavy metal."
---

# exco_hmet.exc

{% hint style="info" %}
The inspected Editor has a dispatched exporter for this input format; generation depends on project settings. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Defines named heavy-metal export-coefficient records with one value per heavy metal.

The reader obtains the filename through `in_exco%hmet`.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a title record, then a header record, then a title record.

### Record at line 63

Source condition/loop: `if (i_exist .or. in_exco%hmet /= "null") then > do > do ii = 1, db_mx%exco_hmet`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [exco_hmet_name(ii)](exco_hmet_name_ii.md) | Name identifying a heavy metals hydrograph record (character identifier used to match the exco hmet file to the corresponding exco database entry) | string | n/a | — | — |
| [hmet(ihmet)](hmet_ihmet.md) | Export-coefficient value for heavy metal ihmet | real | — | — | — |
