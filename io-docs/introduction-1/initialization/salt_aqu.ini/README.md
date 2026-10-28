---
description: "Defines initial salt-aquifer constituent data, assigning each named constituent its starting concentration and mineral fraction for use in the salt loading module."
---

# salt_aqu.ini

{% hint style="info" %}
The inspected Editor has a dispatched exporter for this input format; generation depends on project settings. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Defines initial salt-aquifer constituent data, assigning each named constituent its starting concentration and mineral fraction for use in the salt loading module.

SWAT+ uses the literal filename `salt_aqu.ini` in the simulation working directory rather than selecting this filename through `file.cio`. It is read by [salt_aqu_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/salt_aqu_read.f90#L23). File-presence requirements and feature conditions are determined by this reader; a missing file is not assumed to be harmless.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a title record, then a header record, then a header record, then a header record.

### Data record

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [name](name.md) | Name identifying this set of initial constituent values | string | n/a | — | — |
| [conc](conc.md) | Salt ion concentration at the start of the simulation | real | — | — | — |
| [frac](frac.md) | Salt mineral fractions at the start of the simulation | real | — | — | — |
