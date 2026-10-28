---
description: "Defines water pipe records with storage capacity, drawdown time, water-loss fraction, and aquifer loss fractions."
---

# water_pipe.wal

{% hint style="info" %}
Editor generation of this exact format has not been verified in the inspected checkout. The table below describes the Fortran source, not an Editor export contract. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Defines water pipe records with storage capacity, drawdown time, water-loss fraction, and aquifer loss fractions.

SWAT+ uses the literal filename `water_pipe.wal` in the simulation working directory rather than selecting this filename through `file.cio`. It is read by [water_pipe_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/water_pipe_read.f90#L32). File-presence requirements and feature conditions are determined by this reader; a missing file is not assumed to be harmless.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a title record.

### Record at line 35

Source condition/loop: `if (.not. i_exist .or. 'water_pipe.wal' == "null") then / else > do`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [imax](imax.md) | integer count determining the maximum number of water pipe or water tower entries in the file | integer | n/a | — | — |

### Record at line 45

Source condition/loop: `if (.not. i_exist .or. 'water_pipe.wal' == "null") then / else > do > do ipipe = 1, imax`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [i](i.md) | Leading integer identifier consumed by this source read | integer | n/a | — | — |
| [name](name.md) | character identifier naming the water tower or pipe | string | n/a | — | — |
| [stor_mx](stor_mx.md) | Maximum storage capacity of the pipe object | real | — | — | — |
| [ddown_days](ddown_days.md) | real value representing the number of days to draw down the storage to zero | real | — | — | — |
| [loss_fr](loss_fr.md) | Water-loss fraction for the object | real | — | — | — |
| [num_aqu](num_aqu.md) | integer count of aquifers associated with the pipe or tower | integer | n/a | — | — |

### Record at line 52

Source condition/loop: `if (.not. i_exist .or. 'water_pipe.wal' == "null") then / else > do > do ipipe = 1, imax`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [i](i.md) | Leading integer identifier consumed by this source read | integer | n/a | — | — |
| [name](name.md) | character identifier naming the water tower or pipe | string | n/a | — | — |
| [stor_mx](stor_mx.md) | Maximum storage capacity of the pipe object | real | — | — | — |
| [ddown_days](ddown_days.md) | real value representing the number of days to draw down the storage to zero | real | — | — | — |
| [loss_fr](loss_fr.md) | Water-loss fraction for the object | real | — | — | — |
| [num_aqu](num_aqu_2.md) | integer count of aquifers associated with the pipe or tower | integer | n/a | — | — |
| [aqu_loss_fr(iaq)](aqu_loss_fr_iaq.md) | real loss fraction applied to each aquifer linked to the pipe or tower | real | — | — | — |
