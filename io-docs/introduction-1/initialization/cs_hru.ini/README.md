---
description: "Initial concentrations of constituents on HRU soil and plant compartments at the start of simulation, indexed by constituent name."
---

# cs_hru.ini

{% hint style="info" %}
Editor generation of this exact format has not been verified in the inspected checkout. The table below describes the Fortran source, not an Editor export contract. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Initial concentrations of constituents on HRU soil and plant compartments at the start of simulation, indexed by constituent name.

SWAT+ uses the literal filename `cs_hru.ini` in the simulation working directory rather than selecting this filename through `file.cio`. It is read by [cs_hru_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/cs_hru_read.f90#L23). File-presence requirements and feature conditions are determined by this reader; a missing file is not assumed to be harmless.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a title record, then a header record, then a header record, then a header record, then a header record.

### Record at line 68

Source condition/loop: `if (i_exist .or. "cs_hru.ini" /= "null") then > do > do ics = 1, imax`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [name](name.md) | Name identifying this set of initial constituent values | string | n/a | — | — |

### Record at line 70

Source condition/loop: `if (i_exist .or. "cs_hru.ini" /= "null") then > do > do ics = 1, imax`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [soil](soil.md) | amount of constituent in soil at start of simulation | real | — | — | — |

### Record at line 72

Source condition/loop: `if (i_exist .or. "cs_hru.ini" /= "null") then > do > do ics = 1, imax`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [plt](plt.md) | amount of constituent on plant at start of simulation | real | — | — | — |
