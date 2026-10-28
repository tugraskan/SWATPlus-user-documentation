---
description: "Defines named pesticide export-coefficient records with one value per pesticide."
---

# exco_pest.exc

{% hint style="info" %}
The inspected Editor has a dispatched exporter for this input format; generation depends on project settings. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Defines named pesticide export-coefficient records with one value per pesticide.

The reader obtains the filename through `in_exco%pest`.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a title record, then a header record, then a title record.

### Record at line 62

Source condition/loop: `if (i_exist .or. in_exco%pest /= "null") then > do > do ii = 1, db_mx%exco_pest`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [exco_pest_name(ii)](exco_pest_name_ii.md) | Identifier naming the pesticide hydrograph set associated with this EXCO pest record | string | n/a | — | — |
| [pest(ipest)](pest_ipest.md) | Sequence of pesticide hydrograph values for the named pesticide, as pesticide hydrographs | real | — | — | — |
