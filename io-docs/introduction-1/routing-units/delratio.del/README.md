---
description: "Defines named delivery-ratio sets and references to the associated organic/mineral, pesticide, pathogen, heavy-metal, and salt records."
---

# delratio.del

{% hint style="info" %}
The inspected Editor has a dispatched exporter for this input format; generation depends on project settings. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Defines named delivery-ratio sets and references to the associated organic/mineral, pesticide, pathogen, heavy-metal, and salt records.

The reader obtains the filename through `in_delr%del_ratio`.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a title record, then a header record.

### Data record

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [name](name.md) | Identifier name for this delivery ratio record, used to match references in element or routing input | string | n/a | — | — |
| [om_file](om_file.md) | Name of the associated organic-mineral (om) file providing source data for this delivery ratio | string | n/a | — | — |
| [pest_file](pest_file.md) | Name of the associated pesticide (pest) file providing source data for this delivery ratio | string | n/a | — | — |
| [path_file](path_file.md) | Name of the associated pathogen (path) file providing source data for this delivery ratio | string | n/a | — | — |
| [hmet_file](hmet_file.md) | Name of the associated heavy-metal delivery record | string | n/a | — | — |
| [salts_file](salts_file.md) | Name of the associated salt (salts) file providing source data for this delivery ratio | string | n/a | — | — |
