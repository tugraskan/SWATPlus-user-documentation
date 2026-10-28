---
description: "Defines the initial salt ion constituents and their starting concentrations for channel water, read during channel initialization to populate the channel water salt arrays."
---

# salt_channel.ini

{% hint style="info" %}
The inspected Editor has a dispatched exporter for this input format; generation depends on project settings. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Defines the initial salt ion constituents and their starting concentrations for channel water, read during channel initialization to populate the channel water salt arrays.

SWAT+ uses the literal filename `salt_channel.ini` in the simulation working directory rather than selecting this filename through `file.cio`. It is read by [salt_cha_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/salt_cha_read.f90#L27). File-presence requirements and feature conditions are determined by this reader; a missing file is not assumed to be harmless.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a title record, then a header record.

### Record at line 54

Source condition/loop: `if (i_exist .or. "salt_channel.ini" /= "null") then > do > do isalti = 1, imax`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [name](name.md) | Name identifying this set of initial constituent values | string | n/a | — | — |
| [conc](conc.md) | Initial salt ion concentration at the start of the simulation, expressed in g/m3 | real | — | — | — |
