---
description: "Defines named export-coefficient sets and their organic/mineral, pesticide, pathogen, heavy-metal, and salt record references."
---

# exco.exc

{% hint style="info" %}
The inspected Editor has a dispatched exporter for this input format; generation depends on project settings. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Defines named export-coefficient sets and their organic/mineral, pesticide, pathogen, heavy-metal, and salt record references.

The reader obtains the filename through `in_exco%exco`.

{% hint style="warning" %}
Source limitation: Initialization named-row crosswalk and RU direct-row routing differ; no universal coefficient/unit interpretation. These pages describe the inspected source and do not establish a working runtime configuration.
{% endhint %}

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a title record, then a header record.

### Data record

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [name](name.md) | Identifier name for this external input connection record, used to reference the set of external files associated with a particular simulation context or spatial unit | string | n/a | — | — |
| [om_file](om_file.md) | Name of the external Organic Matter (OM) input file linked to this connection record, matched against registered OM file names during data reading | string | n/a | — | — |
| [pest_file](pest_file.md) | Name of the external Pesticide input file linked to this connection record, matched against registered pesticide file names during data reading | string | n/a | — | — |
| [path_file](path_file.md) | Name of the external Pathogen (PATH) input file linked to this connection record, matched against registered pathogen file names during data reading | string | n/a | — | — |
| [hmet_file](hmet_file.md) | Name of the associated heavy-metal export-coefficient record | string | n/a | — | — |
| [salts_file](salts_file.md) | Name of the external Salt loading input file linked to this connection record, matched against registered salt file names during data reading | string | n/a | — | — |
