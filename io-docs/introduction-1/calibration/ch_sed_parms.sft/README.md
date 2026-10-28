---
description: "Specifies channel sediment parameter calibration adjustments, defining the target parameter, type and limits of change, and bounds for each calibration entry."
---

# ch_sed_parms.sft

{% hint style="info" %}
The inspected Editor has a dispatched exporter for this input format; generation depends on project settings. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Specifies channel sediment parameter calibration adjustments, defining the target parameter, type and limits of change, and bounds for each calibration entry.

The reader obtains the filename through `in_chg%ch_sed_parms_sft`.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a title record.

### Additional read at line 25

Source condition/loop: `if (.not. i_exist .or. in_chg%ch_sed_parms_sft == "null") then / else > do`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [mchp](mchp.md) | Number of channel sediment calibration parameter entries to read | integer | n/a | — | — |

### Data record

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [name](name.md) | Name of the channel sediment calibration parameter to adjust | string | n/a | — | — |
| [chg_typ](chg_typ.md) | Type of change to apply, one of absval, abschg, or pctchg | string | n/a | — | — |
| [neg](neg.md) | Negative limit constraining the magnitude of a downward parameter change | real | — | — | — |
| [pos](pos.md) | Positive limit constraining the magnitude of an upward parameter change | real | — | — | — |
| [lo](lo.md) | Lower bound enforced on the parameter value during calibration | real | — | — | — |
| [up](up.md) | Upper bound enforced on the parameter value during calibration | real | — | — | — |
