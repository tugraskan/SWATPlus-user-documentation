---
description: "Defines water tower records with storage capacity, drawdown time, and water-loss fraction."
---

# water_tower.wal

{% hint style="info" %}
Editor generation of this exact format has not been verified in the inspected checkout. The table below describes the Fortran source, not an Editor export contract. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Defines water tower records with storage capacity, drawdown time, and water-loss fraction.

SWAT+ uses the literal filename `water_tower.wal` in the simulation working directory rather than selecting this filename through `file.cio`. It is read by [water_tower_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/water_tower_read.f90#L28). File-presence requirements and feature conditions are determined by this reader; a missing file is not assumed to be harmless.

{% hint style="warning" %}
Source limitation: Outer read loop lacks a normal exit before re-reading/reallocating; source concern, not a reproduced runtime result. These pages describe the inspected source and do not establish a working runtime configuration.
{% endhint %}

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a title record.

### Additional read at line 31

Source condition/loop: `if (i_exist) then > do`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [imax](imax.md) | integer determining the maximum number for array allocation and total number of records in the file | integer | n/a | — | — |

### Data record

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [i](i.md) | Leading integer identifier consumed by this source read | integer | n/a | — | — |
| [name](name.md) | character string identifying the name of the water tower or pipe | string | n/a | — | — |
| [stor_mx](stor_mx.md) | Maximum storage capacity of the water tower | real | — | — | — |
| [ddown_days](ddown_days.md) | real value representing the number of days to drawdown the storage to zero | real | — | — | — |
| [loss_fr](loss_fr.md) | Water-loss fraction for the object | real | — | — | — |
