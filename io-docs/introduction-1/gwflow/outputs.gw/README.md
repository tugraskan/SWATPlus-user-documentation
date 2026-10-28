---
description: "The outputs.gw file specifies groundwater output times and the cells used for observation and detailed debugging output. Each nonblank row contains a record-type keyword followed by a single integer value, and the available record types are alternatives rather than a required sequence."
---

# outputs.gw

{% hint style="info" %}
The inspected Editor has an exporter for this filename; generation depends on the relevant feature settings. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

The outputs.gw file specifies groundwater output times and the cells used for observation and detailed debugging output. Each nonblank row contains a record-type keyword followed by a single integer value, and the available record types are alternatives rather than a required sequence.

SWAT+ uses the literal filename `outputs.gw` in the simulation working directory rather than selecting this filename through `file.cio`. It is read by [gwflow_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/gwflow_read.f90#L575). File-presence requirements and feature conditions are determined by this reader; a missing file is not assumed to be harmless.

Skip metadata and column-header records. Each subsequent nonblank row contains a record-type keyword and one value. The three tables show alternatives, not three consecutive required records. Unknown keywords have no matching branch. The file selects output times and cells; general output flags are configured separately.

### Head output time

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [record_type](record_type.md) | Literal record type head_output_time | string | n/a | — | — |
| [value](value.md) | Integer encoding year and day for a groundwater head output time, where the year is the value divided by 1000 and the day is the remainder of that division | integer | n/a | — | — |

### Observation cell

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [record_type](record_type.md) | Literal record type observation_cell | string | n/a | — | — |
| [value](value_2.md) | Cell identifier selected for groundwater observation output | integer | n/a | — | — |

### Detail debug cell

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [record_type](record_type.md) | Literal record type detail_debug_cell | string | n/a | — | — |
| [value](value_3.md) | Cell identifier selected for detailed groundwater debugging output | integer | n/a | — | — |
