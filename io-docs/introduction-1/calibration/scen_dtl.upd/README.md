---
description: "The scen_dtl.upd file defines conditional update rules that are scheduled through rulesets declared in conditional.ctl. Each data record specifies a table type, a target ruleset name, and the maximum number of times the update is executed, allowing scenario-driven modifications to land use or HRU fractions to be applied during the simulation."
---

# scen_dtl.upd

{% hint style="info" %}
Editor generation of this exact format has not been verified in the inspected checkout. The table below describes the Fortran source, not an Editor export contract. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

The scen_dtl.upd file defines conditional update rules that are scheduled through rulesets declared in conditional.ctl. Each data record specifies a table type, a target ruleset name, and the maximum number of times the update is executed, allowing scenario-driven modifications to land use or HRU fractions to be applied during the simulation.

SWAT+ uses the literal filename `scen_dtl.upd` in the simulation working directory rather than selecting this filename through `file.cio`. It is read by [cal_cond_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/cal_cond_read.f90#L43). File-presence requirements and feature conditions are determined by this reader; a missing file is not assumed to be harmless.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a title record.

### Additional read at line 46

Source condition/loop: `if (.not. i_exist .or. "scen_dtl.upd" == "null") then / else > do`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [num_dtls](num_dtls.md) | integer count of update condition records that follow in this file, used to allocate and size the upd_cond array | integer | n/a | — | — |

### Data record

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [max_hits](max_hits.md) | maximum number of times the referenced update table is executed during the simulation | integer | n/a | — | — |
| [typ](typ.md) | type of update table to apply, where "lu_change" checks all HRUs and "hru_fr_change" sets all HRU fractions | string | n/a | — | — |
| [dtbl](dtbl.md) | name of the ruleset in conditional.ctl that schedules when this update is applied | string | n/a | — | — |
